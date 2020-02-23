---
title: Migración de DNX a CLI de .NET Core
description: Migre de las herramientas de DNX a las herramientas de la CLI de .NET Core.
ms.date: 06/20/2016
ms.openlocfilehash: 31317f110ae1e8586b78becd757d0a8ff07f1459
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503823"
---
# <a name="migrating-from-dnx-to-net-core-cli-projectjson"></a>Migración de DNX a CLI de .NET Core (project.json)

## <a name="overview"></a>Información general
Con la versión RC1 de .NET Core y ASP.NET Core 1.0, presentamos las herramientas DNX. Con la versión RC2 de .NET Core y ASP.NET Core 1.0, hicimos la transición de DNX a .NET Core CLI.

Resumamos un poco de qué se trata DNX como un breve recordatorio. DNX era un entorno de ejecución y un conjunto de herramientas para compilar aplicaciones de .NET Core y, más específicamente, de ASP.NET Core 1.0. Constaba de 3 componentes principales:

1. DNVM: un script de instalación para obtener DNX.
2. DNX (entorno de ejecución Dotnet): el entorno de ejecución que ejecuta el código.
3. DNU (utilidad para desarrolladores de Dotnet): herramientas para administrar dependencias y compilar y publicar las aplicaciones.

Con la presentación de la CLI, todos los componentes anteriores ahora forman parte de un conjunto de herramientas único. Sin embargo, como DNX estaba disponible en el período de tiempo de RC1, es posible que tenga proyectos que se compilaron así que desearía mover a las nuevas herramientas de CLI.

En esta guía de migración se analizarán los aspectos fundamentales sobre cómo migrar proyectos de DNX a la CLI de .NET Core. Si recién está comenzando un proyecto en .NET Core desde cero, puede omitir sin problemas este documento.

## <a name="main-changes-in-the-tooling"></a>Principales cambios en las herramientas
En primer lugar, es necesario describir algunos cambios generales en las herramientas.

### <a name="no-more-dnvm"></a>No más DNVM
DNVM, abreviatura para el inglés de *Administrador de versiones DotNet* era un script de PowerShell/búsqueda intensiva que se usaba para instalar un DNX en la máquina. Ayudó a los usuarios a obtener el DNX que necesitaban a partir de la fuente que especificaban (o la fuente predeterminada), además de marcar cierto DNX como "activo", lo que lo ubicaría en la $PATH de la sesión especificada. Esto le permitiría usar las diversas herramientas.

DNVM se interrumpió porque su conjunto de características se volvió redundante debido a los cambios introducidos con la CLI de .NET Core.

La CLI viene empaquetada de dos maneras principales:

1. Instaladores nativos en una plataforma determinada.
2. Script de instalación para otras situaciones (como los servidores de CI).

Por lo tanto, no se necesitan las características de instalación de DNVM. ¿Qué sucede, entonces, con las características de selección del entorno de ejecución?

Si agrega un paquete de cierta versión a las dependencias, hace referencia a un entorno de ejecución en su `project.json`. Con este cambio, la aplicación podrá usar los nuevos bits de entorno de ejecución. Incorporar estos bits a la máquina es similar a lo que sucede con la CLI: instala el entorno de ejecución a través de los instaladores nativos que admite o a través del script de instalación.

### <a name="different-commands"></a>Otros comandos
Si usó DNX, usaba algunos comandos provenientes de uno de sus tres componentes (DNX, DNU o DNVM). Con la CLI, algunos de estos comandos cambian, algunos no están disponibles y otros son iguales, pero con pequeñas diferencias semánticas.

La tabla siguiente muestra la asignación entre los comandos de DNX/DNU y sus contrapartes de la CLI.

