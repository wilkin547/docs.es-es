---
title: Valores de configuración de los subprocesos
description: Obtenga información sobre los valores del entorno de ejecución que configuran los subprocesos para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761933"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="239c8-103">Opciones de configuración del entorno de ejecución para subprocesos</span><span class="sxs-lookup"><span data-stu-id="239c8-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="239c8-104">Grupos de CPU</span><span class="sxs-lookup"><span data-stu-id="239c8-104">CPU groups</span></span>

- <span data-ttu-id="239c8-105">Configura si los subprocesos se distribuyen automáticamente entre los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="239c8-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="239c8-106">Si se omite esta configuración, los subprocesos no se distribuyen entre los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="239c8-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="239c8-107">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="239c8-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="239c8-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="239c8-108">Setting name</span></span> | <span data-ttu-id="239c8-109">Valores</span><span class="sxs-lookup"><span data-stu-id="239c8-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="239c8-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="239c8-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="239c8-111">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-111">N/A</span></span> | <span data-ttu-id="239c8-112">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-112">N/A</span></span> |
| <span data-ttu-id="239c8-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="239c8-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="239c8-114">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="239c8-114">`0` - disabled</span></span><br/><span data-ttu-id="239c8-115">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="239c8-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="239c8-116">Mínimo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="239c8-116">Minimum threads</span></span>

- <span data-ttu-id="239c8-117">Especifica el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="239c8-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="239c8-118">Corresponde al método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="239c8-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="239c8-119">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="239c8-119">Setting name</span></span> | <span data-ttu-id="239c8-120">Valores</span><span class="sxs-lookup"><span data-stu-id="239c8-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="239c8-121">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="239c8-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="239c8-122">Entero que representa el número mínimo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="239c8-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="239c8-123">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="239c8-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="239c8-124">Entero que representa el número mínimo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="239c8-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="239c8-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="239c8-125">**Environment variable**</span></span> | <span data-ttu-id="239c8-126">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-126">N/A</span></span> | <span data-ttu-id="239c8-127">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="239c8-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="239c8-128">Examples</span></span>

<span data-ttu-id="239c8-129">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="239c8-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="239c8-130">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="239c8-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="239c8-131">Máximo de subprocesos</span><span class="sxs-lookup"><span data-stu-id="239c8-131">Maximum threads</span></span>

- <span data-ttu-id="239c8-132">Especifica el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="239c8-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="239c8-133">Corresponde al método <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="239c8-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="239c8-134">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="239c8-134">Setting name</span></span> | <span data-ttu-id="239c8-135">Valores</span><span class="sxs-lookup"><span data-stu-id="239c8-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="239c8-136">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="239c8-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="239c8-137">Entero que representa el número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="239c8-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="239c8-138">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="239c8-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="239c8-139">Entero que representa el número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="239c8-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="239c8-140">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="239c8-140">**Environment variable**</span></span> | <span data-ttu-id="239c8-141">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-141">N/A</span></span> | <span data-ttu-id="239c8-142">N/D</span><span class="sxs-lookup"><span data-stu-id="239c8-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="239c8-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="239c8-143">Examples</span></span>

<span data-ttu-id="239c8-144">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="239c8-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="239c8-145">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="239c8-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
