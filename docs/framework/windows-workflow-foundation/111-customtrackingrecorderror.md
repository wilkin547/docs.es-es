---
title: 111 - CustomTrackingRecordError
ms.date: 03/30/2017
ms.assetid: d469fb12-e094-4d6c-9b4d-abd7ce0d17da
ms.openlocfilehash: 20c038fda6360c68a84397cde382489b83612536
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294227"
---
# <a name="111---customtrackingrecorderror"></a>111 - CustomTrackingRecordError

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Identificador|111|  
|Palabras clave|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una actividad dentro de una instancia de flujo de trabajo emite CustomTrackingRecord con error de nivel.  
  
## <a name="message"></a>Message  

 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|NOMBRE|xs:string|El nombre de la clase CustomTrackingRecord.|  
|ActivityName|xs:string|El nombre de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityId|xs:string|El id. de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityInstance|xs:string|El id. de instancia de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityTypeName|xs:string|El nombre de la actividad que emitió la clase CustomTrackingRecord.|  
|data|xs:string|Los datos a los que se realizó el seguimiento con este evento.  Los valores se almacenan en un elemento XML con el formato de valor de dataFormat \<items> \< item  name = "dataName" type="System.String"> \</item> \</items> .  Si no se realiza el seguimiento de ningún dato, la cadena contiene \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de datos por \<items> ... \</items> .  Los tipos siguientes se almacenan como su valor devuelto por ToString (); String, Char, bool, int, Short, Long, uint, ushort, Ulong, System. single, Float, Double, System. GUID, System. DateTimeOffset, System. DateTime.  Todos los demás tipos se serializan con System.Runtime.Serialization.NetDataContractSerializer.|  
|anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso virtual de la aplicación del nombre del sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName ' ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