| Comando de DNX                    | Comando de la CLI    | Descripción                                                                                                     |
|--------------------------------|----------------|-----------------------------------------------------------------------------------------------------------------|
| dnx run                        | `dotnet run`     | Ejecute el código desde el origen.                                                                                           |
| dnu build                      | `dotnet build`   | Compile un archivo binario de IL del código.                                                                                |
| dnu pack                       | `dotnet pack`    | Cree un paquete NuGet del código.                                                                        |
| dnx \[comando] (por ejemplo, "dnx web") | no disponible\*          | Si se usa DNX, ejecute un comando según lo definido en project.json.                                                     |
| dnu install                    | no disponible\*          | Si se usa DNX, instale un paquete como dependencia.                                                            |
| dnu restore                    | `dotnet restore` | Restaure las dependencias especificadas en project.json. ([vea la nota](#dotnet-restore-note))                                                            |
| dnu publish                    | `dotnet publish` | Publique la aplicación para su implementación en una de tres formas (portátil, portátil con nativo e independiente). |
| dnu wrap                       | no disponible\*          | Si se usa DNX, encapsule un archivo project.json en csproj.                                                                    |
| dnu commands                   | no disponible\*          | Si se usa DNX, administre los comandos instalados globalmente.                                                           |

(\*): por diseño, la CLI no admite estas características.

## <a name="dnx-features-that-are-not-supported"></a>Características de DNX no admitidas
Tal como muestra la tabla anterior, hay características de DNX que decidimos no admitir en la CLI, al menos por el momento. En esta sección se analizarán las más importantes y se describe el razonamiento detrás de la decisión de no admitirlas, además de las soluciones que puede implementar si las necesita.

### <a name="global-commands"></a>Comandos globales
DNU incluía un concepto llamado "comandos globales". En esencia, se trataba de aplicaciones de consola empaquetadas como paquetes NuGet con un script de shell que podría invocar el DNX especificado para ejecutar la aplicación.

La CLI no admite este concepto. Sin embargo, sí admite el concepto de agregar comandos por proyecto que se pueden invocar con la conocida sintaxis `dotnet <command>`.

### <a name="installing-dependencies"></a>Instalación de dependencias
A partir de la versión v1, la CLI de .NET Core no tiene un comando `install` para instalar dependencias. Para instalar un paquete desde NuGet, necesita agregarlo como una dependencia al archivo `project.json` y, luego, ejecutar `dotnet restore` ([vea la nota](#dotnet-restore-note)).

### <a name="running-your-code"></a>Ejecución del código
Existen dos formas principales de ejecutar el código. Una es desde el origen, con `dotnet run`. A diferencia de `dnx run`, no hará ninguna compilación en memoria. En realidad, invocará a `dotnet build` para compilar el código y, luego, ejecutar el archivo binario compilado.

La otra forma es usar el `dotnet` mismo para ejecutar el código. Para ello, proporcione una ruta de acceso al ensamblado: `dotnet path/to/an/assembly.dll`.

## <a name="migrating-your-dnx-project-to-net-core-cli"></a>Migración del proyecto DNX a la CLI de .NET Core
Además de usar los comandos nuevos cuando se trabaja con el código, hay 3 aspectos importantes que se dejaron en la migración desde DNX:

1. Si lo tiene, migre el archivo `global.json` para usar la CLI.
2. Migración del archivo del proyecto (`project.json`) mismo a las herramientas de la CLI.
3. Migración de cualquier API de DNX a sus contrapartes de BCL.

### <a name="changing-the-globaljson-file"></a>Cambio del archivo global.json
El archivo `global.json` actúa como un archivo de solución tanto para los proyectos de RC1 como para los de RC2 (o posteriores). A fin de que la CLI de .NET Core (como también Visual Studio) diferencie entre RC1 y las versiones posteriores, usa la propiedad `"sdk": { "version" }` para hacer la distinción entre qué proyecto es RC1 o posterior. Si `global.json` no tiene este nodo, se supone que es la versión más reciente.

Con el fin de actualizar el archivo `global.json`, quite la propiedad o establézcala en la versión exacta de las herramientas que desea usar; en este caso, **1.0.0-preview2-003121**:

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```

### <a name="migrating-the-project-file"></a>Migración del archivo del proyecto

Tanto la CLI como DNX usan el mismo sistema de proyectos básico basado en el archivo `project.json`. La sintaxis y la semántica del archivo del proyecto son prácticamente iguales, con pequeñas diferencias en función de los escenarios. También hay algunos cambios en el esquema que puede ver en el [archivo del esquema](http://json.schemastore.org/project).

Si compila una aplicación de consola, debe agregar el siguiente fragmento de código al archivo del proyecto:

```json
"buildOptions": {
    "emitEntryPoint": true
}
```

Esto indica a `dotnet build` que emita un punto de entrada para la aplicación, lo que permitirá que el código se pueda ejecutar. Si compila una biblioteca de clases, simplemente debe omitir la sección anterior. Por supuesto, una vez que agregue el fragmento de código anterior al archivo `project.json`, deberá agregar un punto de entrada estático. Con la migración de DNX, los servicios de DI que proporcionaba ya no están disponibles y, por lo tanto, debe tratarse de un punto de entrada .NET básico: `static void Main()`.

Si tiene una sección de "comandos" en su `project.json`, puede quitarla. Algunos de los comandos que existían como comandos de DNU, como los comandos de la CLI de Entity Framework, se trasladan para convertirse en extensiones por proyecto en la CLI. Si compila sus propios comandos que usa en los proyectos, debe reemplazarlos con extensiones de la CLI. En este caso, el nodo `commands` de `project.json` debe reemplazarse por el nodo `tools` y se deben enumerar las dependencias de herramientas.

Una vez hecho esto, deberá decidir qué tipo de portabilidad desea para la aplicación. Con .NET Core, invertimos en proporcionar un espectro de opciones de portabilidad entre las que puede elegir. Por ejemplo, podría tener una aplicación completamente *portátil*, o bien podría querer tener una aplicación *autocontenida*. La opción de la aplicación portátil es más similar a cómo funcionan las aplicaciones de .NET Framework: necesita un componente compartido para ejecutarlo en la máquina de destino (.NET Core). La aplicación autocontenida no requiere que .NET Core esté instalado en el destino, pero es necesario generar una aplicación para cada SO que desea admitir. Estos tipos de portabilidad, y otros más, se analizan en el documento sobre los [tipos de portabilidad de aplicaciones](../deploying/index.md).

Una vez que decide el tipo de portabilidad que desea, deberá cambiar las plataformas de destino. Si escribiera aplicaciones para .NET Core, es probable que use `dnxcore50` como la plataforma de destino. Con la CLI y los cambios que trajo la nueva especificación [.NET Standard](../../standard/net-standard.md), la plataforma debe ser una de las siguientes:

1. `netcoreapp1.0`, si escribe aplicaciones en .NET Core (incluidas las aplicaciones de ASP.NET Core).
2. `netstandard1.6`, si escribe las bibliotecas de clases para .NET Core.

Si usa otros destinos `dnx`, como `dnx451`, también deberá cambiarlos. `dnx451`se debe cambiar a `net451`.
Consulte el tema [Estándar .NET](../../standard/net-standard.md) para obtener más información.

El archivo `project.json` está casi listo. Debe revisar la lista de dependencias y actualizarlas a sus versiones más recientes, especialmente si usa las dependencias de ASP.NET Core. Si usará los paquetes independientes para las API de BCL, puede usar el paquete del entorno de ejecución tal como se explica en el documento sobre los [tipos de portabilidad de aplicaciones](../deploying/index.md).

Cuando esté listo, puede intentar la restauración con `dotnet restore` ([vea la nota](#dotnet-restore-note)). En función de la versión de las dependencias, puede encontrar errores si NuGet no puede resolver las dependencias de una de las plataformas de destino anteriormente mencionadas. Este es un problema "en un momento específico"; a medida que pase el tiempo, cada vez más paquetes incluirán compatibilidad con estos marcos de trabajo. Por ahora, si se enfrenta con este problema, puede usar la instrucción `imports` dentro del nodo `framework` para especificar a NuGet que puede restaurar los paquetes que tienen como destino el marco de trabajo que se encuentra dentro de la instrucción de "importaciones".
Los errores de restauración que recibe en este caso deben proporcionar información suficiente que le permita distinguir los marcos de trabajo que debe importar. Si está un poco confundido o es nuevo en esto, en palabras generales, bastaría con especificar `dnxcore50` y `portable-net45+win8` en la instrucción `imports`. El fragmento de código JSON siguiente muestra cómo se verá:

```json
    "frameworks": {
        "netcoreapp1.0": {
            "imports": ["dnxcore50", "portable-net45+win8"]
        }
    }
```

La ejecución de `dotnet build` mostrará cualquier posible error de compilación, aunque no debería haber muchos. Una vez que el código se compile y ejecute correctamente, puede probarlo con el ejecutor. Ejecute `dotnet <path-to-your-assembly>` y vea si se ejecuta correctamente.

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
