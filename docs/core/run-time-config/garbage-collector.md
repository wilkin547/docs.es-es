---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: d7e3d040cd634eeb020beff806c60f834cc02585
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761985"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="f54a9-103">Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="f54a9-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="f54a9-104">Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f54a9-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="f54a9-105">Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="f54a9-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="f54a9-106">Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.</span><span class="sxs-lookup"><span data-stu-id="f54a9-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="f54a9-107">En esta página, la configuración se organiza en grupos.</span><span class="sxs-lookup"><span data-stu-id="f54a9-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="f54a9-108">La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.</span><span class="sxs-lookup"><span data-stu-id="f54a9-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f54a9-109">La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.</span><span class="sxs-lookup"><span data-stu-id="f54a9-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="f54a9-110">Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="f54a9-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="f54a9-111">Estos valores se omiten en esta página.</span><span class="sxs-lookup"><span data-stu-id="f54a9-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="f54a9-112">En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="f54a9-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="f54a9-113">Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="f54a9-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="f54a9-114">Tipos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="f54a9-114">Flavors of garbage collection</span></span>

<span data-ttu-id="f54a9-115">Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="f54a9-116">Para más información sobre la diferencia entre estos dos tipos, consulte [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="f54a9-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="f54a9-117">Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.</span><span class="sxs-lookup"><span data-stu-id="f54a9-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="f54a9-118">Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="f54a9-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="f54a9-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="f54a9-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="f54a9-120">Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="f54a9-121">Predeterminado: recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="f54a9-122">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f54a9-123">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-123">Setting name</span></span> | <span data-ttu-id="f54a9-124">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-124">Values</span></span> | <span data-ttu-id="f54a9-125">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="f54a9-127">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-127">`false` - workstation</span></span><br/><span data-ttu-id="f54a9-128">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-128">`true` - server</span></span> | <span data-ttu-id="f54a9-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-130">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="f54a9-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="f54a9-131">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-131">`false` - workstation</span></span><br/><span data-ttu-id="f54a9-132">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-132">`true` - server</span></span> | <span data-ttu-id="f54a9-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-134">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="f54a9-135">`0`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-135">`0` - workstation</span></span><br/><span data-ttu-id="f54a9-136">`1`: servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-136">`1` - server</span></span> | <span data-ttu-id="f54a9-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-138">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="f54a9-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="f54a9-140">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-140">`false` - workstation</span></span><br/><span data-ttu-id="f54a9-141">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="f54a9-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f54a9-142">Examples</span></span>

<span data-ttu-id="f54a9-143">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="f54a9-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="f54a9-144">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="f54a9-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="f54a9-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="f54a9-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="f54a9-146">Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).</span><span class="sxs-lookup"><span data-stu-id="f54a9-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="f54a9-147">Predeterminado: uso de GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f54a9-147">Default: Use background GC.</span></span> <span data-ttu-id="f54a9-148">Esto es equivalente a establecer el valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="f54a9-149">Para más información, consulte [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="f54a9-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="f54a9-150">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-150">Setting name</span></span> | <span data-ttu-id="f54a9-151">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-151">Values</span></span> | <span data-ttu-id="f54a9-152">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="f54a9-154">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f54a9-154">`true` - background GC</span></span><br/><span data-ttu-id="f54a9-155">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="f54a9-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-157">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="f54a9-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="f54a9-158">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f54a9-158">`true` - background GC</span></span><br/><span data-ttu-id="f54a9-159">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="f54a9-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-161">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="f54a9-162">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f54a9-162">`true` - background GC</span></span><br/><span data-ttu-id="f54a9-163">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-163">`false` - non-concurrent GC</span></span> | <span data-ttu-id="f54a9-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-165">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="f54a9-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="f54a9-167">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f54a9-167">`true` - background GC</span></span><br/><span data-ttu-id="f54a9-168">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="f54a9-169">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f54a9-169">Examples</span></span>

<span data-ttu-id="f54a9-170">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="f54a9-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="f54a9-171">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="f54a9-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="f54a9-172">Administración del uso de recursos</span><span class="sxs-lookup"><span data-stu-id="f54a9-172">Manage resource usage</span></span>

<span data-ttu-id="f54a9-173">Use los valores descritos en esta sección para administrar el uso del procesador y la memoria del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f54a9-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="f54a9-174">Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="f54a9-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="f54a9-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="f54a9-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="f54a9-176">Limita el número de montones creados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f54a9-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="f54a9-177">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f54a9-178">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está habilitada (el valor predeterminado) el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores.</span><span class="sxs-lookup"><span data-stu-id="f54a9-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="f54a9-179">(Use los valores [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) para especificar exactamente los procesadores entre los que se va a establecer afinidad).</span><span class="sxs-lookup"><span data-stu-id="f54a9-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="f54a9-180">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración limita el número de montones de GC.</span><span class="sxs-lookup"><span data-stu-id="f54a9-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="f54a9-181">Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="f54a9-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="f54a9-182">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-182">Setting name</span></span> | <span data-ttu-id="f54a9-183">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-183">Values</span></span> | <span data-ttu-id="f54a9-184">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="f54a9-186">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-186">*decimal value*</span></span> | <span data-ttu-id="f54a9-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-188">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="f54a9-189">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-189">*hexadecimal value*</span></span> | <span data-ttu-id="f54a9-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-191">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="f54a9-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="f54a9-193">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-193">*decimal value*</span></span> | <span data-ttu-id="f54a9-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f54a9-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f54a9-195">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-195">Example:</span></span>

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
> <span data-ttu-id="f54a9-196">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f54a9-197">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f54a9-198">Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="f54a9-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="f54a9-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="f54a9-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="f54a9-200">Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f54a9-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="f54a9-201">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="f54a9-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="f54a9-202">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f54a9-203">El valor es una máscara de bits que define los procesadores que están disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="f54a9-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="f54a9-204">Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria.</span><span class="sxs-lookup"><span data-stu-id="f54a9-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="f54a9-205">Esto especifica que se usarán los 10 primeros procesadores.</span><span class="sxs-lookup"><span data-stu-id="f54a9-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="f54a9-206">Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="f54a9-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="f54a9-207">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-207">Setting name</span></span> | <span data-ttu-id="f54a9-208">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-208">Values</span></span> | <span data-ttu-id="f54a9-209">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="f54a9-211">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-211">*decimal value*</span></span> | <span data-ttu-id="f54a9-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-213">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="f54a9-214">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-214">*hexadecimal value*</span></span> | <span data-ttu-id="f54a9-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-216">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="f54a9-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="f54a9-218">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-218">*decimal value*</span></span> | <span data-ttu-id="f54a9-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f54a9-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f54a9-220">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="f54a9-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="f54a9-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="f54a9-222">Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f54a9-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="f54a9-223">Este valor es similar a [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), salvo que permite especificar más de 64 procesadores.</span><span class="sxs-lookup"><span data-stu-id="f54a9-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="f54a9-224">En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="f54a9-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="f54a9-225">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="f54a9-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="f54a9-226">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f54a9-227">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="f54a9-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="f54a9-228">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-228">Setting name</span></span> | <span data-ttu-id="f54a9-229">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-229">Values</span></span> | <span data-ttu-id="f54a9-230">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="f54a9-232">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="f54a9-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="f54a9-233">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="f54a9-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="f54a9-234">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="f54a9-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="f54a9-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-236">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="f54a9-237">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="f54a9-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="f54a9-238">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="f54a9-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="f54a9-239">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="f54a9-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="f54a9-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-240">.NET Core 3.0</span></span> |

<span data-ttu-id="f54a9-241">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="f54a9-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="f54a9-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="f54a9-243">Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.</span><span class="sxs-lookup"><span data-stu-id="f54a9-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="f54a9-244">Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="f54a9-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="f54a9-245">El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.</span><span class="sxs-lookup"><span data-stu-id="f54a9-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="f54a9-246">Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f54a9-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="f54a9-247">Predeterminado: GC no se extiende por los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="f54a9-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="f54a9-248">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="f54a9-249">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="f54a9-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="f54a9-250">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-250">Setting name</span></span> | <span data-ttu-id="f54a9-251">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-251">Values</span></span> | <span data-ttu-id="f54a9-252">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="f54a9-254">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-254">N/A</span></span> | <span data-ttu-id="f54a9-255">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-255">N/A</span></span> | <span data-ttu-id="f54a9-256">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-256">N/A</span></span> |
| <span data-ttu-id="f54a9-257">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="f54a9-258">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-258">`0` - disabled</span></span><br/><span data-ttu-id="f54a9-259">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-259">`1` - enabled</span></span> | <span data-ttu-id="f54a9-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-261">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="f54a9-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="f54a9-263">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-263">`false` - disabled</span></span><br/><span data-ttu-id="f54a9-264">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="f54a9-265">Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="f54a9-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="f54a9-266">En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="f54a9-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="f54a9-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="f54a9-268">Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="f54a9-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="f54a9-269">El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta.</span><span class="sxs-lookup"><span data-stu-id="f54a9-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="f54a9-270">Se crea un montón para cada subproceso de GC.</span><span class="sxs-lookup"><span data-stu-id="f54a9-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="f54a9-271">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f54a9-272">Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="f54a9-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="f54a9-273">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f54a9-274">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-274">Setting name</span></span> | <span data-ttu-id="f54a9-275">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-275">Values</span></span> | <span data-ttu-id="f54a9-276">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="f54a9-278">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-278">`false` - affinitize</span></span><br/><span data-ttu-id="f54a9-279">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-279">`true` - don't affinitize</span></span> | <span data-ttu-id="f54a9-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-281">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="f54a9-282">`0`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-282">`0` - affinitize</span></span><br/><span data-ttu-id="f54a9-283">`1`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-283">`1` - don't affinitize</span></span> | <span data-ttu-id="f54a9-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-285">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="f54a9-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="f54a9-287">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-287">`false` - affinitize</span></span><br/><span data-ttu-id="f54a9-288">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="f54a9-288">`true` - don't affinitize</span></span> | <span data-ttu-id="f54a9-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f54a9-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f54a9-290">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="f54a9-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="f54a9-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="f54a9-292">Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.</span><span class="sxs-lookup"><span data-stu-id="f54a9-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="f54a9-293">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f54a9-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="f54a9-294">El valor predeterminado, que solo se aplica en ciertos casos, es el mayor de 20 MB o de 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="f54a9-295">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="f54a9-295">The default value applies if:</span></span>

  - <span data-ttu-id="f54a9-296">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="f54a9-297">No se ha establecido [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent).</span><span class="sxs-lookup"><span data-stu-id="f54a9-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="f54a9-298">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-298">Setting name</span></span> | <span data-ttu-id="f54a9-299">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-299">Values</span></span> | <span data-ttu-id="f54a9-300">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-301">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="f54a9-302">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-302">*decimal value*</span></span> | <span data-ttu-id="f54a9-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-304">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="f54a9-305">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-305">*hexadecimal value*</span></span> | <span data-ttu-id="f54a9-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-306">.NET Core 3.0</span></span> |

<span data-ttu-id="f54a9-307">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-307">Example:</span></span>

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
> <span data-ttu-id="f54a9-308">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f54a9-309">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f54a9-310">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="f54a9-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="f54a9-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="f54a9-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="f54a9-312">Especifica el uso del montón de GC permitido como porcentaje de la memoria física total.</span><span class="sxs-lookup"><span data-stu-id="f54a9-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="f54a9-313">Si también se establece [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), este valor se omite.</span><span class="sxs-lookup"><span data-stu-id="f54a9-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="f54a9-314">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f54a9-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="f54a9-315">Si el proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado, el porcentaje se calcula como un porcentaje de ese límite de memoria.</span><span class="sxs-lookup"><span data-stu-id="f54a9-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="f54a9-316">El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f54a9-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="f54a9-317">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="f54a9-317">The default value applies if:</span></span>

  - <span data-ttu-id="f54a9-318">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="f54a9-319">No se ha establecido [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit).</span><span class="sxs-lookup"><span data-stu-id="f54a9-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="f54a9-320">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-320">Setting name</span></span> | <span data-ttu-id="f54a9-321">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-321">Values</span></span> | <span data-ttu-id="f54a9-322">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="f54a9-324">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-324">*decimal value*</span></span> | <span data-ttu-id="f54a9-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="f54a9-326">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="f54a9-327">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-327">*hexadecimal value*</span></span> | <span data-ttu-id="f54a9-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-328">.NET Core 3.0</span></span> |

<span data-ttu-id="f54a9-329">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-329">Example:</span></span>

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
> <span data-ttu-id="f54a9-330">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f54a9-331">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f54a9-332">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="f54a9-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="f54a9-333">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="f54a9-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="f54a9-334">Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="f54a9-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="f54a9-335">Predeterminado: devolver los segmentos al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="f54a9-336">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f54a9-337">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-337">Setting name</span></span> | <span data-ttu-id="f54a9-338">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-338">Values</span></span> | <span data-ttu-id="f54a9-339">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-340">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="f54a9-341">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-341">`false` - release to OS</span></span><br/><span data-ttu-id="f54a9-342">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="f54a9-342">`true` - put on standby</span></span> | <span data-ttu-id="f54a9-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-344">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="f54a9-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="f54a9-345">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-345">`false` - release to OS</span></span><br/><span data-ttu-id="f54a9-346">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="f54a9-346">`true` - put on standby</span></span> | <span data-ttu-id="f54a9-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-348">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="f54a9-349">`0`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f54a9-349">`0` - release to OS</span></span><br/><span data-ttu-id="f54a9-350">`1`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="f54a9-350">`1` - put on standby</span></span> | <span data-ttu-id="f54a9-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="f54a9-352">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f54a9-352">Examples</span></span>

<span data-ttu-id="f54a9-353">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="f54a9-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="f54a9-354">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="f54a9-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="f54a9-355">Páginas grandes</span><span class="sxs-lookup"><span data-stu-id="f54a9-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="f54a9-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="f54a9-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="f54a9-357">Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.</span><span class="sxs-lookup"><span data-stu-id="f54a9-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="f54a9-358">Predeterminado: no utilizar páginas grandes cuando se establezca un límite rígido de montones.</span><span class="sxs-lookup"><span data-stu-id="f54a9-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="f54a9-359">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="f54a9-360">Se trata de un valor de configuración experimental.</span><span class="sxs-lookup"><span data-stu-id="f54a9-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="f54a9-361">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-361">Setting name</span></span> | <span data-ttu-id="f54a9-362">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-362">Values</span></span> | <span data-ttu-id="f54a9-363">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-364">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="f54a9-365">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-365">N/A</span></span> | <span data-ttu-id="f54a9-366">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-366">N/A</span></span> | <span data-ttu-id="f54a9-367">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-367">N/A</span></span> |
| <span data-ttu-id="f54a9-368">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="f54a9-369">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-369">`0` - disabled</span></span><br/><span data-ttu-id="f54a9-370">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-370">`1` - enabled</span></span> | <span data-ttu-id="f54a9-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="f54a9-372">Objetos grandes</span><span class="sxs-lookup"><span data-stu-id="f54a9-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="f54a9-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="f54a9-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="f54a9-374">Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.</span><span class="sxs-lookup"><span data-stu-id="f54a9-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="f54a9-375">Predeterminado: GC admite matrices de más de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="f54a9-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="f54a9-376">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="f54a9-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="f54a9-377">Esta opción puede quedar obsoleta en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="f54a9-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="f54a9-378">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-378">Setting name</span></span> | <span data-ttu-id="f54a9-379">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-379">Values</span></span> | <span data-ttu-id="f54a9-380">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-381">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="f54a9-382">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-382">N/A</span></span> | <span data-ttu-id="f54a9-383">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-383">N/A</span></span> | <span data-ttu-id="f54a9-384">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-384">N/A</span></span> |
| <span data-ttu-id="f54a9-385">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="f54a9-386">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-386">`1` - enabled</span></span><br/> <span data-ttu-id="f54a9-387">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-387">`0` - disabled</span></span> | <span data-ttu-id="f54a9-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-389">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="f54a9-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="f54a9-391">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-391">`1` - enabled</span></span><br/> <span data-ttu-id="f54a9-392">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-392">`0` - disabled</span></span> | <span data-ttu-id="f54a9-393">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f54a9-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="f54a9-394">Umbral del montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="f54a9-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="f54a9-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="f54a9-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="f54a9-396">Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="f54a9-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="f54a9-397">El valor predeterminado del umbral es de 85 000 bytes.</span><span class="sxs-lookup"><span data-stu-id="f54a9-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="f54a9-398">El valor que especifique debe ser mayor que el umbral predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f54a9-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="f54a9-399">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-399">Setting name</span></span> | <span data-ttu-id="f54a9-400">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-400">Values</span></span> | <span data-ttu-id="f54a9-401">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-402">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="f54a9-403">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-403">*decimal value*</span></span> | <span data-ttu-id="f54a9-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-405">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="f54a9-406">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-406">*hexadecimal value*</span></span> | <span data-ttu-id="f54a9-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="f54a9-408">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="f54a9-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f54a9-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="f54a9-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="f54a9-410">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="f54a9-410">*decimal value*</span></span> | <span data-ttu-id="f54a9-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f54a9-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="f54a9-412">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f54a9-412">Example:</span></span>

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
> <span data-ttu-id="f54a9-413">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f54a9-414">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f54a9-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f54a9-415">Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="f54a9-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="f54a9-416">GC independiente</span><span class="sxs-lookup"><span data-stu-id="f54a9-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="f54a9-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="f54a9-417">COMPlus_GCName</span></span>

- <span data-ttu-id="f54a9-418">Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.</span><span class="sxs-lookup"><span data-stu-id="f54a9-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="f54a9-419">Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="f54a9-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="f54a9-420">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f54a9-420">Setting name</span></span> | <span data-ttu-id="f54a9-421">Valores</span><span class="sxs-lookup"><span data-stu-id="f54a9-421">Values</span></span> | <span data-ttu-id="f54a9-422">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f54a9-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f54a9-423">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f54a9-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="f54a9-424">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-424">N/A</span></span> | <span data-ttu-id="f54a9-425">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-425">N/A</span></span> | <span data-ttu-id="f54a9-426">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a9-426">N/A</span></span> |
| <span data-ttu-id="f54a9-427">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f54a9-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="f54a9-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="f54a9-428">*string_path*</span></span> | <span data-ttu-id="f54a9-429">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f54a9-429">.NET Core 2.0</span></span> |
