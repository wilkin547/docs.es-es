---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: cfcf9b5fc8d11a4ae35ab9b152f32133cd6930bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762011"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="2b14e-103">Opciones de configuración del entorno de ejecución para compilación</span><span class="sxs-lookup"><span data-stu-id="2b14e-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="2b14e-104">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="2b14e-104">Tiered compilation</span></span>

- <span data-ttu-id="2b14e-105">Configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="2b14e-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="2b14e-106">La compilación en niveles realiza la transición de métodos mediante dos niveles:</span><span class="sxs-lookup"><span data-stu-id="2b14e-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="2b14e-107">El primer nivel genera código más rápidamente ([JIT rápido](#quick-jit)) o carga código previamente compilado ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="2b14e-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="2b14e-108">El segundo nivel genera código optimizado en segundo plano ("JIT de optimización").</span><span class="sxs-lookup"><span data-stu-id="2b14e-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="2b14e-109">En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b14e-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="2b14e-110">En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b14e-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="2b14e-111">Para obtener más información, vea la [Guía de compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="2b14e-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="2b14e-112">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2b14e-112">Setting name</span></span> | <span data-ttu-id="2b14e-113">Valores</span><span class="sxs-lookup"><span data-stu-id="2b14e-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2b14e-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2b14e-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="2b14e-115">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-115">`true` - enabled</span></span><br/><span data-ttu-id="2b14e-116">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-116">`false` - disabled</span></span> |
| <span data-ttu-id="2b14e-117">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="2b14e-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="2b14e-118">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-118">`true` - enabled</span></span><br/><span data-ttu-id="2b14e-119">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-119">`false` - disabled</span></span> |
| <span data-ttu-id="2b14e-120">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2b14e-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="2b14e-121">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-121">`1` - enabled</span></span><br/><span data-ttu-id="2b14e-122">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="2b14e-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2b14e-123">Examples</span></span>

<span data-ttu-id="2b14e-124">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="2b14e-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="2b14e-125">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="2b14e-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="2b14e-126">JIT rápido</span><span class="sxs-lookup"><span data-stu-id="2b14e-126">Quick JIT</span></span>

- <span data-ttu-id="2b14e-127">Configura si el compilador JIT usa *JIT rápido*.</span><span class="sxs-lookup"><span data-stu-id="2b14e-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="2b14e-128">En el caso de los métodos que no contienen bucles y para los que no hay código compilado previamente, JIT rápido los compila más rápidamente, pero sin optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="2b14e-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="2b14e-129">La habilitación de JIT rápido reduce el tiempo de inicio, pero puede generar código con características de rendimiento degradadas.</span><span class="sxs-lookup"><span data-stu-id="2b14e-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="2b14e-130">Por ejemplo, el código puede usar más espacio de pila, asignar más memoria y ejecutarse más lentamente.</span><span class="sxs-lookup"><span data-stu-id="2b14e-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="2b14e-131">Si JIT rápido está deshabilitado pero la [compilación en niveles](#tiered-compilation) está habilitada, solo el código compilado previamente participa en la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="2b14e-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="2b14e-132">Si un método no está compilado previamente con [ReadyToRun](#readytorun), el comportamiento de JIT es el mismo que si la [compilación en niveles](#tiered-compilation) estuviera deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="2b14e-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="2b14e-133">En .NET Core 3.0 y versiones posteriores, JIT rápido está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b14e-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="2b14e-134">En .NET Core 2.1 y 2.2, JIT rápido está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b14e-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="2b14e-135">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2b14e-135">Setting name</span></span> | <span data-ttu-id="2b14e-136">Valores</span><span class="sxs-lookup"><span data-stu-id="2b14e-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2b14e-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2b14e-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="2b14e-138">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-138">`true` - enabled</span></span><br/><span data-ttu-id="2b14e-139">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-139">`false` - disabled</span></span> |
| <span data-ttu-id="2b14e-140">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="2b14e-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="2b14e-141">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-141">`true` - enabled</span></span><br/><span data-ttu-id="2b14e-142">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-142">`false` - disabled</span></span> |
| <span data-ttu-id="2b14e-143">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2b14e-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="2b14e-144">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-144">`1` - enabled</span></span><br/><span data-ttu-id="2b14e-145">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="2b14e-146">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2b14e-146">Examples</span></span>

<span data-ttu-id="2b14e-147">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="2b14e-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="2b14e-148">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="2b14e-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="2b14e-149">JIT rápido para bucles</span><span class="sxs-lookup"><span data-stu-id="2b14e-149">Quick JIT for loops</span></span>

- <span data-ttu-id="2b14e-150">Configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="2b14e-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="2b14e-151">La habilitación de JIT rápido para bucles puede mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="2b14e-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="2b14e-152">Pero los bucles de ejecución prolongada se pueden bloquear en código menos optimizado durante períodos largos.</span><span class="sxs-lookup"><span data-stu-id="2b14e-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="2b14e-153">Si [JIT rápido](#quick-jit) está deshabilitado, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="2b14e-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="2b14e-154">Si se omite esta configuración, el método JIT rápido no se utiliza para los métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="2b14e-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="2b14e-155">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="2b14e-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="2b14e-156">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2b14e-156">Setting name</span></span> | <span data-ttu-id="2b14e-157">Valores</span><span class="sxs-lookup"><span data-stu-id="2b14e-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2b14e-158">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2b14e-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="2b14e-159">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-159">`false` - disabled</span></span><br/><span data-ttu-id="2b14e-160">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-160">`true` - enabled</span></span> |
| <span data-ttu-id="2b14e-161">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="2b14e-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="2b14e-162">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-162">`false` - disabled</span></span><br/><span data-ttu-id="2b14e-163">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-163">`true` - enabled</span></span> |
| <span data-ttu-id="2b14e-164">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2b14e-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="2b14e-165">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-165">`0` - disabled</span></span><br/><span data-ttu-id="2b14e-166">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="2b14e-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2b14e-167">Examples</span></span>

<span data-ttu-id="2b14e-168">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="2b14e-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="2b14e-169">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="2b14e-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="2b14e-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="2b14e-170">ReadyToRun</span></span>

- <span data-ttu-id="2b14e-171">Configura si el entorno de ejecución de .NET Core usa código precompilado para las imágenes con datos de ReadyToRun disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b14e-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="2b14e-172">Al deshabilitar esta opción, se fuerza al entorno de ejecución a compilar código de marco mediante JIT.</span><span class="sxs-lookup"><span data-stu-id="2b14e-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="2b14e-173">Para obtener más información, vea [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="2b14e-173">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="2b14e-174">Si se omite esta configuración, .NET usa datos ReadyToRun cuando están disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b14e-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="2b14e-175">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="2b14e-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="2b14e-176">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2b14e-176">Setting name</span></span> | <span data-ttu-id="2b14e-177">Valores</span><span class="sxs-lookup"><span data-stu-id="2b14e-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2b14e-178">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2b14e-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="2b14e-179">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-179">`1` - enabled</span></span><br/><span data-ttu-id="2b14e-180">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2b14e-180">`0` - disabled</span></span> |
