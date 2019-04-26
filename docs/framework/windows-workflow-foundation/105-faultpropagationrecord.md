---
title: 105 - FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: c48f42a91ad9a15b49aad8c1ab684f2348954174
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924207"
---
# <a name="105---faultpropagationrecord"></a>105 - FaultPropagationRecord
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|105|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 El participante de seguimiento de ETW emite este evento cuando una actividad con la instancia de flujo de trabajo emite FaultPropagationRecord.  
  
## <a name="message"></a>Mensaje  
 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|FaultSourceActivityName|xs:string|El nombre de la actividad que emitió el error.|  
|FaultSourceActivityId|xs:string|El id. de la actividad que emitió el error.|  
|FaultSourceActivityInstanceId|xs:string|El id. de la instancia de la actividad que emitió el error.|  
|FaultSourceActivityTypeName|xs:string|El tipo de la actividad que emitió el error.|  
|FaultHandlerActivityName|xs:string|El nombre para mostrar de la actividad del controlador de errores.|  
|FaultHandlerActivityId|xs:string|El id. de la actividad de controlador de errores.|  
|FaultHandlerActivityInstanceId|xs:string|El id. de instancia de la actividad del controlador de errores.|  
|FaultHandlerActivityTypeName|xs:string|El tipo de la actividad de controlador de errores.|  
|Fault|xs:string|Los detalles del error.|  
|IsFaultSource|xs:unsignedByte|Indica si el evento se emitió desde el origen del error.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre del elemento = "annotationName" Type = "> annotationValue\</artículo >\</Items >.  Si se especifica ninguna anotación, la cadena contendría \<elementos / >. El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >... \</Items >.|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;NombreServicio ' ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
