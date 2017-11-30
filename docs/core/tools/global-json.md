---
title: Referencia de Global.json
description: "Consulte el esquema del archivo global.json, que permite establecer la versión de las herramientas de .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="globaljson-reference"></a><span data-ttu-id="58218-104">Referencia de Global.json</span><span class="sxs-lookup"><span data-stu-id="58218-104">global.json reference</span></span>

<span data-ttu-id="58218-105">El archivo *global.json* permite la selección de la versión de herramientas de .NET Core que se está usando mediante la propiedad `sdk`.</span><span class="sxs-lookup"><span data-stu-id="58218-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="58218-106">Las herramientas de la CLI de .NET Core buscan este archivo en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o uno de sus directorios principales.</span><span class="sxs-lookup"><span data-stu-id="58218-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="58218-107">sdk</span><span class="sxs-lookup"><span data-stu-id="58218-107">sdk</span></span>
<span data-ttu-id="58218-108">Tipo: objeto</span><span class="sxs-lookup"><span data-stu-id="58218-108">Type: Object</span></span>

<span data-ttu-id="58218-109">Especifica información acerca del SDK.</span><span class="sxs-lookup"><span data-stu-id="58218-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="58218-110">version</span><span class="sxs-lookup"><span data-stu-id="58218-110">version</span></span>
<span data-ttu-id="58218-111">Tipo: string</span><span class="sxs-lookup"><span data-stu-id="58218-111">Type: String</span></span>

<span data-ttu-id="58218-112">Versión del SDK para usar.</span><span class="sxs-lookup"><span data-stu-id="58218-112">The version of the SDK to use.</span></span>

<span data-ttu-id="58218-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="58218-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
