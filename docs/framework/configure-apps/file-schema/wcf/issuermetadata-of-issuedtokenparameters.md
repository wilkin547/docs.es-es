---
title: "&lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt;
## Sintaxis  
  
```  
  
<issuerMetaData address=String"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|address|Requerido.  Cadena que especifica la dirección del extremo.  La dirección debe ser un URI absoluto.  El valor predeterminado es una cadena vacía.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<encabezados\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Una colección de encabezados de dirección.|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Una identidad que habilita la autenticación de un extremo por otros extremos que intercambian mensajes con él.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<IssuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Especifica los parámetros para un símbolo \(token\) de seguridad emitido en un escenario de seguridad aliado.|  
  
## Vea también  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>   
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