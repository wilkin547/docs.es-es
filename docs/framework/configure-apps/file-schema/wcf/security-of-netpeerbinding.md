---
title: "Elemento &lt;security&gt; de &lt;netPeerBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Elemento &lt;security&gt; de &lt;netPeerBinding&gt;
Define la configuración de seguridad de [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte de mensajes.  
  
## Sintaxis  
  
```  
  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|Opcional.  Especifica el tipo de seguridad utilizado por pares configurados con este enlace.  El valor predeterminado es `Message`.  Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Mensaje|La seguridad SOAP proporciona autenticación, integridad y confidencialidad.|  
|Ninguna|La seguridad está deshabilitada.|  
|Transporte|La seguridad se proporciona utilizando HTTPS.|  
|TransportWithMessageCredential|HTTPS proporciona autenticación y confidencialidad.  Los mensajes SOAP proporcionan tipos de credencial enriquecidos.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funciones de enlace de [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Comentarios  
 La seguridad puede ser específica de los mensajes o del transporte.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Selección de tipos de credenciales](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)