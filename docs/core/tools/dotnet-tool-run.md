---
title: Comando dotnet tool run
description: El comando dotnet tool run invoca una herramienta local.
ms.date: 02/14/2020
ms.openlocfilehash: f79c239363e8b3abbd55c54dd1912443e6777fb7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463326"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool run`: invoca una herramienta local.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet tool run` busca los archivos de manifiesto de las herramientas que se encuentran en el ámbito del directorio actual. Cuando encuentra una referencia a la herramienta especificada, ejecuta la herramienta. Para obtener más información, vea [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argumentos

- **`COMMAND_NAME`**

  El nombre del comando de la herramienta que se va a ejecutar.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="example"></a>Ejemplo

- **`dotnet tool run dotnetsay`**

  Ejecuta la herramienta local `dotnetsay`.

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core](local-tools-how-to-use.md)
