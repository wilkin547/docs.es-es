---
title: "&lt;mtomMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;mtomMessageEncoding&gt;
Especifica la codificación y la versión del mensaje utilizada para los mensajes basados en el mecanismo de optimización de la transmisión de mensajes \(MTOM\) SOAP.  
  
## Sintaxis  
  
```  
  
<mtomMessageEncoding   
   maxBufferSize="Integer"  
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing1/Soap12Addressing10"  
      writeEncoding=”UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|maxBufferSize|Un entero que especifica el tamaño máximo del búfer que se puede utilizar.|  
|maxReadPoolSize|Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.  Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.  El valor predeterminado es 64.|  
|maxWritePoolSize|Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.  Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.  El valor predeterminado es 16.|  
|messageVersion|Especifica la versión SOAP de los mensajes enviados utilizando el enlace.  Los valores válidos son<br /><br /> -   Soap11Addressing1<br />-   Soap12Addressing10<br /><br /> El valor predeterminado es Soap12Addressing10.  Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.  Los valores válidos son<br /><br /> -   UnicodeFffeTextEncoding: codificación de Unicode BigEndian<br />-   Utf16TextEncoding: Codificación Unicode<br />-   Utf8TextEncoding: codificación de 8 bits.<br /><br /> El valor predeterminado es Utf8TextEncoding.  Este atributo es del tipo <xref:System.Text.Encoding>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los extremos configurados con este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.  La descodificación es el proceso inverso.  Windows Communication Foundation \(WCF\) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje \(MTOM\).  
  
 El elemento `MtomMessageEncoding` especifica la codificación de caracteres y control de versión de mensajes y otros valores usados para los mensajes que utilizan una codificación MTOM \(mecanismo de optimización de transmisión de mensajes\).  MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF.  El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad.  El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza los bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos a su formato codificado base64.  
  
## Ejemplo  
  
```  
<mtomMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion=”Soap11Addressing10”  
    textEncoding=”utf-8” />  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>   
 [Codificación de mensajes](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)