---
title: Comando dotnet clean
description: El comando dotnet clean limpia el directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503754"
---
# <a name="dotnet-clean"></a>dotnet clean

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet clean`: limpia la salida de un proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet clean` limpia la salida de la compilación anterior. Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando. Solo se limpian las salidas que se crearon durante la compilación. Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).

## <a name="arguments"></a>Argumentos

`PROJECT | SOLUTION`

Proyecto o solución de MSBuild que se va a limpiar. Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* o *sln* y lo usa.

## <a name="options"></a>Opciones

* **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto. Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.

* **`-f|--framework <FRAMEWORK>`**

  El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación. El marco se debe definir en el [archivo de proyecto](csproj.md). Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

* **`--nologo`**

  No se muestra la pancarta de inicio ni el mensaje de copyright. Disponible desde el SDK de .NET Core 3.0.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directorio que contiene los artefactos compilados que se van a limpiar. Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Limpia la carpeta de salida del tiempo de ejecución especificado. Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#publish-self-contained).

* **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle de MSBuild. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `normal`.

## <a name="examples"></a>Ejemplos

* Limpie una compilación predeterminada del proyecto:

  ```dotnetcli
  dotnet clean
  ```

* Limpie un proyecto creado con la configuración de lanzamiento:

  ```dotnetcli
  dotnet clean --configuration Release
  ```
