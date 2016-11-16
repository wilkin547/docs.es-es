---
title: Modelo de extensibilidad de la CLI de .NET Core
description: Modelo de extensibilidad de la CLI de .NET Core
keywords: CLI, extensibilidad, comandos personalizados, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 1bebd25a-120f-48d3-8c25-c89965afcbcd
translationtype: Human Translation
ms.sourcegitcommit: aeb199a9aeb1584570ad2a2942e2f22c75a59616
ms.openlocfilehash: ea16d4b841f5c93da222df56db36d6fb70ea35f9

---

# <a name="net-core-cli-extensibility-model"></a>Modelo de extensibilidad de la CLI de .NET Core 

## <a name="overview"></a>Información general
En este documento se tratan las principales formas de ampliar las herramientas de la CLI y se explican los escenarios que impulsan cada una. Se describe cómo consumir las herramientas y se proporcionan notas cortas sobre cómo compilar ambos tipos de herramientas. 

## <a name="how-to-extend-cli-tools"></a>Cómo extender las herramientas de la CLI
Las herramientas de la CLI pueden extenderse de dos maneras principales:

1. A través de paquetes de NuGet por proyecto
2. Mediante la RUTA DE ACCESO del sistema

Los dos mecanismos de extensibilidad descritos anteriormente no son mutuamente excluyentes; puede usar uno solo o ambos. La selección de uno u otro depende en gran medida de cuál sea el objetivo que intenta alcanzar con su extensión.

## <a name="perproject-based-extensibility"></a>Extensibilidad por proyecto
Las herramientas por proyecto son [aplicaciones de consola portátiles](../deploying/index.md) que se distribuyen como paquetes de NuGet. Las herramientas solo están disponibles en el contexto del proyecto que hace referencia a ellas y para el que se restauran; la invocación fuera del contexto del proyecto (por ejemplo, fuera del directorio que contiene el proyecto) dará error ya que no se podrá encontrar el comando.

Estas herramientas son perfectas también para servidores de compilación, dado que no se necesita nada fuera de `project.json`. El proceso de compilación ejecuta la restauración para el proyecto que se compila y hay herramientas disponibles. Proyectos de lenguajes, como F #, también están en esta categoría; después de todo, cada proyecto solo se puede escribir en un lenguaje específico. 

