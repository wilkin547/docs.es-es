---
title: Registros de seguimiento personalizados
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: d4733b4ffc0d866cf90fd5a5e7d649de261c45fb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499126"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="2c1a8-102">Registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="2c1a8-102">Custom Tracking Records</span></span>

<span data-ttu-id="2c1a8-103">En este tema se muestra cómo crear registros del seguimiento personalizados y cómo rellenarlos con datos que se van a emitir junto con los registros.</span><span class="sxs-lookup"><span data-stu-id="2c1a8-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="2c1a8-104">Emitir registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="2c1a8-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="2c1a8-105">Tal y como se muestra en el ejemplo siguiente, se pueden emitir registros de seguimiento personalizados de una actividad de código.</span><span class="sxs-lookup"><span data-stu-id="2c1a8-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="2c1a8-106">La clase <xref:System.Activities.Tracking.CustomTrackingRecord> se emite en una actividad de código al invocar el método <xref:System.Activities.NativeActivityContext.Track%2A> en la clase `ActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="2c1a8-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c1a8-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c1a8-107">See also</span></span>

- [<span data-ttu-id="2c1a8-108">Supervisión de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="2c1a8-108">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="2c1a8-109">Supervisión de aplicaciones con App Fabric</span><span class="sxs-lookup"><span data-stu-id="2c1a8-109">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
