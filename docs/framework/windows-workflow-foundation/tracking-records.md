---
title: "Registros de seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Registros de seguimiento
El tiempo de ejecución del flujo de trabajo sirve para emitir los registros de seguimiento con el fin de seguir la ejecución de una instancia de flujo de trabajo.  
  
## Registros de seguimiento  
 En la siguiente tabla se detallan los registros de seguimiento que emite el tiempo de ejecución del flujo de trabajo.  
  
|Registro de seguimiento|Descripción|  
|-----------------------------|-----------------|  
|Registros de ciclo de vida del flujo de trabajo|Emitidos durante varias fases del ciclo de vida de la instancia de flujo de trabajo.Por ejemplo, se emite un registro cuando el flujo de trabajo se inicia o se completa.|  
|Registros de ciclo de vida de la actividad|Describe la ejecución de la actividad.Estos registros indican el estado de una actividad de flujo de trabajo como cuándo se programa una actividad, cuándo se completa o cuándo se produce un error.|  
|Registro de reanudación de marcadores|Se emite siempre que se reanude un marcador en una instancia de flujo de trabajo.|  
|Registros de seguimiento personalizados|Un autor del flujo de trabajo puede crear registros de seguimiento personalizados y emitirlos en una actividad personalizada.|  
  
 Todos los registros relacionados con el seguimiento que se emitan a partir del tiempo de ejecución de WF derivan de la clase base <xref:System.Activities.Tracking.TrackingRecord>, que contiene el conjunto común de los datos.Los registros de seguimiento muestran el ciclo de vida de un flujo de trabajo simple.Cada registro de seguimiento contiene los detalles sobre el evento de seguimiento asociado, como las propiedades <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>, además de la información adicional específica del tipo de registro de seguimiento.  
  
 El tiempo de ejecución del flujo de trabajo emite los siguientes tipos de objetos <xref:System.Activities.Tracking.TrackingRecord>:  
  
-   **WorkflowInstanceRecord**: esta clase <xref:System.Activities.Tracking.TrackingRecord> describe el ciclo de vida de la instancia de flujo de trabajo.Por ejemplo, se emite un registro cuando el flujo de trabajo se inicia o se completa, y contiene el estado de la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en la clase <xref:System.Activities.Tracking.WorkflowInstanceRecord>.  
  
-   **WorkflowInstanceAbortedRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> cuando una instancia de flujo de trabajo se anula.El registro contiene el motivo de la anulación de la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.  
  
-   **WorkflowInstanceUnhandledExceptionRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> si se produce una excepción en la instancia de flujo de trabajo y no hay ninguna actividad que la administre.El registro contiene los detalles de la excepción.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.  
  
-   **WorkflowInstanceSuspendedRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> siempre que se suspenda una instancia de flujo de trabajo.El registro contiene el motivo de la suspensión de la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.  
  
-   **WorkflowInstanceTerminatedRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> siempre que finaliza una instancia de flujo de trabajo.El registro contiene el motivo de la finalización de la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.  
  
-   **ActivityStateRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> cuando se ejecuta una actividad dentro de un flujo de trabajo.Estos registros indican el estado de la actividad dentro de la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.ActivityStateRecord>.  
  
-   **ActivityScheduledRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> cuando una actividad programa una actividad secundaria.Este registro contiene los detalles para el actividad primaria \(la actividad que se programa\) y la actividad secundaria programada.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
-   **FaultPropagationRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> para cada controlador que examine el registro hasta que se administre.Se utiliza para denotar la ruta de acceso que usó un error en la instancia de flujo de trabajo.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
-   **CancelRequestedRecord**: se emite la clase <xref:System.Activities.Tracking.TrackingRecord> siempre que una actividad intenta cancelar una actividad secundaria.Este registro contiene los detalles para la actividad primaria \(la actividad que se programa\) y la actividad secundaria que se vaya a cancelar.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
-   **BookmarkResumptionRecord**: <xref:System.Activities.Tracking.TrackingRecord> realiza el seguimiento de cualquier marcador que se haya reanudado correctamente.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
-   **CustomTrackingRecord**: un autor de flujo de trabajo crea y emite la clase <xref:System.Activities.Tracking.TrackingRecord> en una actividad de flujo de trabajo personalizada.Los registros de seguimiento personalizados se pueden rellenar con datos que se van a emitir junto con los registros.Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
 Por ejemplo, podría haber una actividad <xref:System.Activities.Statements.Sequence> simple que contenga una operación <xref:System.Activities.Statements.WriteLine> en la que los registros de seguimiento se emitan en el siguiente orden:  
  
1.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica que está comenzando el flujo de trabajo.  
  
2.  <xref:System.Activities.Tracking.ActivityScheduledRecord> indica que se ha programado una actividad.En este caso se trata de una actividad <xref:System.Activities.Statements.Sequence>.  
  
3.  <xref:System.Activities.Tracking.ActivityScheduledRecord> representa la actividad <xref:System.Activities.Statements.WriteLine>.  
  
4.  Hay dos registros <xref:System.Activities.Tracking.ActivityStateRecord> que representan las dos actividades que se están completando.  
  
5.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica que el flujo de trabajo se está completando.  
  
## Vea también  
 [Supervisión de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Supervisión de aplicaciones con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)