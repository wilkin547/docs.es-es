---
title: "&lt;identidad&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;identidad&gt;
El elemento de identidad permite a un programador del cliente especificar en tiempo de diseño la identidad esperada del servicio.  En el proceso de protocolo de enlace entre el cliente y el servicio, la infraestructura de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] se asegurará de que la identidad del servicio esperado coincida con los valores de este elemento y, por tanto, pueda autenticarse.  Para obtener más información, consulta [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Sintaxis  
  
```  
  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|certificate|Especifica los valores de un certificado X.509.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateElement>.  Contiene un atributo `encodedValue` que es una cadena, que especifica el valor codificado por este certificado.|  
|certificateReference|Especifica los valores para la validación del certificado X.509.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Especifica el DNS de un certificado X.509 usado para autenticar un servicio.  Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.|  
|rsa|Especifica el valor del campo RSA de un certificado X.509 usado para autenticar un servicio a un cliente.  Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.|  
|servicePrincipalName|Especifica una identidad del nombre de entidad de seguridad de servidor \(SPN\) que es el nombre de entidad de seguridad usado por un cliente para identificar de manera unívoca una instancia de un servicio.  Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Especifica una identidad del nombre principal del usuario \(UPN\), que es el tipo de nombre de inicio de sesión de un usuario en una red.  El nombre principal del usuario se compone del nombre de objeto del usuario usado en Active Directory, seguido por el símbolo \(@\) y a continuación, normalmente, el dominio primario del Sistema de nombres de dominio \(DNS\).  Por ejemplo, Jeff en el árbol de dominios de Fabrikam.com podría tener el nombre principal de usuario [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<personalizadas\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Especifica la resolución del mismo nivel personalizado de un netPeerTcpBinding.|  
|[\<endpoint\>](http://msdn.microsoft.com/es-es/13aa23b7-2f08-4add-8dbf-a99f8127c017)|Configura tipos diferentes de extremos.|  
|[\<issuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Especifica el servicio de token de seguridad \(STS\) para el servicio aliado.|  
|[\<issuerMetadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Especifica el extremo de metadatos para el servicio de token de seguridad \(STS\) de un servicio aliado.|  
|[\<IssuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Define los parámetros para un token emitido en un enlace personalizado.|  
|[\<localIssuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Especifica un servicio de token de seguridad \(STS\) local.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Extremos: direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)