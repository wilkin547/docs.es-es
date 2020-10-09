---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: e5f9e1245b749864787fb808527d022665197edf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654847"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="15c40-103">Opciones de configuración del entorno de ejecución para compilación</span><span class="sxs-lookup"><span data-stu-id="15c40-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="15c40-104">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="15c40-104">Tiered compilation</span></span>

- <span data-ttu-id="15c40-105">Configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="15c40-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="15c40-106">La compilación en niveles realiza la transición de métodos mediante dos niveles:</span><span class="sxs-lookup"><span data-stu-id="15c40-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="15c40-107">El primer nivel genera código más rápidamente ([JIT rápido](#quick-jit)) o carga código previamente compilado ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="15c40-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="15c40-108">El segundo nivel genera código optimizado en segundo plano ("JIT de optimización").</span><span class="sxs-lookup"><span data-stu-id="15c40-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="15c40-109">En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15c40-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="15c40-110">En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15c40-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="15c40-111">Para obtener más información, vea la [Guía de compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="15c40-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="15c40-112">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="15c40-112">Setting name</span></span> | <span data-ttu-id="15c40-113">Valores</span><span class="sxs-lookup"><span data-stu-id="15c40-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="15c40-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="15c40-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="15c40-115">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-115">`true` - enabled</span></span><br/><span data-ttu-id="15c40-116">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-116">`false` - disabled</span></span> |
| <span data-ttu-id="15c40-117">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="15c40-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="15c40-118">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-118">`true` - enabled</span></span><br/><span data-ttu-id="15c40-119">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-119">`false` - disabled</span></span> |
| <span data-ttu-id="15c40-120">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="15c40-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="15c40-121">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-121">`1` - enabled</span></span><br/><span data-ttu-id="15c40-122">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="15c40-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15c40-123">Examples</span></span>

<span data-ttu-id="15c40-124">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="15c40-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="15c40-125">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="15c40-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="15c40-126">JIT rápido</span><span class="sxs-lookup"><span data-stu-id="15c40-126">Quick JIT</span></span>

- <span data-ttu-id="15c40-127">Configura si el compilador JIT usa *JIT rápido*.</span><span class="sxs-lookup"><span data-stu-id="15c40-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="15c40-128">En el caso de los métodos que no contienen bucles y para los que no hay código compilado previamente, JIT rápido los compila más rápidamente, pero sin optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="15c40-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="15c40-129">La habilitación de JIT rápido reduce el tiempo de inicio, pero puede generar código con características de rendimiento degradadas.</span><span class="sxs-lookup"><span data-stu-id="15c40-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="15c40-130">Por ejemplo, el código puede usar más espacio de pila, asignar más memoria y ejecutarse más lentamente.</span><span class="sxs-lookup"><span data-stu-id="15c40-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="15c40-131">Si JIT rápido está deshabilitado pero la [compilación en niveles](#tiered-compilation) está habilitada, solo el código compilado previamente participa en la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="15c40-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="15c40-132">Si un método no está compilado previamente con [ReadyToRun](#readytorun), el comportamiento de JIT es el mismo que si la [compilación en niveles](#tiered-compilation) estuviera deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="15c40-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="15c40-133">En .NET Core 3.0 y versiones posteriores, JIT rápido está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15c40-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="15c40-134">En .NET Core 2.1 y 2.2, JIT rápido está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15c40-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="15c40-135">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="15c40-135">Setting name</span></span> | <span data-ttu-id="15c40-136">Valores</span><span class="sxs-lookup"><span data-stu-id="15c40-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="15c40-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="15c40-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="15c40-138">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-138">`true` - enabled</span></span><br/><span data-ttu-id="15c40-139">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-139">`false` - disabled</span></span> |
| <span data-ttu-id="15c40-140">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="15c40-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="15c40-141">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-141">`true` - enabled</span></span><br/><span data-ttu-id="15c40-142">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-142">`false` - disabled</span></span> |
| <span data-ttu-id="15c40-143">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="15c40-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="15c40-144">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-144">`1` - enabled</span></span><br/><span data-ttu-id="15c40-145">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="15c40-146">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15c40-146">Examples</span></span>

<span data-ttu-id="15c40-147">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="15c40-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="15c40-148">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="15c40-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="15c40-149">JIT rápido para bucles</span><span class="sxs-lookup"><span data-stu-id="15c40-149">Quick JIT for loops</span></span>

- <span data-ttu-id="15c40-150">Configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="15c40-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="15c40-151">La habilitación de JIT rápido para bucles puede mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="15c40-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="15c40-152">Pero los bucles de ejecución prolongada se pueden bloquear en código menos optimizado durante períodos largos.</span><span class="sxs-lookup"><span data-stu-id="15c40-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="15c40-153">Si [JIT rápido](#quick-jit) está deshabilitado, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="15c40-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="15c40-154">Si se omite esta configuración, el método JIT rápido no se utiliza para los métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="15c40-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="15c40-155">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="15c40-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="15c40-156">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="15c40-156">Setting name</span></span> | <span data-ttu-id="15c40-157">Valores</span><span class="sxs-lookup"><span data-stu-id="15c40-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="15c40-158">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="15c40-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="15c40-159">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-159">`false` - disabled</span></span><br/><span data-ttu-id="15c40-160">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-160">`true` - enabled</span></span> |
| <span data-ttu-id="15c40-161">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="15c40-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="15c40-162">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-162">`false` - disabled</span></span><br/><span data-ttu-id="15c40-163">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-163">`true` - enabled</span></span> |
| <span data-ttu-id="15c40-164">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="15c40-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="15c40-165">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-165">`0` - disabled</span></span><br/><span data-ttu-id="15c40-166">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="15c40-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15c40-167">Examples</span></span>

<span data-ttu-id="15c40-168">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="15c40-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="15c40-169">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="15c40-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="15c40-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="15c40-170">ReadyToRun</span></span>

- <span data-ttu-id="15c40-171">Configura si el entorno de ejecución de .NET Core usa código precompilado para las imágenes con datos de ReadyToRun disponibles.</span><span class="sxs-lookup"><span data-stu-id="15c40-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="15c40-172">Al deshabilitar esta opción, se fuerza al entorno de ejecución a compilar código de marco mediante JIT.</span><span class="sxs-lookup"><span data-stu-id="15c40-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="15c40-173">Para obtener más información, consulte [Ready to Run](../deploying/ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="15c40-173">For more information, see [Ready to Run](../deploying/ready-to-run.md).</span></span>
- <span data-ttu-id="15c40-174">Si se omite esta configuración, .NET usa datos ReadyToRun cuando están disponibles.</span><span class="sxs-lookup"><span data-stu-id="15c40-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="15c40-175">Esto es equivalente a establecer el valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="15c40-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="15c40-176">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="15c40-176">Setting name</span></span> | <span data-ttu-id="15c40-177">Valores</span><span class="sxs-lookup"><span data-stu-id="15c40-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="15c40-178">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="15c40-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="15c40-179">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-179">`1` - enabled</span></span><br/><span data-ttu-id="15c40-180">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="15c40-180">`0` - disabled</span></span> |
