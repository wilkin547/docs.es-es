---
title: Comando dotnet tool list
description: El comando dotnet tool list muestra la herramienta global especificada de .NET Core que hay instalada en el equipo.
ms.date: 05/29/2018
ms.openlocfilehash: d3ff7fc90faf6ede3f7de0d5af5112c77ca140db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712938"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nombre

`dotnet tool list`: enumera todas las [herramientas globales de .NET Core](global-tools.md) instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.

## <a name="synopsis"></a>Sinopsis

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>Descripción

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
