---
title: "&lt;behavior&gt; de &lt;endpointBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;behavior&gt; de &lt;endpointBehaviors&gt;
El elemento `behavior` contiene una colección de valores para el comportamiento de un extremo.  Su `name` indiza cada comportamiento.  Los extremos se pueden vincular a cada comportamiento a través de este nombre.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## Sintaxis  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento.  Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
|[\<callbackDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|Especifica la depuración de servicio para un objeto de devolución de llamada [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
|[\<callbackTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|Especifica el tiempo de espera para la devolución de la llamada del cliente.|  
|[\<clientVia\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|Especifica la ruta que un mensaje debe tomar.|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<dispatcherSynchronization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.|  
|[\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|Habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.  El comportamiento solo se debería usar junto con el enlace estándar \<webHttpBinding\> o el elemento de enlace \<webMessageEncoding\>.|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Especifica las distintas configuraciones de detección para un extremo, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.|  
|[\<soapProcessing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|Define el comportamiento del extremo de cliente usado para calcular las referencias entre distintos tipos de enlaces y versiones de mensajes.|  
|[\<synchronousReceive\>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|Especifica el comportamiento de tiempo de ejecución para recibir los mensajes en una aplicación de servicio o de cliente.  No tiene ningún atributo o elementos secundarios.|  
|[\<transactedBatching\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.|  
|[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|Especifica WebHttpBehavior en un extremo a través de la configuración.  Este comportamiento, cuando se usa junto con el enlace estándar \<webHttpBinding\>, habilita el modelo de programación web para un servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Una colección de elementos de comportamiento del extremo.|