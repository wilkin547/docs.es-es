---
title: "Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;
Define todas las funciones de seguridad de [\<wsDualHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).  
  
## Sintaxis  
  
```  
  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|-   Opcional.  Especifica el tipo de seguridad que se aplica.  El valor predeterminado es `Message`.  Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.|  
  
## Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|La seguridad está deshabilitada.|  
|Mensaje|La seguridad se proporciona mediante la seguridad del mensaje SOAP.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|Define la configuración de seguridad del nivel del mensaje.  Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funciones de enlace de [\<wsDualHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).|  
  
## Comentarios  
 Un enlace dual expone la dirección IP del cliente al servicio.  El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.  
  
## Vea también  
 <xref:System.ServiceModel.WSDualHttpSecurity>   
 <xref:System.ServiceModel.WsDualHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WsDualHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.WsDualHttpSecurityElement>   
 <xref:System.ServiceModel.BasicHttpSecurity>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)