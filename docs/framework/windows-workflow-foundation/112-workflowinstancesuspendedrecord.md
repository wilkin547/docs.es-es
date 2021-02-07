---
description: 'Más información acerca de: 112-WorkflowInstanceSuspendedRecord'
title: 112 - WorkflowInstanceSuspendedRecord
ms.date: 03/30/2017
ms.assetid: bc825c7c-8c90-48f7-9336-9a978a8246c6
ms.openlocfilehash: 6d2088da6e395476bba05d5e2f4557ea527ecdd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667400"
---
# <a name="112---workflowinstancesuspendedrecord"></a>112 - WorkflowInstanceSuspendedRecord

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Identificador|112|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceSuspended Record.  
  
## <a name="message"></a>Message  

 TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|Motivo|xs:string|La razón por la que se suspendió el flujo de trabajo.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso virtual de la aplicación del nombre del sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName ' ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
