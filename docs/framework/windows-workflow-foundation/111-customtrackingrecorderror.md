---
title: "111 - CustomTrackingRecordError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d469fb12-e094-4d6c-9b4d-abd7ce0d17da
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 111 - CustomTrackingRecordError
## Propiedades  
  
|||  
|-|-|  
|Id.|111|  
|Palabras clave|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Error|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 El participante de seguimiento de ETW emite este evento cuando una actividad dentro de una instancia de flujo de trabajo emite CustomTrackingRecord con error de nivel.  
  
## Mensaje  
 TrackRecord \= CustomTrackingRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityName\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Data\=%9, Annotations\=%10, ProfileName \= %11  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|Name|xs:string|El nombre de la clase CustomTrackingRecord.|  
|ActivityName|xs:string|El nombre de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityId|xs:string|El id. de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityInstanceId|xs:string|El id. de instancia de la actividad que emitió la clase CustomTrackingRecord.|  
|ActivityTypeName|xs:string|El nombre de la actividad que emitió la clase CustomTrackingRecord.|  
|Data|xs:string|Los datos a los que se realizó el seguimiento con este evento.Los valores están almacenados en un elemento de xml con el formato \<items\>\< item  name \= "dataName" type\="System.String"\>dataValue\<\/item\>\<\/items\>.Si no se realizara el seguimiento de ningún dato, la cadena contendría \<items\/\>.El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de los datos con \<items\>...\<\/items.\>Los tipos siguientes están almacenados como valores posibles ya que los devuelve ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.Todos los demás tipos se serializan con System.Runtime.Serialization.NetDataContractSerializer.|  
|Annotations|xs:string|Las anotaciones que se agregaron a este evento.Los valores se almacenan en un elemento xml con el formato\<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\>.Si no se especifica ninguna anotación, la cadena contendrá \<items\/\>.El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<items\>...\<\/items.\>|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.Su formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio' Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|