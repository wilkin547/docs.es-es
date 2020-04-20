---
title: Comando dotnet remove package
description: El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463451"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>Name

`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a>Description

El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

`PACKAGE_NAME`

La referencia de paquete que hay que quitar.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

- Quite el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
