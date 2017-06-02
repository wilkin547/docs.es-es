---
title: "Elemento &lt;security&gt; de &lt;msmqIntegrationBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Elemento &lt;security&gt; de &lt;msmqIntegrationBinding&gt;
Define la configuración de seguridad de transporte para el canal de integración de Message Queuing \(MSMQ\).  
  
## Sintaxis  
  
```  
  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.  Los valores válidos son los siguientes:<br /><br /> -   Ninguno: esto deshabilita la seguridad.<br />-   Transporte: el transporte proporciona la protección y la autenticación.  Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.  No se proporciona seguridad entre la aplicación y el administrador de cola.  Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.<br /><br /> El valor predeterminado es `Transport`.  Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|Define la configuración de seguridad para el transporte de integración de Message Queuing.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|El elemento de enlace del [\<msmqIntegrationBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 [Colas en WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)   
 [\<msmqIntegrationBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)