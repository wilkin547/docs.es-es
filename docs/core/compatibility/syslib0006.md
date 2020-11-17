---
title: Advertencia SYSLIB0006
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0006.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 222b669a8a0260713e85721e6031144bb7bda5cc
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440665"
---
# <a name="syslib0006-threadabort-is-not-supported"></a>SYSLIB0006: Thread.Abort no se admite

Las siguientes API se han marcado como obsoletas a partir de .NET 5.0. El uso de estas API genera una advertencia `SYSLIB0006` en tiempo de compilación.

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluciones alternativas

Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [Thread.Abort está obsoleto: cambio importante](3.1-5.0.md#threadabort-is-obsolete)
- [Cancelación de subprocesos administrados](../../standard/threading/cancellation-in-managed-threads.md)
