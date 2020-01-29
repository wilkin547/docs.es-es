---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733520"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="fdc30-103">Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="fdc30-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="fdc30-104">Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fdc30-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="fdc30-105">Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="fdc30-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="fdc30-106">Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.</span><span class="sxs-lookup"><span data-stu-id="fdc30-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="fdc30-107">En esta página, la configuración se organiza en grupos.</span><span class="sxs-lookup"><span data-stu-id="fdc30-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="fdc30-108">La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.</span><span class="sxs-lookup"><span data-stu-id="fdc30-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fdc30-109">La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.</span><span class="sxs-lookup"><span data-stu-id="fdc30-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="fdc30-110">Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="fdc30-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="fdc30-111">Estos valores se omiten en esta página.</span><span class="sxs-lookup"><span data-stu-id="fdc30-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="fdc30-112">En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="fdc30-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="fdc30-113">Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="fdc30-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="fdc30-114">Tipos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="fdc30-114">Flavors of garbage collection</span></span>

<span data-ttu-id="fdc30-115">Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="fdc30-116">Para obtener más información sobre la diferencia entre estos dos tipos, vea [Fundamentos de la recolección de elementos no utilizados](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="fdc30-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="fdc30-117">Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.</span><span class="sxs-lookup"><span data-stu-id="fdc30-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="fdc30-118">Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="fdc30-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="fdc30-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="fdc30-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="fdc30-120">Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="fdc30-121">Predeterminado: recolección de elementos no utilizados de estación de trabajo (`false`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="fdc30-122">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-122">Setting name</span></span> | <span data-ttu-id="fdc30-123">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-123">Values</span></span> | <span data-ttu-id="fdc30-124">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="fdc30-126">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-126">`false` - workstation</span></span><br/><span data-ttu-id="fdc30-127">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-127">`true` - server</span></span> | <span data-ttu-id="fdc30-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-129">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="fdc30-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="fdc30-130">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-130">`false` - workstation</span></span><br/><span data-ttu-id="fdc30-131">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-131">`true` - server</span></span> | <span data-ttu-id="fdc30-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-133">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="fdc30-134">`0`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-134">`0` - workstation</span></span><br/><span data-ttu-id="fdc30-135">`1`: servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-135">`1` - server</span></span> | <span data-ttu-id="fdc30-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-137">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="fdc30-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="fdc30-139">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-139">`false` - workstation</span></span><br/><span data-ttu-id="fdc30-140">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="fdc30-141">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fdc30-141">Examples</span></span>

<span data-ttu-id="fdc30-142">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="fdc30-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="fdc30-143">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="fdc30-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="fdc30-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="fdc30-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="fdc30-145">Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).</span><span class="sxs-lookup"><span data-stu-id="fdc30-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="fdc30-146">Predeterminado: habilitado (`true`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="fdc30-147">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) y [Recolección de elementos no utilizados de servidor en segundo plano](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="fdc30-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="fdc30-148">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-148">Setting name</span></span> | <span data-ttu-id="fdc30-149">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-149">Values</span></span> | <span data-ttu-id="fdc30-150">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="fdc30-152">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fdc30-152">`true` - background GC</span></span><br/><span data-ttu-id="fdc30-153">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="fdc30-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-155">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="fdc30-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="fdc30-156">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fdc30-156">`true` - background GC</span></span><br/><span data-ttu-id="fdc30-157">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="fdc30-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-159">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="fdc30-160">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fdc30-160">`true` - background GC</span></span><br/><span data-ttu-id="fdc30-161">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="fdc30-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-163">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="fdc30-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="fdc30-165">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fdc30-165">`true` - background GC</span></span><br/><span data-ttu-id="fdc30-166">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="fdc30-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fdc30-167">Examples</span></span>

<span data-ttu-id="fdc30-168">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="fdc30-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="fdc30-169">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="fdc30-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="fdc30-170">Administración del uso de recursos</span><span class="sxs-lookup"><span data-stu-id="fdc30-170">Manage resource usage</span></span>

