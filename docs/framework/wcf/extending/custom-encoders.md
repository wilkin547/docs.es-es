---
description: 'Más información acerca de: codificadores personalizados'
title: Codificadores personalizados
ms.date: 03/30/2017
ms.assetid: fa0e1d7f-af36-4bf4-aac9-cd4eab95bc4f
ms.openlocfilehash: 12c706daf025b6ab63bd5c4e2cbb426a2ea83af1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735301"
---
# <a name="custom-encoders"></a>Codificadores personalizados

Este tema describe cómo crear codificadores personalizados.  
  
 En Windows Communication Foundation (WCF), se utiliza un *enlace* para especificar cómo se transfieren los datos a través de una red entre los extremos. Un enlace se compone de una secuencia de *elementos de enlace*. Un enlace incluye elementos de enlace de protocolo opcionales como la seguridad, un elemento de enlace del *codificador de mensajes* necesario y un elemento de enlace de transporte necesario. Un codificador de mensaje está representado por un elemento de enlace de codificación de mensaje. En WCF se incluyen tres codificadores de mensaje: binario, mecanismo de optimización de transmisión de mensajes (MTOM) y texto.  
  
 Un elemento de enlace de codificación de mensajes serializa un <xref:System.ServiceModel.Channels.Message> saliente y lo pasa al transporte, o recibe del transporte la forma serializada de un mensaje y lo pasa al nivel de protocolo, si está presente, o, si no lo está, a la aplicación.  
  
 Los codificadores del mensaje transforman las instancias <xref:System.ServiceModel.Channels.Message> a y desde una representación de la conexión. Aunque los codificadores se describen como situados encima del nivel de transporte en la pila del canal, en realidad residen en el nivel de transporte. Los transportes (por ejemplo HTTP) dan formato al mensaje según los requisitos de la norma de transporte. Los codificadores (por ejemplo texto/Xml) apenas codifican el mensaje.  
  
 Al establecer una conexión con un cliente o servidor existente previamente, puede tener opciones sobre la utilización de una codificación de mensajes determinada. Sin embargo, se puede tener acceso a los servicios WCF a través de varios puntos de conexión, cada uno con un codificador de mensajes diferente. Cuando un único codificador no abarca toda la audiencia de su servicio, considere la exposición del servicio en varios extremos. De este modo, las aplicaciones cliente pueden elegir el extremo que más les convenga. La utilización de múltiples extremos permite combinar las ventajas de diferentes codificadores de mensaje con otros elementos de enlace.  
  
