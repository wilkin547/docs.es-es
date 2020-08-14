---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915997"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="1cb34-103">Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="1cb34-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="1cb34-104">Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1cb34-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="1cb34-105">Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb34-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="1cb34-106">Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.</span><span class="sxs-lookup"><span data-stu-id="1cb34-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="1cb34-107">En esta página, la configuración se organiza en grupos.</span><span class="sxs-lookup"><span data-stu-id="1cb34-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="1cb34-108">La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.</span><span class="sxs-lookup"><span data-stu-id="1cb34-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="1cb34-109">La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.</span><span class="sxs-lookup"><span data-stu-id="1cb34-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="1cb34-110">Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="1cb34-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="1cb34-111">Estos valores se omiten en esta página.</span><span class="sxs-lookup"><span data-stu-id="1cb34-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="1cb34-112">En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="1cb34-113">Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="1cb34-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="1cb34-114">Tipos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="1cb34-114">Flavors of garbage collection</span></span>

<span data-ttu-id="1cb34-115">Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="1cb34-116">Para más información sobre la diferencia entre estos dos tipos, consulte [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="1cb34-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="1cb34-117">Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.</span><span class="sxs-lookup"><span data-stu-id="1cb34-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="1cb34-118">Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="1cb34-118">Use the following settings to select flavors of garbage collection:</span></span>

- [<span data-ttu-id="1cb34-119">Recolección de elementos no utilizados de estación de trabajo y de servidor</span><span class="sxs-lookup"><span data-stu-id="1cb34-119">Workstation vs. server GC</span></span>](#workstation-vs-server)
- [<span data-ttu-id="1cb34-120">GC en segundo plano</span><span class="sxs-lookup"><span data-stu-id="1cb34-120">Background GC</span></span>](#background-gc)

### <a name="workstation-vs-server"></a><span data-ttu-id="1cb34-121">Estación de trabajo frente a servidor</span><span class="sxs-lookup"><span data-stu-id="1cb34-121">Workstation vs. server</span></span>

- <span data-ttu-id="1cb34-122">Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-122">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="1cb34-123">Predeterminado: recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-123">Default: Workstation garbage collection.</span></span> <span data-ttu-id="1cb34-124">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-124">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="1cb34-125">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-125">Setting name</span></span> | <span data-ttu-id="1cb34-126">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-126">Values</span></span> | <span data-ttu-id="1cb34-127">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-127">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-128">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="1cb34-129">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-129">`false` - workstation</span></span><br/><span data-ttu-id="1cb34-130">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-130">`true` - server</span></span> | <span data-ttu-id="1cb34-131">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-131">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-132">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="1cb34-132">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="1cb34-133">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-133">`false` - workstation</span></span><br/><span data-ttu-id="1cb34-134">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-134">`true` - server</span></span> | <span data-ttu-id="1cb34-135">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-135">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-136">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-136">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="1cb34-137">`0`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-137">`0` - workstation</span></span><br/><span data-ttu-id="1cb34-138">`1`: servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-138">`1` - server</span></span> | <span data-ttu-id="1cb34-139">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-139">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-140">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-140">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-141">GCServer</span><span class="sxs-lookup"><span data-stu-id="1cb34-141">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="1cb34-142">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-142">`false` - workstation</span></span><br/><span data-ttu-id="1cb34-143">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-143">`true` - server</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="1cb34-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1cb34-144">Examples</span></span>

<span data-ttu-id="1cb34-145">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="1cb34-145">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="1cb34-146">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="1cb34-146">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a><span data-ttu-id="1cb34-147">GC en segundo plano</span><span class="sxs-lookup"><span data-stu-id="1cb34-147">Background GC</span></span>

- <span data-ttu-id="1cb34-148">Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).</span><span class="sxs-lookup"><span data-stu-id="1cb34-148">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="1cb34-149">Predeterminado: uso de GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1cb34-149">Default: Use background GC.</span></span> <span data-ttu-id="1cb34-150">Esto es equivalente a establecer el valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-150">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="1cb34-151">Para más información, consulte [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="1cb34-151">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="1cb34-152">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-152">Setting name</span></span> | <span data-ttu-id="1cb34-153">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-153">Values</span></span> | <span data-ttu-id="1cb34-154">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-154">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-155">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-155">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="1cb34-156">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1cb34-156">`true` - background GC</span></span><br/><span data-ttu-id="1cb34-157">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="1cb34-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-159">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="1cb34-159">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="1cb34-160">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1cb34-160">`true` - background GC</span></span><br/><span data-ttu-id="1cb34-161">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="1cb34-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-163">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-163">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="1cb34-164">`1`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1cb34-164">`1` - background GC</span></span><br/><span data-ttu-id="1cb34-165">`0`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-165">`0` - non-concurrent GC</span></span> | <span data-ttu-id="1cb34-166">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-166">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-167">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-167">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-168">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="1cb34-168">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="1cb34-169">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1cb34-169">`true` - background GC</span></span><br/><span data-ttu-id="1cb34-170">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-170">`false` - non-concurrent GC</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="1cb34-171">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1cb34-171">Examples</span></span>

<span data-ttu-id="1cb34-172">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="1cb34-172">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="1cb34-173">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="1cb34-173">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="1cb34-174">Administración del uso de recursos</span><span class="sxs-lookup"><span data-stu-id="1cb34-174">Manage resource usage</span></span>

<span data-ttu-id="1cb34-175">Use la siguiente configuración para administrar el uso del procesador y la memoria del recolector de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="1cb34-175">Use the following settings to manage the garbage collector's memory and processor usage:</span></span>

- <span data-ttu-id="1cb34-176">[Affinitize](#affinitize) (Afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-176">[Affinitize](#affinitize)</span></span>
- <span data-ttu-id="1cb34-177">[Affinitize mask](#affinitize-mask) (Máscara de afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-177">[Affinitize mask](#affinitize-mask)</span></span>
- <span data-ttu-id="1cb34-178">[Affinitize ranges](#affinitize-ranges) (Intervalos de afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-178">[Affinitize ranges](#affinitize-ranges)</span></span>
- [<span data-ttu-id="1cb34-179">Grupos de CPU</span><span class="sxs-lookup"><span data-stu-id="1cb34-179">CPU groups</span></span>](#cpu-groups)
- <span data-ttu-id="1cb34-180">[Heap count](#heap-count) (Recuento de montones)</span><span class="sxs-lookup"><span data-stu-id="1cb34-180">[Heap count](#heap-count)</span></span>
- <span data-ttu-id="1cb34-181">[Heap limit](#heap-limit) (Límite del montón)</span><span class="sxs-lookup"><span data-stu-id="1cb34-181">[Heap limit](#heap-limit)</span></span>
- <span data-ttu-id="1cb34-182">[Heap limit percent](#heap-limit-percent) (Límite del montón (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-182">[Heap limit percent](#heap-limit-percent)</span></span>
- <span data-ttu-id="1cb34-183">[High memory percent](#high-memory-percent) (Uso de memoria alto (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-183">[High memory percent](#high-memory-percent)</span></span>
- [<span data-ttu-id="1cb34-184">Límites por cada montón de objetos</span><span class="sxs-lookup"><span data-stu-id="1cb34-184">Per-object-heap limits</span></span>](#per-object-heap-limits)
- <span data-ttu-id="1cb34-185">[Per-object-heap limit percents](#per-object-heap-limit-percents) (Límite por montón de objetos (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-185">[Per-object-heap limit percents](#per-object-heap-limit-percents)</span></span>
- <span data-ttu-id="1cb34-186">[Retain VM](#retain-vm) (Conservar VM)</span><span class="sxs-lookup"><span data-stu-id="1cb34-186">[Retain VM](#retain-vm)</span></span>

<span data-ttu-id="1cb34-187">Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="1cb34-187">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="heap-count"></a><span data-ttu-id="1cb34-188">Heap count (Recuento de montones)</span><span class="sxs-lookup"><span data-stu-id="1cb34-188">Heap count</span></span>

- <span data-ttu-id="1cb34-189">Limita el número de montones creados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1cb34-189">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="1cb34-190">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-190">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="1cb34-191">Si la [afinidad del procesador de GC](#affinitize) está habilitada (el valor predeterminado) el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores.</span><span class="sxs-lookup"><span data-stu-id="1cb34-191">If [GC processor affinity](#affinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="1cb34-192">(Use los valores [affinitize mask](#affinitize-mask) o [affinitize ranges](#affinitize-ranges) para especificar exactamente los procesadores entre los que se va a establecer afinidad).</span><span class="sxs-lookup"><span data-stu-id="1cb34-192">(Use the [affinitize mask](#affinitize-mask) or [affinitize ranges](#affinitize-ranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="1cb34-193">Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración limita el número de montones de GC.</span><span class="sxs-lookup"><span data-stu-id="1cb34-193">If [GC processor affinity](#affinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="1cb34-194">Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="1cb34-194">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="1cb34-195">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-195">Setting name</span></span> | <span data-ttu-id="1cb34-196">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-196">Values</span></span> | <span data-ttu-id="1cb34-197">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-197">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-198">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-198">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="1cb34-199">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-199">*decimal value*</span></span> | <span data-ttu-id="1cb34-200">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-200">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-201">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-201">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="1cb34-202">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-202">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-203">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-203">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-204">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-204">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-205">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="1cb34-205">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="1cb34-206">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-206">*decimal value*</span></span> | <span data-ttu-id="1cb34-207">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="1cb34-207">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="1cb34-208">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-208">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="1cb34-209">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-209">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-210">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-210">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-211">Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-211">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="affinitize-mask"></a><span data-ttu-id="1cb34-212">Affinitize mask (Máscara de afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-212">Affinitize mask</span></span>

- <span data-ttu-id="1cb34-213">Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1cb34-213">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="1cb34-214">Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="1cb34-214">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="1cb34-215">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-215">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="1cb34-216">El valor es una máscara de bits que define los procesadores que están disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="1cb34-216">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="1cb34-217">Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria.</span><span class="sxs-lookup"><span data-stu-id="1cb34-217">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="1cb34-218">Esto especifica que se usarán los 10 primeros procesadores.</span><span class="sxs-lookup"><span data-stu-id="1cb34-218">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="1cb34-219">Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="1cb34-219">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="1cb34-220">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-220">Setting name</span></span> | <span data-ttu-id="1cb34-221">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-221">Values</span></span> | <span data-ttu-id="1cb34-222">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-222">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-223">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-223">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="1cb34-224">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-224">*decimal value*</span></span> | <span data-ttu-id="1cb34-225">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-225">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-226">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-226">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="1cb34-227">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-227">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-228">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-228">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-229">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-229">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-230">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="1cb34-230">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="1cb34-231">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-231">*decimal value*</span></span> | <span data-ttu-id="1cb34-232">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="1cb34-232">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="1cb34-233">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-233">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a><span data-ttu-id="1cb34-234">Affinitize ranges (Intervalos de afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-234">Affinitize ranges</span></span>

- <span data-ttu-id="1cb34-235">Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1cb34-235">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="1cb34-236">Este valor es similar a [System.GC.HeapAffinitizeMask](#affinitize-mask), salvo que permite especificar más de 64 procesadores.</span><span class="sxs-lookup"><span data-stu-id="1cb34-236">This setting is similar to [System.GC.HeapAffinitizeMask](#affinitize-mask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="1cb34-237">En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="1cb34-237">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="1cb34-238">Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="1cb34-238">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="1cb34-239">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-239">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="1cb34-240">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="1cb34-240">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="1cb34-241">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-241">Setting name</span></span> | <span data-ttu-id="1cb34-242">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-242">Values</span></span> | <span data-ttu-id="1cb34-243">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-243">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-244">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-244">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="1cb34-245">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="1cb34-245">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="1cb34-246">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="1cb34-246">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="1cb34-247">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="1cb34-247">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="1cb34-248">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-248">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-249">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-249">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="1cb34-250">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="1cb34-250">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="1cb34-251">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="1cb34-251">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="1cb34-252">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="1cb34-252">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="1cb34-253">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-253">.NET Core 3.0</span></span> |

<span data-ttu-id="1cb34-254">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-254">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a><span data-ttu-id="1cb34-255">Grupos de CPU</span><span class="sxs-lookup"><span data-stu-id="1cb34-255">CPU groups</span></span>

- <span data-ttu-id="1cb34-256">Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.</span><span class="sxs-lookup"><span data-stu-id="1cb34-256">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="1cb34-257">Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="1cb34-257">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="1cb34-258">El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.</span><span class="sxs-lookup"><span data-stu-id="1cb34-258">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="1cb34-259">Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1cb34-259">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="1cb34-260">Predeterminado: GC no se extiende por los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="1cb34-260">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="1cb34-261">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-261">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="1cb34-262">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="1cb34-262">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="1cb34-263">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-263">Setting name</span></span> | <span data-ttu-id="1cb34-264">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-264">Values</span></span> | <span data-ttu-id="1cb34-265">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-265">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-266">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-266">**runtimeconfig.json**</span></span> | `System.GC.CpuGroup` | <span data-ttu-id="1cb34-267">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-267">`0` - disabled</span></span><br/><span data-ttu-id="1cb34-268">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-268">`1` - enabled</span></span> | <span data-ttu-id="1cb34-269">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-269">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-270">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-270">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="1cb34-271">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-271">`0` - disabled</span></span><br/><span data-ttu-id="1cb34-272">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-272">`1` - enabled</span></span> | <span data-ttu-id="1cb34-273">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-273">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-274">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-274">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-275">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="1cb34-275">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="1cb34-276">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-276">`false` - disabled</span></span><br/><span data-ttu-id="1cb34-277">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-277">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="1cb34-278">Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="1cb34-278">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="1cb34-279">En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-279">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="affinitize"></a><span data-ttu-id="1cb34-280">Affinitize (Afinidad)</span><span class="sxs-lookup"><span data-stu-id="1cb34-280">Affinitize</span></span>

- <span data-ttu-id="1cb34-281">Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="1cb34-281">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="1cb34-282">El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta.</span><span class="sxs-lookup"><span data-stu-id="1cb34-282">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="1cb34-283">Se crea un montón para cada subproceso de GC.</span><span class="sxs-lookup"><span data-stu-id="1cb34-283">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="1cb34-284">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-284">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="1cb34-285">Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="1cb34-285">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="1cb34-286">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-286">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="1cb34-287">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-287">Setting name</span></span> | <span data-ttu-id="1cb34-288">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-288">Values</span></span> | <span data-ttu-id="1cb34-289">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-289">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-290">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-290">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="1cb34-291">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-291">`false` - affinitize</span></span><br/><span data-ttu-id="1cb34-292">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-292">`true` - don't affinitize</span></span> | <span data-ttu-id="1cb34-293">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-293">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-294">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-294">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="1cb34-295">`0`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-295">`0` - affinitize</span></span><br/><span data-ttu-id="1cb34-296">`1`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-296">`1` - don't affinitize</span></span> | <span data-ttu-id="1cb34-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-298">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-298">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-299">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="1cb34-299">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="1cb34-300">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-300">`false` - affinitize</span></span><br/><span data-ttu-id="1cb34-301">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="1cb34-301">`true` - don't affinitize</span></span> | <span data-ttu-id="1cb34-302">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="1cb34-302">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="1cb34-303">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a><span data-ttu-id="1cb34-304">Heap limit (Límite del montón)</span><span class="sxs-lookup"><span data-stu-id="1cb34-304">Heap limit</span></span>

- <span data-ttu-id="1cb34-305">Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.</span><span class="sxs-lookup"><span data-stu-id="1cb34-305">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="1cb34-306">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1cb34-306">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="1cb34-307">Este valor se omite si se configuran los [límites por cada montón de objetos](#per-object-heap-limits).</span><span class="sxs-lookup"><span data-stu-id="1cb34-307">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="1cb34-308">El valor predeterminado, que solo se aplica en ciertos casos, es el mayor de 20 MB o de 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-308">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="1cb34-309">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="1cb34-309">The default value applies if:</span></span>

  - <span data-ttu-id="1cb34-310">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-310">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="1cb34-311">No se ha establecido [System.GC.HeapHardLimitPercent](#heap-limit-percent).</span><span class="sxs-lookup"><span data-stu-id="1cb34-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) is not set.</span></span>

| | <span data-ttu-id="1cb34-312">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-312">Setting name</span></span> | <span data-ttu-id="1cb34-313">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-313">Values</span></span> | <span data-ttu-id="1cb34-314">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-314">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-315">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-315">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="1cb34-316">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-316">*decimal value*</span></span> | <span data-ttu-id="1cb34-317">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-317">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-318">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-318">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="1cb34-319">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-319">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-320">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-320">.NET Core 3.0</span></span> |

<span data-ttu-id="1cb34-321">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-321">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="1cb34-322">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-322">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-323">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-323">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-324">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-324">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="heap-limit-percent"></a><span data-ttu-id="1cb34-325">Heap limit percent (Límite del montón (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-325">Heap limit percent</span></span>

- <span data-ttu-id="1cb34-326">Especifica el uso del montón de GC permitido como porcentaje de la memoria física total.</span><span class="sxs-lookup"><span data-stu-id="1cb34-326">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="1cb34-327">Si también se establece [System.GC.HeapHardLimit](#heap-limit), este valor se omite.</span><span class="sxs-lookup"><span data-stu-id="1cb34-327">If [System.GC.HeapHardLimit](#heap-limit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="1cb34-328">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1cb34-328">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="1cb34-329">Si el proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado, el porcentaje se calcula como un porcentaje de ese límite de memoria.</span><span class="sxs-lookup"><span data-stu-id="1cb34-329">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="1cb34-330">Este valor se omite si se configuran los [límites por cada montón de objetos](#per-object-heap-limits).</span><span class="sxs-lookup"><span data-stu-id="1cb34-330">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="1cb34-331">El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-331">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="1cb34-332">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="1cb34-332">The default value applies if:</span></span>

  - <span data-ttu-id="1cb34-333">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-333">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="1cb34-334">No se ha establecido [System.GC.HeapHardLimit](#heap-limit).</span><span class="sxs-lookup"><span data-stu-id="1cb34-334">[System.GC.HeapHardLimit](#heap-limit) is not set.</span></span>

| | <span data-ttu-id="1cb34-335">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-335">Setting name</span></span> | <span data-ttu-id="1cb34-336">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-336">Values</span></span> | <span data-ttu-id="1cb34-337">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-337">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-338">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-338">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="1cb34-339">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-339">*decimal value*</span></span> | <span data-ttu-id="1cb34-340">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-340">.NET Core 3.0</span></span> |
| <span data-ttu-id="1cb34-341">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-341">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="1cb34-342">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-342">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-343">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-343">.NET Core 3.0</span></span> |

<span data-ttu-id="1cb34-344">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-344">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="1cb34-345">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-345">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-346">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-346">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-347">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-347">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="1cb34-348">Límites por cada montón de objetos</span><span class="sxs-lookup"><span data-stu-id="1cb34-348">Per-object-heap limits</span></span>

<span data-ttu-id="1cb34-349">Puede especificar el uso de montones permitidos de la recolección de elementos no utilizados por cada objeto.</span><span class="sxs-lookup"><span data-stu-id="1cb34-349">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="1cb34-350">Los diferentes montones son el montón de objetos grandes (LOH), el montón de objetos pequeños (SOH) y el montón de objetos anclados (POH).</span><span class="sxs-lookup"><span data-stu-id="1cb34-350">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="1cb34-351">Si especifica un valor para `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` o `COMPLUS_GCHeapHardLimitPOH`, también debe especificar un valor para `COMPLUS_GCHeapHardLimitSOH` y `COMPLUS_GCHeapHardLimitLOH`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-351">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="1cb34-352">Si no lo hace, el runtime no se inicializará.</span><span class="sxs-lookup"><span data-stu-id="1cb34-352">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="1cb34-353">El valor predeterminado para `COMPLUS_GCHeapHardLimitPOH` es 0.</span><span class="sxs-lookup"><span data-stu-id="1cb34-353">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="1cb34-354">`COMPLUS_GCHeapHardLimitSOH` y `COMPLUS_GCHeapHardLimitLOH` no tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1cb34-354">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="1cb34-355">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-355">Setting name</span></span> | <span data-ttu-id="1cb34-356">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-356">Values</span></span> | <span data-ttu-id="1cb34-357">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-358">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOH` | <span data-ttu-id="1cb34-359">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-359">*decimal value*</span></span> | <span data-ttu-id="1cb34-360">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-360">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-361">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-361">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="1cb34-362">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-362">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-363">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-363">.NET 5.0</span></span> |

| | <span data-ttu-id="1cb34-364">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-364">Setting name</span></span> | <span data-ttu-id="1cb34-365">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-365">Values</span></span> | <span data-ttu-id="1cb34-366">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-366">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-367">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-367">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOH` | <span data-ttu-id="1cb34-368">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-368">*decimal value*</span></span> | <span data-ttu-id="1cb34-369">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-369">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-370">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-370">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="1cb34-371">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-371">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-372">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-372">.NET 5.0</span></span> |

| | <span data-ttu-id="1cb34-373">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-373">Setting name</span></span> | <span data-ttu-id="1cb34-374">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-374">Values</span></span> | <span data-ttu-id="1cb34-375">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-375">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-376">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-376">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOH` | <span data-ttu-id="1cb34-377">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-377">*decimal value*</span></span> | <span data-ttu-id="1cb34-378">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-378">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-379">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-379">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="1cb34-380">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-380">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-381">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-381">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="1cb34-382">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-382">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-383">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-383">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-384">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-384">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="per-object-heap-limit-percents"></a><span data-ttu-id="1cb34-385">Per-object-heap limit percents (Límite por montón de objetos (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-385">Per-object-heap limit percents</span></span>

<span data-ttu-id="1cb34-386">Puede especificar el uso de montones permitidos de la recolección de elementos no utilizados por cada objeto.</span><span class="sxs-lookup"><span data-stu-id="1cb34-386">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="1cb34-387">Los diferentes montones son el montón de objetos grandes (LOH), el montón de objetos pequeños (SOH) y el montón de objetos anclados (POH).</span><span class="sxs-lookup"><span data-stu-id="1cb34-387">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="1cb34-388">Si especifica un valor para `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` o `COMPLUS_GCHeapHardLimitPOHPercent`, también debe especificar un valor para `COMPLUS_GCHeapHardLimitSOHPercent` y `COMPLUS_GCHeapHardLimitLOHPercent`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-388">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="1cb34-389">Si no lo hace, el runtime no se inicializará.</span><span class="sxs-lookup"><span data-stu-id="1cb34-389">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="1cb34-390">Estos valores se omiten si se especifican `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` y `COMPLUS_GCHeapHardLimitPOH`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-390">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="1cb34-391">Un valor de 1 significa que la recolección de elementos no utilizados usa el 1 % de la memoria física total para ese montón de objetos.</span><span class="sxs-lookup"><span data-stu-id="1cb34-391">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="1cb34-392">Cada valor debe ser mayor que cero y menor o igual que 100.</span><span class="sxs-lookup"><span data-stu-id="1cb34-392">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="1cb34-393">Además, la suma de los tres valores de porcentaje debe ser inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="1cb34-393">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="1cb34-394">En caso contrario, el runtime no se inicializará.</span><span class="sxs-lookup"><span data-stu-id="1cb34-394">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="1cb34-395">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-395">Setting name</span></span> | <span data-ttu-id="1cb34-396">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-396">Values</span></span> | <span data-ttu-id="1cb34-397">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-397">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-398">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-398">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOHPercent` | <span data-ttu-id="1cb34-399">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-399">*decimal value*</span></span> | <span data-ttu-id="1cb34-400">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-400">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-401">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-401">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="1cb34-402">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-402">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-403">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-403">.NET 5.0</span></span> |

| | <span data-ttu-id="1cb34-404">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-404">Setting name</span></span> | <span data-ttu-id="1cb34-405">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-405">Values</span></span> | <span data-ttu-id="1cb34-406">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-406">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-407">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-407">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOHPercent` | <span data-ttu-id="1cb34-408">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-408">*decimal value*</span></span> | <span data-ttu-id="1cb34-409">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-409">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-410">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-410">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="1cb34-411">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-411">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-412">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-412">.NET 5.0</span></span> |

| | <span data-ttu-id="1cb34-413">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-413">Setting name</span></span> | <span data-ttu-id="1cb34-414">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-414">Values</span></span> | <span data-ttu-id="1cb34-415">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-416">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOHPercent` | <span data-ttu-id="1cb34-417">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-417">*decimal value*</span></span> | <span data-ttu-id="1cb34-418">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-418">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-419">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-419">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="1cb34-420">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-420">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-421">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-421">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="1cb34-422">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-422">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-423">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-423">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-424">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-424">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="high-memory-percent"></a><span data-ttu-id="1cb34-425">High memory percent (Uso de memoria alto (porcentaje))</span><span class="sxs-lookup"><span data-stu-id="1cb34-425">High memory percent</span></span>

<span data-ttu-id="1cb34-426">La carga de memoria se indica mediante el porcentaje de memoria física en uso.</span><span class="sxs-lookup"><span data-stu-id="1cb34-426">Memory load is indicated by the percentage of physical memory in use.</span></span> <span data-ttu-id="1cb34-427">De forma predeterminada, cuando la carga de memoria física alcanza el **90 %** , la recolección de elementos no utilizados se vuelve más agresiva a la hora de realizar recolecciones de elementos no utilizados completas y compactas para evitar la paginación.</span><span class="sxs-lookup"><span data-stu-id="1cb34-427">By default, when the physical memory load reaches **90%**, garbage collection becomes more aggressive about doing full, compacting garbage collections to avoid paging.</span></span> <span data-ttu-id="1cb34-428">Cuando la carga de memoria está por debajo del 90 %, la recolección de elementos no utilizados favorece las recolecciones en segundo plano de recolecciones de elementos no utilizados completas, que tienen pausas más cortas pero no reducen mucho el tamaño total del montón.</span><span class="sxs-lookup"><span data-stu-id="1cb34-428">When memory load is below 90%, GC favors background collections for full garbage collections, which have shorter pauses but don't reduce the total heap size by much.</span></span> <span data-ttu-id="1cb34-429">En los equipos con una cantidad de memoria considerable (80 GB o más), el umbral de carga predeterminado está entre el 90 % y el 97 %.</span><span class="sxs-lookup"><span data-stu-id="1cb34-429">On machines with a significant amount of memory (80GB or more), the default load threshold is between 90% and 97%.</span></span>

<span data-ttu-id="1cb34-430">El umbral de carga de uso de memoria alto se puede ajustar mediante la variable de entorno `COMPlus_GCHighMemPercent` o la opción de configuración JSON `System.GC.HighMemoryPercent`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-430">The high memory load threshold can be adjusted by the `COMPlus_GCHighMemPercent` environment variable or `System.GC.HighMemoryPercent` JSON configuration setting.</span></span> <span data-ttu-id="1cb34-431">Considere la posibilidad de ajustar el umbral si quiere controlar el tamaño del montón.</span><span class="sxs-lookup"><span data-stu-id="1cb34-431">Consider adjusting the threshold if you want to control heap size.</span></span> <span data-ttu-id="1cb34-432">Por ejemplo, en el proceso dominante de un equipo con 64 GB de memoria, es razonable que la recolección de elementos no utilizados empiece a reaccionar cuando haya un 10 % de memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="1cb34-432">For example, for the dominant process on a machine with 64GB of memory, it's reasonable for GC to start reacting when there's 10% of memory available.</span></span> <span data-ttu-id="1cb34-433">Pero en el caso de procesos más pequeños, por ejemplo, un proceso que solo usa 1 GB de memoria, la recolección de elementos no utilizados puede ejecutarse cómodamente con menos del 10 % de memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="1cb34-433">But for smaller processes, for example, a process that only consumes 1GB of memory, GC can comfortably run with less than 10% of memory available.</span></span> <span data-ttu-id="1cb34-434">En estos procesos más pequeños, considere la posibilidad de establecer un umbral más alto.</span><span class="sxs-lookup"><span data-stu-id="1cb34-434">For these smaller processes, consider setting the threshold higher.</span></span> <span data-ttu-id="1cb34-435">Por otro lado, si quiere que los procesos más grandes tengan tamaños de montón más pequeños (incluso cuando haya mucha memoria física disponible), la reducción de este umbral es una manera eficaz de que la recolección de elementos no utilizados reaccione antes para reducir el montón.</span><span class="sxs-lookup"><span data-stu-id="1cb34-435">On the other hand, if you want larger processes to have smaller heap sizes (even when there's plenty of physical memory available), lowering this threshold is an effective way for GC to react sooner to compact the heap down.</span></span>

> [!NOTE]
> <span data-ttu-id="1cb34-436">En el caso de los procesos que se ejecutan en un contenedor, la recolección de elementos no utilizados considera la memoria física según el límite del contenedor.</span><span class="sxs-lookup"><span data-stu-id="1cb34-436">For processes running in a container, GC considers the physical memory based on the container limit.</span></span>

| | <span data-ttu-id="1cb34-437">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-437">Setting name</span></span> | <span data-ttu-id="1cb34-438">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-438">Values</span></span> | <span data-ttu-id="1cb34-439">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-439">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-440">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-440">**runtimeconfig.json**</span></span> | `System.GC.HighMemoryPercent` | <span data-ttu-id="1cb34-441">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-441">*decimal value*</span></span> | <span data-ttu-id="1cb34-442">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-442">.NET 5.0</span></span> |
| <span data-ttu-id="1cb34-443">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-443">**Environment variable**</span></span> | `COMPlus_GCHighMemPercent` | <span data-ttu-id="1cb34-444">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-444">*hexadecimal value*</span></span> | |

> [!TIP]
> <span data-ttu-id="1cb34-445">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-445">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-446">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-446">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-447">Por ejemplo, para establecer el umbral de uso de memoria alto en el 75 %, los valores serían 75 para el archivo JSON y 0x4B o 4B para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-447">For example, to set the high memory threshold to 75%, the values would be 75 for the JSON file and 0x4B or 4B for the environment variable.</span></span>

### <a name="retain-vm"></a><span data-ttu-id="1cb34-448">Retain VM (Conservar VM)</span><span class="sxs-lookup"><span data-stu-id="1cb34-448">Retain VM</span></span>

- <span data-ttu-id="1cb34-449">Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="1cb34-449">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="1cb34-450">Predeterminado: devolver los segmentos al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-450">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="1cb34-451">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-451">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="1cb34-452">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-452">Setting name</span></span> | <span data-ttu-id="1cb34-453">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-453">Values</span></span> | <span data-ttu-id="1cb34-454">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-454">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-455">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-455">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="1cb34-456">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-456">`false` - release to OS</span></span><br/><span data-ttu-id="1cb34-457">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="1cb34-457">`true` - put on standby</span></span> | <span data-ttu-id="1cb34-458">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-458">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-459">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="1cb34-459">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="1cb34-460">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-460">`false` - release to OS</span></span><br/><span data-ttu-id="1cb34-461">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="1cb34-461">`true` - put on standby</span></span> | <span data-ttu-id="1cb34-462">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-462">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-463">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-463">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="1cb34-464">`0`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1cb34-464">`0` - release to OS</span></span><br/><span data-ttu-id="1cb34-465">`1`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="1cb34-465">`1` - put on standby</span></span> | <span data-ttu-id="1cb34-466">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-466">.NET Core 1.0</span></span> |

#### <a name="examples"></a><span data-ttu-id="1cb34-467">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1cb34-467">Examples</span></span>

<span data-ttu-id="1cb34-468">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="1cb34-468">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="1cb34-469">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="1cb34-469">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="1cb34-470">Páginas grandes</span><span class="sxs-lookup"><span data-stu-id="1cb34-470">Large pages</span></span>

- <span data-ttu-id="1cb34-471">Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.</span><span class="sxs-lookup"><span data-stu-id="1cb34-471">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="1cb34-472">Predeterminado: no utilizar páginas grandes cuando se establezca un límite rígido de montones.</span><span class="sxs-lookup"><span data-stu-id="1cb34-472">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="1cb34-473">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-473">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="1cb34-474">Se trata de un valor de configuración experimental.</span><span class="sxs-lookup"><span data-stu-id="1cb34-474">This is an experimental setting.</span></span>

| | <span data-ttu-id="1cb34-475">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-475">Setting name</span></span> | <span data-ttu-id="1cb34-476">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-476">Values</span></span> | <span data-ttu-id="1cb34-477">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-477">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-478">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-478">**runtimeconfig.json**</span></span> | <span data-ttu-id="1cb34-479">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-479">N/A</span></span> | <span data-ttu-id="1cb34-480">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-480">N/A</span></span> | <span data-ttu-id="1cb34-481">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-481">N/A</span></span> |
| <span data-ttu-id="1cb34-482">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-482">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="1cb34-483">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-483">`0` - disabled</span></span><br/><span data-ttu-id="1cb34-484">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-484">`1` - enabled</span></span> | <span data-ttu-id="1cb34-485">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-485">.NET Core 3.0</span></span> |

## <a name="allow-large-objects"></a><span data-ttu-id="1cb34-486">Allow large objects (Permitir objetos grandes)</span><span class="sxs-lookup"><span data-stu-id="1cb34-486">Allow large objects</span></span>

- <span data-ttu-id="1cb34-487">Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.</span><span class="sxs-lookup"><span data-stu-id="1cb34-487">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="1cb34-488">Predeterminado: GC admite matrices de más de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="1cb34-488">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="1cb34-489">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="1cb34-489">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="1cb34-490">Esta opción puede quedar obsoleta en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="1cb34-490">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="1cb34-491">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-491">Setting name</span></span> | <span data-ttu-id="1cb34-492">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-492">Values</span></span> | <span data-ttu-id="1cb34-493">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-493">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-494">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-494">**runtimeconfig.json**</span></span> | <span data-ttu-id="1cb34-495">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-495">N/A</span></span> | <span data-ttu-id="1cb34-496">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-496">N/A</span></span> | <span data-ttu-id="1cb34-497">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-497">N/A</span></span> |
| <span data-ttu-id="1cb34-498">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-498">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="1cb34-499">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-499">`1` - enabled</span></span><br/> <span data-ttu-id="1cb34-500">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-500">`0` - disabled</span></span> | <span data-ttu-id="1cb34-501">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-501">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-502">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-502">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-503">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="1cb34-503">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="1cb34-504">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-504">`1` - enabled</span></span><br/> <span data-ttu-id="1cb34-505">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-505">`0` - disabled</span></span> | <span data-ttu-id="1cb34-506">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1cb34-506">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="1cb34-507">Umbral del montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="1cb34-507">Large object heap threshold</span></span>

- <span data-ttu-id="1cb34-508">Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="1cb34-508">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="1cb34-509">El valor predeterminado del umbral es de 85 000 bytes.</span><span class="sxs-lookup"><span data-stu-id="1cb34-509">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="1cb34-510">El valor que especifique debe ser mayor que el umbral predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1cb34-510">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="1cb34-511">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-511">Setting name</span></span> | <span data-ttu-id="1cb34-512">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-512">Values</span></span> | <span data-ttu-id="1cb34-513">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-513">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-514">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-514">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="1cb34-515">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-515">*decimal value*</span></span> | <span data-ttu-id="1cb34-516">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-516">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-517">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-517">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="1cb34-518">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-518">*hexadecimal value*</span></span> | <span data-ttu-id="1cb34-519">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-519">.NET Core 1.0</span></span> |
| <span data-ttu-id="1cb34-520">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1cb34-520">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="1cb34-521">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="1cb34-521">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="1cb34-522">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="1cb34-522">*decimal value*</span></span> | <span data-ttu-id="1cb34-523">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="1cb34-523">.NET Framework 4.8</span></span> |

<span data-ttu-id="1cb34-524">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1cb34-524">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="1cb34-525">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-525">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="1cb34-526">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="1cb34-526">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="1cb34-527">Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1cb34-527">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="1cb34-528">GC independiente</span><span class="sxs-lookup"><span data-stu-id="1cb34-528">Standalone GC</span></span>

- <span data-ttu-id="1cb34-529">Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.</span><span class="sxs-lookup"><span data-stu-id="1cb34-529">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="1cb34-530">Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="1cb34-530">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="1cb34-531">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1cb34-531">Setting name</span></span> | <span data-ttu-id="1cb34-532">Valores</span><span class="sxs-lookup"><span data-stu-id="1cb34-532">Values</span></span> | <span data-ttu-id="1cb34-533">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1cb34-533">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="1cb34-534">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1cb34-534">**runtimeconfig.json**</span></span> | <span data-ttu-id="1cb34-535">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-535">N/A</span></span> | <span data-ttu-id="1cb34-536">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-536">N/A</span></span> | <span data-ttu-id="1cb34-537">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb34-537">N/A</span></span> |
| <span data-ttu-id="1cb34-538">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1cb34-538">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="1cb34-539">*string_path*</span><span class="sxs-lookup"><span data-stu-id="1cb34-539">*string_path*</span></span> | <span data-ttu-id="1cb34-540">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1cb34-540">.NET Core 2.0</span></span> |
