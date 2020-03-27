---
title: Elección de un codificador de mensajes
ms.date: 03/30/2017
ms.assetid: 2204d82d-d962-4922-a79e-c9a231604f19
ms.openlocfilehash: a306896af7a73d43956638981908c12d86126a9f
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345254"
---
# <a name="choosing-a-message-encoder"></a>Elección de un codificador de mensajes
En este tema se describen los criterios para elegir entre los codificadores de mensajes que se incluyen en Windows Communication Foundation (WCF): binario, texto y mecanismo de optimización de transmisión de mensajes (MTOM).  
  
 En WCF, se especifica cómo transferir datos a través de una red entre extremos mediante un *enlace,* que se compone de una secuencia de elementos de *enlace.* Un codificador de mensajes se representa mediante un elemento de enlace de codificación de mensajes en la pila de enlaces. Un enlace incluye elementos de enlace protocolares opcionales, como un elemento de enlace de seguridad o un elemento de enlace de mensajería de confianza, un elemento de enlace de la codificación de mensajes necesario y un elemento de enlace de transporte necesario.  
  
 El elemento de enlace de codificación de mensajes se sienta bajo los elementos de enlace protocolares opcionales y sobre el elemento de enlace de transporte necesario. En el lado de salida, un codificador de mensajes serializa los <xref:System.ServiceModel.Channels.Message> de salida y los pasa al transporte. En el lado de entrada, un codificador de mensajes recibe la forma serializada de un <xref:System.ServiceModel.Channels.Message> desde el transporte y lo pasa a la capa de protocolo más alta, si estuviese presente, o a la aplicación, si no lo estuviese.  
  
 Al conectar a un cliente o servidor preexistente, puede que no tenga una opción sobre el uso de una codificación de mensajes determinada, puesto que necesita codificar sus mensajes de la manera que el otro lado espera. Sin embargo, si está escribiendo un servicio WCF, puede exponer el servicio a través de varios extremos, cada uno con una codificación de mensajes diferente. Esto permite a los clientes elegir la mejor codificación para hablar con su servicio sobre el punto de conexión que es mejor para ellos, así como dar la flexibilidad a sus clientes para que elijan la codificación que más les convenga. La utilización de múltiples extremos también le permite combinar las ventajas de diferentes codificaciones de mensaje con otros elementos de enlace.  
  
## <a name="system-provided-encoders"></a>Codificadores proporcionados por el sistema  
 WCF incluye tres codificadores de mensajes, que se representan mediante las tres clases siguientes:  
  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>, el codificador del mensaje de texto, admite codificación simple XML y codificación SOAP. El modo de codificación XML simple del codificador de mensajes de texto se denomina “XML sin formato” (POX) para distinguirlo de la codificación SOAP basada en texto. Para habilitar POX, establezca la propiedad <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement.MessageVersion%2A> en <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. Utilice el codificador de mensajes de texto para interoperar con extremos que no sean WCF.  
  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>, el codificador de mensajes binarios, usa un formato binario compacto y está optimizado para la comunicación de WCF a WCF y, por lo tanto, no es interoperable. También es el codificador más realizante de todos los codificadores que proporciona WCF.  
  
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, el elemento de enlace, especifica la codificación de caracteres y el control de versiones de los mensajes para los mensajes que utilizan la codificación MTOM. MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF. El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad. El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos en texto. En términos de eficiencia, entre los codificadores que proporciona WCF, MTOM es de texto intermedio (el más lento) y binario (el más rápido).  
  
## <a name="how-to-choose-a-message-encoder"></a>Cómo elegir un codificador de mensajes  
 La siguiente tabla describe los factores comunes utilizados para elegir un codificador de mensajes. Clasifique por orden de prioridad los factores que son importantes para su aplicación y, a continuación, elija los codificadores de mensajes que funcionan mejor con estos factores. Asegúrese de considerar factores adicionales no enumerados en esta tabla y cualquier codificador de mensajes personalizado que se puedan requerir en su aplicación.  
  
