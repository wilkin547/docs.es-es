---
title: "100 - WorkflowInstanceRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 100 - WorkflowInstanceRecord
## Propiedades  
  
|||  
|-|-|  
|Id.|100|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceRecord para los estados del flujo de trabajo: iniciado, reanudado, conservado, inactivo, eliminado, completado, cancelado, descargado y no suspendido.  
  
## Mensaje  
 TrackRecord\= WorkflowInstanceRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, Annotations \= %6, ProfileName \= %7  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|State|xs:string|El estado actual del flujo de trabajo.|  
|Annotations|xs:string|Las anotaciones que se agregaron a este evento.Los valores se almacenan en un elemento xml con el formato\<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\>.Si no se especifica ninguna anotación, la cadena contendrá \<items\/\>.El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<items\>...\<\/items.\>|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.Su formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio' Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|