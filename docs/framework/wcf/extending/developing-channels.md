---
title: "Desarrollo de canales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Desarrollo de canales
Para desarrollar un protocolo o canal de transporte que se pueda utilizar con el nivel de aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son necesarios varios pasos.En este tema se describen esos pasos y se le dirige a temas con información específica.Para entender el modelo del canal y los distintos tipos que se mencionan en este tema, vea [Información general del modelo de canales](../../../../docs/framework/wcf/extending/channel-model-overview.md).Para obtener un ejemplo de canal de transporte completo, vea [Transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## La lista de tareas de desarrollo de canal  
 Los pasos para crear un canal definido por el usuario son como sigue.Todos los canales deben:  
  
1.  Decidir qué modelos de intercambio de mensajes de canal \(<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IReplyChannel>\) <xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener> admitirán, así como si serán compatibles las variaciones con sesión de estas interfaces.Para obtener información detallada, vea [Elección de un modelo de intercambio de mensajes](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).  
  
2.  Cree un generador de canales y un agente de escucha \(<xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener>\) que admitan su modelo de intercambio de mensajes.Para obtener detalles sobre cómo desarrollar los generadores, vea [Cliente: generadores de canales y canales](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md).Para obtener información detallada sobre cómo desarrollar los agentes de escucha, vea [Servicio: Canales y escuchas de canales](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).  
  
3.  Asegurarse de que cualquier excepción específica de la red se normaliza a <xref:System.TimeoutException?displayProperty=fullName> o a la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.Para obtener información detallada, vea [Administración de excepciones y errores](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
4.  Para habilitar el uso del nivel de aplicación, agregue un <xref:System.ServiceModel.Channels.BindingElement> que añade el canal personalizado a una pila del canal.Para obtener más información, vea [Creación de un BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).  
  
 Son necesarios pasos adicionales para permitir una compatibilidad más completa en el nivel de la aplicación:  
  
1.  Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.Para obtener más información, vea [Compatibilidad con metadatos y configuración](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
2.  Agregue las extensiones de metadatos para comunicar las funciones a otros extremos.Para obtener más información, vea [Compatibilidad con metadatos y configuración](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
3.  Agregue un enlace que configura previamente una pila de elementos de enlace según un perfil bien determinado.Para obtener más información, vea [Creación de enlaces definidos por el usuario](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
4.  Agregue una sección de enlace y un elemento de configuración de enlace para exponer el enlace en el sistema de configuración.Para obtener más información, vea [Compatibilidad con metadatos y configuración](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
## Vea también  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)