## <a name="system-provided-encoders"></a>Codificadores proporcionados por el sistema  

 WCF proporciona varios enlaces proporcionados por el sistema que están diseñados para cubrir los escenarios de aplicación más comunes. Cada uno de estos enlaces combina un transporte, un codificador de mensaje y otras opciones (por ejemplo, seguridad). En este tema se describe cómo extender `Text` los `Binary` `MTOM` codificadores de mensajes, y que se incluyen en WCF, o crear su propio Codificador personalizado. El codificador de mensajes de texto admite tanto la codificación XML como la codificación SOAP. El modo de codificación XML sin formato del codificador de mensajes de texto se denomina POX (“XML sin formato"), para distinguirlo de la codificación SOAP basada en texto.  
  
 Para obtener más información sobre las combinaciones de elementos de enlace proporcionados por los enlaces proporcionados por el sistema, vea la sección correspondiente en [elegir un transporte](../feature-details/choosing-a-transport.md).  
  
## <a name="how-to-work-with-system-provided-encoders"></a>Cómo trabajar con codificadores proporcionados por el sistema  

 Se agrega una codificación a un enlace mediante una clase derivada de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 WCF proporciona los siguientes tipos de elementos de enlace derivados de la <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> clase que puede proporcionar la codificación de texto, binaria y del mecanismo de optimización de transmisión de mensajes (MTOM):  
  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>: el codificador más interoperable, pero el menos eficaz con mensajes XML. En general, un servicio web, o un cliente de servicios web, pueden entender XML textual. No obstante, la transmisión de grandes bloques de datos binarios en forma de texto no es eficaz.  
  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>: representa el elemento de enlace que especifica la codificación de caracteres y el control de versiones del mensaje, utilizados con los mensajes binarios basados en XML. Esta es la opción más eficaz de las opciones de codificación, pero la menos interoperable, porque solo la admiten los puntos de conexión de WCF.  
  
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>: representa el elemento de enlace que especifica la codificación de caracteres y el control de versiones del mensaje, utilizados con un mensaje codificado mediante el mecanismo de optimización de la transmisión del mensaje (MTOM). MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF. El codificador MTOM intenta equilibrar la eficacia y la interoperabilidad. El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos en texto.  
  
 El elemento de enlace crea un binario, MTOM, o <xref:System.ServiceModel.Channels.MessageEncoderFactory> de texto. El generador crea un binario, MTOM o una instancia <xref:System.ServiceModel.Channels.MessageEncoderFactory> de texto. Normalmente, solo existe una instancia. No obstante, si se utilizan sesiones, puede proporcionarse un codificador diferente para cada sesión. El codificador binario utiliza este recurso para coordinar los diccionarios dinámicos (vea, Infrastructura de XML).  
  
 Los métodos <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A> y <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A> constituyen el núcleo de los codificadores. Los métodos proporcionan la lectura de un mensaje desde una secuencia o desde una matriz <xref:System.Byte>. Las matrices de bytes se utilizan cuando el transporte está operando en modo de almacenamiento en búfer. Los mensajes siempre se escriben en secuencias. Si el transporte debe almacenar el mensaje en búfer, proporciona una secuencia que realiza el almacenamiento en búfer.  
  
 El resto del trabajo de los miembros que admiten contenido, tipos de medio y <xref:System.ServiceModel.Channels.MessageEncoder.MessageVersion%2A>. El transporte llama a estos métodos de codificación para probar si puede descodificar el mensaje entrante, o determinar si el mensaje saliente es válido para este codificador.  
  
 Cada una de las tres implementaciones del codificador agrega propiedades que son relevantes para las codificaciones específicas y que son totalmente configurables. Los codificadores también exponen cuotas de lector con valores predeterminados seguros. Vea Infrastructura de XML para obtener una descripción de las cuotas.  
  
## <a name="features-of-system-provided-encoders"></a>Características de los codificadores proporcionados por el sistema  

 Los codificadores proporcionados por sistema ofrecen diferentes características.  
  
### <a name="pooling"></a>Agrupación  

 Cada una de las implementaciones del codificador intenta agrupar el máximo posible. La reducción de las asignaciones es una manera clave de mejorar el rendimiento del código administrado. Para lograr esta agrupación, las implementaciones utilizan la clase `SynchronizedPool`. El archivo C# contiene una descripción de las optimizaciones adicionales utilizadas por esta clase.  
  
 <xref:System.Xml.XmlDictionaryReader> y las instancias <xref:System.Xml.XmlDictionaryWriter> se agrupan y reinicializan para evitar la asignación de otras nuevas para cada mensaje. Para los lectores, una devolución de llamada `OnClose` reclama al lector cuando se llama a `Close()`. El codificador también recicla algunos objetos de estados del mensaje utilizados al construir los mensajes. Los tamaños de estos grupos pueden configurarse mediante `MaxReadPoolSize` y las propiedades `MaxWritePoolSize`, en cada una de las tres clases derivadas de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
### <a name="binary-encoding"></a>Codificación binaria  

 Cuando la codificación binaria utiliza sesiones, la cadena del diccionario dinámico debe comunicarse con el receptor del mensaje. Para ello, las cadenas del diccionario dinámico se incluyen como prefijo del mensaje. El receptor quita las cadenas, las agrega a la sesión, y procesa el mensaje. Para pasar correctamente las cadenas del diccionario es necesario que el transporte se almacene en búfer.  
  
 Las cadenas se anexan al mensaje mediante un método `AddSessionInformationToMessage` interno. Agrega las cadenas con formato UTF-8 al principio del mensaje prefijado con su longitud. A continuación, se prefija el encabezado de diccionario completo con la longitud de sus datos. La operación inversa la realiza un método `ExtractSessionInformationFromMessage` interno.  
  
 Además de procesar las claves de diccionario dinámico, los mensajes con sesión almacenados en búfer se reciben de una única manera. En lugar de crear un lector sobre el documento y procesarlo, el codificador binario utiliza la clase `MessagePatterns` interna para deconstruir la secuencia binaria. La idea es que la mayoría de los mensajes tienen un determinado conjunto de encabezados que se muestran en un determinado orden cuando se generan mediante WCF. El sistema del patrón interrumpe el mensaje basándose en sus expectativas. Si es correcto, inicializa un objeto <xref:System.ServiceModel.Channels.MessageHeaders> sin analizar el XML. Si no lo es, recurre al método estándar.  
  
### <a name="mtom-encoding"></a>Codificación MTOM  

 La clase <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> tiene una propiedad de configuración adicional denominada <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement.MaxBufferSize%2A>. Esta propiedad establece un límite superior a la cantidad de datos que pueden almacenarse en búfer durante el proceso de lectura de un mensaje. Puede que sea necesario almacenar en búfer el conjunto de información XML (Infoset), u otras partes MIME, para volver a ensamblar todas las partes MIME en un mensaje único.  
  
 Para trabajar correctamente con HTTP, la clase interna del codificador de mensajes de MTOM proporciona algunas API internas para `GetContentType`, qué también es interno, y `WriteMessage`, que es público y puede invalidarse. Puede producirse una mayor comunicación para garantizar que los valores de los encabezados HTTP coinciden con los valores de los encabezados MIME.  
  
 Internamente, el codificador de mensajes MTOM utiliza los lectores de texto de WCF y es similar al codificador de texto. La diferencia principal es que optimiza grandes fragmentos de datos binarios, o BLOB (grandes objetos binarios), sin convertirlos a la codificación Base 64 antes de incrustarlos en los bytes del mensaje. En su lugar, estos BLOB se mantienen extraídos y se les hace referencia como datos adjuntos de MIME.  
  
## <a name="writing-your-own-encoder"></a>Escritura de los propios controles  

 Para implementar su propio codificador de mensajes personalizado, debe proporcionar implementaciones personalizadas de las siguientes tres clases base abstractas:  
  
- <xref:System.ServiceModel.Channels.MessageEncoder>  
  
- <xref:System.ServiceModel.Channels.MessageEncoderFactory>  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
  
 La conversión de la representación en memoria de un mensaje a una representación que pueda escribirse en una secuencia, se encapsula en la clase <xref:System.ServiceModel.Channels.MessageEncoder>, que actúa como generador para los lectores y sistemas de escritura XML que admiten tipos específicos de codificación XML.  
  
- Los métodos clave de esta clase que deben invalidarse son:  
  
- <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A> que adopta un objeto <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> y lo escribe en un objeto <xref:System.IO.Stream>.  
  
- <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A> que adopta un objeto <xref:System.IO.Stream> y un tamaño de encabezado máximo, y devuelve un objeto <xref:System.ServiceModel.Channels.Message>.  
  
 Es el código que se escribe en los métodos que administran la conversión entre el protocolo de transporte estándar y su codificación personalizada.  
  
 A continuación, es necesario programar una clase de generador que cree el codificador personalizado. Invalide <xref:System.ServiceModel.Channels.MessageEncoderFactory.Encoder%2A> para devolver una instancia de su <xref:System.ServiceModel.Channels.MessageEncoder> personalizado.  
  
 A continuación, conecte su <xref:System.ServiceModel.Channels.MessageEncoderFactory> personalizado a la pila de elementos de enlace utilizada para configurar el servicio o el cliente, invalidando el método <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>, para devolver una instancia de este generador.  
  
 Se proporcionan dos ejemplos con WCF que ilustran este proceso con código de ejemplo: codificador de [mensaje personalizado:](../samples/custom-message-encoder-custom-text-encoder.md) codificador de texto personalizado y [codificador de mensajes personalizado: codificador de compresión](../samples/custom-message-encoder-compression-encoder.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory>
- <xref:System.ServiceModel.Channels.MessageEncoder>
- [Información general sobre la arquitectura de transferencia de datos](../feature-details/data-transfer-architectural-overview.md)
- [Elección de un codificador de mensajes](../feature-details/choosing-a-message-encoder.md)
- [Elección del transporte](../feature-details/choosing-a-transport.md)