<span data-ttu-id="fdc30-171">Use los valores descritos en esta sección para administrar el uso del procesador y la memoria del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fdc30-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="fdc30-172">Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="fdc30-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="fdc30-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="fdc30-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="fdc30-174">Limita el número de montones creados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fdc30-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="fdc30-175">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="fdc30-176">Si la afinidad del procesador de GC está habilitada, que es el valor predeterminado de esta opción, el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores.</span><span class="sxs-lookup"><span data-stu-id="fdc30-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="fdc30-177">(Utilice la configuración pertinente para establecer la afinidad entre una máscara o entre rangos para especificar exactamente los procesadores entre los que se va a establecer afinidad).</span><span class="sxs-lookup"><span data-stu-id="fdc30-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="fdc30-178">Si está deshabilitada la afinidad del procesador de GC, esta configuración limita el número de montones de GC.</span><span class="sxs-lookup"><span data-stu-id="fdc30-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="fdc30-179">Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="fdc30-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="fdc30-180">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-180">Setting name</span></span> | <span data-ttu-id="fdc30-181">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-181">Values</span></span> | <span data-ttu-id="fdc30-182">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="fdc30-184">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-184">*decimal value*</span></span> | <span data-ttu-id="fdc30-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-186">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="fdc30-187">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-187">*hexadecimal value*</span></span> | <span data-ttu-id="fdc30-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-189">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="fdc30-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="fdc30-191">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-191">*decimal value*</span></span> | <span data-ttu-id="fdc30-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="fdc30-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="fdc30-193">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-193">Example:</span></span>

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
> <span data-ttu-id="fdc30-194">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="fdc30-195">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="fdc30-196">Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fdc30-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="fdc30-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="fdc30-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="fdc30-198">Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fdc30-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="fdc30-199">Si la afinidad del procesador está deshabilitada estableciendo `System.GC.NoAffinitize` en `true`, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="fdc30-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="fdc30-200">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="fdc30-201">El valor es una máscara de bits que define los procesadores que están disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="fdc30-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="fdc30-202">Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria.</span><span class="sxs-lookup"><span data-stu-id="fdc30-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="fdc30-203">Esto especifica que se usarán los 10 primeros procesadores.</span><span class="sxs-lookup"><span data-stu-id="fdc30-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="fdc30-204">Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="fdc30-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="fdc30-205">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-205">Setting name</span></span> | <span data-ttu-id="fdc30-206">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-206">Values</span></span> | <span data-ttu-id="fdc30-207">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="fdc30-209">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-209">*decimal value*</span></span> | <span data-ttu-id="fdc30-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-211">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="fdc30-212">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-212">*hexadecimal value*</span></span> | <span data-ttu-id="fdc30-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-214">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="fdc30-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="fdc30-216">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-216">*decimal value*</span></span> | <span data-ttu-id="fdc30-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="fdc30-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="fdc30-218">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="fdc30-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="fdc30-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="fdc30-220">Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fdc30-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="fdc30-221">Este valor es similar a `System.GC.HeapAffinitizeMask`, salvo que permite especificar más de 64 procesadores.</span><span class="sxs-lookup"><span data-stu-id="fdc30-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="fdc30-222">En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="fdc30-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="fdc30-223">Si la afinidad del procesador está deshabilitada estableciendo `System.GC.NoAffinitize` en `true`, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="fdc30-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="fdc30-224">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="fdc30-225">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="fdc30-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="fdc30-226">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-226">Setting name</span></span> | <span data-ttu-id="fdc30-227">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-227">Values</span></span> | <span data-ttu-id="fdc30-228">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="fdc30-230">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="fdc30-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="fdc30-231">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="fdc30-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="fdc30-232">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="fdc30-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="fdc30-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-234">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="fdc30-235">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="fdc30-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="fdc30-236">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="fdc30-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="fdc30-237">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="fdc30-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="fdc30-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-238">.NET Core 3.0</span></span> |

