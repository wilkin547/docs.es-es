---
title: Referencia de Global.json
description: Consulte el esquema del archivo global.json, que permite establecer la versión de las herramientas de .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a><span data-ttu-id="1feb3-103">Referencia de Global.json</span><span class="sxs-lookup"><span data-stu-id="1feb3-103">global.json reference</span></span>

<span data-ttu-id="1feb3-104">El archivo *global.json* permite la selección de la versión de herramientas de .NET Core que se está usando mediante la propiedad `sdk`.</span><span class="sxs-lookup"><span data-stu-id="1feb3-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="1feb3-105">Las herramientas de la CLI de .NET Core buscan este archivo en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o uno de sus directorios principales.</span><span class="sxs-lookup"><span data-stu-id="1feb3-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="1feb3-106">sdk</span><span class="sxs-lookup"><span data-stu-id="1feb3-106">sdk</span></span>
<span data-ttu-id="1feb3-107">Tipo: objeto</span><span class="sxs-lookup"><span data-stu-id="1feb3-107">Type: Object</span></span>

<span data-ttu-id="1feb3-108">Especifica información acerca del SDK.</span><span class="sxs-lookup"><span data-stu-id="1feb3-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="1feb3-109">version</span><span class="sxs-lookup"><span data-stu-id="1feb3-109">version</span></span>
<span data-ttu-id="1feb3-110">Tipo: string</span><span class="sxs-lookup"><span data-stu-id="1feb3-110">Type: String</span></span>

<span data-ttu-id="1feb3-111">Versión del SDK para usar.</span><span class="sxs-lookup"><span data-stu-id="1feb3-111">The version of the SDK to use.</span></span>

<span data-ttu-id="1feb3-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1feb3-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
