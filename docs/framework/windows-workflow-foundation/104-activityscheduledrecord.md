---
title: "104 - ActivityScheduledRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 104 - ActivityScheduledRecord
## Propiedades  
  
|||  
|-|-|  
|Id.|104|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 El participante de seguimiento de ETW emite este evento cuando una actividad en una instancia de flujo de trabajo emite ActivityScheduledRecord.  
  
## Mensaje  
 TrackRecord \= ActivityScheduledRecord, InstanceID \= %1,  RecordNumber \= %2, EventTime \= %3, Name \= %4, ActivityId \= %5, ActivityInstanceId \= %6, ActivityTypeName \= %7, ChildActivityName \= %8, ChildActivityId \= %9, ChildActivityInstanceId \= %10, ChildActivityTypeName \=%11, Annotations\=%12, ProfileName \= %13  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|Name|xs:string|El nombre de la actividad que programó la actividad secundaria.|  
|ActivityId|xs:string|El id. de la actividad que programó la actividad secundaria.|  
|ActivityInstanceId|xs:string|El id. de la instancia de la actividad que programó la actividad secundaria.|  
|ActivityTypeName|xs:string|El tipo de la actividad que solicitó la operación de cancelación.|  
|ChildActivityName|xs:string|El nombre de la actividad programada.|  
|ChildActivityId|xs:string|El id. de la actividad programada.|  
|ChildActivityInstanceId|xs:string|El id. de instancia de la actividad programada.|  
|ChildActivityTypeName|xs:string|El tipo de la actividad programada.|  
|Annotations|xs:string|Las anotaciones que se agregaron a este evento.Los valores se almacenan en un elemento xml con el formato\<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\>.Si no se especifica ninguna anotación, la cadena contendrá \<items\/\>.El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<items\>...\<\/items.\>|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.Su formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio' Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|