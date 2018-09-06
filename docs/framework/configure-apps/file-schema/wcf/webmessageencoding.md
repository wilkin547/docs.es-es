---
title: '&lt;webMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: eddda5e805d7e2cc361b6925d34d13eb8fd614f9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773636"
---
# <a name="ltwebmessageencodinggt"></a>&lt;webMessageEncoding&gt;
Habilita XML de texto sin formato, codificaciones de mensajes de Notación de objetos JavaScript (JSON) y el contenido binario "sin procesar" que se va a leer y escribir cuando se use en un enlace de Windows Communication Foundation (WCF).  
  
 \<system.serviceModel>  
\<enlaces >  
\<customBinding >  
\<enlace >  
\<webMessageEncoding >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`maxReadPoolSize`|El número de mensajes que se pueden leer simultáneamente sin asignar nuevos lectores. Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor. El valor predeterminado es 64 lectores para cada uno de los codificadores internos (texto, JSON, y "sin formato").<br /><br /> Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes entrantes porque puede utilizar los lectores del grupo ya creados en lugar de tener que crear nuevos.|  
|`maxWritePoolSize`|El número de mensajes que se pueden enviar simultáneamente sin asignar nuevos escritores. Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor. El valor predeterminado es 16 escritores para cada uno de los codificadores internos (texto, JSON, y "sin formato").<br /><br /> Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes salientes porque puede utilizar los escritores del grupo ya creados en lugar de tener que crear nuevos.|  
|`writeEncoding`|Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos son:<br /><br /> -UnicodeFffeTextEncoding: Unicode codificación Big Endian.<br />-Utf16TextEncoding: Codificación de Unicode.<br />-Utf8TextEncoding: codificación de 8 bits.<br /><br /> El valor predeterminado es Utf8TextEncoding. Este atributo es del tipo <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enlace >](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 La codificación es el proceso de transformación de un mensaje en una secuencia de bytes. La descodificación es el proceso inverso. Estos procesos requieren la especificación de una codificación de caracteres.  
  
 El elemento `webMessageEncoding` funciona delegando a una serie de codificadores internos para administrar el texto sin formato XML y las codificaciones JSON, así como los datos binarios "sin formato." Un codificador del mensaje compuesto hace esta delegación.  
  
 Este elemento de enlace y su codificador compuesto se utilizan para controlar la codificación en escenarios que no utilizan la mensajería de SOAP utilizada por el elemento `webHttpBinding`. Estos escenarios incluyen "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) y Atom syndication, y Asynchronous JavaScript y XML (AJAX). El codificador del mensaje compuesto no admite SOAP o WS-Addressing.  
  
 El elemento de enlace se puede configurar con una codificación de caracteres de escritura utilizando el atributo `writeEncoding`. El valor <xref:System.Text.Encoding> proporcionado especifica el comportamiento en escritura para los casos de texto XML y JSON. En lectura, cualquier codificación de mensajes válida y codificación de texto se entenderán.  
  
 `maxReadPoolSize` y `maxWritePoolSize` también se pueden utilizar para establecer el número máximo de lectores y escritores que se van a asignar respectivamente. De forma predeterminada se asignan 64 lectores y 16 escritores.  
  
 Las restricciones de complejidad predeterminadas también se establecen mediante el [ \<readerQuotas >](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) ataques de elemento que se va a proteger contra una clase de denegación de servicio (DOS) que intentan utilizar la complejidad del mensaje para paralizar el procesamiento del punto de conexión recursos.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [Codificación de mensajes](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
