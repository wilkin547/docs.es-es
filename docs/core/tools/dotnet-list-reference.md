---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463643"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>Name

`dotnet list reference`: enumera las referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a>Description

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.

## <a name="arguments"></a>Argumentos

* **`PROJECT | SOLUTION`**

  Especifica el archivo de solución o proyecto que se usará para enumerar las referencias. Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

* Enumerar las referencias del proyecto para el proyecto especificado:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Enumerar las referencias del proyecto para el proyecto en el directorio actual:

  ```dotnetcli
  dotnet list reference
  ```
