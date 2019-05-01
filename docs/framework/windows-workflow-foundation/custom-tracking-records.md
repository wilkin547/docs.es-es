---
title: Registros de seguimiento personalizados
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: d4733b4ffc0d866cf90fd5a5e7d649de261c45fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945839"
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

- [Supervisión de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Supervisión de aplicaciones con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
