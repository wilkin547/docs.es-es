---
title: 106 - CancelRequestRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f72a59aa-8093-4a8e-94df-40acaffb1ffb
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5ff1d76ace5c11e788b3259ec6e0467e12348d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="106---cancelrequestrecord"></a>106 - CancelRequestRecord
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|106|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 El participante de seguimiento de ETW emite este evento cuando una actividad en una instancia de flujo de trabajo emite cancelrequestedrecord.  
  
## <a name="message"></a>Mensaje  
 TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|Name|xs:string|El nombre de la actividad que solicitó la operación de cancelación.|  
|ActivityId|xs:string|El id. de la actividad que solicitó la operación de cancelación.|  
|ActivityInstance|xs:string|El id. de instancia de la actividad que solicitó la operación de cancelación.|  
|ActivityTypeName|xs:string|El tipo de la actividad que solicitó la operación de cancelación.|  
|ChildActivityName|xs:string|El nombre de la actividad que se va a cancelar.|  
|ChildActivityId|xs:string|El id. de la actividad que se va a cancelar.|  
|ChildActivityInstanceId|xs:string|El id. de instancia de la actividad que se va a cancelar.|  
|ChildActivityTypeName|xs:string|El tipo de la actividad que se va a cancelar.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre de elemento = "annotationName" Type = "> annotationValue\</artículo > \< /artículos >.  Si se especifica ninguna anotación, a continuación, la cadena contiene \<elementos / >. El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >...  \< /artículos >.|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; NombreServicio ' ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
