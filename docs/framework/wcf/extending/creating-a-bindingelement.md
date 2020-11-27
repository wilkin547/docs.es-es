---
title: Creación de un BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 285bed029cf8487b37757de6a56075abe448f3ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257872"
---
# <a name="creating-a-bindingelement"></a>Creación de un BindingElement

Los enlaces y los elementos de enlace (objetos que extienden <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> y <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> , respectivamente) son el lugar donde el modelo de aplicación de Windows Communication Foundation (WCF) está asociado a generadores de canales y agentes de escucha del canal. Sin enlaces, el uso de canales personalizados requiere la programación en el nivel de canal, como se describe en [programación de Service Channel-Level](service-channel-level-programming.md) y [programación de Channel-Level de cliente](client-channel-level-programming.md). En este tema se describe el requisito mínimo para habilitar el uso del canal en WCF, el desarrollo de un <xref:System.ServiceModel.Channels.BindingElement> para el canal y permitir el uso de la aplicación como se describe en el paso 4 de [desarrollo de canales](developing-channels.md).  
  
## <a name="overview"></a>Información general  

 La creación de un <xref:System.ServiceModel.Channels.BindingElement> para el canal permite a los desarrolladores usarlo en una aplicación WCF. <xref:System.ServiceModel.Channels.BindingElement> los objetos se pueden usar desde la <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> clase para conectar una aplicación WCF al canal sin tener que especificar la información de tipo precisa del canal.  
  
 Una vez que se ha <xref:System.ServiceModel.Channels.BindingElement> creado un, puede habilitar más funcionalidad en función de sus requisitos siguiendo los pasos de desarrollo de canal restantes descritos en [desarrollo de canales](developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Adición de un elemento de enlace  

 Para implementar un <xref:System.ServiceModel.Channels.BindingElement> personalizado, escriba una clase que se hereda desde <xref:System.ServiceModel.Channels.BindingElement>. Por ejemplo, si ha desarrollado un `ChunkingChannel` que puede dividir los mensajes grandes en fragmentos y volverlos a ensamblar en el otro extremo, puede utilizar este canal en cualquier enlace implementando un <xref:System.ServiceModel.Channels.BindingElement> y configurando el enlace para utilizarlo. El resto de este tema utiliza `ChunkingChannel` como un ejemplo para mostrar los requisitos para implementar un elemento de enlace.  
  
 `ChunkingBindingElement` es el responsable de crear `ChunkingChannelFactory` y `ChunkingChannelListener`. Invalida las implementaciones <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> y <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A> y comprueba que el parámetro de tipo sea <xref:System.ServiceModel.Channels.IDuplexSessionChannel> (en nuestro ejemplo es la única forma del canal admitida por `ChunkingChannel`), que los otros elementos del enlace admitan esta forma de canal.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> comprueba primero que la forma de canal solicitada pueda crearse y después obtiene una lista de acciones de mensaje que puedan fragmentarse. Después crea un nuevo `ChunkingChannelFactory` al que se le pasa el generador de canales interno. (Si está creando un elemento de enlace de transporte, ese elemento será el último en la pila obligatoria y, por consiguiente, deberá crear un agente de escucha de canal o generador de canales.)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> tiene una implementación similar para crear `ChunkingChannelListener` y pasarle el agente de escucha de canal interno.  
  
 Como otro ejemplo del uso de un canal de transporte, el ejemplo [Transport: UDP](../samples/transport-udp.md) proporciona la siguiente invalidación.  
  
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

 Los nuevos elementos de enlace pueden reemplazar o aumentar cualquiera de los elementos de enlace incluidos, agregando nuevos transportes, codificaciones o protocolos de nivel más alto. Para crear un nuevo elemento de enlace de protocolo, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement>. Como mínimo, debe implementar <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> e implementar el `ChannelProtectionRequirements` mediante <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType> . Esto devuelve <xref:System.ServiceModel.Security.ChannelProtectionRequirements> para este elemento de enlace.  Para obtener más información, vea <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> debería devolver una copia nueva de este elemento de enlace. Como mejor procedimiento, recomendamos que los autores de los elementos de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> mediante utilizando un constructor de copias que llama al constructor de copias base y, a continuación, clona cualquier campo adicional en esta clase.  
  
#### <a name="transport-binding-elements"></a>Elementos de enlace de transporte  

 Para crear un nuevo elemento de transporte de enlace, extienda la interfaz <xref:System.ServiceModel.Channels.TransportBindingElement>. Como mínimo, deberá implementar el método <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> y la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>: debería devolver una copia nueva de este elemento de enlace.  Como mejor procedimiento, recomendamos que los autores del elemento de enlace implementen el elemento de clonación por medio de un constructor de copias que llame al constructor de copias base y que después clone los campos adicionales en esta clase.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A>: la propiedad de obtención <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> devuelve el esquema de URI para el protocolo de transporte representado por el elemento de enlace. Por ejemplo, <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> y <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> devuelven "http" y "net. TCP" desde sus propiedades respectivas <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> .  
  
#### <a name="encoding-binding-elements"></a>Elementos de enlace de codificación  

 Para crear los nuevos elementos de enlace de codificación, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement> e implementando la clase <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>. Como mínimo, debe implementar los métodos <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> y la propiedad <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Devuelve una copia nueva de este elemento de enlace. Como mejor procedimiento, recomendamos que los autores de los elementos de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> mediante utilizando un constructor de copias que llama al constructor de copias base y, a continuación, clona cualquier campo adicional en esta clase.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Devuelve <xref:System.ServiceModel.Channels.MessageEncoderFactory>, que proporciona un controlador a la clase real que implementa su nuevo codificador y cuál debería extender <xref:System.ServiceModel.Channels.MessageEncoder>. Para obtener más información, vea <xref:System.ServiceModel.Channels.MessageEncoderFactory> y <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Devuelve el <xref:System.ServiceModel.Channels.MessageVersion> utilizado en esta codificación, que representa las versiones de SOAP y WS-Addressing en uso.  
  
 Para una lista completa de métodos opcionales y propiedades para los elementos de enlace de codificación definidos por el usuario, vea <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Para obtener más información sobre cómo crear un nuevo elemento de enlace, vea [crear enlaces de User-Defined](creating-user-defined-bindings.md).  
  
 Una vez que haya creado un elemento de enlace para el canal, vuelva al tema [desarrollo de canales](developing-channels.md) para ver si desea agregar compatibilidad con el archivo de configuración al elemento de enlace, si y cómo agregar compatibilidad para la publicación de metadatos, y si y cómo crear un enlace definido por el usuario que use el elemento de enlace.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.BindingElement>
- [Desarrollo de canales](developing-channels.md)
- [Transporte: UDP](../samples/transport-udp.md)
