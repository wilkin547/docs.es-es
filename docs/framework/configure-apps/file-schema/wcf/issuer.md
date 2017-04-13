---
title: "&lt;issuer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;issuer&gt;
Especifica el servicio de token de seguridad \(STS\) que emite los tokens de seguridad.  
  
## Sintaxis  
  
```  
  
<issuer address="Uri" >  
   <headers>  
      <add name="String"  
                 namespace="String" />  
   </headers>  
   <identity>  
           <certificate encodedValue="String"/>  
      <certificateReference findValue="String"   
         isChainIncluded="Boolean"  
         storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
         storeLocation="LocalMachine/CurrentUser"  
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuer>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|address|Cadena necesaria.  La dirección URL del STS.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<encabezados\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Una colección de encabezados de dirección para los extremos que el generador puede crear.|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|Obtiene la configuración de seguridad a nivel de mensaje para el elemento [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Capacidades de seguridad con enlaces personalizados](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)