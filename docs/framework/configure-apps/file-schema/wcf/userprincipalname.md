---
title: "&lt;userPrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;userPrincipalName&gt;
Especifica el Nombre principal de usuario \(UPN\) de un servicio que va a autenticar el cliente.  
  
 Para obtener más información sobre la configuración de UPN, consulte [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Sintaxis  
  
```  
  
<userPrincipalName value = "String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|value|Un nombre de cuenta de usuario \(a veces denominado nombre de inicio de sesión de usuario\) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.  Éste es el uso estándar para iniciar sesión en un dominio de Windows.  El formato es: nombre@ejemplo.com \(para una dirección de correo electrónico\).|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## Comentarios  
 Un cliente [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] seguro que se conecta a un extremo con esta identidad utiliza UPN al realizar la autenticación de SSPI con el extremo.  
  
## Ejemplo  
 El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.  
  
```  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.UpnEndpointIdentity>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)