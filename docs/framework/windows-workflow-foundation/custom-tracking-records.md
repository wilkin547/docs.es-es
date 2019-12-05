---
title: Registros de seguimiento personalizados
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 986f0350c24414d0ff960474445adf6ac3f39734
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802627"
---
# <a name="custom-tracking-records"></a>Registros de seguimiento personalizados

En este tema se muestra cómo crear registros del seguimiento personalizados y cómo rellenarlos con datos que se van a emitir junto con los registros.

## <a name="emitting-custom-tracking-records"></a>Emitir registros de seguimiento personalizados

Tal y como se muestra en el ejemplo siguiente, se pueden emitir registros de seguimiento personalizados de una actividad de código.

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

La clase <xref:System.Activities.Tracking.CustomTrackingRecord> se emite en una actividad de código al invocar el método <xref:System.Activities.NativeActivityContext.Track%2A> en la clase `ActivityContext`.

## <a name="see-also"></a>Vea también

- [Supervisión de Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
