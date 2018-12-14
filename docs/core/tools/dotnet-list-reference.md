---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 12/03/2018
ms.openlocfilehash: 58b4e07abfe95d1febdd54d117825ecedf502e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152616"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet list reference`: enumera las referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.

## <a name="arguments"></a>Argumentos

* **`PROJECT`**

  Especifica el archivo de proyecto que se usará para enumerar las referencias. Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

* Enumerar las referencias del proyecto para el proyecto especificado:

  ```console
  dotnet list app/app.csproj reference
  ```

* Enumerar las referencias del proyecto para el proyecto en el directorio actual:

  ```console
  dotnet list reference
  ```