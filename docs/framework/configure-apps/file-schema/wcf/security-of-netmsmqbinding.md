---
title: "Elemento &lt;security&gt; de &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# Elemento &lt;security&gt; de &lt;netMsmqBinding&gt;
Define la configuración de seguridad de un enlace MSMQ.  Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.  
  
## Sintaxis  
  
```  
  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.  Los valores válidos son los siguientes:<br /><br /> -   Ninguno: esto deshabilita la seguridad.<br />-   Transporte: el transporte proporciona la protección y la autenticación.  Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.  No se proporciona seguridad entre la aplicación y el administrador de cola.  Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.<br />-   Message: especifica la seguridad de la aplicación final.  No se proporciona seguridad en el nivel de transporte.  Esto es similar a la seguridad proporcionada por otros enlaces estándar.<br />-   Both: proporciona seguridad en el transporte y en la capa de mensajería SOAP.  Se requiere la misma credencial en ambos niveles.<br /><br /> El valor predeterminado es Transport.  Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|Define la configuración de seguridad del mensaje SOAP.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|Define la configuración de seguridad del transporte MSMQ.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|enlace|El elemento de enlace del [\<netMsmqBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>   
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)   
 [Colas en WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)