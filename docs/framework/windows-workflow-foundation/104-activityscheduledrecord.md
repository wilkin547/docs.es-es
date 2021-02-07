---
description: 'Más información acerca de: 104-ActivityScheduledRecord'
title: 104 - ActivityScheduledRecord
ms.date: 03/30/2017
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
ms.openlocfilehash: 9d52dac3ec68de0d38959e81294c5c6ead21428e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667816"
---
# <a name="104---activityscheduledrecord"></a>104 - ActivityScheduledRecord

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Identificador|104|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una actividad en una instancia de flujo de trabajo emite ActivityScheduledRecord.  
  
## <a name="message"></a>Message  

 TrackRecord = ActivityScheduledRecord, InstanceID = %1,  RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|Nombre|xs:string|El nombre de la actividad que programó la actividad secundaria.|  
|ActivityId|xs:string|El id. de la actividad que programó la actividad secundaria.|  
|ActivityInstance|xs:string|El id. de la instancia de la actividad que programó la actividad secundaria.|  
|ActivityTypeName|xs:string|El tipo de la actividad que solicitó la operación de cancelación.|  
|ChildActivityName|xs:string|El nombre de la actividad programada.|  
|ChildActivityId|xs:string|El id. de la actividad programada.|  
|ChildActivityInstanceId|xs:string|El id. de instancia de la actividad programada.|  
|ChildActivityTypeName|xs:string|El tipo de la actividad programada.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso virtual de la aplicación del nombre del sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName ' ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