Finalmente, este modelo de extensibilidad proporciona compatibilidad con la creación de herramientas que necesitan acceso a la salida compilada del proyecto. Por ejemplo, varias herramientas de vista de Razor de aplicaciones [ASP.NET](https://www.asp.net/) MVC se incluyen dentro de esta categoría. 

### <a name="consuming-perproject-tools"></a>Consumo de herramientas por proyecto
El consumo de estas herramientas requiere agregar un nodo `tools` a su `project.json`. Dentro del nodo `tools`, se hace referencia al paquete en el que reside la herramienta. Después de ejecutar `dotnet restore`, se restauran la herramienta y sus dependencias. 

Para las herramientas que necesitan cargar la salida de compilación del proyecto para su ejecución, hay normalmente otra dependencia que aparece en las dependencias normales del archivo de proyecto. Esto significa que las herramientas que cargan el código del proyecto tienen dos componentes: 

1. El invocador principal "tools".
2. Cualquier número de otras herramientas que contienen la lógica con la que se trabaja. 

¿Por qué dos cosas? Las herramientas que necesitan cargar la salida de compilación de un proyecto deben tener un gráfico de dependencias unificado con el proyecto en el que trabajan. Al agregar el bit de dependencia, permitimos que NuGet resuelva estas dependencias como un gráfico unificado. El invocador está allí porque debe razonar sobre la ubicación, así como los marcos de la herramienta de dependencia. El invocador puede aceptar todos los argumentos de redirección (`-c`, `-o`, `-b`) que el usuario especifica, y busca la herramienta de dependencia; también puede implementar directivas para los casos en que existen varias herramientas de dependencia para varios marcos (es decir, para ejecutar todas ellas, solo una, etc.) En general, la lógica puede compartirse entre estas dos herramientas de cualquier forma que sea necesaria. 

Vamos a ver un ejemplo de cómo agregar una herramienta sencilla tools-only a un proyecto sencillo. Dado un comando de ejemplo llamado `dotnet-api-search` que le permite examinar los paquetes de NuGet hasta encontrar la API especificada, este es un archivo `project.json` de la aplicación de consola que usa esa herramienta:

```json
{
    "version": "1.0.0",
    "compilationOptions": {
        "emitEntryPoint": true
    },
    "dependencies": {
        "Microsoft.NETCore.App": {
            "type": "platform",
            "version": "1.0.0"
        }
    },
    "tools": {
        "dotnet-api-search": {
            "version": "1.0.0",
            "imports": ["dnxcore50"]
        }
    },
    "frameworks": {
        "netcoreapp1.0": {}
    }
}
```

El nodo `tools` está estructurado de forma similar al nodo `dependencies`. Necesita como poco el identificador del paquete que contiene la herramienta y su versión. En el ejemplo anterior, podemos ver que hay otra instrucción, `imports`. Esta instrucción influye en el proceso de restauración de la herramienta y especifica que la herramienta también es compatible, además de con los marcos de destino que tiene la herramienta, con el destino `dnxcore50`. Para más información, puede consultar la [referencia de project.json](project-json.md).

### <a name="building-tools"></a>Compilación de herramientas
Como se ha mencionado, las herramientas son simples aplicaciones de consola portátiles. Se compila lo mismo que cualquier aplicación de consola. Después de compilarla, puede usar el comando [`dotnet pack`](dotnet-pack.md) para crear un paquete de NuGet (nupkg) que contiene el código, información sobre sus dependencias. etc. El nombre del paquete puede ser lo que quiera el autor, pero la aplicación que contiene, el archivo binario de la herramienta real, debe respetar las convenciones de `dotnet-<command>` para que `dotnet` pueda invocarlo. 

Como las herramientas son aplicaciones portátiles, el usuario que las consume tiene que tener la versión de las bibliotecas .NET Core con la que se compiló la herramienta para poder ejecutar esta. Cualquier otra dependencia que use la herramienta y que no esté contenida en las bibliotecas .NET Core se restauran y colocan en la caché de NuGet. Por lo tanto, la herramienta entera se ejecuta con los ensamblados de las bibliotecas .NET Core, así como los ensamblados de la caché de NuGet. 

Estas clases de herramientas tienen un gráfico de dependencias que es completamente independiente del gráfico de dependencias del proyecto que los usa. El proceso de restauración restaura primero las dependencias del proyecto y, a continuación, cada una de las herramientas y sus dependencias. 

Puede encontrar más ejemplos y diferentes combinaciones de esto en el [repositorio de la CLI de .NET Core](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects). También puede ver las [herramientas de implementación usadas](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages) en el mismo repositorio. 

La compilación de herramientas que cargan las salidas de compilación del proyecto para su ejecución es algo diferente. Como se ha indicado, hay dos componentes para estas clases de herramientas:

1. Una herramienta de distribuidor que invoca el usuario.
2. Una dependencia específica del marco que contiene la lógica sobre cómo buscar las salidas de compilación y qué hacer con ellas.

Un buen ejemplo de ello son los comandos [Entity Framework (EF)](https://github.com/aspnet/EntityFramework) y el comando [`dotnet test`](dotnet-test.md). En ambos casos, hay una herramienta a la que se hace referencia en el nodo `tools` de `project.json` y que es el distribuidor principal. El usuario invoca esta herramienta en la línea de comandos. La segunda pieza del rompecabezas es la dependencia que se proporciona en las dependencias principales del proyecto (las de raíz o las específicas del marco). Este paquete contiene la lógica real de la herramienta. El paquete es una dependencia normal, por lo tanto, se restaura como parte del proceso de restauración del proyecto. 

A diferencia de la clase anterior de herramientas, estas herramientas son realmente parte del gráfico del proyecto que las consume. El motivo es que necesitan acceso al código del proyecto y posiblemente a todas sus dependencias. Por ejemplo, en el caso de las herramientas EF esto es así porque deben examinar los ensamblados para encontrar el código que necesitan, como las migraciones.  

Otro motivo de por qué existe esta solución de dos componentes es para permitir un modelo de invocación más limpio. La mayoría de los comandos de la CLI que colocan determinados artefactos en el disco (por ejemplo, `dotnet build`, `dotnet publish`) permiten a los usuarios redirigir las salidas a una ruta de acceso diferente mediante los argumentos `--output`, `--build-base-path` o `--configuration`. En el caso de las herramientas EF, por ejemplo, para poder encontrar la salida de compilación del proyecto, tendría que proporcionar los mismos argumentos con los mismos valores *tanto al controlador* `dotnet` como al comando `ef`. Con el modelo de invocación, los usuarios pasan argumentos a la herramienta de distribuidor que luego usa para encontrar el archivo binario necesario que contiene la lógica en los directorios de salida. 

Un buen ejemplo de este enfoque puede encontrarse en el [repositorio de la CLI de .NET Core](https://github.com/dotnet/cli):

* [Archivo project.json de ejemplo](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/TestAssets/DesktopTestProjects/AppWithDirectDependencyDesktopAndPortable/project.json)
* [Implementación del distribuidor](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages/dotnet-dependency-tool-invoker)
* [Implementación de la dependencia específica del marco](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages/dotnet-desktop-and-portable)


### <a name="pathbased-extensibility"></a>Extensibilidad basada en la RUTA DE ACCESO
La extensibilidad basada en la RUTA DE ACCESO se suele usar con equipos de desarrollo, donde necesita una herramienta que abarque conceptualmente más de un único proyecto. La principal desventaja de este mecanismo de extensiones es que está vinculado a la máquina donde existe la herramienta. Si lo necesita en otro equipo, tendría que implementarlo.

Este patrón de extensibilidad del conjunto de herramientas de la CLI es muy sencillo. Como se explica en la [información general de la CLI de .NET Core](index.md), el controlador `dotnet` puede ejecutar cualquier comando que se nombre según la convención `dotnet-<command>`. La lógica de resolución predeterminada sondeará primero varias ubicaciones y finalmente llegará a la RUTA DE ACCESO del sistema. Si el comando solicitado existe en la RUTA DE ACCESO del sistema y es un archivo binario que se puede invocar, el controlador `dotnet` lo invoca. 

El archivo binario puede ser casi cualquier cosa que el sistema operativo pueda ejecutar. En sistemas Unix, esto significa todo lo que tiene el bit de ejecución establecido mediante `chmod +x`. En Windows, significa todo lo que Windows sabe ejecutar. 

Por ejemplo, echemos un vistazo a una implementación muy sencilla de un comando `dotnet clean`. Usaremos `bash` para implementar este comando. El comando eliminará simplemente los directorios `bin/` y `obj/` del directorio actual. Si el argumento `--lock` se pasa a él, también se elimina el archivo `project.lock.json`. La totalidad del comando se proporciona a continuación. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

En macOS, podemos guardar este script como `dotnet-clean` y establecer su bit ejecutable con `chmod +x dotnet-clean`. Luego, podemos crear un vínculo simbólico a él en `/usr/local/bin` con el comando `ln -s dotnet-clean /usr/local/bin/`. De esta manera se podrá invocar el comando de limpieza mediante la sintaxis `dotnet clean`. Para probar esto, cree una aplicación ejecutando `dotnet build` en él y, luego, ejecute `dotnet clean`. 

## <a name="conclusion"></a>Conclusión
Las herramientas de la CLI de .NET Core permiten dos puntos de extensibilidad principales. Las herramientas por proyecto están contenidas en el contexto del proyecto, pero permiten la instalación fácil mediante la restauración. Las herramientas basadas en la RUTA DE ACCESO son buenas para herramientas entre proyectos generales que se pueden usar en una sola máquina. 



<!--HONumber=Nov16_HO1-->


