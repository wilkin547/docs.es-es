---
description: 'Más información acerca de: 119-WorkflowInstanceUpdatedRecord'
title: 119 - WorkflowInstanceUpdatedRecord
ms.date: 03/30/2017
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
ms.openlocfilehash: e59bbe81d548fccb0d44d6f8c1b442ee6ad685f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703203"
---
# <a name="119---workflowinstanceupdatedrecord"></a>119 - WorkflowInstanceUpdatedRecord

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|119|  
|Palabras clave|HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo se actualiza.  
  
## <a name="message"></a>Message  

 TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|Estado|xs:string|El estado actual del flujo de trabajo.|  
|OriginalDefinitionIdentity|xs:string|Identificador de la definición de flujo de trabajo original|  
|UpdatedDefinitionIdentity|xs:string|Identificador de la dDefinición de flujo de trabajo actualizada.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento. Los valores se almacenan en un elemento XML con el formato \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|WorkflowDefinitionIdentity|xs:string|Id. de definición de flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
