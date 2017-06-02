---
title: "&lt;webMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;webMessageEncoding&gt;
Habilita texto sin formato XML, las codificaciones de mensajes de JavaScript Object Notation \(JSON\) y el contenido binario "sin formato" para ser leído y escrito cuando se utiliza en un enlace [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Sintaxis  
  
```  
  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding=”UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`maxReadPoolSize`|El número de mensajes que se pueden leer simultáneamente sin asignar nuevos lectores.  Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.  El valor predeterminado es 64 lectores para cada uno de los codificadores internos \(texto, JSON, y "sin formato"\).<br /><br /> Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes entrantes porque puede utilizar los lectores del grupo ya creados en lugar de tener que crear nuevos.|  
|`maxWritePoolSize`|El número de mensajes que se pueden enviar simultáneamente sin asignar nuevos escritores.  Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.  El valor predeterminado es 16 escritores para cada uno de los codificadores internos \(texto, JSON, y "sin formato"\).<br /><br /> Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes salientes porque puede utilizar los escritores del grupo ya creados en lugar de tener que crear nuevos.|  
|`writeEncoding`|Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.  Los valores válidos son:<br /><br /> -   UnicodeFffeTextEncoding: codificación Big Endian de Unicode.<br />-   Utf16TextEncoding: codificación Unicode.<br />-   Utf8TextEncoding: codificación de 8 bits.<br /><br /> El valor predeterminado es Utf8TextEncoding.  Este atributo es del tipo <xref:System.Text.Encoding>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los extremos configurados con este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.  La descodificación es el proceso inverso.  Estos procesos requieren la especificación de una codificación de caracteres.  
  
 El elemento `webMessageEncoding` funciona delegando a una serie de codificadores internos para administrar el texto sin formato XML y las codificaciones JSON, así como los datos binarios "sin formato."  Un codificador del mensaje compuesto hace esta delegación.  
  
 Este elemento de enlace y su codificador compuesto se utilizan para controlar la codificación en escenarios que no utilizan la mensajería de SOAP utilizada por el elemento `webHttpBinding`.  Estos escenarios incluyen "Plain Old XML" \(POX\), Representational State Transfer \(REST\), Really Simple Syndication \(RSS\) y Atom syndication, y Asynchronous JavaScript y XML \(AJAX\).  El codificador del mensaje compuesto no admite SOAP o WS\-Addressing.  
  
 El elemento de enlace se puede configurar con una codificación de caracteres de escritura utilizando el atributo `writeEncoding`.  El valor <xref:System.Text.Encoding> proporcionado especifica el comportamiento en escritura para los casos de texto XML y JSON.  En lectura, cualquier codificación de mensajes válida y codificación de texto se entenderán.  
  
 `maxReadPoolSize` y `maxWritePoolSize` también se pueden utilizar para establecer el número máximo de lectores y escritores que se van a asignar respectivamente.  De forma predeterminada se asignan 64 lectores y 16 escritores.  
  
 Las restricciones de complejidad predeterminadas también se establecen con el elemento [\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md) para protegerse contra una clase de ataques por denegación de servicio \(DOS\) que intentan usar la complejidad del mensaje para atar los recursos de procesamiento del extremo.  
  
## Ejemplo  
  
```  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding=”utf-8”   
/>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>   
 [Codificación de mensajes](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)