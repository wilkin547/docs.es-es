---
title: "Creaci&#243;n de un BindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Creaci&#243;n de un BindingElement
Los enlaces y elementos de enlace \(los objetos que extienden <xref:System.ServiceModel.Channels.Binding?displayProperty=fullName> y <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>, respectivamente\) son el lugar donde el modelo de aplicación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] está asociado a generadores de canales y agentes de escucha de canal.Sin los enlaces, usar los canales personalizados requiere programación en el nivel de canal tal y como se describe en [Programación de servicios a nivel de canal](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) y [Programación a nivel de canal de cliente](../../../../docs/framework/wcf/extending/client-channel-level-programming.md).Este tema trata sobre el requisito mínimo para permitir usar el canal en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el desarrollo de <xref:System.ServiceModel.Channels.BindingElement> para su canal y habilitar el uso desde la aplicación tal y como se describe en el paso 4 de [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## Información general  
 La creación de un <xref:System.ServiceModel.Channels.BindingElement> para el canal permite a los desarrolladores usarlo en una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Los objetos <xref:System.ServiceModel.Channels.BindingElement> se pueden usar desde la clase <xref:System.ServiceModel.ServiceHost?displayProperty=fullName> para conectar una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al canal sin tener la información de tipo exacta del canal.  
  
 Una vez que se haya creado <xref:System.ServiceModel.Channels.BindingElement>, puede permitir más funcionalidad según sus requisitos siguiendo los pasos de desarrollo de canal restantes descritos en [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## Adición de un elemento de enlace  
 Para implementar un <xref:System.ServiceModel.Channels.BindingElement> personalizado, escriba una clase que se hereda desde <xref:System.ServiceModel.Channels.BindingElement>.Por ejemplo, si ha desarrollado un `ChunkingChannel` que puede dividir los mensajes grandes en fragmentos y volverlos a ensamblar en el otro extremo, puede utilizar este canal en cualquier enlace implementando un <xref:System.ServiceModel.Channels.BindingElement> y configurando el enlace para utilizarlo.El resto de este tema utiliza `ChunkingChannel` como un ejemplo para mostrar los requisitos para implementar un elemento de enlace.  
  
 `ChunkingBindingElement` es el responsable de crear `ChunkingChannelFactory` y `ChunkingChannelListener`.Invalida las implementaciones <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> y <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A> y comprueba que el parámetro de tipo sea <xref:System.ServiceModel.Channels.IDuplexSessionChannel> \(en nuestro ejemplo es la única forma del canal admitida por `ChunkingChannel`\), que los otros elementos del enlace admitan esta forma de canal.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> comprueba primero que la forma de canal solicitada pueda crearse y después obtiene una lista de acciones de mensaje que puedan fragmentarse.Después crea un nuevo `ChunkingChannelFactory` al que se le pasa el generador de canales interno.\(Si está creando un elemento de enlace de transporte, ese elemento será el último en la pila obligatoria y, por consiguiente, deberá crear un agente de escucha de canal o generador de canales.\)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> tiene una implementación similar para crear `ChunkingChannelListener` y pasarle el agente de escucha de canal interno.  
  
 Si desea ver otro ejemplo de uso del canal de transporte, la muestra de [Transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) proporciona la invalidación siguiente.  
  
 En el ejemplo, el elemento de enlace es `UdpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>.Invalida los métodos siguientes para crear los generadores asociados con el canal.  
  
```  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
            return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
            return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema \(soap.udp\).  
  
#### Elementos de enlace de protocolo  
 Los nuevos elementos de enlace pueden reemplazar o aumentar cualquiera de los elementos de enlace incluidos, agregando nuevos transportes, codificaciones o protocolos de nivel más alto.Para crear un nuevo elemento de enlace de protocolo, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement>.Como mínimo, debe implementar <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=fullName> y  `ChannelProtectionRequirements` mediante <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=fullName>.Esto devuelve <xref:System.ServiceModel.Security.ChannelProtectionRequirements> para este elemento de enlace.Para obtener más información, vea <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> debería devolver una copia nueva de este elemento de enlace.Como procedimiento recomendado, recomendamos que los autores del elemento de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> utilizando un constructor de copias que llama al constructor de copias base, a continuación, clona cualquier campo adicional en esta clase.  
  
#### Elementos de enlace de transporte  
 Para crear un nuevo elemento de transporte de enlace, extienda la interfaz <xref:System.ServiceModel.Channels.TransportBindingElement>.Como mínimo, deberá implementar el método <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> y la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=fullName>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>: debería devolver una copia nueva de este elemento de enlace.Como mejor procedimiento, recomendamos que los autores del elemento de enlace implementen el elemento de clonación por medio de un constructor de copias que llame al constructor de copias base y que después clone los campos adicionales en esta clase.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A>: la propiedad de obtención <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> devuelve el esquema de URI para el protocolo de transporte representado por el elemento de enlace.Por ejemplo, <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> y <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=fullName> devuelven "http" y "net.tcp" desde sus propiedades <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> respectivas.  
  
#### Elementos de enlace de codificación  
 Para crear los nuevos elementos de enlace de codificación, comience extendiendo la clase <xref:System.ServiceModel.Channels.BindingElement> e implementando la clase <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=fullName>.Como mínimo, debe implementar los métodos <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=fullName> y la propiedad <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=fullName>.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>.Devuelve una copia nueva de este elemento de enlace.Como mejor procedimiento, recomendamos que los autores de los elementos de enlace implementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> mediante utilizando un constructor de copias que llama al constructor de copias base y, a continuación, clona cualquier campo adicional en esta clase.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>.Devuelve <xref:System.ServiceModel.Channels.MessageEncoderFactory>, que proporciona un controlador a la clase real que implementa su nuevo codificador y cuál debería extender <xref:System.ServiceModel.Channels.MessageEncoder>.Para obtener más información, vea <xref:System.ServiceModel.Channels.MessageEncoderFactory> y <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>.Devuelve el <xref:System.ServiceModel.Channels.MessageVersion> utilizado en esta codificación, que representa las versiones de SOAP y WS\-Addressing en uso.  
  
 Para una lista completa de métodos opcionales y propiedades para los elementos de enlace de codificación definidos por el usuario, vea <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Para obtener más información sobre cómo crear un nuevo elemento de enlace, vea [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Cuando haya creado un elemento de enlace para el canal, vuelva al tema [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md) para ver si desea agregar la compatibilidad del archivo de configuración a su elemento de enlace, si agregar la compatibilidad de publicación de metadatos y cómo, y si construir un enlace definido por el usuario que utiliza su elemento de enlace y cómo.  
  
## Vea también  
 <xref:System.ServiceModel.Channels.BindingElement>   
 [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md)   
 [Transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)