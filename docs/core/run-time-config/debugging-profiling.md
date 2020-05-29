---
title: Depuración de la configuración de la generación de perfiles
description: Obtenga información sobre los valores del entorno de ejecución que configuran la depuración y la generación de perfiles para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761998"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="1c5a3-103">Opciones de configuración del ejecución para la depuración y la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1c5a3-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="1c5a3-104">Habilitación de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1c5a3-104">Enable diagnostics</span></span>

- <span data-ttu-id="1c5a3-105">Configura si el depurador, el generador de perfiles y los diagnósticos de EventPipe están habilitados o deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="1c5a3-106">Si se omite esta configuración, se habilitan los diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-106">If you omit this setting, diagnostics are enabled.</span></span> <span data-ttu-id="1c5a3-107">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-107">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="1c5a3-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-108">Setting name</span></span> | <span data-ttu-id="1c5a3-109">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="1c5a3-111">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-111">N/A</span></span> | <span data-ttu-id="1c5a3-112">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-112">N/A</span></span> |
| <span data-ttu-id="1c5a3-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-113">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="1c5a3-114">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-114">`1` - enabled</span></span><br/><span data-ttu-id="1c5a3-115">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-115">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="1c5a3-116">Habilitación de la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1c5a3-116">Enable profiling</span></span>

- <span data-ttu-id="1c5a3-117">Configura si la generación de perfiles está habilitada para el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-117">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="1c5a3-118">Si se omite esta configuración, la generación de perfiles está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-118">If you omit this setting, profiling is disabled.</span></span> <span data-ttu-id="1c5a3-119">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-119">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1c5a3-120">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-120">Setting name</span></span> | <span data-ttu-id="1c5a3-121">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-122">**runtimeconfig.json**</span></span> | <span data-ttu-id="1c5a3-123">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-123">N/A</span></span> | <span data-ttu-id="1c5a3-124">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-124">N/A</span></span> |
| <span data-ttu-id="1c5a3-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-125">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="1c5a3-126">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-126">`0` - disabled</span></span><br/><span data-ttu-id="1c5a3-127">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-127">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="1c5a3-128">GUID de generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="1c5a3-128">Profiler GUID</span></span>

- <span data-ttu-id="1c5a3-129">Especifica el GUID del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-129">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="1c5a3-130">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-130">Setting name</span></span> | <span data-ttu-id="1c5a3-131">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-131">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-132">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-132">**runtimeconfig.json**</span></span> | <span data-ttu-id="1c5a3-133">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-133">N/A</span></span> | <span data-ttu-id="1c5a3-134">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-134">N/A</span></span> |
| <span data-ttu-id="1c5a3-135">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-135">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="1c5a3-136">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="1c5a3-136">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="1c5a3-137">Ubicación del generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="1c5a3-137">Profiler location</span></span>

- <span data-ttu-id="1c5a3-138">Especifica la ruta de acceso a la biblioteca de vínculos dinámicos del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente (proceso de 32 bits o de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="1c5a3-138">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="1c5a3-139">Si se establece más de una variable, las variables concretas de valor de bits tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-139">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="1c5a3-140">Especifican el valor de bits del generador de perfiles que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-140">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="1c5a3-141">Para obtener más información, vea [Búsqueda de la biblioteca del generador de perfiles](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="1c5a3-141">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="1c5a3-142">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-142">Setting name</span></span> | <span data-ttu-id="1c5a3-143">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-143">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-144">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="1c5a3-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1c5a3-145">*string-path*</span></span> |
| <span data-ttu-id="1c5a3-146">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="1c5a3-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1c5a3-147">*string-path*</span></span> |
| <span data-ttu-id="1c5a3-148">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-148">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="1c5a3-149">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1c5a3-149">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="1c5a3-150">Escritura del mapa de rendimiento</span><span class="sxs-lookup"><span data-stu-id="1c5a3-150">Write perf map</span></span>

- <span data-ttu-id="1c5a3-151">Habilita o deshabilita la escritura de */tmp/perf-$pid.map* en los sistemas Linux.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-151">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="1c5a3-152">Si se omite esta configuración, la escritura del mapa de rendimiento está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-152">If you omit this setting, writing the perf map is disabled.</span></span> <span data-ttu-id="1c5a3-153">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-153">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1c5a3-154">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-154">Setting name</span></span> | <span data-ttu-id="1c5a3-155">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-156">**runtimeconfig.json**</span></span> | <span data-ttu-id="1c5a3-157">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-157">N/A</span></span> | <span data-ttu-id="1c5a3-158">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-158">N/A</span></span> |
| <span data-ttu-id="1c5a3-159">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-159">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="1c5a3-160">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-160">`0` - disabled</span></span><br/><span data-ttu-id="1c5a3-161">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-161">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="1c5a3-162">Marcadores del registro de rendimiento</span><span class="sxs-lookup"><span data-stu-id="1c5a3-162">Perf log markers</span></span>

- <span data-ttu-id="1c5a3-163">Habilita o deshabilita la señal especificada que se va a aceptar y omitir como marcador en los registros de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-163">Enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="1c5a3-164">Si se omite este valor, la señal especificada no se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-164">If you omit this setting, the specified signal is not ignored.</span></span> <span data-ttu-id="1c5a3-165">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-165">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1c5a3-166">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="1c5a3-166">Setting name</span></span> | <span data-ttu-id="1c5a3-167">Valores</span><span class="sxs-lookup"><span data-stu-id="1c5a3-167">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1c5a3-168">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-168">**runtimeconfig.json**</span></span> | <span data-ttu-id="1c5a3-169">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-169">N/A</span></span> | <span data-ttu-id="1c5a3-170">N/D</span><span class="sxs-lookup"><span data-stu-id="1c5a3-170">N/A</span></span> |
| <span data-ttu-id="1c5a3-171">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-171">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="1c5a3-172">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-172">`0` - disabled</span></span><br/><span data-ttu-id="1c5a3-173">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-173">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="1c5a3-174">Este valor se omite si se omite [COMPlus_PerfMapEnabled](#write-perf-map) o se establece en `0` (es decir, deshabilitado).</span><span class="sxs-lookup"><span data-stu-id="1c5a3-174">This setting is ignored if [COMPlus_PerfMapEnabled](#write-perf-map) is omitted or set to `0` (that is, disabled).</span></span>