<span data-ttu-id="fdc30-239">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="fdc30-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="fdc30-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="fdc30-241">Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.</span><span class="sxs-lookup"><span data-stu-id="fdc30-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="fdc30-242">Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="fdc30-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="fdc30-243">El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.</span><span class="sxs-lookup"><span data-stu-id="fdc30-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="fdc30-244">Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fdc30-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="fdc30-245">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="fdc30-246">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="fdc30-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="fdc30-247">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-247">Setting name</span></span> | <span data-ttu-id="fdc30-248">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-248">Values</span></span> | <span data-ttu-id="fdc30-249">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="fdc30-251">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-251">N/A</span></span> | <span data-ttu-id="fdc30-252">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-252">N/A</span></span> | <span data-ttu-id="fdc30-253">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-253">N/A</span></span> |
| <span data-ttu-id="fdc30-254">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="fdc30-255">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-255">`0` - disabled</span></span><br/><span data-ttu-id="fdc30-256">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-256">`1` - enabled</span></span> | <span data-ttu-id="fdc30-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-258">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="fdc30-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="fdc30-260">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-260">`false` - disabled</span></span><br/><span data-ttu-id="fdc30-261">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="fdc30-262">Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="fdc30-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="fdc30-263">En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.</span><span class="sxs-lookup"><span data-stu-id="fdc30-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="fdc30-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="fdc30-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="fdc30-265">Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="fdc30-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="fdc30-266">El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta.</span><span class="sxs-lookup"><span data-stu-id="fdc30-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="fdc30-267">Se crea un montón para cada subproceso de GC.</span><span class="sxs-lookup"><span data-stu-id="fdc30-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="fdc30-268">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="fdc30-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="fdc30-269">Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores (`false`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="fdc30-270">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-270">Setting name</span></span> | <span data-ttu-id="fdc30-271">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-271">Values</span></span> | <span data-ttu-id="fdc30-272">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="fdc30-274">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-274">`false` - affinitize</span></span><br/><span data-ttu-id="fdc30-275">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-275">`true` - don't affinitize</span></span> | <span data-ttu-id="fdc30-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-277">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="fdc30-278">`0`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-278">`0` - affinitize</span></span><br/><span data-ttu-id="fdc30-279">`1`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-279">`1` - don't affinitize</span></span> | <span data-ttu-id="fdc30-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-281">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="fdc30-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="fdc30-283">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-283">`false` - affinitize</span></span><br/><span data-ttu-id="fdc30-284">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="fdc30-284">`true` - don't affinitize</span></span> | <span data-ttu-id="fdc30-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="fdc30-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="fdc30-286">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="fdc30-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="fdc30-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="fdc30-288">Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.</span><span class="sxs-lookup"><span data-stu-id="fdc30-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="fdc30-289">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-289">Setting name</span></span> | <span data-ttu-id="fdc30-290">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-290">Values</span></span> | <span data-ttu-id="fdc30-291">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="fdc30-293">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-293">*decimal value*</span></span> | <span data-ttu-id="fdc30-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-295">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="fdc30-296">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-296">*hexadecimal value*</span></span> | <span data-ttu-id="fdc30-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-297">.NET Core 3.0</span></span> |

<span data-ttu-id="fdc30-298">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-298">Example:</span></span>

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
> <span data-ttu-id="fdc30-299">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="fdc30-300">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="fdc30-301">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fdc30-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="fdc30-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="fdc30-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="fdc30-303">Especifica el uso del montón de GC como porcentaje de la memoria total.</span><span class="sxs-lookup"><span data-stu-id="fdc30-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="fdc30-304">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-304">Setting name</span></span> | <span data-ttu-id="fdc30-305">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-305">Values</span></span> | <span data-ttu-id="fdc30-306">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="fdc30-308">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-308">*decimal value*</span></span> | <span data-ttu-id="fdc30-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="fdc30-310">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="fdc30-311">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-311">*hexadecimal value*</span></span> | <span data-ttu-id="fdc30-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-312">.NET Core 3.0</span></span> |

<span data-ttu-id="fdc30-313">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-313">Example:</span></span>

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
> <span data-ttu-id="fdc30-314">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="fdc30-315">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="fdc30-316">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fdc30-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="fdc30-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="fdc30-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="fdc30-318">Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="fdc30-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="fdc30-319">Predeterminado: devolver los segmentos al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="fdc30-320">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-320">Setting name</span></span> | <span data-ttu-id="fdc30-321">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-321">Values</span></span> | <span data-ttu-id="fdc30-322">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="fdc30-324">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-324">`false` - release to OS</span></span><br/><span data-ttu-id="fdc30-325">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="fdc30-325">`true` - put on standby</span></span> | <span data-ttu-id="fdc30-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-327">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="fdc30-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="fdc30-328">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-328">`false` - release to OS</span></span><br/><span data-ttu-id="fdc30-329">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="fdc30-329">`true` - put on standby</span></span> | <span data-ttu-id="fdc30-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-331">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="fdc30-332">`0`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fdc30-332">`0` - release to OS</span></span><br/><span data-ttu-id="fdc30-333">`1`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="fdc30-333">`1` - put on standby</span></span> | <span data-ttu-id="fdc30-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="fdc30-335">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fdc30-335">Examples</span></span>

<span data-ttu-id="fdc30-336">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="fdc30-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="fdc30-337">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="fdc30-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="fdc30-338">Páginas grandes</span><span class="sxs-lookup"><span data-stu-id="fdc30-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="fdc30-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="fdc30-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="fdc30-340">Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.</span><span class="sxs-lookup"><span data-stu-id="fdc30-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="fdc30-341">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="fdc30-342">Se trata de un valor de configuración experimental.</span><span class="sxs-lookup"><span data-stu-id="fdc30-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="fdc30-343">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-343">Setting name</span></span> | <span data-ttu-id="fdc30-344">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-344">Values</span></span> | <span data-ttu-id="fdc30-345">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="fdc30-347">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-347">N/A</span></span> | <span data-ttu-id="fdc30-348">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-348">N/A</span></span> | <span data-ttu-id="fdc30-349">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-349">N/A</span></span> |
| <span data-ttu-id="fdc30-350">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="fdc30-351">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-351">`0` - disabled</span></span><br/><span data-ttu-id="fdc30-352">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-352">`1` - enabled</span></span> | <span data-ttu-id="fdc30-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="fdc30-354">Objetos grandes</span><span class="sxs-lookup"><span data-stu-id="fdc30-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="fdc30-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="fdc30-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="fdc30-356">Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.</span><span class="sxs-lookup"><span data-stu-id="fdc30-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="fdc30-357">Predeterminado: habilitado (`1`).</span><span class="sxs-lookup"><span data-stu-id="fdc30-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="fdc30-358">Esta opción puede quedar obsoleta en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="fdc30-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="fdc30-359">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-359">Setting name</span></span> | <span data-ttu-id="fdc30-360">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-360">Values</span></span> | <span data-ttu-id="fdc30-361">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="fdc30-363">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-363">N/A</span></span> | <span data-ttu-id="fdc30-364">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-364">N/A</span></span> | <span data-ttu-id="fdc30-365">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-365">N/A</span></span> |
| <span data-ttu-id="fdc30-366">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="fdc30-367">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-367">`1` - enabled</span></span><br/> <span data-ttu-id="fdc30-368">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-368">`0` - disabled</span></span> | <span data-ttu-id="fdc30-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-370">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="fdc30-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="fdc30-372">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-372">`1` - enabled</span></span><br/> <span data-ttu-id="fdc30-373">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-373">`0` - disabled</span></span> | <span data-ttu-id="fdc30-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="fdc30-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="fdc30-375">Umbral del montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="fdc30-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="fdc30-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="fdc30-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="fdc30-377">Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="fdc30-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="fdc30-378">El valor predeterminado del umbral es de 85 000 bytes.</span><span class="sxs-lookup"><span data-stu-id="fdc30-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="fdc30-379">El valor que especifique debe ser mayor que el umbral predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fdc30-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="fdc30-380">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-380">Setting name</span></span> | <span data-ttu-id="fdc30-381">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-381">Values</span></span> | <span data-ttu-id="fdc30-382">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="fdc30-384">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-384">*decimal value*</span></span> | <span data-ttu-id="fdc30-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-386">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="fdc30-387">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-387">*hexadecimal value*</span></span> | <span data-ttu-id="fdc30-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="fdc30-389">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fdc30-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="fdc30-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="fdc30-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="fdc30-391">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="fdc30-391">*decimal value*</span></span> | <span data-ttu-id="fdc30-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="fdc30-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="fdc30-393">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdc30-393">Example:</span></span>

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
> <span data-ttu-id="fdc30-394">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="fdc30-395">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fdc30-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="fdc30-396">Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fdc30-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="fdc30-397">GC independiente</span><span class="sxs-lookup"><span data-stu-id="fdc30-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="fdc30-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="fdc30-398">COMPlus_GCName</span></span>

- <span data-ttu-id="fdc30-399">Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.</span><span class="sxs-lookup"><span data-stu-id="fdc30-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="fdc30-400">Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="fdc30-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="fdc30-401">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="fdc30-401">Setting name</span></span> | <span data-ttu-id="fdc30-402">Valores</span><span class="sxs-lookup"><span data-stu-id="fdc30-402">Values</span></span> | <span data-ttu-id="fdc30-403">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fdc30-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="fdc30-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fdc30-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="fdc30-405">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-405">N/A</span></span> | <span data-ttu-id="fdc30-406">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-406">N/A</span></span> | <span data-ttu-id="fdc30-407">N/D</span><span class="sxs-lookup"><span data-stu-id="fdc30-407">N/A</span></span> |
| <span data-ttu-id="fdc30-408">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="fdc30-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="fdc30-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="fdc30-409">*string_path*</span></span> | <span data-ttu-id="fdc30-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fdc30-410">.NET Core 2.0</span></span> |
