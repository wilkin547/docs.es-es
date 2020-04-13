---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ac51aa13254b2f2b1fdd8d1dd9c52559831a1659
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989121"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="45576-103">Opciones de configuración del entorno de ejecución para compilación</span><span class="sxs-lookup"><span data-stu-id="45576-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="45576-104">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="45576-104">Tiered compilation</span></span>

- <span data-ttu-id="45576-105">Configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="45576-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="45576-106">La compilación en niveles realiza la transición de métodos mediante dos niveles:</span><span class="sxs-lookup"><span data-stu-id="45576-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="45576-107">El primer nivel genera código más rápidamente ([JIT rápido](#quick-jit)) o carga código previamente compilado ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="45576-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="45576-108">El segundo nivel genera código optimizado en segundo plano ("JIT de optimización").</span><span class="sxs-lookup"><span data-stu-id="45576-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="45576-109">En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45576-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="45576-110">En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45576-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="45576-111">Para obtener más información, vea la [Guía de compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="45576-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="45576-112">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="45576-112">Setting name</span></span> | <span data-ttu-id="45576-113">Valores</span><span class="sxs-lookup"><span data-stu-id="45576-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="45576-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="45576-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="45576-115">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-115">`true` - enabled</span></span><br/><span data-ttu-id="45576-116">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-116">`false` - disabled</span></span> |
| <span data-ttu-id="45576-117">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="45576-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="45576-118">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-118">`true` - enabled</span></span><br/><span data-ttu-id="45576-119">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-119">`false` - disabled</span></span> |
| <span data-ttu-id="45576-120">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="45576-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="45576-121">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-121">`1` - enabled</span></span><br/><span data-ttu-id="45576-122">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="45576-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="45576-123">Examples</span></span>

<span data-ttu-id="45576-124">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="45576-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="45576-125">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="45576-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="45576-126">JIT rápido</span><span class="sxs-lookup"><span data-stu-id="45576-126">Quick JIT</span></span>

- <span data-ttu-id="45576-127">Configura si el compilador JIT usa *JIT rápido*.</span><span class="sxs-lookup"><span data-stu-id="45576-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="45576-128">En el caso de los métodos que no contienen bucles y para los que no hay código compilado previamente, JIT rápido los compila más rápidamente, pero sin optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="45576-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="45576-129">La habilitación de JIT rápido reduce el tiempo de inicio, pero puede generar código con características de rendimiento degradadas.</span><span class="sxs-lookup"><span data-stu-id="45576-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="45576-130">Por ejemplo, el código puede usar más espacio de pila, asignar más memoria y ejecutarse más lentamente.</span><span class="sxs-lookup"><span data-stu-id="45576-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="45576-131">Si JIT rápido está deshabilitado pero la [compilación en niveles](#tiered-compilation) está habilitada, solo el código compilado previamente participa en la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="45576-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="45576-132">Si un método no está compilado previamente con [ReadyToRun](#readytorun), el comportamiento de JIT es el mismo que si la [compilación en niveles](#tiered-compilation) estuviera deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="45576-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="45576-133">En .NET Core 3.0 y versiones posteriores, JIT rápido está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45576-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="45576-134">En .NET Core 2.1 y 2.2, JIT rápido está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45576-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="45576-135">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="45576-135">Setting name</span></span> | <span data-ttu-id="45576-136">Valores</span><span class="sxs-lookup"><span data-stu-id="45576-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="45576-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="45576-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="45576-138">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-138">`true` - enabled</span></span><br/><span data-ttu-id="45576-139">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-139">`false` - disabled</span></span> |
| <span data-ttu-id="45576-140">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="45576-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="45576-141">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-141">`true` - enabled</span></span><br/><span data-ttu-id="45576-142">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-142">`false` - disabled</span></span> |
| <span data-ttu-id="45576-143">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="45576-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="45576-144">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-144">`1` - enabled</span></span><br/><span data-ttu-id="45576-145">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="45576-146">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="45576-146">Examples</span></span>

<span data-ttu-id="45576-147">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="45576-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="45576-148">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="45576-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="45576-149">JIT rápido para bucles</span><span class="sxs-lookup"><span data-stu-id="45576-149">Quick JIT for loops</span></span>

- <span data-ttu-id="45576-150">Configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="45576-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="45576-151">La habilitación de JIT rápido para bucles puede mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="45576-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="45576-152">Pero los bucles de ejecución prolongada se pueden bloquear en código menos optimizado durante períodos largos.</span><span class="sxs-lookup"><span data-stu-id="45576-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="45576-153">Si [JIT rápido](#quick-jit) está deshabilitado, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="45576-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="45576-154">Predeterminado: deshabilitado (`false`).</span><span class="sxs-lookup"><span data-stu-id="45576-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="45576-155">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="45576-155">Setting name</span></span> | <span data-ttu-id="45576-156">Valores</span><span class="sxs-lookup"><span data-stu-id="45576-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="45576-157">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="45576-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="45576-158">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-158">`false` - disabled</span></span><br/><span data-ttu-id="45576-159">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-159">`true` - enabled</span></span> |
| <span data-ttu-id="45576-160">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="45576-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="45576-161">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-161">`false` - disabled</span></span><br/><span data-ttu-id="45576-162">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-162">`true` - enabled</span></span> |
| <span data-ttu-id="45576-163">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="45576-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="45576-164">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-164">`0` - disabled</span></span><br/><span data-ttu-id="45576-165">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="45576-166">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="45576-166">Examples</span></span>

<span data-ttu-id="45576-167">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="45576-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="45576-168">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="45576-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="45576-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="45576-169">ReadyToRun</span></span>

- <span data-ttu-id="45576-170">Configura si el entorno de ejecución de .NET Core usa código precompilado para las imágenes con datos de ReadyToRun disponibles.</span><span class="sxs-lookup"><span data-stu-id="45576-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="45576-171">Al deshabilitar esta opción, se fuerza al entorno de ejecución a compilar código de marco mediante JIT.</span><span class="sxs-lookup"><span data-stu-id="45576-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="45576-172">Para obtener más información, vea [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="45576-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="45576-173">Predeterminado: habilitado (`1`).</span><span class="sxs-lookup"><span data-stu-id="45576-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="45576-174">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="45576-174">Setting name</span></span> | <span data-ttu-id="45576-175">Valores</span><span class="sxs-lookup"><span data-stu-id="45576-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="45576-176">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="45576-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="45576-177">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-177">`1` - enabled</span></span><br/><span data-ttu-id="45576-178">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="45576-178">`0` - disabled</span></span> |
