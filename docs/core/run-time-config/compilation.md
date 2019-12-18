---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998880"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="552c9-103">Opciones de configuración del entorno de ejecución para compilación</span><span class="sxs-lookup"><span data-stu-id="552c9-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="552c9-104">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="552c9-104">Tiered compilation</span></span>

- <span data-ttu-id="552c9-105">Configura si el compilador JIT utiliza la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="552c9-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="552c9-106">En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="552c9-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="552c9-107">En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="552c9-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="552c9-108">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="552c9-108">Setting name</span></span> | <span data-ttu-id="552c9-109">Valores</span><span class="sxs-lookup"><span data-stu-id="552c9-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="552c9-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="552c9-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="552c9-111">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="552c9-111">`true` - enabled</span></span><br/><span data-ttu-id="552c9-112">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="552c9-112">`false` - disabled</span></span> |
| <span data-ttu-id="552c9-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="552c9-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="552c9-114">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="552c9-114">`1` - enabled</span></span><br/><span data-ttu-id="552c9-115">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="552c9-115">`0` - disabled</span></span> |
