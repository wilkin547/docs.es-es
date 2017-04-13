---
title: "&lt;sslStreamSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# &lt;sslStreamSecurity&gt;
Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.  
  
## Sintaxis  
  
```  
  
<sslStreamSecurity requireClientCertificate="Boolean"  
      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|requireClientCertificate|Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.  De manera predeterminada, es `false`.|  
|sslProtocols|Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.  El valor predeterminado es Ssl3&#124;Tls&#124;Tls11&#124;Tls12.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)