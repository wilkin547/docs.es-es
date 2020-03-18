---
title: Arquitectura de las herramientas de la línea de comandos de .NET Core
description: Obtenga información sobre las capas de herramientas de .NET Core y sobre lo que ha cambiado en versiones recientes.
ms.date: 03/06/2017
ms.openlocfilehash: fde1a0acb6af9dd65aa3466b4ea37473b2eab6fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092920"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Introducción de alto nivel de los cambios en las herramientas de .NET Core

En este documento se describen los cambios asociados con el traslado de *project.json* a MSBuild y al sistema del proyecto *csproj* con información sobre los cambios realizados en las capas de las herramientas de .NET Core y en la implementación de los comandos de la CLI. Estos cambios se han producido con la versión de .NET Core SDK 1.0 y Visual Studio 2017 de 7 de marzo de 2017 (vea el [anuncio](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)), pero se han implementado inicialmente con la versión de .NET Core SDK Preview 3.

## <a name="moving-away-from-projectjson"></a>Abandono de project.json

El cambio más importante en las herramientas para .NET Core es ciertamente el [abandono de project.json en favor de csproj](https://devblogs.microsoft.com/dotnet/changes-to-project-json/) como sistema de proyectos. Las últimas versiones de las herramientas de línea de comandos no admiten archivos *project.json*. Esto significa que no puede utilizarse para compilar, ejecutar o publicar bibliotecas y aplicaciones basadas en project.json. Para utilizar esta versión de las herramientas, migre los proyectos existentes o inicie otros nuevos.

Como parte de este proceso, el motor de compilación personalizado que se desarrolló para compilar proyectos de project.json se ha reemplazado por un motor de compilación maduro y totalmente compatible llamado [MSBuild](https://github.com/Microsoft/msbuild). MSBuild es un motor conocido en la comunidad de .NET. Ha sido una tecnología clave desde la primera versión de la plataforma. Puesto que debe compilar aplicaciones .NET Core, MSBuild se ha trasladado a .NET Core y puede utilizarse en cualquier plataforma donde se ejecute .NET Core. Una de las promesas principales de .NET Core es una pila de desarrollo multiplataforma, y nos hemos asegurado de que esta transición no rompa esa promesa.

> [!TIP]
> Si no está familiarizado con MSBuild y quiere aprender más al respecto, puede empezar por leer el artículo [Conceptos de MSBuild](/visualstudio/msbuild/msbuild-concepts).

## <a name="the-tooling-layers"></a>Las capas de herramientas

Con el cambio en el motor de compilación y el abandono del sistema del proyecto existente, es lógico que surjan algunas preguntas. ¿Alguno de estos cambios modifica la "disposición en capas" del ecosistema de herramientas de .NET Core? ¿Hay nuevos bits y componentes?

Comencemos con un repaso rápido de la disposición en capas de Preview 2, como se muestra en la siguiente imagen:

![Arquitectura de alto nivel de herramientas de Preview 2](media/cli-msbuild-architecture/p2-arch.png)

La disposición en capas de las herramientas en la Versión preliminar 2 es sencilla. En el fondo, la base es la CLI de .NET Core. El resto de herramientas de mayor nivel, como Visual Studio o Visual Studio Code, dependen de la CLI, y se basan en esta, para compilar proyectos, restaurar dependencias, etc. Por ejemplo, si se quisiera realizar una operación de restauración con Visual Studio, se llamaría al comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) de la CLI.

Con el paso al nuevo sistema de proyecto, el diagrama anterior cambia:

![Arquitectura de alto nivel del SDK 1.0.0 de .NET Core](media/cli-msbuild-architecture/p3-arch.png)

La principal diferencia es que la CLI ya no es la base; este papel es ocupado ahora por el "componente de SDK compartido". Este componente de SDK compartido es un conjunto de destinos y tareas asociadas que son responsables de compilar el código y publicarlo, de empaquetar paquetes NuGet, etc. El SDK de .NET Core es código abierto y está disponible en GitHub en el [repositorio de SDK](https://github.com/dotnet/sdk).

> [!NOTE]
> Un "destino" es un término de MSBuild que indica una operación con nombre que puede invocar MSBuild. Normalmente está unido a una o varias tareas que ejecutan alguna lógica que se supone que debe hacer el destino. MSBuild admite muchos destinos predefinidos, como `Copy` o `Execute`; también permite a los usuarios escribir sus propias tareas mediante código administrado y definir destinos para ejecutar esas tareas. Para obtener más información, consulte [Tareas de MSBuild](/visualstudio/msbuild/msbuild-tasks).

Todos los conjuntos de herramientas consumen ahora el componente de SDK compartido y sus destinos, incluida la CLI. Por ejemplo, Visual Studio 2019 no llama al comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias de los proyectos de .NET Core. En su lugar, usa el destino "Restauración" directamente. Como son destinos de MSBuild, también puede usar MSBuild sin procesar para ejecutarlos mediante el comando [dotnet msbuild](dotnet-msbuild.md).

### <a name="cli-commands"></a>Comandos de la CLI

El componente de SDK compartido implica que la mayoría de los comandos de la CLI existentes se han vuelto a implementar como tareas y destinos de MSBuild. ¿Qué significa esto para los comandos de la CLI y el uso del conjunto de herramientas?

Desde una perspectiva del uso, no cambia la forma de usar la CLI. La CLI sigue teniendo los comandos principales que existían en la versión preliminar 2 de .NET Core 1.0:

- `new`
- `restore`
- `run`
- `build`
- `publish`
- `test`
- `pack`

Estos comandos todavía hacen lo que se espera que hagan (crear un nuevo proyecto, compilarlo, publicarlo, empaquetarlo, etc.). Se puede consultar la pantalla de ayuda del comando (mediante `dotnet <command> --help`) o la documentación de este sitio para familiarizarse con su comportamiento.

Desde una perspectiva de la ejecución, los comandos de la CLI toman sus parámetros y construyen una llamada a MSBuild "sin procesar" que establece las propiedades necesarias y ejecuta el destino deseado. Para ilustrar mejor esto, considere el siguiente comando:

   ```dotnetcli
   dotnet publish -o pub -c Release
   ```

Este comando publica una aplicación en una carpeta `pub` mediante la configuración de "Versión". Internamente, este comando se traduce en la siguiente invocación de MSBuild:

   ```dotnetcli
   dotnet msbuild -t:Publish -p:OutputPath=pub -p:Configuration=Release
   ```

Las excepciones destacadas a esta regla son los comandos `new` y `run`. No se han implementado como destinos de MSBuild.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
