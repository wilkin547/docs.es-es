---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900096"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="3c097-103">Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="3c097-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="3c097-104">Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3c097-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="3c097-105">Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="3c097-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="3c097-106">Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.</span><span class="sxs-lookup"><span data-stu-id="3c097-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="3c097-107">En esta página, la configuración se organiza en grupos.</span><span class="sxs-lookup"><span data-stu-id="3c097-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="3c097-108">La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.</span><span class="sxs-lookup"><span data-stu-id="3c097-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="3c097-109">La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.</span><span class="sxs-lookup"><span data-stu-id="3c097-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="3c097-110">Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3c097-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="3c097-111">Estos valores se omiten en esta página.</span><span class="sxs-lookup"><span data-stu-id="3c097-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="3c097-112">En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="3c097-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="3c097-113">Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".</span><span class="sxs-lookup"><span data-stu-id="3c097-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="3c097-114">Tipos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="3c097-114">Flavors of garbage collection</span></span>

<span data-ttu-id="3c097-115">Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="3c097-116">Para obtener más información sobre la diferencia entre estos dos tipos, vea [Fundamentos de la recolección de elementos no utilizados](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="3c097-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="3c097-117">Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.</span><span class="sxs-lookup"><span data-stu-id="3c097-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="3c097-118">Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="3c097-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="3c097-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="3c097-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="3c097-120">Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="3c097-121">Predeterminado: recolección de elementos no utilizados de estación de trabajo (`false`).</span><span class="sxs-lookup"><span data-stu-id="3c097-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="3c097-122">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-122">Setting name</span></span> | <span data-ttu-id="3c097-123">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-123">Values</span></span> | <span data-ttu-id="3c097-124">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="3c097-126">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c097-126">`false` - workstation</span></span><br/><span data-ttu-id="3c097-127">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-127">`true` - server</span></span> | <span data-ttu-id="3c097-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-129">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="3c097-130">`0`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c097-130">`0` - workstation</span></span><br/><span data-ttu-id="3c097-131">`1`: servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-131">`1` - server</span></span> | <span data-ttu-id="3c097-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-133">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="3c097-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="3c097-135">`false`: estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c097-135">`false` - workstation</span></span><br/><span data-ttu-id="3c097-136">`true`: servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-136">`true` - server</span></span> |  |

<span data-ttu-id="3c097-137">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="3c097-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="3c097-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="3c097-139">Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).</span><span class="sxs-lookup"><span data-stu-id="3c097-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="3c097-140">Predeterminado: habilitado (`true`).</span><span class="sxs-lookup"><span data-stu-id="3c097-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="3c097-141">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) y [Recolección de elementos no utilizados de servidor en segundo plano](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="3c097-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="3c097-142">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-142">Setting name</span></span> | <span data-ttu-id="3c097-143">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-143">Values</span></span> | <span data-ttu-id="3c097-144">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="3c097-146">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c097-146">`true` - background GC</span></span><br/><span data-ttu-id="3c097-147">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="3c097-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="3c097-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-149">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="3c097-150">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c097-150">`true` - background GC</span></span><br/><span data-ttu-id="3c097-151">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="3c097-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="3c097-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-153">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="3c097-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="3c097-155">`true`: GC en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c097-155">`true` - background GC</span></span><br/><span data-ttu-id="3c097-156">`false`: GC no simultáneo.</span><span class="sxs-lookup"><span data-stu-id="3c097-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="3c097-157">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="3c097-158">Administración del uso de recursos</span><span class="sxs-lookup"><span data-stu-id="3c097-158">Manage resource usage</span></span>

<span data-ttu-id="3c097-159">Use los valores descritos en esta sección para administrar el uso del procesador y la memoria del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3c097-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="3c097-160">Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="3c097-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="3c097-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="3c097-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="3c097-162">Limita el número de montones creados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3c097-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="3c097-163">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="3c097-164">Si la afinidad del procesador de GC está habilitada, que es el valor predeterminado de esta opción, el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores.</span><span class="sxs-lookup"><span data-stu-id="3c097-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="3c097-165">(Utilice la configuración pertinente para establecer la afinidad entre una máscara o entre rangos para especificar exactamente los procesadores entre los que se va a establecer afinidad).</span><span class="sxs-lookup"><span data-stu-id="3c097-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="3c097-166">Si está deshabilitada la afinidad del procesador de GC, esta configuración limita el número de montones de GC.</span><span class="sxs-lookup"><span data-stu-id="3c097-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="3c097-167">Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="3c097-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="3c097-168">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-168">Setting name</span></span> | <span data-ttu-id="3c097-169">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-169">Values</span></span> | <span data-ttu-id="3c097-170">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="3c097-172">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-172">*decimal value*</span></span> | <span data-ttu-id="3c097-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-174">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="3c097-175">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-175">*hexadecimal value*</span></span> | <span data-ttu-id="3c097-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-177">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="3c097-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="3c097-179">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-179">*decimal value*</span></span> | <span data-ttu-id="3c097-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3c097-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="3c097-181">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-181">Example:</span></span>

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
> <span data-ttu-id="3c097-182">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="3c097-183">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="3c097-184">Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="3c097-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="3c097-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="3c097-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="3c097-186">Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3c097-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="3c097-187">Si la afinidad del procesador está deshabilitada estableciendo `System.GC.NoAffinitize` en `true`, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="3c097-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="3c097-188">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="3c097-189">El valor es una máscara de bits que define los procesadores que están disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="3c097-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="3c097-190">Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria.</span><span class="sxs-lookup"><span data-stu-id="3c097-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="3c097-191">Esto especifica que se usarán los 10 primeros procesadores.</span><span class="sxs-lookup"><span data-stu-id="3c097-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="3c097-192">Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="3c097-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="3c097-193">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-193">Setting name</span></span> | <span data-ttu-id="3c097-194">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-194">Values</span></span> | <span data-ttu-id="3c097-195">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="3c097-197">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-197">*decimal value*</span></span> | <span data-ttu-id="3c097-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-199">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="3c097-200">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-200">*hexadecimal value*</span></span> | <span data-ttu-id="3c097-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-202">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="3c097-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="3c097-204">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-204">*decimal value*</span></span> | <span data-ttu-id="3c097-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3c097-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="3c097-206">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="3c097-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="3c097-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="3c097-208">Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3c097-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="3c097-209">Este valor es similar a `System.GC.HeapAffinitizeMask`, salvo que permite especificar más de 64 procesadores.</span><span class="sxs-lookup"><span data-stu-id="3c097-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="3c097-210">En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="3c097-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="3c097-211">Si la afinidad del procesador está deshabilitada estableciendo `System.GC.NoAffinitize` en `true`, esta configuración se omite.</span><span class="sxs-lookup"><span data-stu-id="3c097-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="3c097-212">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="3c097-213">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="3c097-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="3c097-214">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-214">Setting name</span></span> | <span data-ttu-id="3c097-215">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-215">Values</span></span> | <span data-ttu-id="3c097-216">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="3c097-218">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="3c097-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="3c097-219">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="3c097-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="3c097-220">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="3c097-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="3c097-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-222">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="3c097-223">Lista separada por comas de números de procesador o rangos de números de procesador.</span><span class="sxs-lookup"><span data-stu-id="3c097-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="3c097-224">Ejemplo de Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="3c097-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="3c097-225">Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="3c097-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="3c097-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-226">.NET Core 3.0</span></span> |

<span data-ttu-id="3c097-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="3c097-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="3c097-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="3c097-229">Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.</span><span class="sxs-lookup"><span data-stu-id="3c097-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="3c097-230">Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="3c097-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="3c097-231">El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.</span><span class="sxs-lookup"><span data-stu-id="3c097-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="3c097-232">Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3c097-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="3c097-233">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="3c097-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="3c097-234">Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).</span><span class="sxs-lookup"><span data-stu-id="3c097-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="3c097-235">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-235">Setting name</span></span> | <span data-ttu-id="3c097-236">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-236">Values</span></span> | <span data-ttu-id="3c097-237">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="3c097-239">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-239">N/A</span></span> | <span data-ttu-id="3c097-240">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-240">N/A</span></span> | <span data-ttu-id="3c097-241">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-241">N/A</span></span> |
| <span data-ttu-id="3c097-242">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="3c097-243">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-243">`0` - disabled</span></span><br/><span data-ttu-id="3c097-244">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-244">`1` - enabled</span></span> | <span data-ttu-id="3c097-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-246">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="3c097-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="3c097-248">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-248">`false` - disabled</span></span><br/><span data-ttu-id="3c097-249">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="3c097-250">Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="3c097-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="3c097-251">En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.</span><span class="sxs-lookup"><span data-stu-id="3c097-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="3c097-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="3c097-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="3c097-253">Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores.</span><span class="sxs-lookup"><span data-stu-id="3c097-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="3c097-254">El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta.</span><span class="sxs-lookup"><span data-stu-id="3c097-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="3c097-255">Se crea un montón para cada subproceso de GC.</span><span class="sxs-lookup"><span data-stu-id="3c097-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="3c097-256">Solo se aplica a la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="3c097-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="3c097-257">Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores (`false`).</span><span class="sxs-lookup"><span data-stu-id="3c097-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="3c097-258">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-258">Setting name</span></span> | <span data-ttu-id="3c097-259">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-259">Values</span></span> | <span data-ttu-id="3c097-260">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="3c097-262">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-262">`false` - affinitize</span></span><br/><span data-ttu-id="3c097-263">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-263">`true` - don't affinitize</span></span> | <span data-ttu-id="3c097-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-265">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="3c097-266">`0`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-266">`0` - affinitize</span></span><br/><span data-ttu-id="3c097-267">`1`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-267">`1` - don't affinitize</span></span> | <span data-ttu-id="3c097-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-269">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="3c097-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="3c097-271">`false`: establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-271">`false` - affinitize</span></span><br/><span data-ttu-id="3c097-272">`true`: no establecer afinidad.</span><span class="sxs-lookup"><span data-stu-id="3c097-272">`true` - don't affinitize</span></span> | <span data-ttu-id="3c097-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3c097-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="3c097-274">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="3c097-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="3c097-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="3c097-276">Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.</span><span class="sxs-lookup"><span data-stu-id="3c097-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="3c097-277">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-277">Setting name</span></span> | <span data-ttu-id="3c097-278">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-278">Values</span></span> | <span data-ttu-id="3c097-279">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="3c097-281">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-281">*decimal value*</span></span> | <span data-ttu-id="3c097-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-283">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="3c097-284">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-284">*hexadecimal value*</span></span> | <span data-ttu-id="3c097-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-285">.NET Core 3.0</span></span> |

<span data-ttu-id="3c097-286">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-286">Example:</span></span>

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
> <span data-ttu-id="3c097-287">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="3c097-288">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="3c097-289">Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="3c097-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="3c097-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="3c097-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="3c097-291">Especifica el uso del montón de GC como porcentaje de la memoria total.</span><span class="sxs-lookup"><span data-stu-id="3c097-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="3c097-292">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-292">Setting name</span></span> | <span data-ttu-id="3c097-293">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-293">Values</span></span> | <span data-ttu-id="3c097-294">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="3c097-296">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-296">*decimal value*</span></span> | <span data-ttu-id="3c097-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="3c097-298">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="3c097-299">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-299">*hexadecimal value*</span></span> | <span data-ttu-id="3c097-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-300">.NET Core 3.0</span></span> |

<span data-ttu-id="3c097-301">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-301">Example:</span></span>

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
> <span data-ttu-id="3c097-302">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="3c097-303">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="3c097-304">Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="3c097-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="3c097-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="3c097-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="3c097-306">Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="3c097-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="3c097-307">Predeterminado: devolver los segmentos al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="3c097-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="3c097-308">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-308">Setting name</span></span> | <span data-ttu-id="3c097-309">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-309">Values</span></span> | <span data-ttu-id="3c097-310">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="3c097-312">`false`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3c097-312">`false` - release to OS</span></span><br/><span data-ttu-id="3c097-313">`true`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="3c097-313">`true` - put on standby</span></span>| <span data-ttu-id="3c097-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-315">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="3c097-316">`0`: liberar al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3c097-316">`0` - release to OS</span></span><br/><span data-ttu-id="3c097-317">`1`: poner en espera.</span><span class="sxs-lookup"><span data-stu-id="3c097-317">`1` - put on standby</span></span> | <span data-ttu-id="3c097-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-318">.NET Core 1.0</span></span> |

<span data-ttu-id="3c097-319">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="3c097-320">Páginas grandes</span><span class="sxs-lookup"><span data-stu-id="3c097-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="3c097-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="3c097-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="3c097-322">Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.</span><span class="sxs-lookup"><span data-stu-id="3c097-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="3c097-323">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="3c097-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="3c097-324">Se trata de un valor de configuración experimental.</span><span class="sxs-lookup"><span data-stu-id="3c097-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="3c097-325">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-325">Setting name</span></span> | <span data-ttu-id="3c097-326">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-326">Values</span></span> | <span data-ttu-id="3c097-327">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="3c097-329">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-329">N/A</span></span> | <span data-ttu-id="3c097-330">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-330">N/A</span></span> | <span data-ttu-id="3c097-331">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-331">N/A</span></span> |
| <span data-ttu-id="3c097-332">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="3c097-333">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-333">`0` - disabled</span></span><br/><span data-ttu-id="3c097-334">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-334">`1` - enabled</span></span> | <span data-ttu-id="3c097-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3c097-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="3c097-336">Objetos grandes</span><span class="sxs-lookup"><span data-stu-id="3c097-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="3c097-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="3c097-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="3c097-338">Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.</span><span class="sxs-lookup"><span data-stu-id="3c097-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="3c097-339">Predeterminado: habilitado (`1`).</span><span class="sxs-lookup"><span data-stu-id="3c097-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="3c097-340">Esta opción puede quedar obsoleta en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="3c097-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="3c097-341">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-341">Setting name</span></span> | <span data-ttu-id="3c097-342">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-342">Values</span></span> | <span data-ttu-id="3c097-343">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="3c097-345">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-345">N/A</span></span> | <span data-ttu-id="3c097-346">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-346">N/A</span></span> | <span data-ttu-id="3c097-347">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-347">N/A</span></span> |
| <span data-ttu-id="3c097-348">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="3c097-349">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-349">`1` - enabled</span></span><br/> <span data-ttu-id="3c097-350">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-350">`0` - disabled</span></span> | <span data-ttu-id="3c097-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-352">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="3c097-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="3c097-354">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-354">`1` - enabled</span></span><br/> <span data-ttu-id="3c097-355">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c097-355">`0` - disabled</span></span> | <span data-ttu-id="3c097-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3c097-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="3c097-357">Umbral del montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="3c097-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="3c097-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="3c097-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="3c097-359">Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="3c097-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="3c097-360">El valor predeterminado del umbral es de 85 000 bytes.</span><span class="sxs-lookup"><span data-stu-id="3c097-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="3c097-361">El valor que especifique debe ser mayor que el umbral predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3c097-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="3c097-362">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-362">Setting name</span></span> | <span data-ttu-id="3c097-363">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-363">Values</span></span> | <span data-ttu-id="3c097-364">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="3c097-366">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-366">*decimal value*</span></span> | <span data-ttu-id="3c097-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-368">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="3c097-369">*valor hexadecimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-369">*hexadecimal value*</span></span> | <span data-ttu-id="3c097-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3c097-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="3c097-371">**app.config para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="3c097-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="3c097-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="3c097-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="3c097-373">*valor decimal*</span><span class="sxs-lookup"><span data-stu-id="3c097-373">*decimal value*</span></span> | <span data-ttu-id="3c097-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="3c097-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="3c097-375">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c097-375">Example:</span></span>

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
> <span data-ttu-id="3c097-376">Si configura la opción en *runtimeconfig.json*, especifique un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="3c097-377">Si configura la opción como una variable de entorno, especifique un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3c097-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="3c097-378">Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="3c097-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="3c097-379">GC independiente</span><span class="sxs-lookup"><span data-stu-id="3c097-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="3c097-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="3c097-380">COMPlus_GCName</span></span>

- <span data-ttu-id="3c097-381">Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.</span><span class="sxs-lookup"><span data-stu-id="3c097-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="3c097-382">Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="3c097-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="3c097-383">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="3c097-383">Setting name</span></span> | <span data-ttu-id="3c097-384">Valores</span><span class="sxs-lookup"><span data-stu-id="3c097-384">Values</span></span> | <span data-ttu-id="3c097-385">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3c097-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="3c097-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3c097-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="3c097-387">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-387">N/A</span></span> | <span data-ttu-id="3c097-388">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-388">N/A</span></span> | <span data-ttu-id="3c097-389">N/D</span><span class="sxs-lookup"><span data-stu-id="3c097-389">N/A</span></span> |
| <span data-ttu-id="3c097-390">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="3c097-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="3c097-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="3c097-391">*string_path*</span></span> | <span data-ttu-id="3c097-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3c097-392">.NET Core 2.0</span></span> |
