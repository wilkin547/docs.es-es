---
title: Comando dotnet tool list
description: El comando dotnet tool list muestra la herramienta global especificada de .NET Core que hay instalada en el equipo.
ms.date: 05/29/2018
ms.openlocfilehash: 6d35b1dce0c6d57edb0c6dd5f9711f093bc804aa
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117554"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>Name

`dotnet tool list`: enumera todas las [herramientas globales de .NET Core](global-tools.md) instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet tool list` muestra todas las herramientas globales de .NET Core instaladas para los usuarios en el equipo (perfil de usuario actual) o en la ruta de acceso especificada. El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta global. Para utilizar el comando list, especifique que quiere ver las herramientas de los usuarios con la opción `--global`, o bien especifique una ruta de acceso personalizada con la opción `--tool-path`.

## <a name="options"></a>Opciones

`-g|--global`

Enumera las herramientas globales de los usuarios. No se puede combinar con la opción `--tool-path`. Si no especifica esta opción, debe especificar la opción `--tool-path`.

`-h|--help`

Imprime una corta ayuda para el comando.

`--tool-path <PATH>`

Especifica una ubicación personalizada para las herramientas globales. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Si no especifica esta opción, debe especificar la opción `--global`.

## <a name="examples"></a>Ejemplos

Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual):

`dotnet tool list -g`

Enumera las herramientas globales de una carpeta específica de Windows:

`dotnet tool list --tool-path c:\global-tools`

Enumera las herramientas globales de una carpeta específica de Linux/macOS:

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a>Vea también

- [Herramientas globales de .NET Core](global-tools.md)
