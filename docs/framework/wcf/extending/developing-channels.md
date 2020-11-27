---
title: Desarrollo de canales
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: 11e7a78282a3c9f7cd221e2ef44bc43c625e447b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286804"
---
# <a name="developing-channels"></a>Desarrollo de canales

Para desarrollar un protocolo o un canal de transporte que se puede utilizar con el nivel de aplicación de Windows Communication Foundation (WCF), es necesario realizar varios pasos. En este tema se describen esos pasos y se le dirige a temas con información específica. Para comprender el modelo de canal y los distintos tipos que se mencionan en este tema, consulte [información general del modelo de canal](channel-model-overview.md). Para obtener un ejemplo de canal de transporte completo, vea [Transport: UDP](../samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>La lista de tareas de desarrollo de canal  

 Los pasos para crear un canal definido por el usuario son como sigue. Todos los canales deben:  
  
1. Decidir qué patrones de intercambio de mensajes de canal (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> o <xref:System.ServiceModel.Channels.IReplyChannel>) <xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener> admitirán, así como si serán compatibles las variaciones con sesión de estas interfaces. Para obtener más información, consulte [elección de un patrón de intercambio de mensajes](choosing-a-message-exchange-pattern.md).  
  
2. Cree un generador de canales y un agente de escucha (<xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener>) que admitan su patrón de intercambio de mensajes. Para obtener más información sobre el desarrollo de generadores, vea [Client: Channel factorys and](client-channel-factories-and-channels.md)Channels. Para obtener más información sobre el desarrollo de agentes de escucha, vea [servicio: canales y escuchas de canales](service-channel-listeners-and-channels.md).  
  
3. Asegurarse de que cualquier excepción específica de la red se normaliza a <xref:System.TimeoutException?displayProperty=nameWithType> o a la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>. Para obtener más información, consulte [control de excepciones y errores](handling-exceptions-and-faults.md).  
  
4. Para habilitar el uso del nivel de aplicación, agregue un <xref:System.ServiceModel.Channels.BindingElement> que añade el canal personalizado a una pila del canal. Para obtener más información, vea [crear un BindingElement](creating-a-bindingelement.md).  
  
 Son necesarios pasos adicionales para permitir una compatibilidad más completa en el nivel de la aplicación:  
  
1. Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración. Para obtener más información, consulte [compatibilidad con la configuración y los metadatos](configuration-and-metadata-support.md).  
  
2. Agregue las extensiones de metadatos para comunicar las funciones a otros puntos de conexión. Para obtener más información, consulte [compatibilidad con la configuración y los metadatos](configuration-and-metadata-support.md).  
  
3. Agregue un enlace que configura previamente una pila de elementos de enlace según un perfil bien determinado. Para obtener más información, vea [crear enlaces de User-Defined](creating-user-defined-bindings.md).  
  
4. Agregue una sección de enlace y un elemento de configuración de enlace para exponer el enlace al sistema de configuración. Para obtener más información, consulte [compatibilidad con la configuración y los metadatos](configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>Vea también

- [Extensión de enlaces](extending-bindings.md)
