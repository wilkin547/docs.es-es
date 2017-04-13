---
title: "Registros de seguimiento personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Registros de seguimiento personalizados
En este tema se muestra cómo crear registros del seguimiento personalizados y cómo rellenarlos con datos que se van a emitir junto con los registros.  
  
## Emitir registros de seguimiento personalizados  
 Tal y como se muestra en el ejemplo siguiente, se pueden emitir registros de seguimiento personalizados de una actividad de código.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 La clase <xref:System.Activities.Tracking.CustomTrackingRecord> se emite en una actividad de código al invocar el método <xref:System.Activities.NativeActivityContext.Track%2A> en la clase `ActvityContext`.  
  
## Vea también  
 [Supervisión de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Supervisión de aplicaciones con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)