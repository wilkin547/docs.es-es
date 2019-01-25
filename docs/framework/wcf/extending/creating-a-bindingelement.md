---
title: Creación de un BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 8c4f3b4b3f9a3e4694ece814de691c07ef88ec5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684884"
---
# <a name="creating-a-bindingelement"></a>Creación de un BindingElement
Los enlaces y elementos de enlace (objetos que extienden <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> y <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>, respectivamente) son el lugar donde el modelo de aplicación de Windows Communication Foundation (WCF) está asociado con los generadores de canales y escuchas de canales. Sin enlaces, utilizando los canales personalizados requiere programación en el nivel de canal como se describe en [a nivel de canal de servicio de programación](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) y [programación de nivel de canal de cliente](../../../../docs/framework/wcf/extending/client-channel-level-programming.md). Este tema describe el requisito mínimo para habilitar el uso de su canal de WCF, el desarrollo de un <xref:System.ServiceModel.Channels.BindingElement> de canal y habilitar el uso de la aplicación tal como se describe en el paso 4 de [desarrollar canales](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="overview"></a>Información general  
 Creación de un <xref:System.ServiceModel.Channels.BindingElement> para el canal permite a los desarrolladores utilizarlo en una aplicación de WCF. <xref:System.ServiceModel.Channels.BindingElement> se pueden usar objetos desde el <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> clase para conectar una aplicación de WCF para su canal sin tener que la información de su canal de tipo precisa.  
  
 Una vez un <xref:System.ServiceModel.Channels.BindingElement> ha sido creado, puede habilitar más funcionalidad según sus requisitos siguiendo los pasos de desarrollo de canal restantes descritos en [desarrollar canales](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Adición de un elemento de enlace  
 Para implementar un <xref:System.ServiceModel.Channels.BindingElement> personalizado, escriba una clase que se hereda desde <xref:System.ServiceModel.Channels.BindingElement>. Por ejemplo, si ha desarrollado un `ChunkingChannel` que puede dividir los mensajes grandes en fragmentos y volverlos a ensamblar en el otro extremo, puede utilizar este canal en cualquier enlace implementando un <xref:System.ServiceModel.Channels.BindingElement> y configurando el enlace para utilizarlo. El resto de este tema utiliza `ChunkingChannel` como un ejemplo para mostrar los requisitos para implementar un elemento de enlace.  
  
 `ChunkingBindingElement` es el responsable de crear `ChunkingChannelFactory` y `ChunkingChannelListener`. Invalida las implementaciones <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> y <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A> y comprueba que el parámetro de tipo sea <xref:System.ServiceModel.Channels.IDuplexSessionChannel> (en nuestro ejemplo es la única forma del canal admitida por `ChunkingChannel`), que los otros elementos del enlace admitan esta forma de canal.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> comprueba primero que la forma de canal solicitada pueda crearse y después obtiene una lista de acciones de mensaje que puedan fragmentarse. Después crea un nuevo `ChunkingChannelFactory` al que se le pasa el generador de canales interno. (Si está creando un elemento de enlace de transporte, ese elemento será el último en la pila obligatoria y, por consiguiente, deberá crear un agente de escucha de canal o generador de canales.)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> tiene una implementación similar para crear `ChunkingChannelListener` y pasarle el agente de escucha de canal interno.  
  
 Como otro ejemplo del uso de un canal de transporte, el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo proporciona la invalidación siguiente.  
  
 En el ejemplo, el elemento de enlace es `UdpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>. Invalida los métodos siguientes para crear los generadores asociados con el canal.  
  
```csharp  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema (soap.udp).  
  
#### <a name="protocol-binding-elements"></a>Elementos de enlace de protocolo  
 Los nuevos elementos de enlace pueden reemplazar o aumentar cualquiera de los elementos de enlace incluidos, agregando nuevos transportes, codificaciones o protocolos de nivel más alto. Para crear un nuevo elemento de enlace de protocolo, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement>. Como mínimo, a continuación, debe implementar la <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> e implemente el `ChannelProtectionRequirements` mediante <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. Esto devuelve <xref:System.ServiceModel.Security.ChannelProtectionRequirements> para este elemento de enlace.  Para obtener más información, consulta <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> debería devolver una copia nueva de este elemento de enlace. Como mejor procedimiento, recomendamos que los autores de los elementos de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> mediante utilizando un constructor de copias que llama al constructor de copias base y, a continuación, clona cualquier campo adicional en esta clase.  
  
#### <a name="transport-binding-elements"></a>Elementos de enlace de transporte  
 Para crear un nuevo elemento de transporte de enlace, extienda la interfaz <xref:System.ServiceModel.Channels.TransportBindingElement>. Como mínimo, deberá implementar el método <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> y la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>: debería devolver una copia nueva de este elemento de enlace.  Como mejor procedimiento, recomendamos que los autores del elemento de enlace implementen el elemento de clonación por medio de un constructor de copias que llame al constructor de copias base y que después clone los campos adicionales en esta clase.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A>: la propiedad de obtención <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> devuelve el esquema de URI para el protocolo de transporte representado por el elemento de enlace. Por ejemplo, el <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> y <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> devuelven "http" y "net.tcp" desde sus respectivas <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> propiedades.  
  
#### <a name="encoding-binding-elements"></a>Elementos de enlace de codificación  
 Para crear los nuevos elementos de enlace de codificación, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement> e implementando la clase <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>. Como mínimo, debe implementar los métodos <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> y la propiedad <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Devuelve una copia nueva de este elemento de enlace. Como mejor procedimiento, recomendamos que los autores de los elementos de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> mediante utilizando un constructor de copias que llama al constructor de copias base y, a continuación, clona cualquier campo adicional en esta clase.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Devuelve <xref:System.ServiceModel.Channels.MessageEncoderFactory>, que proporciona un controlador a la clase real que implementa su nuevo codificador y cuál debería extender <xref:System.ServiceModel.Channels.MessageEncoder>. Para obtener más información, vea <xref:System.ServiceModel.Channels.MessageEncoderFactory> y <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Devuelve el <xref:System.ServiceModel.Channels.MessageVersion> utilizado en esta codificación, que representa las versiones de SOAP y WS-Addressing en uso.  
  
 Para una lista completa de métodos opcionales y propiedades para los elementos de enlace de codificación definidos por el usuario, vea <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Para obtener más información sobre cómo crear un nuevo elemento de enlace, consulte [crear enlaces](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Una vez haya creado un elemento de enlace para el canal, volver a la [desarrollar canales](../../../../docs/framework/wcf/extending/developing-channels.md) tema para ver si desea agregar compatibilidad con archivos de configuración a su elemento de enlace, si y cómo agregar compatibilidad con la publicación de metadatos, y Si y cómo para construir un enlace definido por el usuario que usa el elemento de enlace.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.BindingElement>
- [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md)
- [Transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