|Factor|Descripción|Codificadores que admiten este factor|  
|------------|-----------------|---------------------------------------|  
|Juegos de caracteres compatibles|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> soporta sólo las codificaciones Unicode UTF8 y UTF16 (*big-endian* y *little-endian*). Si se requieren otras codificaciones, como UTF7 o ASCII, se debe usar un codificador personalizado. Para obtener un codificador personalizado de ejemplo, vea [Custom Message Encoder](https://docs.microsoft.com/dotnet/framework/wcf/samples/custom-message-encoder-custom-text-encoder).|Text|  
|Inspección|La inspección es la capacidad para examinar mensajes durante la transmisión. Las codificaciones de texto, con o sin el uso de SOAP, permiten a muchas aplicaciones inspeccionar y analizar mensajes sin el uso de herramientas especializadas. Tenga en cuenta que el uso de seguridad de transferencia en el nivel de mensaje o transporte, afecta a su capacidad para inspeccionar los mensajes. La confidencialidad evita que se examine un mensaje y la integridad evita que se modifique un mensaje.|Text|  
|Confiabilidad|La fiabilidad es la capacidad de recuperación de que dispone un codificador ante los errores de transmisión. La fiabilidad también se proporciona en el nivel de mensaje, transporte o aplicación. Todos los codificadores WCF estándar suponen que otra capa proporciona confiabilidad. El codificador tiene poca capacidad de recuperación ante los errores de transmisión.|None|  
|Simplicidad|La simplicidad representa la facilidad con la que puede crear codificadores y decodificadores para una especificación de codificación. Las codificaciones de texto son particularmente ventajosas para proporcionar simplicidad y la codificación de texto de POX tiene la ventaja adicional de que no requiere compatibilidad para procesar SOAP.|Texto (POX)|  
|Size|La codificación determina la cantidad de sobrecarga impuesta sobre el contenido. El tamaño de los mensajes codificados está directamente relacionado con el rendimiento máximo de las operaciones del servicio. Las codificaciones binarias generalmente son más compactas que las codificaciones de texto. Cuando el tamaño del mensaje es muy importante, considere también la posibilidad de comprimir el contenido del mensaje durante la codificación. Sin embargo, la compresión agrega costes de procesamiento para el remitente y receptor del mensaje.|Binary|  
|Streaming|La transmisión por secuencias permite a las aplicaciones comenzar a procesar un mensaje antes de que haya llegado el mensaje completo. El uso eficaz de la transmisión por secuencias requiere que los datos importantes de un mensaje estén disponibles al principio del mensaje para que la aplicación receptora no tenga que esperar a que llegue. Es más, las aplicaciones que utilizan la transferencia por secuencias deben organizar incrementalmente los datos en el mensaje para que el contenido no tenga dependencias hacia delante. En muchos casos, debe establecer un compromiso entre el contenido de transmisión por secuencias y tener el tamaño de transferencia más pequeño posible para ese contenido.|None|  
|Compatibilidad con herramientas de terceros|Entre las áreas de compatibilidad de una codificación se incluyen el desarrollo y el diagnóstico. Los desarrolladores de terceros han realizado una gran inversión en bibliotecas y kits de herramientas para administrar mensajes codificados en formato POX.|Texto (POX)|  
|Interoperabilidad|Este factor hace referencia a la capacidad de un codificador WCF para interoperar con servicios que no son WCF.|Text<br /><br /> MTOM (parcial)|  
  
Nota: cuando se usa el codificador binario, el uso del valor IgnoreWhitespace al crear un XMLReader no tendrá ningún efecto.  Por ejemplo, si hace lo siguiente dentro de una operación de servicio:  

```csharp
public void OperationContract(XElement input)
{
    Console.WriteLine("{0}", input.Value);
    int counter = 0;
    var xreader = input.CreateReader();
    var reader = XmlReader.Create(xreader, new XmlReaderSettings() { IgnoreWhitespace = true });
    while (reader.Read())
    {
        counter++;
    }

    Console.WriteLine("Read {0} lines with reader", counter);
}
```  
  
Se omite el valor de IgnoreWhitespace.  
  
## <a name="compression-and-the-binary-encoder"></a>Compresión y el codificador binario

A partir de WCF 4.5, el codificador binario de WCF agrega compatibilidad con la compresión. Esto le permite usar el algoritmo gzip/deflate para enviar mensajes comprimidos desde un cliente de WCF y también responder con mensajes comprimidos desde un servicio WCF hospedado a sí mismo. Esta característica habilita la compresión en los transportes HTTP y TCP. Un servicio de WCF hospedado en IIS siempre se puede habilitar para enviar respuestas comprimidas si se configura el servidor host de IIS. El tipo de compresión se configura con la propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A?displayProperty=nameWithType>. Esta propiedad se establece en uno de los valores de la enumeración <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>:

- <xref:System.ServiceModel.Channels.CompressionFormat.Deflate>
- <xref:System.ServiceModel.Channels.CompressionFormat.GZip>
- <xref:System.ServiceModel.Channels.CompressionFormat.None>
  
Puesto que esta propiedad solo se expone en el binaryMessageEncodingBindingElement, tendrá que crear un enlace personalizado como el siguiente para usar esta característica:

 ```xml
 <customBinding>
   <binding name="BinaryCompressionBinding">
     <binaryMessageEncoding compressionFormat ="GZip" />
     <httpTransport />
  </binding>
</customBinding>
 ```

Tanto el cliente como el servicio deben aceptar enviar y recibir mensajes comprimidos y, por lo tanto, la propiedad compressionFormat debe configurarse en el elemento binaryMessageEncoding tanto en el cliente como en el servicio. Se produce una ProtocolException si el servicio o el cliente no está configurado para la compresión pero el otro extremo sí lo está. Debe considerarse detenidamente habilitar la compresión. La compresión es más útil si el ancho de banda de red es un cuello de botella. En el caso en que el cuello de botella sea la CPU, la compresión reducirá el rendimiento. Se debe realizar una prueba adecuada en un entorno simulado para averiguar si esto beneficia a la aplicación  
  
## <a name="see-also"></a>Vea también

- [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)
