---
title: "&lt;byteStreamMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;byteStreamMessageEncoding&gt;
Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.  
  
## Sintaxis  
  
```  
  
<byteStreamMessageEncoding/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|messageVersion|Especifica la versión SOAP de los mensajes enviados utilizando el enlace.  Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los extremos configurados con este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>   
 [Codificación de mensajes](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)