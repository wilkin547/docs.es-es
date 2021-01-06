---
title: Advertencia SYSLIB0004
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0004.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 03be8bb54f71f74ed94ee2c3f8489397ae1e99b5
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596400"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="8f88c-103">SYSLIB0004: no se admite la característica de regiones de ejecución restringidas (CER)</span><span class="sxs-lookup"><span data-stu-id="8f88c-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="8f88c-104">La característica de [regiones de ejecución restringidas (CER)](../../../framework/performance/constrained-execution-regions.md) solo se admite en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f88c-104">The [Constrained execution regions (CER)](../../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="8f88c-105">Por tanto, varias API relacionadas con CER se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="8f88c-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="8f88c-106">El uso de estas API genera una advertencia `SYSLIB0004` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8f88c-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="8f88c-107">Las siguientes API relacionadas con CER están obsoletas:</span><span class="sxs-lookup"><span data-stu-id="8f88c-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="8f88c-108">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="8f88c-108">Workarounds</span></span>

- <span data-ttu-id="8f88c-109">Si ha aplicado un atributo CER a un método, quite el atributo.</span><span class="sxs-lookup"><span data-stu-id="8f88c-109">If you have applied a CER attribute to a method, remove the attribute.</span></span> <span data-ttu-id="8f88c-110">Estos atributos no tienen ningún efecto en .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f88c-110">These attributes have no effect in .NET 5.0 and later versions.</span></span>

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

- <span data-ttu-id="8f88c-111">Si llama a `RuntimeHelpers.ProbeForSufficientStack` o `RuntimeHelpers.PrepareContractedDelegate`, quite la llamada.</span><span class="sxs-lookup"><span data-stu-id="8f88c-111">If you are calling `RuntimeHelpers.ProbeForSufficientStack` or `RuntimeHelpers.PrepareContractedDelegate`, remove the call.</span></span> <span data-ttu-id="8f88c-112">Estas llamadas no tienen ningún efecto en .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f88c-112">These calls have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething()
  {
      // REMOVE the call below.
      RuntimeHelpers.ProbeForSufficientStack();

      // (Remainder of your method logic here.)
  }
  ```

- <span data-ttu-id="8f88c-113">Si llama a `RuntimeHelpers.PrepareConstrainedRegions`, quite la llamada.</span><span class="sxs-lookup"><span data-stu-id="8f88c-113">If you are calling `RuntimeHelpers.PrepareConstrainedRegions`, remove the call.</span></span> <span data-ttu-id="8f88c-114">Esta llamada no tiene ningún efecto en .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f88c-114">This call has no effect in .NET 5.0 and later versions.</span></span>

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

- <span data-ttu-id="8f88c-115">Si llama a `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, reemplace la llamada por un bloque _try / catch / finally_ estándar.</span><span class="sxs-lookup"><span data-stu-id="8f88c-115">If you are calling `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, replace the call with a standard _try / catch / finally_ block.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8f88c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f88c-116">See also</span></span>

- [<span data-ttu-id="8f88c-117">Regiones de ejecución restringidas</span><span class="sxs-lookup"><span data-stu-id="8f88c-117">Constrained execution regions</span></span>](../../../framework/performance/constrained-execution-regions.md)
