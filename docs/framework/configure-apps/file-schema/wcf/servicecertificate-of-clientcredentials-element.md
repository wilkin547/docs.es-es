---
title: "Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt;
Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.  
  
## Sintaxis  
  
```  
  
<serviceCertificate />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<defaultCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.|  
|[\<scopedCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Representa una colección de certificados X.509 proporcionada por servicios concretos \(con ámbito\) para la autenticación.  Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.|  
|[\<autenticación\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.|  
  
## Comentarios  
 Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL.  También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.  
  
 Los atributos del elemento `serviceCertificate` son idénticos a los atributos del [\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)