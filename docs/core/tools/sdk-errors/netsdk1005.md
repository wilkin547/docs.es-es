---
title: 'NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos'
description: Procedimiento para resolver el problema de la falta de un destino en un archivo de recursos.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678165"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="9f212-103">NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos</span><span class="sxs-lookup"><span data-stu-id="9f212-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="9f212-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9f212-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="9f212-105">Cuando el SDK de .NET emite el error NETSDK1005 o NETSDK1047, falta información sobre una de las plataformas de destino en el archivo de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f212-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="9f212-106">NuGet escribe un archivo llamado *project.assets.json* en la carpeta *obj* y el SDK de .NET lo usa para obtener información sobre los paquetes que se van a pasar al compilador.</span><span class="sxs-lookup"><span data-stu-id="9f212-106">NuGet writes a file named *project.assets.json* in the *obj* folder, and the .NET SDK uses it to get information about packages to pass into the compiler.</span></span> <span data-ttu-id="9f212-107">En .NET 5, NuGet agregó un nuevo campo denominado `TargetFrameworkAlias`, por lo que las versiones anteriores de MSBuild o NuGet generan un archivo de recursos sin el nuevo campo.</span><span class="sxs-lookup"><span data-stu-id="9f212-107">In .NET 5, NuGet added a new field named `TargetFrameworkAlias`, so earlier versions of MSBuild or NuGet generate an assets file without the new field.</span></span> <span data-ttu-id="9f212-108">Para obtener más información, vea [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span><span class="sxs-lookup"><span data-stu-id="9f212-108">For more information, see [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span></span>

<span data-ttu-id="9f212-109">Estas son algunas acciones que puede realizar y que pueden resolver el error:</span><span class="sxs-lookup"><span data-stu-id="9f212-109">Here are some actions you can take that may resolve the error:</span></span>

* <span data-ttu-id="9f212-110">Asegúrese de que está usando la versión 16.8 o posterior de MSBuild y la versión 5.8 o posterior de NuGet y restaure el proyecto después de actualizar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="9f212-110">Make sure that you're using MSBuild version 16.8 or later and NuGet version 5.8 or later, and restore the project after updating your tools.</span></span> <span data-ttu-id="9f212-111">Si usa la versión 5.8 o posterior de NuGet, debe usar Visual Studio 2019, versión 16.8 o posterior; MSBuild, versión 16.8 o posterior, y el SDK de .NET 5.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9f212-111">When you're using NuGet version 5.8 or later, you should be using Visual Studio 2019 version 16.8 or later, MSBuild version 16.8 or later, and .NET 5.0 SDK or later.</span></span>

* <span data-ttu-id="9f212-112">Si obtiene el error durante la compilación de un proyecto en Visual Studio 2019 por primera vez después de instalar la versión 16.8 o después de cambiar la plataforma de destino del proyecto, vuelva a compilar el proyecto por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="9f212-112">If you get the error while building a project in Visual Studio 2019 for the first time after installing version 16.8 or after changing the project's target framework, build the project a second time.</span></span>

* <span data-ttu-id="9f212-113">Elimine la carpeta *obj* antes de compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f212-113">Delete the *obj* folder before building the project.</span></span>

* <span data-ttu-id="9f212-114">Asegúrese de que el valor de destino que falta está incluido en la propiedad `TargetFrameworks` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f212-114">Make sure that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>
