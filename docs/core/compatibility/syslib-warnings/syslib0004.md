---
title: Advertencia SYSLIB0004
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0004.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 76726e233e2900c82dce1b0872533e5356e91c8c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256377"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a>SYSLIB0004: no se admite la característica de regiones de ejecución restringidas (CER)

La característica de [regiones de ejecución restringidas (CER)](../../../framework/performance/constrained-execution-regions.md) solo se admite en .NET Framework. Por tanto, varias API relacionadas con CER se han marcado como obsoletas a partir de .NET 5.0. El uso de estas API genera una advertencia `SYSLIB0004` en tiempo de compilación.

Las siguientes API relacionadas con CER están obsoletas:

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluciones alternativas

- Si ha aplicado un atributo CER a un método, quite el atributo. Estos atributos no tienen ningún efecto en .NET 5 y versiones posteriores.

  ```csharp
  // REMOVE the attribute below.
  [ReliabilityContract(Consistency.WillNotCorruptState, Cer.Success)]
  public void DoSomething()
  {
  }

  // REMOVE the attribute below.
  [PrePrepareMethod]
  public void DoSomething()
  {
  }
  ```

- Si llama a `RuntimeHelpers.ProbeForSufficientStack` o `RuntimeHelpers.PrepareContractedDelegate`, quite la llamada. Estas llamadas no tienen ningún efecto en .NET 5 y versiones posteriores.

  ```csharp
  public void DoSomething()
  {
      // REMOVE the call below.
      RuntimeHelpers.ProbeForSufficientStack();

      // (Remainder of your method logic here.)
  }
  ```

- Si llama a `RuntimeHelpers.PrepareConstrainedRegions`, quite la llamada. Esta llamada no tiene ningún efecto en .NET 5 y versiones posteriores.

  ```csharp
  public void DoSomething_Old()
  {
      // REMOVE the call below.
      RuntimeHelpers.PrepareConstrainedRegions();
      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }

  public void DoSomething_Corrected()
  {
      // There is no call to PrepareConstrainedRegions. It's a normal try / finally block.

      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

- Si llama a `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, reemplace la llamada por un bloque _try / catch / finally_ estándar.

  ```csharp
  // The sample below produces warning SYSLIB0004.
  public void DoSomething_Old()
  {
      RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(MyTryCode, MyCleanupCode, null);
  }
  public void MyTryCode(object state) { /* try code */ }
  public void MyCleanupCode(object state, bool exceptionThrown) { /* cleanup code */ }

  // The corrected sample below does not produce warning SYSLIB0004.
  public void DoSomething_Corrected()
  {
      try
      {
          // try code
      }
      catch (Exception ex)
      {
          // exception handling code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [Regiones de ejecución restringidas](../../../framework/performance/constrained-execution-regions.md)
