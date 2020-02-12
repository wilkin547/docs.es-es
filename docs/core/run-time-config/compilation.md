---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: adf1f01dba7387b89ee56784e33653d6a132c0e3
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092894"
---
# <a name="run-time-configuration-options-for-compilation"></a>Opciones de configuración del entorno de ejecución para compilación

## <a name="tiered-compilation"></a>Compilación en niveles

- Configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation). La compilación en niveles realiza la transición de métodos mediante dos niveles:
  - El primer nivel genera código más rápidamente ([JIT rápido](#quick-jit)) o carga código previamente compilado ([ReadyToRun](#readytorun)).
  - El segundo nivel genera código optimizado en segundo plano ("JIT de optimización").
- En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.
- En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.
- Para obtener más información, vea la [Guía de compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true`: habilitado.<br/>`false`: deshabilitado. |
| **Propiedad de MSBuild** | `TieredCompilation` | `true`: habilitado.<br/>`false`: deshabilitado. |
| **Variable del entorno** | `COMPlus_TieredCompilation` | `1`: habilitado.<br/>`0`: deshabilitado. |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a>JIT rápido

- Configura si el compilador JIT usa *JIT rápido*. En el caso de los métodos que no contienen bucles y para los que no hay código compilado previamente, JIT rápido los compila más rápidamente, pero sin optimizaciones.
- La habilitación de JIT rápido reduce el tiempo de inicio, pero puede generar código con características de rendimiento degradadas. Por ejemplo, el código puede usar más espacio de pila, asignar más memoria y ejecutarse más lentamente.
- Si JIT rápido está deshabilitado pero la [compilación en niveles](#tiered-compilation) está habilitada, solo el código compilado previamente participa en la compilación en niveles. Si un método no está compilado previamente con [ReadyToRun](#readytorun), el comportamiento de JIT es el mismo que si la [compilación en niveles](#tiered-compilation) estuviera deshabilitada.
- En .NET Core 3.0 y versiones posteriores, JIT rápido está habilitado de forma predeterminada.
- En .NET Core 2.1 y 2.2, JIT rápido está deshabilitado de forma predeterminada.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJit` | `true`: habilitado.<br/>`false`: deshabilitado. |
| **Propiedad de MSBuild** | `TieredCompilationQuickJit` | `true`: habilitado.<br/>`false`: deshabilitado. |
| **Variable del entorno** | `COMPlus_TC_QuickJit` | `1`: habilitado.<br/>`0`: deshabilitado. |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a>JIT rápido para bucles

- Configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.
- La habilitación de JIT rápido para bucles puede mejorar el rendimiento de inicio. Pero los bucles de ejecución prolongada se pueden bloquear en código menos optimizado durante períodos largos.
- Si [JIT rápido](#quick-jit) está deshabilitado, este valor no tiene ningún efecto.
- Predeterminado: deshabilitado (`false`).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJitForLoops` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Propiedad de MSBuild** | `TieredCompilationQuickJitForLoops` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Variable del entorno** | `COMPlus_TC_QuickJitForLoops` | `0`: deshabilitado.<br/>`1`: habilitado. |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a>ReadyToRun

- Configura si el entorno de ejecución de .NET Core usa código precompilado para las imágenes con datos de ReadyToRun disponibles. Al deshabilitar esta opción, se fuerza al entorno de ejecución a compilar código de marco mediante JIT.
- Para obtener más información, vea [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).
- Predeterminado: habilitado (`1`).

| | Nombre de valor | Valores |
| - | - | - |
| **Variable del entorno** | `COMPlus_ReadyToRun` | `1`: habilitado.<br/>`0`: deshabilitado. |
