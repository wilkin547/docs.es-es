---
description: 'Más información acerca de: registros de seguimiento personalizados'
title: Registros de seguimiento personalizados
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 9d6988465fa3afca4302c86e0c2cad2778f2beae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742698"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="365e2-103">Registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="365e2-103">Custom Tracking Records</span></span>

<span data-ttu-id="365e2-104">En este tema se muestra cómo crear registros del seguimiento personalizados y cómo rellenarlos con datos que se van a emitir junto con los registros.</span><span class="sxs-lookup"><span data-stu-id="365e2-104">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="365e2-105">Emitir registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="365e2-105">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="365e2-106">Tal y como se muestra en el ejemplo siguiente, se pueden emitir registros de seguimiento personalizados de una actividad de código.</span><span class="sxs-lookup"><span data-stu-id="365e2-106">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="365e2-107">La clase <xref:System.Activities.Tracking.CustomTrackingRecord> se emite en una actividad de código al invocar el método <xref:System.Activities.NativeActivityContext.Track%2A> en la clase `ActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="365e2-107">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="365e2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="365e2-108">See also</span></span>

- <span data-ttu-id="365e2-109">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="365e2-109">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="365e2-110">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="365e2-110">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
