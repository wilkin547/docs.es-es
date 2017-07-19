---
title: "&lt;serviceDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;serviceDiscovery&gt;
Especifica la detectabilidad de extremos de servicio.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </announcementEndpoints>  
        <discoveryEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </discoveryEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Colección de extremos de anuncio.  Utilice esta sección para especificar los extremos que se van a usar para enviar mensajes de anuncio.|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Colección de extremos de detección.  Utilice esta sección para especificar los extremos en los que se van a escuchar mensajes de detección.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los extremos de ese servicio en detectables.  Puede seguir configurando las características de detección de tales extremos usando los elementos secundarios [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) o [\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md).  Use la sección [\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) para configurar los anuncios especificando la configuración del extremo que se va a utilizar para enviar los anuncios del servicio \(en línea\/Hola y sin conexión\/Adiós\).  Utilice la sección [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) para especificar manualmente el extremo en el que se van a escuchar los mensajes de detección.  
  
## Ejemplo  
 El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el extremo del anuncio que se va a utilizar.  
  
```  
  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
  ...  
  </service>  
</services>  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="udpEndpoint"  
                        kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>