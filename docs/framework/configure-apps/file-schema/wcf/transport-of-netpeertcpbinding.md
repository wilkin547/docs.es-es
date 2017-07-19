---
title: "Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt;
Especifica la configuración de la seguridad de nivel de transporte al utilizar [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).  
  
## Sintaxis  
  
```  
  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|credentialType|Opcional.  Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.  Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## Atributo credentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Certificado|La autenticación del transporte de canal del mismo nivel requiere un certificado X509.|  
|Contraseña|La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|Define la configuración de seguridad del [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)