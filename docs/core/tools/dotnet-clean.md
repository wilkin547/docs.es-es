---
title: Comando dotnet clean
description: El comando dotnet clean limpia el directorio actual.
ms.date: 12/04/2018
ms.openlocfilehash: a25b7930794795e3dff5051a8ca1dd1b9c261dfd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169864"
---
# <a name="dotnet-clean"></a>dotnet clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet clean`: limpia la salida de un proyecto.

## <a name="synopsis"></a>Sinopsis

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet clean` limpia la salida de la compilación anterior. Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando. Solo se limpian las salidas que se crearon durante la compilación. Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).

## <a name="arguments"></a>Argumentos

`PROJECT`

El proyecto de MSBuild para limpiar. Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.

## <a name="options"></a>Opciones

* **`-c|--configuration {Debug|Release}`**

  Define la configuración de compilación. El valor predeterminado es `Debug`. Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.

* **`-f|--framework <FRAMEWORK>`**

  El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación. El marco se debe definir en el [archivo de proyecto](csproj.md). Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directorio en el que se colocan las salidas de compilación. Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Limpia la carpeta de salida del tiempo de ejecución especificado. Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd). Opción disponible desde el SDK de .NET Core 2.0.

* **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].

## <a name="examples"></a>Ejemplos

* Limpie una compilación predeterminada del proyecto:

  ```console
  dotnet clean
  ```

* Limpie un proyecto creado con la configuración de lanzamiento:

  ```console
  dotnet clean --configuration Release
  ```