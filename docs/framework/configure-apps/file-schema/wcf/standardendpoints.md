---
title: "&lt;standardEndpoints&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;standardEndpoints&gt;
Esta sección de configuración le permite definir una colección de extremos estándar, que son los extremos preconfigurados reutilizables.  Un extremo estándar tendrá uno o más atributos de la dirección, el enlace y el contrato establecidos en un valor fijo.  Por ejemplo, en el extremo de la detección el contrato es fijo.  También puede usar los extremos estándar para extender el extremo de servicio con nuevas propiedades similares a la definición de enlaces personalizados.  
  
 \<system.ServiceModel\>  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Define un extremo estándar con un contrato de anuncio fijo.  Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.  Un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] especifica los extremos del anuncio en el elemento [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) y utiliza AnnouncementClient para realizar los anuncios.  Un cliente que desea escuchar el anuncio de otro servicio realmente está actuando como un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]; por tanto, tendrá que configurar los extremos del anuncio para dicho cliente en la sección [\<servicios\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md).|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Define un extremo estándar con un contrato de detección fijo.  Cuando se agrega a la configuración de servicio, especifica dónde escuchar los mensajes de detección.  Cuando se agrega a la configuración del cliente, especifica dónde enviar las consultas de detección.|  
|[\<dynamicEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|Este elemento de configuración define un extremo estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del extremo dinámicamente en tiempo de ejecución.|  
|[\<mexEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|Define un extremo estándar con un contrato IMetadataExchange fijo.  Puesto que todos los extremos del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.|  
|[\<udpAnnoucementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Define un extremo estándar que usan los servicios para enviar mensajes de anuncio a través de un enlace de UDP.  Tiene un contrato fijo y admite dos versiones de la detección.  Además, tiene un enlace de UDP fijo y un valor de dirección predeterminado según se indica en las especificaciones de WS\-Discovery \(WS\-Discovery April 2005 o WS\-Discovery versión 1.1\).  Puede especificar la dirección de multidifusión que se va a usar para enviar y recibir los mensajes del anuncio.|  
|[\<udpDiscoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Define un extremo estándar que se pre\-configura para las operaciones de detección en un enlace de multidifusión de UDP.  Este extremo tiene un contrato fijo y admite dos versiones del protocolo WS\-Discovery.  Además, tiene un enlace de UDP fijo y una dirección predeterminada según se indica en las especificaciones de WS\-Discovery \(WS\-Discovery April 2005 o WS\-Discovery V1.1\).|  
|[\<webHttpEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|Define un extremo estándar con un enlace [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fijo que agrega automáticamente el comportamiento [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md).  Utilice este extremo al escribir un servicio REST.|  
|[\<webScriptEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|Define un extremo estándar con un enlace [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fijo que agrega automáticamente el comportamiento [\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md).  Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.|  
|[\<workflowControlEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|Define un extremo estándar para controlar la ejecución de instancias de flujo de trabajo \(crear, ejecutar, suspender, terminar, etc\).|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<system.ServiceModel\>|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## Vea también  
 [Extremos estándar](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)