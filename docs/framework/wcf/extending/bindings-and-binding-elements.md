---
title: "Enlaces y elementos de enlace | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "elementos de enlace [WCF]"
ms.assetid: 765ff77b-7682-4ea3-90eb-e4d751e37379
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Enlaces y elementos de enlace
Los enlaces son colecciones de elementos de configuración especiales, llamados *elementos de enlace*, que son evaluados por el servicio en tiempo de ejecución cada vez que se construye un extremo de cliente o servicio.El tipo y orden de los elementos de enlace dentro de un enlace determina la selección y el orden de apilamiento del protocolo y los canales de transporte en la pila de canales de un extremo.  
  
 Los enlaces, sobre todo los enlaces proporcionados por el sistema, normalmente tienen también varias propiedades de configuración que reflejan las propiedades más modificadas habitualmente de los elementos de enlace encapsulados.  
  
 Un enlace debe contener exactamente un elemento de enlace del transporte.Cada elemento de enlace de transporte implica un elemento de enlace de codificación de mensajes predeterminado, que se puede invalidar agregando a lo sumo un elemento de enlace de codificación de mensajes al enlace.Además de los elementos de enlace de codificador y transporte, el enlace puede contener cualquier número de elementos de enlace protocolares que juntos implementan la funcionalidad necesaria para el servicio y envío de un mensaje SOAP de un extremo a otro.Para obtener información detallada, consulte [Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
## Extender enlaces y elementos de enlace  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] incluye enlaces proporcionados por el sistema que cubren una gama amplia de escenarios.Para obtener más información, vea [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md). Puede que haya ocasiones, sin embargo, en las que necesite crear y utilizar un enlace que no esté incluido en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Los siguientes escenarios requieren la creación de un nuevo enlace.  
  
-   Para utilizar un nuevo elemento de enlace \(como un nuevo transporte, codificación o elemento de enlace protocolar\), debe crear un nuevo enlace que incluya ese elemento de enlace.Por ejemplo, si agregase un `UdpTransportBindingElement` personalizado para transporte de UDP, necesitaría crear un nuevo enlace para utilizarlo.Para obtener información sobre cómo realizar este comportamiento mediante el tipo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>, vea [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
-   Para configurar elementos de enlace existentes de tal modo que los enlaces proporcionados por el sistema no se expongan en propiedades públicas.Por ejemplo, debe crear un nuevo enlace para cambiar el orden en el que se realizan las operaciones de firmado y cifrado.Para obtener información sobre cómo realizar este comportamiento, vea [Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
-   Para establecer enlaces estándar corporativos que solo exponen opciones de configuración específicas.Por ejemplo, para crear para su compañía una variante de <xref:System.ServiceModel.WSHttpBinding> en la que la seguridad no puede estar deshabilitada, cree un nuevo enlace que se comporte como el <xref:System.ServiceModel.WSHttpBinding>, pero con la seguridad siempre habilitada.Para obtener información detallada, consulte [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
-   Para realizar alguna personalización de metadatos, normalmente, pero no necesariamente, para configurar o utilizar algún elemento de enlace personalizado.Para obtener más información sobre cómo proporcionar compatibilidad de metadatos para los enlaces y elementos de enlace, vea [Compatibilidad con metadatos y configuración](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
-  
  
## Canales, enlaces y elementos de enlace  
 Los enlaces y elementos de enlace son la conexión entre el modelo de programación de aplicaciones, que incluye los atributos y comportamientos, y el modelo del canal, que incluye los generadores y agentes de escucha, codificadores de mensajes e implementaciones de protocolo y transporte.Normalmente, los elementos de enlace y los enlaces se implementan para permitir al nivel de aplicaciones el uso de los canales.  
  
 La capa de canales entrega o recibe mensajes a y desde la capa del servicio y transporta esos mensajes entre extremos.En un cliente, la capa de canales es una pila de generadores de canales que crean canales para un extremo de la red.En un servicio, la capa de canales es una pila de agentes de escucha de canales que aceptan los canales recibidos en un extremo de la red.  
  
 Hay dos tipos de canales generales: canales de transporte y canales de protocolo.Los canales de transporte son responsables de la transmisión real de un mensaje des un extremo de la red a otro.Los canales de transporte deben tener un codificador de mensajes predeterminado y poder utilizar un codificador de mensajes alternativo proporcionado a través de un elemento de enlace del codificador de mensajes.Un codificador de mensajes es responsable de convertir un<xref:System.ServiceModel.Channels.Message?displayProperty=fullName> en una representación de la conexión y viceversa.Los canales protocolares son responsables de la implementación de los protocolos de nivel SOAP \(por ejemplo, WS\-Security o WS\-ReliableMessaging\).  
  
 El requisito primario para los canales protocolares y de transporte es que implementen las interfaces de canales necesarias.Para crear una capa de canales activa, deben tener asociados generadores y agentes de escucha, etc.Para utilizar las implementaciones de canal de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es necesario que haya un  elemento de enlace asociado derivado de <xref:System.ServiceModel.Channels.BindingElement> para cada canal y debería haber un elemento de extensión de enlace relacionado para la inclusión en los archivos de configuración que deriva de <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.  
  
 Como se mencionó anteriormente, los elementos de enlace para los codificadores de mensajes, protocolo e implementaciones de canal de transporte, se pueden apilar para formar una pila de canales y el mecanismo para alinearlos en un conjunto ordenado es el enlace.Los enlaces y elementos de enlace conectan el modelo de programación de aplicaciones al modelo de canales.Puede utilizar sus implementaciones de canal directamente a partir de código, pero, a menos que los codificadores, transportes y protocolos se implementen como elementos de enlace, no se podrán utilizar desde el modelo de programación de capa de servicio.  
  
 Para obtener detalles sobre cómo desarrollar canales y sus elementos de enlace, vea [Extensión de la capa de canales](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).