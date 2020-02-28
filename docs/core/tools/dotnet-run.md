---
title: Comando dotnet run
description: El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente.
ms.date: 02/19/2020
ms.openlocfilehash: 415d7079db6a3da80c4fcf2074307ea760e84982
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503607"
---
# <a name="dotnet-run"></a>dotnet run

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] 
    [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] 
    [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando. Es útil para un desarrollo iterativo rápido desde la línea de comandos. El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código. Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`.

Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`. Por ejemplo, si tiene una aplicación `netcoreapp2.1` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp2.1`. Los archivos se sobrescriben según sea necesario. Los archivos temporales se colocan en el directorio `obj`.

Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.

El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados. Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando. Por ejemplo, para ejecutar `myapp.dll`, use:

```dotnetcli
dotnet myapp.dll
```

Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).

Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet. Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción. En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Opciones

- **`--`**

  Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.

- **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.

- **`-f|--framework <FRAMEWORK>`**

  Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado. El marco debe especificarse en el archivo de proyecto.

- **`--force`**

  Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Disponible desde el SDK de .NET Core 3.0.

- **`--launch-profile <NAME>`**

  El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación. Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`. Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).

- **`--no-build`**

  No compila el proyecto antes de ejecutarlo. También establece la marca `--no-restore` de forma implícita.

- **`--no-dependencies`**

  Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.

- **`--no-launch-profile`**

  No intenta usar *launchSettings.json* para configurar la aplicación.

- **`--no-restore`**

  No ejecuta una restauración implícita al ejecutar el comando.

- **`-p|--project <PATH>`**

  Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa). Si no se especifica, se toma como predeterminado el directorio actual.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Especifica el tiempo de ejecución de destino para el que restaurar los paquetes. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). Opción corta `-r` disponible a partir del SDK de .NET Core 3.0.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `m`. Disponible a partir del SDK de .NET Core 2.1. 

## <a name="examples"></a>Ejemplos

- Ejecución del proyecto en el directorio actual:

  ```dotnetcli
  dotnet run
  ```

- Ejecución del proyecto especificado:

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usa la opción `--` en blanco):

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- Restaure las dependencias y herramientas del proyecto en el directorio actual mostrando solo la salida mínima y, después, ejecute el proyecto: (SDK de .NET Core 2.0 y versiones superiores):

  ```dotnetcli
  dotnet run --verbosity m
  ```
