---
title: "Arquitectura de las herramientas de la línea de comandos de .NET Core"
description: "Obtenga información sobre las capas de herramientas de .NET Core y sobre lo que ha cambiado en versiones recientes."
keywords: .NET Core, MSBuild, arquitectura
author: blackdwarf
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 7fff0f61-ac23-42f0-9661-72a7240a4456
ms.openlocfilehash: ad34faa0c2577bd5e3a0ba339b19a9ad387e015a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Introducción de alto nivel de los cambios en las herramientas de .NET Core

En este documento se describen los cambios asociados con el traslado de *project.json* a MSBuild y al sistema del proyecto *csproj* con información sobre los cambios realizados en las capas de las herramientas de .NET Core y en la implementación de los comandos de la CLI. Estos cambios se han producido con la versión de .NET Core SDK 1.0 y Visual Studio 2017 de 7 de marzo de 2017 (vea el [anuncio](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)), pero se han implementado inicialmente con la versión de .NET Core SDK Preview 3.

## <a name="moving-away-from-projectjson"></a>Abandono de project.json
El cambio más importante en las herramientas para .NET Core es ciertamente el [abandono de project.json en favor de csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) como sistema de proyectos. Las últimas versiones de las herramientas de línea de comandos no admiten archivos *project.json*. Esto significa que no puede utilizarse para compilar, ejecutar o publicar bibliotecas y aplicaciones basadas en project.json. Para poder utilizar esta versión de las herramientas, debe migrar los proyectos existentes o iniciar otros nuevos. 

Como parte de este proceso, el motor de compilación personalizado que se desarrolló para compilar proyectos de project.json se ha reemplazado por un motor de compilación maduro y totalmente compatible llamado [MSBuild](https://github.com/Microsoft/msbuild). MSBuild es un motor conocido en la comunidad. NET, ya que ha sido una tecnología clave desde el primer lanzamiento de la plataforma. Por supuesto, como debe compilar aplicaciones .NET Core, MSBuild se ha trasladado a .NET Core y puede utilizarse en cualquier plataforma donde se ejecute .NET Core. Una de las promesas principales de .NET Core es una pila de desarrollo multiplataforma, y nos hemos asegurado de que esta transición no rompa esa promesa.

> [!NOTE]
> Si no está familiarizado con MSBuild y quiere aprender más al respecto, puede empezar por leer el artículo [Conceptos de MSBuild](/visualstudio/msbuild/msbuild-concepts). 

## <a name="the-tooling-layers"></a>Las capas de herramientas
Cuando nos alejamos del sistema de proyecto existente y pensamos en la compilación de modificadores del motor, la pregunta que surge de manera natural es: ¿cambiarán algunos de estos cambios la "disposición en capas" general del ecosistema completo de herramientas de .NET Core? ¿Hay nuevos bits y componentes?

Comencemos con un repaso rápido de la disposición en capas de Preview 2, como se muestra en la siguiente imagen:

![Arquitectura de alto nivel de herramientas de Preview 2](media/cli-msbuild-architecture/p2-arch.png)

La disposición en capas de las herramientas es bastante sencilla. En la parte inferior, tenemos como base las herramientas de línea de comandos de .NET Core. Todas las demás herramientas de mayor nivel, como Visual Studio o Visual Studio Code, dependen de la CLI para compilar proyectos, restaurar dependencias, etc. Esto significaba que, por ejemplo, si deseara Visual Studio realizar una operación de restauración, llamaría a en `dotnet restore` ([Véase la nota](#dotnet-restore-note)) en la CLI. 

Con el paso al nuevo sistema de proyecto, el diagrama anterior cambia: 

![Arquitectura de alto nivel del SDK 1.0.0 de .NET Core](media/cli-msbuild-architecture/p3-arch.png)

La principal diferencia es que la CLI ya no es la base; este papel es ocupado ahora por el "componente de SDK compartido". Este componente de SDK compartido es un conjunto de destinos y tareas asociadas que son responsables de compilar el código y publicarlo, de empaquetar paquetes de NuGet, etc. El propio SDK es código abierto y está disponible en GitHub en el [repositorio de SDK](https://github.com/dotnet/sdk). 

> [!NOTE]
> Un "destino" es un término de MSBuild que indica una operación con nombre que puede invocar MSBuild. Normalmente está unido a una o varias tareas que ejecutan alguna lógica que se supone que debe hacer el destino. MSBuild admite michos destinos predefinidos, como `Copy` o `Execute`; también permite a los usuarios escribir sus propias tareas mediante código administrado y definir destinos para ejecutar esas tareas. Para obtener más información, consulte [Tareas de MSBuild](/visualstudio/msbuild/msbuild-tasks). 

Todos los conjuntos de herramientas consumen ahora el componente de SDK compartido y sus destinos, incluida la CLI. Por ejemplo, la próxima versión de Visual Studio no llamará a `dotnet restore` ([Véase la nota](#dotnet-restore-note)) comando para restaurar las dependencias para los proyectos de .NET Core, utilizará el destino de "Restore" directamente. Como son destinos de MSBuild, también puede usar MSBuild sin procesar para ejecutarlos mediante el comando [dotnet msbuild](dotnet-msbuild.md). 

### <a name="cli-commands"></a>Comandos de la CLI
El componente de SDK compartido implica que la mayoría de los comandos de la CLI existentes se han vuelto a implementar como tareas y destinos de MSBuild. ¿Qué significa esto para los comandos de la CLI y el uso del conjunto de herramientas? 

Desde una perspectiva del uso, no cambia la forma de usar la CLI. La CLI sigue teniendo los comandos principales que existen en la versión Preview 2:

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

Estos comandos todavía hacen lo que se espera que hagan (crear un nuevo proyecto, compilarlo, publicarlo, empaquetarlo, etc.). La mayoría de las opciones no varían y siguen ahí. Puede consultar las pantallas de ayuda de los comandos (mediante `dotnet <command> --help`) o la documentación de este sitio para familiarizarse con los cambios. 

Desde una perspectiva de la ejecución, los comandos de la CLI tomarán sus parámetros y construirán una llamada a MSBuild "sin procesar" que establecerá las propiedades necesarias y ejecutará el destino deseado. Para ilustrar mejor esto, considere el siguiente comando: 

   `dotnet publish -o pub -c Release`
    
Este comando está publicando una aplicación en una carpeta `pub` mediante la configuración de "Release". Internamente, este comando se traduce en la siguiente invocación de MSBuild: 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

La excepción importante a esta regla son los comandos `new` y `run`, dado que no se han implementado como destinos de MSBuild.

<a name="dotnet-restore-note"></a> [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]