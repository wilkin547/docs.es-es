---
title: "&lt;soapProcessing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;soapProcessing&gt;
Define el comportamiento del extremo de cliente usado para calcular las referencias entre distintos tipos de enlaces y versiones de mensajes.  
  
## Sintaxis  
  
```  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|processMessages|Valor booleano que especifica si se deberían calcular las referencias a los mensajes entre las versiones del mensaje SOAP.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un extremo.|  
  
## Comentarios  
 El procesamiento SOAP es el proceso donde los mensajes se convierten entre las versiones del mensaje.  
  
 El servicio de enrutamiento [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] puede convertir los mensajes de un protocolo en otro.  Si las versiones del mensaje de entrada y de salida son diferentes, se crea un nuevo mensaje de la versión correcta.  El procesamiento de los mensajes de una <xref:System.ServiceModel.Channel.MessageVersion> a otra se logra construyendo un nuevo mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que contiene la parte del cuerpo y los encabezados pertinentes del mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] de entrada.  Los encabezados específicos del direccionamiento, o que se interpretan en el nivel del enrutador, no se usan durante la construcción del nuevo mensaje WCF porque estos encabezados son de una versión diferente \(en el caso de los encabezados de direccionamiento\) o se han procesado como parte de la comunicación entre el cliente y el enrutador.  
  
 La colocación de un encabezado en el mensaje de salida está determinada por si se marcó o no como comprendido al atravesar la capa del canal de entrada.  Los encabezados que no se entienden \(como los encabezados personalizados\) no se quitan y pasan así por el servicio del enrutamiento copiándose en el mensaje de salida.  El cuerpo del mensaje se copia en el mensaje de salida.  A continuación, el mensaje se envía al canal de salida en el que se señalan todos los encabezados y se crearán y agregarán otros datos del sobre específicos de dicho protocolo\/transporte de comunicaciones.  
  
 Dichos pasos de procesamiento tienen lugar cuando se especifica el comportamiento del procesamiento SOAP.  Este comportamiento [\<soapProcessingExtension\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) es un comportamiento de extremo que se aplica a todos los extremos \(salientes\) del cliente cuando se inicia el servicio de enrutamiento.  forma predeterminada, el comportamiento [\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) crea y adjunta un nuevo comportamiento [\<soapProcessingExtension\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) con `processMessages` establecido en `true` para cada extremo del cliente.  Si tiene un protocolo que el servicio de enrutamiento no entiende, o desea invalidar el comportamiento del procesamiento predeterminado, puede deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo o solo para determinados extremos. Para deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo en todos los extremos, establezca el atributo `soapProcessing` del comportamiento [\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) en `false`.  Para desactivar el procesamiento SOAP para un extremo determinado, use este comportamiento y establezca el atributo `processMessages` en `false`; a continuación, adjunte este comportamiento al extremo en el que no desea que se ejecute el código de procesamiento predeterminado. Cuando el comportamiento [\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) configura el servicio de enrutamiento, omitirá la reaplicación del comportamiento del extremo puesto que ya existe uno.  
  
## Vea también  
 <xref:System.ServiceModel.Routing.Configuration.> SoapProcessingExtensionElement?qualifyHint=False&autoUpgrade=True   
 <xref:System.ServiceModel.Routing.SoapProcessingBehavior>