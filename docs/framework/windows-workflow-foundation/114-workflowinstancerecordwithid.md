---
description: 'Más información acerca de: 114-WorkflowInstanceRecordWithId'
title: 114 - WorkflowInstanceRecordWithId
ms.date: 03/30/2017
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
ms.openlocfilehash: 77d39cd91476d9de41bbb00b5df034fc79cdec08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667257"
---
# <a name="114---workflowinstancerecordwithid"></a>114 - WorkflowInstanceRecordWithId

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|114|  
|Palabras clave|HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceRecord para los estados del flujo de trabajo: iniciado, reanudado, conservado, inactivo, eliminado, completado, cancelado, descargado y no suspendido.  
  
## <a name="message"></a>Message  

 TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|Estado|xs:string|El estado actual del flujo de trabajo.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento. Los valores se almacenan en un elemento XML con el formato \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|WorkflowDefinitionIdentity|xs:string|Id. de definición de flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
