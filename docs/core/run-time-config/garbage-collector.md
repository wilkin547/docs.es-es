---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102871"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="ba742-103">Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="ba742-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="ba742-104">Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba742-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="ba742-105">Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="ba742-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="ba742-106">Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.</span><span class="sxs-lookup"><span data-stu-id="ba742-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="ba742-107">En esta página, la configuración se organiza en grupos.</span><span class="sxs-lookup"><span data-stu-id="ba742-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="ba742-108">La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.</span><span class="sxs-lookup"><span data-stu-id="ba742-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ba742-109">La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.</span><span class="sxs-lookup"><span data-stu-id="ba742-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="ba742-110">Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ba742-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="ba742-111">Estos valores se omiten en esta página.</span><span class="sxs-lookup"><span data-stu-id="ba742-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="ba742-112">En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="ba742-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="ba742-113">Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="ba742-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="ba742-114">Tipos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="ba742-114">Flavors of garbage collection</span></span>

<span data-ttu-id="ba742-115">Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="ba742-116">Para más información sobre la diferencia entre estos dos tipos, consulte [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="ba742-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="ba742-117">Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.</span><span class="sxs-lookup"><span data-stu-id="ba742-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="ba742-118">Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="ba742-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="ba742-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="ba742-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="ba742-120">Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="ba742-121">Predeterminado: recolección de elementos no utilizados de estación de trabajo (`false`).</span><span class="sxs-lookup"><span data-stu-id="ba742-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="ba742-122">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-122">Setting name</span></span> | <span data-ttu-id="ba742-123">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-123">Values</span></span> | <span data-ttu-id="ba742-124">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="ba742-126">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba742-126">`false` - workstation</span></span><br/><span data-ttu-id="ba742-127">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-127">`true` - server</span></span> | <span data-ttu-id="ba742-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-129">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="ba742-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="ba742-130">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba742-130">`false` - workstation</span></span><br/><span data-ttu-id="ba742-131">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-131">`true` - server</span></span> | <span data-ttu-id="ba742-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-133">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="ba742-134">`0`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba742-134">`0` - workstation</span></span><br/><span data-ttu-id="ba742-135">`1`: servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-135">`1` - server</span></span> | <span data-ttu-id="ba742-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-137">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="ba742-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="ba742-139">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba742-139">`false` - workstation</span></span><br/><span data-ttu-id="ba742-140">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="ba742-141">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ba742-141">Examples</span></span>

<span data-ttu-id="ba742-142">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="ba742-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="ba742-143">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="ba742-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="ba742-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="ba742-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="ba742-145">Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).</span><span class="sxs-lookup"><span data-stu-id="ba742-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="ba742-146">Predeterminado: habilitado (`true`).</span><span class="sxs-lookup"><span data-stu-id="ba742-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="ba742-147">Para más información, consulte [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="ba742-147">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="ba742-148">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-148">Setting name</span></span> | <span data-ttu-id="ba742-149">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-149">Values</span></span> | <span data-ttu-id="ba742-150">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="ba742-152">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ba742-152">`true` - background GC</span></span><br/><span data-ttu-id="ba742-153">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ba742-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="ba742-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-155">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="ba742-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="ba742-156">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ba742-156">`true` - background GC</span></span><br/><span data-ttu-id="ba742-157">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ba742-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="ba742-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-159">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="ba742-160">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ba742-160">`true` - background GC</span></span><br/><span data-ttu-id="ba742-161">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ba742-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="ba742-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-163">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="ba742-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="ba742-165">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ba742-165">`true` - background GC</span></span><br/><span data-ttu-id="ba742-166">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="ba742-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="ba742-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ba742-167">Examples</span></span>

<span data-ttu-id="ba742-168">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="ba742-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="ba742-169">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="ba742-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="ba742-170">Administración del uso de recursos</span><span class="sxs-lookup"><span data-stu-id="ba742-170">Manage resource usage</span></span>

<span data-ttu-id="ba742-171">Use los valores descritos en esta sección para administrar el uso del procesador y la memoria del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ba742-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="ba742-172">Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="ba742-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="ba742-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="ba742-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="ba742-174">Limita el número de montones creados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ba742-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="ba742-175">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ba742-176">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está habilitada (el valor predeterminado) el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores.</span><span class="sxs-lookup"><span data-stu-id="ba742-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="ba742-177">(Use los valores [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) para especificar exactamente los procesadores entre los que se va a establecer afinidad).</span><span class="sxs-lookup"><span data-stu-id="ba742-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="ba742-178">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración limita el número de montones de GC.</span><span class="sxs-lookup"><span data-stu-id="ba742-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="ba742-179">Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="ba742-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="ba742-180">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-180">Setting name</span></span> | <span data-ttu-id="ba742-181">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-181">Values</span></span> | <span data-ttu-id="ba742-182">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="ba742-184">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-184">*decimal value*</span></span> | <span data-ttu-id="ba742-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-186">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="ba742-187">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-187">*hexadecimal value*</span></span> | <span data-ttu-id="ba742-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-189">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="ba742-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="ba742-191">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-191">*decimal value*</span></span> | <span data-ttu-id="ba742-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ba742-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ba742-193">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-193">Example:</span></span>

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
> <span data-ttu-id="ba742-194">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ba742-195">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ba742-196">Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="ba742-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="ba742-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="ba742-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="ba742-198">Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ba742-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="ba742-199">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="ba742-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="ba742-200">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ba742-201">El valor es una máscara de bits que define los procesadores que están disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba742-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="ba742-202">Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria.</span><span class="sxs-lookup"><span data-stu-id="ba742-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="ba742-203">Esto especifica que se usarán los 10 primeros procesadores.</span><span class="sxs-lookup"><span data-stu-id="ba742-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="ba742-204">Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="ba742-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="ba742-205">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-205">Setting name</span></span> | <span data-ttu-id="ba742-206">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-206">Values</span></span> | <span data-ttu-id="ba742-207">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="ba742-209">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-209">*decimal value*</span></span> | <span data-ttu-id="ba742-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-211">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="ba742-212">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-212">*hexadecimal value*</span></span> | <span data-ttu-id="ba742-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-214">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="ba742-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="ba742-216">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-216">*decimal value*</span></span> | <span data-ttu-id="ba742-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ba742-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ba742-218">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="ba742-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="ba742-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="ba742-220">Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ba742-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="ba742-221">Este valor es similar a [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), salvo que permite especificar más de 64 procesadores.</span><span class="sxs-lookup"><span data-stu-id="ba742-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="ba742-222">En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="ba742-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="ba742-223">Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.</span><span class="sxs-lookup"><span data-stu-id="ba742-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="ba742-224">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ba742-225">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="ba742-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="ba742-226">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-226">Setting name</span></span> | <span data-ttu-id="ba742-227">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-227">Values</span></span> | <span data-ttu-id="ba742-228">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="ba742-230">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="ba742-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="ba742-231">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="ba742-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="ba742-232">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="ba742-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="ba742-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-234">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="ba742-235">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="ba742-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="ba742-236">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="ba742-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="ba742-237">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="ba742-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="ba742-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-238">.NET Core 3.0</span></span> |

<span data-ttu-id="ba742-239">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="ba742-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="ba742-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="ba742-241">Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.</span><span class="sxs-lookup"><span data-stu-id="ba742-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="ba742-242">Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="ba742-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="ba742-243">El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.</span><span class="sxs-lookup"><span data-stu-id="ba742-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="ba742-244">Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ba742-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="ba742-245">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="ba742-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="ba742-246">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="ba742-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="ba742-247">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-247">Setting name</span></span> | <span data-ttu-id="ba742-248">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-248">Values</span></span> | <span data-ttu-id="ba742-249">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="ba742-251">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-251">N/A</span></span> | <span data-ttu-id="ba742-252">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-252">N/A</span></span> | <span data-ttu-id="ba742-253">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-253">N/A</span></span> |
| <span data-ttu-id="ba742-254">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="ba742-255">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-255">`0` - disabled</span></span><br/><span data-ttu-id="ba742-256">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-256">`1` - enabled</span></span> | <span data-ttu-id="ba742-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-258">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="ba742-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="ba742-260">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-260">`false` - disabled</span></span><br/><span data-ttu-id="ba742-261">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="ba742-262">Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="ba742-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="ba742-263">En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.</span><span class="sxs-lookup"><span data-stu-id="ba742-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="ba742-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="ba742-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="ba742-265">Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="ba742-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="ba742-266">El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta.</span><span class="sxs-lookup"><span data-stu-id="ba742-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="ba742-267">Se crea un montón para cada subproceso de GC.</span><span class="sxs-lookup"><span data-stu-id="ba742-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="ba742-268">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="ba742-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ba742-269">Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores (`false`).</span><span class="sxs-lookup"><span data-stu-id="ba742-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="ba742-270">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-270">Setting name</span></span> | <span data-ttu-id="ba742-271">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-271">Values</span></span> | <span data-ttu-id="ba742-272">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="ba742-274">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-274">`false` - affinitize</span></span><br/><span data-ttu-id="ba742-275">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-275">`true` - don't affinitize</span></span> | <span data-ttu-id="ba742-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-277">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="ba742-278">`0`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-278">`0` - affinitize</span></span><br/><span data-ttu-id="ba742-279">`1`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-279">`1` - don't affinitize</span></span> | <span data-ttu-id="ba742-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-281">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="ba742-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="ba742-283">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-283">`false` - affinitize</span></span><br/><span data-ttu-id="ba742-284">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="ba742-284">`true` - don't affinitize</span></span> | <span data-ttu-id="ba742-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ba742-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ba742-286">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="ba742-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="ba742-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="ba742-288">Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.</span><span class="sxs-lookup"><span data-stu-id="ba742-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="ba742-289">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ba742-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="ba742-290">El valor predeterminado, que solo se aplica en ciertos casos, es el mayor de 20 MB o de 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="ba742-290">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="ba742-291">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="ba742-291">The default value applies if:</span></span>

  - <span data-ttu-id="ba742-292">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="ba742-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="ba742-293">No se ha establecido [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent).</span><span class="sxs-lookup"><span data-stu-id="ba742-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="ba742-294">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-294">Setting name</span></span> | <span data-ttu-id="ba742-295">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-295">Values</span></span> | <span data-ttu-id="ba742-296">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="ba742-298">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-298">*decimal value*</span></span> | <span data-ttu-id="ba742-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-300">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="ba742-301">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-301">*hexadecimal value*</span></span> | <span data-ttu-id="ba742-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-302">.NET Core 3.0</span></span> |

<span data-ttu-id="ba742-303">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-303">Example:</span></span>

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
> <span data-ttu-id="ba742-304">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ba742-305">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ba742-306">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="ba742-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="ba742-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="ba742-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="ba742-308">Especifica el uso del montón de GC permitido como porcentaje de la memoria física total.</span><span class="sxs-lookup"><span data-stu-id="ba742-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="ba742-309">Si también se establece [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), este valor se omite.</span><span class="sxs-lookup"><span data-stu-id="ba742-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="ba742-310">Esta configuración solo se aplica a los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ba742-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="ba742-311">Si el proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado, el porcentaje se calcula como un porcentaje de ese límite de memoria.</span><span class="sxs-lookup"><span data-stu-id="ba742-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="ba742-312">El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor.</span><span class="sxs-lookup"><span data-stu-id="ba742-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="ba742-313">El valor predeterminado se aplica si:</span><span class="sxs-lookup"><span data-stu-id="ba742-313">The default value applies if:</span></span>

  - <span data-ttu-id="ba742-314">El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="ba742-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="ba742-315">No se ha establecido [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit).</span><span class="sxs-lookup"><span data-stu-id="ba742-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="ba742-316">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-316">Setting name</span></span> | <span data-ttu-id="ba742-317">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-317">Values</span></span> | <span data-ttu-id="ba742-318">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="ba742-320">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-320">*decimal value*</span></span> | <span data-ttu-id="ba742-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="ba742-322">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="ba742-323">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-323">*hexadecimal value*</span></span> | <span data-ttu-id="ba742-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-324">.NET Core 3.0</span></span> |

<span data-ttu-id="ba742-325">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-325">Example:</span></span>

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
> <span data-ttu-id="ba742-326">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ba742-327">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ba742-328">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="ba742-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="ba742-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="ba742-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="ba742-330">Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="ba742-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="ba742-331">Predeterminado: devolver los segmentos al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="ba742-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="ba742-332">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-332">Setting name</span></span> | <span data-ttu-id="ba742-333">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-333">Values</span></span> | <span data-ttu-id="ba742-334">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="ba742-336">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ba742-336">`false` - release to OS</span></span><br/><span data-ttu-id="ba742-337">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="ba742-337">`true` - put on standby</span></span> | <span data-ttu-id="ba742-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-339">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="ba742-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="ba742-340">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ba742-340">`false` - release to OS</span></span><br/><span data-ttu-id="ba742-341">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="ba742-341">`true` - put on standby</span></span> | <span data-ttu-id="ba742-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-343">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="ba742-344">`0`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ba742-344">`0` - release to OS</span></span><br/><span data-ttu-id="ba742-345">`1`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="ba742-345">`1` - put on standby</span></span> | <span data-ttu-id="ba742-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="ba742-347">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ba742-347">Examples</span></span>

<span data-ttu-id="ba742-348">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="ba742-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="ba742-349">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="ba742-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="ba742-350">Páginas grandes</span><span class="sxs-lookup"><span data-stu-id="ba742-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="ba742-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="ba742-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="ba742-352">Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.</span><span class="sxs-lookup"><span data-stu-id="ba742-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="ba742-353">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="ba742-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="ba742-354">Se trata de un valor de configuración experimental.</span><span class="sxs-lookup"><span data-stu-id="ba742-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="ba742-355">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-355">Setting name</span></span> | <span data-ttu-id="ba742-356">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-356">Values</span></span> | <span data-ttu-id="ba742-357">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="ba742-359">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-359">N/A</span></span> | <span data-ttu-id="ba742-360">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-360">N/A</span></span> | <span data-ttu-id="ba742-361">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-361">N/A</span></span> |
| <span data-ttu-id="ba742-362">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="ba742-363">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-363">`0` - disabled</span></span><br/><span data-ttu-id="ba742-364">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-364">`1` - enabled</span></span> | <span data-ttu-id="ba742-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba742-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="ba742-366">Objetos grandes</span><span class="sxs-lookup"><span data-stu-id="ba742-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="ba742-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="ba742-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="ba742-368">Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.</span><span class="sxs-lookup"><span data-stu-id="ba742-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="ba742-369">Predeterminado: habilitado (`1`).</span><span class="sxs-lookup"><span data-stu-id="ba742-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="ba742-370">Esta opción puede quedar obsoleta en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="ba742-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="ba742-371">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-371">Setting name</span></span> | <span data-ttu-id="ba742-372">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-372">Values</span></span> | <span data-ttu-id="ba742-373">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="ba742-375">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-375">N/A</span></span> | <span data-ttu-id="ba742-376">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-376">N/A</span></span> | <span data-ttu-id="ba742-377">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-377">N/A</span></span> |
| <span data-ttu-id="ba742-378">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="ba742-379">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-379">`1` - enabled</span></span><br/> <span data-ttu-id="ba742-380">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-380">`0` - disabled</span></span> | <span data-ttu-id="ba742-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-382">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="ba742-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="ba742-384">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-384">`1` - enabled</span></span><br/> <span data-ttu-id="ba742-385">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba742-385">`0` - disabled</span></span> | <span data-ttu-id="ba742-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ba742-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="ba742-387">Umbral del montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="ba742-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="ba742-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="ba742-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="ba742-389">Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="ba742-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="ba742-390">El valor predeterminado del umbral es de 85 000 bytes.</span><span class="sxs-lookup"><span data-stu-id="ba742-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="ba742-391">El valor que especifique debe ser mayor que el umbral predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ba742-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="ba742-392">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-392">Setting name</span></span> | <span data-ttu-id="ba742-393">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-393">Values</span></span> | <span data-ttu-id="ba742-394">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="ba742-396">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-396">*decimal value*</span></span> | <span data-ttu-id="ba742-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-398">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="ba742-399">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-399">*hexadecimal value*</span></span> | <span data-ttu-id="ba742-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ba742-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="ba742-401">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="ba742-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ba742-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="ba742-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="ba742-403">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="ba742-403">*decimal value*</span></span> | <span data-ttu-id="ba742-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="ba742-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="ba742-405">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba742-405">Example:</span></span>

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
> <span data-ttu-id="ba742-406">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ba742-407">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba742-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ba742-408">Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="ba742-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="ba742-409">GC independiente</span><span class="sxs-lookup"><span data-stu-id="ba742-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="ba742-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="ba742-410">COMPlus_GCName</span></span>

- <span data-ttu-id="ba742-411">Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.</span><span class="sxs-lookup"><span data-stu-id="ba742-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="ba742-412">Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="ba742-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="ba742-413">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="ba742-413">Setting name</span></span> | <span data-ttu-id="ba742-414">Valores</span><span class="sxs-lookup"><span data-stu-id="ba742-414">Values</span></span> | <span data-ttu-id="ba742-415">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ba742-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ba742-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba742-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="ba742-417">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-417">N/A</span></span> | <span data-ttu-id="ba742-418">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-418">N/A</span></span> | <span data-ttu-id="ba742-419">N/D</span><span class="sxs-lookup"><span data-stu-id="ba742-419">N/A</span></span> |
| <span data-ttu-id="ba742-420">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="ba742-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="ba742-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="ba742-421">*string_path*</span></span> | <span data-ttu-id="ba742-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ba742-422">.NET Core 2.0</span></span> |
