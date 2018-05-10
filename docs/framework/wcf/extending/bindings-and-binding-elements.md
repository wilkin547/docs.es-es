---
title: Enlaces y elementos de enlace
ms.date: 03/30/2017
helpviewer_keywords:
- binding elements [WCF]
ms.assetid: 765ff77b-7682-4ea3-90eb-e4d751e37379
ms.openlocfilehash: 2a0e797a921ff20b2432e824c92c09fff833bf7d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="bindings-and-binding-elements"></a>Enlaces y elementos de enlace
Los enlaces son colecciones de elementos de configuración especial, denominados *elementos de enlace*, que son evaluados por el runtime del servicio siempre que un cliente o el punto de conexión de servicio se está construyendo. El tipo y orden de los elementos de enlace dentro de un enlace determina la selección y el orden de apilamiento del protocolo y los canales de transporte en la pila de canales de un punto de conexión.  
  
 Los enlaces, sobre todo los enlaces proporcionados por el sistema, normalmente tienen también varias propiedades de configuración que reflejan las propiedades más modificadas habitualmente de los elementos de enlace encapsulados.  
  
 Un enlace debe contener exactamente un elemento de enlace del transporte. Cada elemento de enlace de transporte implica un elemento de enlace de codificación de mensajes predeterminado, que se puede invalidar agregando a lo sumo un elemento de enlace de codificación de mensajes al enlace. Además de los elementos de enlace de codificador y transporte, el enlace puede contener cualquier número de elementos de enlace protocolares que juntos implementan la funcionalidad necesaria para el servicio y envío de un mensaje SOAP de un punto de conexión a otro. Para obtener más información, consulte [utilizando enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
## <a name="extending-bindings-and-binding-elements"></a>Extender enlaces y elementos de enlace  
 Windows Communication Foundation (WCF) incluye enlaces proporcionados por el sistema que abarcan una gran variedad de escenarios. (Para obtener más información, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md).) Puede haber ocasiones, sin embargo, cuando se necesita crear y utilizar un enlace que no se incluye en WCF. Los siguientes escenarios requieren la creación de un nuevo enlace.  
  
-   Para utilizar un nuevo elemento de enlace (como un nuevo transporte, codificación o elemento de enlace protocolar), debe crear un nuevo enlace que incluya ese elemento de enlace. Por ejemplo, si agregase un `UdpTransportBindingElement` personalizado para transporte de UDP, necesitaría crear un nuevo enlace para utilizarlo. Para obtener información acerca de cómo realizar este comportamiento mediante la <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> los tipos, vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
-   Para configurar elementos de enlace existentes de tal modo que los enlaces proporcionados por el sistema no se expongan en propiedades públicas. Por ejemplo, debe crear un nuevo enlace para cambiar el orden en el que se realizan las operaciones de firmado y cifrado. Para obtener información acerca de cómo realizar este comportamiento, consulte [Cómo: personalizar un enlace proporcionados](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
-   Para establecer enlaces estándar corporativos que solo exponen opciones de configuración específicas. Por ejemplo, para crear para su compañía una variante de <xref:System.ServiceModel.WSHttpBinding> en la que la seguridad no puede estar deshabilitada, cree un nuevo enlace que se comporte como el <xref:System.ServiceModel.WSHttpBinding>, pero con la seguridad siempre habilitada. Para obtener más información, consulte [crear enlaces](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
-   Para realizar alguna personalización de metadatos, normalmente, pero no necesariamente, para configurar o utilizar algún elemento de enlace personalizado. Para obtener más información acerca de cómo proporcionar compatibilidad con metadatos a los enlaces y elementos de enlace, vea [configuración y compatibilidad con metadatos](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
-  
  
## <a name="channels-bindings-and-binding-elements"></a>Canales, enlaces y elementos de enlace  
 Los enlaces y elementos de enlace son la conexión entre el modelo de programación de aplicaciones, que incluye los atributos y comportamientos, y el modelo del canal, que incluye los generadores y agentes de escucha, codificadores de mensajes e implementaciones de protocolo y transporte. Normalmente, los elementos de enlace y los enlaces se implementan para permitir al nivel de aplicaciones el uso de los canales.  
  
 La capa de canales entrega o recibe mensajes a y desde la capa del servicio y transporta esos mensajes entre extremos. En un cliente, la capa de canales es una pila de generadores de canales que crean canales para un punto de conexión de la red. En un servicio, la capa de canales es una pila de agentes de escucha de canales que aceptan los canales recibidos en un extremo de la red.  
  
 Hay dos tipos de canales generales: canales de transporte y canales de protocolo. Los canales de transporte son responsables de la transmisión real de un mensaje des un extremo de la red a otro. Los canales de transporte deben tener un codificador de mensajes predeterminado y poder utilizar un codificador de mensajes alternativo proporcionado a través de un elemento de enlace del codificador de mensajes. Un codificador de mensajes es responsable de convertir un<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> en una representación de la conexión y viceversa. Los canales protocolares son responsables de la implementación de los protocolos de nivel SOAP (por ejemplo, WS-Security o WS-ReliableMessaging).  
  
 El requisito primario para los canales protocolares y de transporte es que implementen las interfaces de canales necesarias. Para crear una capa de canales activa, deben tener asociados generadores y agentes de escucha, etc. Para utilizar las implementaciones de canal de WCF, debe haber un elemento de enlace asociado derivado de <xref:System.ServiceModel.Channels.BindingElement> para cada canal y debería haber un elemento de extensión de enlace relacionado para su inclusión en archivos de configuración que deriva de <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.  
  
 Como se mencionó anteriormente, los elementos de enlace para los codificadores de mensajes, protocolo e implementaciones de canal de transporte, se pueden apilar para formar una pila de canales y el mecanismo para alinearlos en un conjunto ordenado es el enlace. Los enlaces y elementos de enlace conectan el modelo de programación de aplicaciones al modelo de canales. Puede utilizar sus implementaciones de canal directamente a partir de código, pero, a menos que los codificadores, transportes y protocolos se implementen como elementos de enlace, no se podrán utilizar desde el modelo de programación de capa de servicio.  
  
 Para obtener más información sobre el desarrollo de canales y los elementos de enlace, vea [extender la capa del canal](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).
