---
title: Advertencia SYSLIB0004
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0004.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: ba7cd8a890a89000b241d286c9d8069ba1398849
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333180"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="27846-103">SYSLIB0004: no se admite la característica de regiones de ejecución restringidas (CER)</span><span class="sxs-lookup"><span data-stu-id="27846-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="27846-104">La característica de [regiones de ejecución restringidas (CER)](../../framework/performance/constrained-execution-regions.md) solo se admite en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="27846-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="27846-105">Por tanto, varias API relacionadas con CER se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="27846-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="27846-106">El uso de estas API genera una advertencia `SYSLIB0004` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="27846-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="27846-107">Las siguientes API relacionadas con CER están obsoletas:</span><span class="sxs-lookup"><span data-stu-id="27846-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="27846-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="27846-108">See also</span></span>

- [<span data-ttu-id="27846-109">Regiones de ejecución restringidas</span><span class="sxs-lookup"><span data-stu-id="27846-109">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
