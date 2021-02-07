---
description: 'Más información acerca de: 118-WorkflowInstanceUnhandledExceptionRecordWithId'
title: 118 - WorkflowInstanceUnhandledExceptionRecordWithId
ms.date: 03/30/2017
ms.assetid: 2ce4b193-e141-4cc4-86a3-2e8c984c110d
ms.openlocfilehash: 9d39afb95db8a393b967d590ee37e9f3f2529ffd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703229"
---
# <a name="118---workflowinstanceunhandledexceptionrecordwithid"></a>118 - WorkflowInstanceUnhandledExceptionRecordWithId

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|118|  
|Palabras clave|HealthMonitoring, WFTracking|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Message  

 TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9,  Annotations= %10, ProfileName = %11, WorkflowDefinitionIdentity = %12  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|SourceName|xs:string|El nombre de la actividad de origen con errores que dio como resultado unhandledException.|  
|SourceId|xs:string|El id. de la actividad de origen con errores.|  
|SourceInstanceId|xs:string|El id. de instancia de la actividad de origen con errores.|  
|SourceTypeName|xs:string|El nombre del tipo de actividad de origen con errores que dio como resultado unhandledException.|  
|Excepción|xs:string|La excepción de información sobre la excepción no controlada.|  
|Estado|xs:string|El estado actual del flujo de trabajo.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento. Los valores se almacenan en un elemento XML con el formato \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|WorkflowDefinitionIdentity|xs:string|Id. de definición de flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
