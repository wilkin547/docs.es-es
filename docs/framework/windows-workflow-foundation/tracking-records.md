---
description: 'Más información acerca de: seguimiento de registros'
title: Registros de seguimiento
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: ab04f7c964ae8ba64b6c67606031217fbe122951
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755127"
---
# <a name="tracking-records"></a>Registros de seguimiento

El tiempo de ejecución del flujo de trabajo sirve para emitir los registros de seguimiento con el fin de seguir la ejecución de una instancia de flujo de trabajo.  
  
## <a name="tracking-records"></a>Registros de seguimiento  

 En la siguiente tabla se detallan los registros de seguimiento que emite el tiempo de ejecución del flujo de trabajo.  
  
|Registro de seguimiento|Descripción|  
|---------------------|-----------------|  
|Registros de ciclo de vida del flujo de trabajo|Emitidos durante varias fases del ciclo de vida de la instancia de flujo de trabajo. Por ejemplo, se emite un registro cuando el flujo de trabajo se inicia o se completa.|  
|Registros de ciclo de vida de la actividad|Describe la ejecución de la actividad. Estos registros indican el estado de una actividad de flujo de trabajo como cuándo se programa una actividad, cuándo se completa o cuándo se produce un error.|  
|Registro de reanudación de marcadores.|Se emite siempre que se reanude un marcador en una instancia de flujo de trabajo.|  
|Registros de seguimiento personalizados|Un autor del flujo de trabajo puede crear registros de seguimiento personalizados y emitirlos en una actividad personalizada.|  
  
 Todos los registros relacionados con el seguimiento que se emitan a partir del tiempo de ejecución de WF derivan de la clase base <xref:System.Activities.Tracking.TrackingRecord>, que contiene el conjunto común de los datos. Los registros de seguimiento muestran el ciclo de vida de un flujo de trabajo simple. Cada registro de seguimiento contiene los detalles sobre el evento de seguimiento asociado, como las propiedades <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>, además de la información adicional específica del tipo de registro de seguimiento.  
  
 El tiempo de ejecución del flujo de trabajo emite los siguientes tipos de objetos <xref:System.Activities.Tracking.TrackingRecord>:  
  
- **WorkflowInstanceRecord** : <xref:System.Activities.Tracking.TrackingRecord> describe el ciclo de vida de la instancia de flujo de trabajo. Por ejemplo, se emite un registro cuando el flujo de trabajo se inicia o se completa, y contiene el estado de la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceRecord>.  
  
- **WorkflowInstanceAbortedRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando se anula una instancia de flujo de trabajo. El registro contiene el motivo de la anulación de la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.  
  
- **WorkflowInstanceUnhandledExceptionRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite si se produce una excepción en la instancia de flujo de trabajo y no está controlada por ninguna actividad. El registro contiene los detalles de la excepción. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.  
  
- **WorkflowInstanceSuspendedRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando se suspende una instancia de flujo de trabajo. El registro contiene el motivo de la suspensión de la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.  
  
- **WorkflowInstanceTerminatedRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando se finaliza una instancia de flujo de trabajo. El registro contiene el motivo de la finalización de la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.  
  
- **ActivityStateRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando se ejecuta una actividad dentro de un flujo de trabajo. Estos registros indican el estado de la actividad dentro de la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.ActivityStateRecord>.  
  
- **ActivityScheduledRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando una actividad programa una actividad secundaria. Este registro contiene los detalles para el actividad primaria (la actividad que se programa) y la actividad secundaria programada. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
- **FaultPropagationRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite para cada controlador que examina el registro hasta que se controla. Se utiliza para denotar la ruta de acceso que usó un error en la instancia de flujo de trabajo. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
- **CancelRequestedRecord** : <xref:System.Activities.Tracking.TrackingRecord> se emite cuando una actividad intenta cancelar una actividad secundaria. Este registro contiene los detalles para la actividad primaria (la actividad que se programa) y la actividad secundaria que se vaya a cancelar. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
- **BookmarkResumptionRecord** : <xref:System.Activities.Tracking.TrackingRecord> realiza un seguimiento de los marcadores que se reanudan correctamente. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
- **CustomTrackingRecord** : lo <xref:System.Activities.Tracking.TrackingRecord> crea y emite un autor de flujo de trabajo dentro de una actividad de flujo de trabajo personalizada. Los registros de seguimiento personalizados se pueden rellenar con datos que se van a emitir junto con los registros. Los detalles de este registro se pueden encontrar en <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
 Por ejemplo, podría haber una actividad <xref:System.Activities.Statements.Sequence> simple que contenga una operación <xref:System.Activities.Statements.WriteLine> con registros de seguimiento emitidos en el siguiente orden:  
  
1. <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica que está comenzando el flujo de trabajo.  
  
2. <xref:System.Activities.Tracking.ActivityScheduledRecord> indica que se ha programado una actividad. En este caso se trata de una actividad <xref:System.Activities.Statements.Sequence>.  
  
3. <xref:System.Activities.Tracking.ActivityScheduledRecord> representa la actividad <xref:System.Activities.Statements.WriteLine>.  
  
4. Hay dos registros <xref:System.Activities.Tracking.ActivityStateRecord> que representan las dos actividades que se están completando.  
  
5. <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica que el flujo de trabajo se está completando.  
  
## <a name="see-also"></a>Vea también

- [Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))
