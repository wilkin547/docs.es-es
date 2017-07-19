---
title: "&lt;udpAnnoucementEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;udpAnnoucementEndpoint&gt;
Este elemento de configuración define un extremo estándar usado por los servicios para enviar los mensajes del anuncio a través de un enlace de UDP.  Tiene un contrato fijo y admite dos versiones de la detección.  Además, tiene un enlace de UDP fijo y un valor de dirección predeterminado según se indica en las especificaciones de WS\-Discovery \(WS\-Discovery April 2005 o WS\-Discovery versión 1.1\).  Puede especificar la dirección de multidifusión que se va a usar para enviar y recibir los mensajes del anuncio.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <announcementEndpoint>   
          <standardEndpoint  
                  discoveryVersion=”WSDiscovery11/WSDiscoveryApril2005”  
                  maxAnnouncementDelay=”Timespan”   
                  multicastAddress=”Uri”  
                  name="String" />   
       </announcementEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|discoveryVersion|Cadena que especifica una de las dos versiones del protocolo WS\-Discovery.  Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.  Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.DiscoveryVersion>.|  
|maxAnnouncementDelay|Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.  Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.  Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.|  
|multicastAddress|URI que especifica una dirección de multidifusión que se va a usar para enviar y recibir los mensajes de detección.  El valor predeterminado es la dirección de multidifusión como compatible con la especificación de protocolo.|  
|name|Cadena que especifica el nombre de la configuración del extremo estándar.  El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<udpTransportSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|Colección de valores que le permite configurar el transporte UDP para el extremo UDP.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de extremos estándar que son extremos predefinidos con una o más de sus propiedades \(dirección, enlace, contrato\) fijas.|  
  
## Ejemplo  
 En el siguiente ejemplo se muestra un cliente que escucha un anuncio a través de un transporte de multidifusión UDP con una dirección de multidifusión predeterminada y transporte de multidifusión UDP con una dirección de multidifusión especificada.  
  
```  
  
<services>  
  <service name="ServiceAnnouncementListener">  
      <endpoint name="udpAnnouncementEndpointStandard"  
                kind="udpAnnouncementEndpoint"  
                bindingConfiguration="..." />  
      <endpoint name="udpAnnouncementEndpoint2"  
                kind="udpAnnouncementEndpoint"  
                endpointConfiguration="AnnouncementConfiguration3702"  
                bindingConfiguration="..." />  
...  
  </service>  
</services>  
<standardEndpoints>  
  <udpAnnouncementEndpoint>  
     <standardEndpoint name="AnnouncementConfiguration2"   
          version="WSDiscoveryApril2005"   
          multicastAddress="soap.udp://239.255.255.250:3703"/>          
  </udpAnnouncementEndpoint>  
</standardEndpoints>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>