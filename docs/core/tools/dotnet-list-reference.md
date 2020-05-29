---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802761"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet list reference`: enumera las referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.

## <a name="arguments"></a>Argumentos

* **`PROJECT`**

  El archivo del proyecto sobre el que actuar. Si no se especifica un archivo, el comando buscará uno en el directorio actual.

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
