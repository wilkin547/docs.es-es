---
title: Advertencia SYSLIB0006
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0006.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: c1eecade9280ac37917bc24aa2973756c7f08d87
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596399"
---
# <a name="syslib0006-threadabort-is-not-supported"></a><span data-ttu-id="5889f-103">SYSLIB0006: Thread.Abort no se admite</span><span class="sxs-lookup"><span data-stu-id="5889f-103">SYSLIB0006: Thread.Abort is not supported</span></span>

<span data-ttu-id="5889f-104">Las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="5889f-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="5889f-105">El uso de estas API genera una advertencia `SYSLIB0006` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5889f-105">Use of these APIs generates warning `SYSLIB0006` at compile time.</span></span>

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="5889f-106">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="5889f-106">Workarounds</span></span>

<span data-ttu-id="5889f-107">Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5889f-107">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5889f-108">En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="5889f-108">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

```csharp
void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
{
    if (QueryIsMoreWorkPending())
    {
        // If the CancellationToken is marked as "needs to cancel",
        // this will throw the appropriate exception.
        cancellationToken.ThrowIfCancellationRequested();

        WorkItem work = DequeueWorkItem();
        ProcessWorkItem(work);
    }
}
```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="5889f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5889f-109">See also</span></span>

- [<span data-ttu-id="5889f-110">Thread.Abort obsoleto</span><span class="sxs-lookup"><span data-stu-id="5889f-110">Thread.Abort is obsolete</span></span>](../core-libraries/5.0/thread-abort-obsolete.md)
- [<span data-ttu-id="5889f-111">Cancelación de subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="5889f-111">Cancellation in managed threads</span></span>](../../../standard/threading/cancellation-in-managed-threads.md)
