---
title: 103 - ActivityStateRecord
ms.date: 03/30/2017
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
ms.openlocfilehash: 02c33f02b7650c9f9b7527c319de3b58980fdd6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275081"
---
# <a name="103---activitystaterecord"></a>103 - ActivityStateRecord

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Identificador|103|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 El participante de seguimiento de ETW emite este evento cuando una actividad en una instancia de flujo de trabajo emite ActivityStateRecord.  
  
## <a name="message"></a>Message  

 TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|State|xs:string|El estado de la actividad.|  
|NOMBRE|xs:string|El nombre para mostrar de la actividad que emitió el evento.|  
|ActivityId|xs:string|El id. de actividad de la actividad que se emite.|  
|ActivityInstance|xs:string|El id. de instancia de la actividad de la actividad que se emite.|  
|ActivityTypeName|xs:string|El nombre del tipo de la actividad que se emite.|  
|Argumentos|xs:string|Los argumentos a los que se realizó el seguimiento con este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "argumentName" type="System.String"> argumentValue \</item> \</items> .  Si no se realiza un seguimiento de ningún argumento, la cadena contiene \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .  Los tipos siguientes se almacenan como su valor devuelto por ToString (); String, Char, bool, int, Short, Long, uint, ushort, Ulong, System. single, Float, Double, System. GUID, System. DateTimeOffset, System. DateTime.  Todos los demás tipos se serializan con System.Runtime.Serialization.NetDataContractSerializer.|  
|Variables|xs:string|Las variables a las que se realizó el seguimiento con este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "variableName" type="System.String"> variableValue \</item> \</items> .  Si no se realizara el seguimiento de ninguna variable, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de las variables con \<items> ... \</items> .  Los tipos siguientes se almacenan como su valor devuelto por ToString (); String, Char, bool, int, Short, Long, uint, ushort, Ulong, System. single, Float, Double, System. GUID, System. DateTimeOffset, System. DateTime.  Todos los demás tipos se serializan con System.Runtime.Serialization.NetDataContractSerializer.|  
|anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento XML con el formato \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Si no se especifica ninguna anotación, la cadena contendrá \<items/> . El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación por \<items> ... \</items> .|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso virtual de la aplicación del nombre del sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName ' ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
