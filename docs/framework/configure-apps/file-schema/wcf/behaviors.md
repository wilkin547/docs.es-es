---
title: "&lt;comportamientos&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;comportamientos&gt;
Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.  Su atributo de `name` único identifica cada elemento de comportamiento.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel\>  
  
## Sintaxis  
  
```  
  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguna  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation \(WCF\).|  
  
## Comentarios  
 Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.  Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.  También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>   
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>   
 [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)   
 [Configuración de los comportamientos del cliente](../../../../../docs/framework/wcf/configuring-client-behaviors.md)   
 [Especificación del comportamiento de tiempo de ejecución del cliente](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [Especificación del comportamiento en tiempo de ejecución del servicio](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)