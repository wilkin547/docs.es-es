---
title: Depuración de la configuración de la generación de perfiles
description: Obtenga información sobre los valores del entorno de ejecución que configuran la depuración y la generación de perfiles para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998862"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="f1682-103">Opciones de configuración del ejecución para la depuración y la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1682-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="f1682-104">Habilitación de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f1682-104">Enable diagnostics</span></span>

- <span data-ttu-id="f1682-105">Configura si el depurador, el generador de perfiles y los diagnósticos de EventPipe están habilitados o deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="f1682-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="f1682-106">Predeterminado: habilitado (`1`).</span><span class="sxs-lookup"><span data-stu-id="f1682-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="f1682-107">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-107">Setting name</span></span> | <span data-ttu-id="f1682-108">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f1682-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1682-110">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-110">N/A</span></span> | <span data-ttu-id="f1682-111">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-111">N/A</span></span> |
| <span data-ttu-id="f1682-112">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="f1682-113">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-113">`1` - enabled</span></span><br/><span data-ttu-id="f1682-114">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="f1682-115">Habilitación de la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1682-115">Enable profiling</span></span>

- <span data-ttu-id="f1682-116">Configura si la generación de perfiles está habilitada para el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="f1682-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="f1682-117">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="f1682-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f1682-118">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-118">Setting name</span></span> | <span data-ttu-id="f1682-119">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f1682-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1682-121">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-121">N/A</span></span> | <span data-ttu-id="f1682-122">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-122">N/A</span></span> |
| <span data-ttu-id="f1682-123">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="f1682-124">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-124">`0` - disabled</span></span><br/><span data-ttu-id="f1682-125">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="f1682-126">GUID de generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1682-126">Profiler GUID</span></span>

- <span data-ttu-id="f1682-127">Especifica el GUID del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="f1682-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="f1682-128">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-128">Setting name</span></span> | <span data-ttu-id="f1682-129">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f1682-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1682-131">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-131">N/A</span></span> | <span data-ttu-id="f1682-132">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-132">N/A</span></span> |
| <span data-ttu-id="f1682-133">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="f1682-134">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="f1682-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="f1682-135">Ubicación del generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1682-135">Profiler location</span></span>

- <span data-ttu-id="f1682-136">Especifica la ruta de acceso a la biblioteca de vínculos dinámicos del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente (proceso de 32 bits o de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="f1682-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="f1682-137">Si se establece más de una variable, las variables concretas de valor de bits tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="f1682-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="f1682-138">Especifican el valor de bits del generador de perfiles que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="f1682-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="f1682-139">Para obtener más información, vea [Búsqueda de la biblioteca del generador de perfiles](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="f1682-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="f1682-140">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-140">Setting name</span></span> | <span data-ttu-id="f1682-141">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-142">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="f1682-143">*string-path*</span><span class="sxs-lookup"><span data-stu-id="f1682-143">*string-path*</span></span> |
| <span data-ttu-id="f1682-144">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="f1682-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="f1682-145">*string-path*</span></span> |
| <span data-ttu-id="f1682-146">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="f1682-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="f1682-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="f1682-148">Escritura del mapa de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f1682-148">Write perf map</span></span>

- <span data-ttu-id="f1682-149">Habilita o deshabilita la escritura de */tmp/perf-$pid.map* en los sistemas Linux.</span><span class="sxs-lookup"><span data-stu-id="f1682-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="f1682-150">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="f1682-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f1682-151">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-151">Setting name</span></span> | <span data-ttu-id="f1682-152">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f1682-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1682-154">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-154">N/A</span></span> | <span data-ttu-id="f1682-155">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-155">N/A</span></span> |
| <span data-ttu-id="f1682-156">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="f1682-157">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-157">`0` - disabled</span></span><br/><span data-ttu-id="f1682-158">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="f1682-159">Marcadores del registro de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f1682-159">Perf log markers</span></span>

- <span data-ttu-id="f1682-160">Cuando `COMPlus_PerfMapEnabled` se establece en `1`, habilita o deshabilita la señal especificada que se va a aceptar y omitir como marcador en los registros de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f1682-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="f1682-161">Predeterminado: deshabilitado (`0`).</span><span class="sxs-lookup"><span data-stu-id="f1682-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f1682-162">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="f1682-162">Setting name</span></span> | <span data-ttu-id="f1682-163">Valores</span><span class="sxs-lookup"><span data-stu-id="f1682-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1682-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f1682-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1682-165">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-165">N/A</span></span> | <span data-ttu-id="f1682-166">N/D</span><span class="sxs-lookup"><span data-stu-id="f1682-166">N/A</span></span> |
| <span data-ttu-id="f1682-167">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="f1682-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="f1682-168">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-168">`0` - disabled</span></span><br/><span data-ttu-id="f1682-169">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="f1682-169">`1` - enabled</span></span> |
