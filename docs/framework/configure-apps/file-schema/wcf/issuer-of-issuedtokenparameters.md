---
title: "&lt;issuer&gt; de &lt;issuedTokenParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;issuer&gt; de &lt;issuedTokenParameters&gt;
Especifica el servicio de token de seguridad \(STS\) que emite los tokens de seguridad.  
  
## Sintaxis  
  
```  
  
<issuer address="Uri" />  
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
|[\<IssuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Especifica el token emitido actual.|  
  
## Vea también  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Capacidades de seguridad con enlaces personalizados](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Seguridad de enlace personalizado](../../../../../docs/framework/wcf/samples/custom-binding-security.md)