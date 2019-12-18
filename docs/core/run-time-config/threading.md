---
title: Valores de configuración de los subprocesos
description: Obtenga información sobre los valores del entorno de ejecución que configuran los subprocesos para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998832"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="0db7d-103">Opciones de configuración del entorno de ejecución para subprocesos</span><span class="sxs-lookup"><span data-stu-id="0db7d-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="0db7d-104">Grupos de CPU</span><span class="sxs-lookup"><span data-stu-id="0db7d-104">CPU groups</span></span>

- <span data-ttu-id="0db7d-105">Configura si los subprocesos se distribuyen automáticamente entre los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="0db7d-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="0db7d-106">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="0db7d-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="0db7d-107">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="0db7d-107">Setting name</span></span> | <span data-ttu-id="0db7d-108">Valores</span><span class="sxs-lookup"><span data-stu-id="0db7d-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0db7d-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0db7d-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="0db7d-110">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-110">N/A</span></span> | <span data-ttu-id="0db7d-111">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-111">N/A</span></span> |
| <span data-ttu-id="0db7d-112">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="0db7d-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="0db7d-113">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0db7d-113">`0` - disabled</span></span><br/><span data-ttu-id="0db7d-114">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="0db7d-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="0db7d-115">Mínimo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="0db7d-115">Minimum threads</span></span>

- <span data-ttu-id="0db7d-116">Especifica el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0db7d-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="0db7d-117">Corresponde al método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0db7d-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="0db7d-118">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="0db7d-118">Setting name</span></span> | <span data-ttu-id="0db7d-119">Valores</span><span class="sxs-lookup"><span data-stu-id="0db7d-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0db7d-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0db7d-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="0db7d-121">Entero que representa el número mínimo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0db7d-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="0db7d-122">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="0db7d-122">**Environment variable**</span></span> | <span data-ttu-id="0db7d-123">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-123">N/A</span></span> | <span data-ttu-id="0db7d-124">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="0db7d-125">Máximo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="0db7d-125">Maximum threads</span></span>

- <span data-ttu-id="0db7d-126">Especifica el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0db7d-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="0db7d-127">Corresponde al método <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0db7d-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="0db7d-128">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="0db7d-128">Setting name</span></span> | <span data-ttu-id="0db7d-129">Valores</span><span class="sxs-lookup"><span data-stu-id="0db7d-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0db7d-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0db7d-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="0db7d-131">Entero que representa el número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0db7d-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="0db7d-132">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="0db7d-132">**Environment variable**</span></span> | <span data-ttu-id="0db7d-133">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-133">N/A</span></span> | <span data-ttu-id="0db7d-134">N/D</span><span class="sxs-lookup"><span data-stu-id="0db7d-134">N/A</span></span> |
