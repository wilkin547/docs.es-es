---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c5cd8e9e2002f44fd9feebdc6bb7ede023de459a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556452"
---
# \<textMessageEncoding>
Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|maxReadPoolSize|Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores. Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor. El valor predeterminado es 64.|  
|maxWritePoolSize|Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores. Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor. El valor predeterminado es 16.|  
|messageVersion|Especifica la versión SOAP de los mensajes enviados utilizando el enlace. Los valores válidos son<br /><br /> - Soap11Addressing10<br />- Soap12Addressing10<br />- Soap11<br />-Soap12<br /><br />El valor predeterminado es Soap12Addressing10. Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos son<br /><br /> -UnicodeFffeTextEncoding: codificación Unicode BigEndian<br />-Utf16TextEncoding: codificación Unicode<br />-Utf8TextEncoding: codificación de 8 bits<br /><br /> El valor predeterminado es Utf8TextEncoding. Este atributo es del tipo <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 La codificación es el proceso de transformación de un mensaje en una secuencia de bytes. La descodificación es el proceso inverso. Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).  
  
 La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.  El codificador de texto crea mensajes basados en texto en la conexión. Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - *. Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual. Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [Elección de un codificador de mensajes](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [Codificación de mensajes](message-encoding.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
