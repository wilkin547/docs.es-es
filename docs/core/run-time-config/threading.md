---
title: Valores de configuración de los subprocesos
description: Obtenga información sobre los valores del entorno de ejecución que configuran los subprocesos para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789849"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="5f81b-103">Opciones de configuración del entorno de ejecución para subprocesos</span><span class="sxs-lookup"><span data-stu-id="5f81b-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="5f81b-104">Grupos de CPU</span><span class="sxs-lookup"><span data-stu-id="5f81b-104">CPU groups</span></span>

- <span data-ttu-id="5f81b-105">Configura si los subprocesos se distribuyen automáticamente entre los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="5f81b-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="5f81b-106">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="5f81b-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="5f81b-107">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="5f81b-107">Setting name</span></span> | <span data-ttu-id="5f81b-108">Valores</span><span class="sxs-lookup"><span data-stu-id="5f81b-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5f81b-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5f81b-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="5f81b-110">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-110">N/A</span></span> | <span data-ttu-id="5f81b-111">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-111">N/A</span></span> |
| <span data-ttu-id="5f81b-112">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="5f81b-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="5f81b-113">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="5f81b-113">`0` - disabled</span></span><br/><span data-ttu-id="5f81b-114">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="5f81b-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="5f81b-115">Mínimo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="5f81b-115">Minimum threads</span></span>

- <span data-ttu-id="5f81b-116">Especifica el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5f81b-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="5f81b-117">Corresponde al método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f81b-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5f81b-118">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="5f81b-118">Setting name</span></span> | <span data-ttu-id="5f81b-119">Valores</span><span class="sxs-lookup"><span data-stu-id="5f81b-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5f81b-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5f81b-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="5f81b-121">Entero que representa el número mínimo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5f81b-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="5f81b-122">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="5f81b-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="5f81b-123">Entero que representa el número mínimo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5f81b-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="5f81b-124">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="5f81b-124">**Environment variable**</span></span> | <span data-ttu-id="5f81b-125">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-125">N/A</span></span> | <span data-ttu-id="5f81b-126">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="5f81b-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f81b-127">Examples</span></span>

<span data-ttu-id="5f81b-128">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="5f81b-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="5f81b-129">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="5f81b-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="5f81b-130">Máximo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="5f81b-130">Maximum threads</span></span>

- <span data-ttu-id="5f81b-131">Especifica el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5f81b-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="5f81b-132">Corresponde al método <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f81b-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5f81b-133">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="5f81b-133">Setting name</span></span> | <span data-ttu-id="5f81b-134">Valores</span><span class="sxs-lookup"><span data-stu-id="5f81b-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5f81b-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5f81b-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="5f81b-136">Entero que representa el número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5f81b-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="5f81b-137">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="5f81b-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="5f81b-138">Entero que representa el número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5f81b-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="5f81b-139">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="5f81b-139">**Environment variable**</span></span> | <span data-ttu-id="5f81b-140">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-140">N/A</span></span> | <span data-ttu-id="5f81b-141">N/D</span><span class="sxs-lookup"><span data-stu-id="5f81b-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="5f81b-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f81b-142">Examples</span></span>

<span data-ttu-id="5f81b-143">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="5f81b-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="5f81b-144">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="5f81b-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
