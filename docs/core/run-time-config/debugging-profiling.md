---
title: Depuración de la configuración de la generación de perfiles
description: Obtenga información sobre los valores del entorno de ejecución que configuran la depuración y la generación de perfiles para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: dd96862582f13adc19df7572b1865800b18d9954
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875023"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="97df2-103">Opciones de configuración del ejecución para la depuración y la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="97df2-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="97df2-104">Habilitación de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="97df2-104">Enable diagnostics</span></span>

- <span data-ttu-id="97df2-105">Configura si el depurador, el generador de perfiles y los diagnósticos de EventPipe están habilitados o deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="97df2-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="97df2-106">Si se omite esta configuración, se habilitan los diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="97df2-106">If you omit this setting, diagnostics are enabled.</span></span> <span data-ttu-id="97df2-107">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="97df2-107">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="97df2-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-108">Setting name</span></span> | <span data-ttu-id="97df2-109">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="97df2-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="97df2-111">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-111">N/A</span></span> | <span data-ttu-id="97df2-112">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-112">N/A</span></span> |
| <span data-ttu-id="97df2-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-113">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="97df2-114">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-114">`1` - enabled</span></span><br/><span data-ttu-id="97df2-115">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-115">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="97df2-116">Habilitación de la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="97df2-116">Enable profiling</span></span>

- <span data-ttu-id="97df2-117">Configura si la generación de perfiles está habilitada para el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="97df2-117">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="97df2-118">Si se omite esta configuración, la generación de perfiles está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="97df2-118">If you omit this setting, profiling is disabled.</span></span> <span data-ttu-id="97df2-119">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="97df2-119">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="97df2-120">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-120">Setting name</span></span> | <span data-ttu-id="97df2-121">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="97df2-122">**runtimeconfig.json**</span></span> | <span data-ttu-id="97df2-123">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-123">N/A</span></span> | <span data-ttu-id="97df2-124">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-124">N/A</span></span> |
| <span data-ttu-id="97df2-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-125">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="97df2-126">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-126">`0` - disabled</span></span><br/><span data-ttu-id="97df2-127">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-127">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="97df2-128">GUID de generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="97df2-128">Profiler GUID</span></span>

- <span data-ttu-id="97df2-129">Especifica el GUID del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="97df2-129">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="97df2-130">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-130">Setting name</span></span> | <span data-ttu-id="97df2-131">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-131">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-132">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="97df2-132">**runtimeconfig.json**</span></span> | <span data-ttu-id="97df2-133">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-133">N/A</span></span> | <span data-ttu-id="97df2-134">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-134">N/A</span></span> |
| <span data-ttu-id="97df2-135">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-135">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="97df2-136">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="97df2-136">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="97df2-137">Ubicación del generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="97df2-137">Profiler location</span></span>

- <span data-ttu-id="97df2-138">Especifica la ruta de acceso a la biblioteca de vínculos dinámicos del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente (proceso de 32 bits o de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="97df2-138">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="97df2-139">Si se establece más de una variable, las variables concretas de valor de bits tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="97df2-139">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="97df2-140">Especifican el valor de bits del generador de perfiles que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="97df2-140">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="97df2-141">Para obtener más información, vea [Búsqueda de la biblioteca del generador de perfiles](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="97df2-141">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="97df2-142">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-142">Setting name</span></span> | <span data-ttu-id="97df2-143">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-143">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-144">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="97df2-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="97df2-145">*string-path*</span></span> |
| <span data-ttu-id="97df2-146">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="97df2-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="97df2-147">*string-path*</span></span> |
| <span data-ttu-id="97df2-148">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-148">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="97df2-149">*string-path*</span><span class="sxs-lookup"><span data-stu-id="97df2-149">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="97df2-150">Escritura del mapa de rendimiento</span><span class="sxs-lookup"><span data-stu-id="97df2-150">Write perf map</span></span>

- <span data-ttu-id="97df2-151">Habilita o deshabilita la escritura de */tmp/perf-$pid.map* en los sistemas Linux.</span><span class="sxs-lookup"><span data-stu-id="97df2-151">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="97df2-152">Si se omite esta configuración, la escritura del mapa de rendimiento está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="97df2-152">If you omit this setting, writing the perf map is disabled.</span></span> <span data-ttu-id="97df2-153">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="97df2-153">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="97df2-154">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-154">Setting name</span></span> | <span data-ttu-id="97df2-155">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="97df2-156">**runtimeconfig.json**</span></span> | <span data-ttu-id="97df2-157">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-157">N/A</span></span> | <span data-ttu-id="97df2-158">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-158">N/A</span></span> |
| <span data-ttu-id="97df2-159">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-159">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="97df2-160">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-160">`0` - disabled</span></span><br/><span data-ttu-id="97df2-161">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-161">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="97df2-162">Marcadores del registro de rendimiento</span><span class="sxs-lookup"><span data-stu-id="97df2-162">Perf log markers</span></span>

- <span data-ttu-id="97df2-163">Habilita o deshabilita la señal especificada que se va a aceptar y omitir como marcador en los registros de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="97df2-163">Enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="97df2-164">Si se omite este valor, la señal especificada no se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="97df2-164">If you omit this setting, the specified signal is not ignored.</span></span> <span data-ttu-id="97df2-165">Esto es equivalente a establecer el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="97df2-165">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="97df2-166">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="97df2-166">Setting name</span></span> | <span data-ttu-id="97df2-167">Valores</span><span class="sxs-lookup"><span data-stu-id="97df2-167">Values</span></span> |
| - | - | - |
| <span data-ttu-id="97df2-168">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="97df2-168">**runtimeconfig.json**</span></span> | <span data-ttu-id="97df2-169">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-169">N/A</span></span> | <span data-ttu-id="97df2-170">N/D</span><span class="sxs-lookup"><span data-stu-id="97df2-170">N/A</span></span> |
| <span data-ttu-id="97df2-171">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="97df2-171">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="97df2-172">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-172">`0` - disabled</span></span><br/><span data-ttu-id="97df2-173">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="97df2-173">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="97df2-174">Este valor se omite si se omite [COMPlus_PerfMapEnabled](#write-perf-map) o se establece en `0` (es decir, deshabilitado).</span><span class="sxs-lookup"><span data-stu-id="97df2-174">This setting is ignored if [COMPlus_PerfMapEnabled](#write-perf-map) is omitted or set to `0` (that is, disabled).</span></span>
