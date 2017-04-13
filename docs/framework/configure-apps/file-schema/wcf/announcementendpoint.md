---
title: "&lt;announcementEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;announcementEndpoint&gt;
Este elemento de configuración define un extremo estándar con un contrato del anuncio fijo.  Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.  Un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] especifica los extremos del anuncio en el elemento [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) y utiliza AnnouncementClient para realizar los anuncios.  Un cliente que desea escuchar el anuncio de otro servicio realmente está actuando como un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]; por tanto, tendrá que configurar los extremos del anuncio para dicho cliente en la sección [\<servicios\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md).  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <announcementEndpoint>   
          <standardEndpoint  
                  discoveryVersion=”WSDiscovery11/WSDiscoveryApril2005”  
                  maxAnnouncementDelay=”Timespan”   
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
|name|Cadena que especifica el nombre de la configuración del extremo estándar.  El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de extremos estándar que son extremos predefinidos con una o más de sus propiedades \(dirección, enlace, contrato\) fijas.|  
  
## Ejemplo  
 En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.  
  
```  
  
<services>  
  <service name="ServiceAnnouncementListener">  
              <endpoint name="httpAnnouncementEndpoint"  
                        kind="announcementEndpoint"  
                        binding="basicHttpBinding"  
                        address="announcements" />  
              <endpoint name="peerNetAnnouncementEndpoint"  
                        kind="announcementEndpoint"  
                        binding="peerTcpBinding"  
                        address="net.p2p://discoveryMesh/multicast"  
                        bindingConfiguration="discoveryPeerTcpBindingConfig" />  
  ...  
  </service>  
</services>  
  
<standardEndpoints>  
  <announcementEndpoint>  
     <standardEndpoint name="httpAnnouncementEndpoint"                         
                       version="WSDiscoveryApril2005" />  
     <standardEndpoint name="peerNetAnnouncementEndpoint"                         
                       version="WSDiscoveryApril2005" />  
   </announcementEndpoint>  
</standardEndpoints>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>