---
title: Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7463f9cfc37c2bf4f271f6e59896a7d77f3f65cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772949"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server
Puede integrar las aplicaciones existentes de Message Queuing (MSMQ) con aplicaciones de Windows Communication Foundation (WCF) utilizando el enlace de integración de MSMQ para convertir los mensajes de MSMQ a y desde los mensajes WCF. Esto permite llamar a las aplicaciones de receptor MSMQ desde clientes WCF, así como llamar a servicios WCF desde las aplicaciones del remitente MSMQ.  
  
 En esta sección, se explica cómo usar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un cliente WCF y un servicio de aplicación de MSMQ escrito mediante System.Messaging y (2) un cliente de aplicación de MSMQ y un servicio WCF.  
  
 Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de recepción MSMQ desde un cliente WCF, vea el [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplo.  
  
 Para obtener un ejemplo completo que muestra cómo llamar a un servicio WCF desde un cliente MSMQ, consulte el [Message Queue Server a Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) ejemplo.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ  
  
1. Defina una interfaz que define el contrato de servicio para el servicio WCF que recibe los mensajes en cola desde una aplicación de remitente MSMQ, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Implemente la interfaz y aplique el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase, como se muestra en el código de ejemplo siguiente.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Cree un archivo de configuración que especifique <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Cree una instancia de un objeto <xref:System.ServiceModel.ServiceHost> que utilice el enlace configurado.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ  
  
1. Defina una interfaz que define el contrato de servicio para el cliente de WCF que envía mensajes en cola en el receptor MSMQ, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Defina una clase de cliente que utiliza el cliente WCF para llamar al receptor de MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general de colas](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Cómo: Intercambiar los mensajes en cola con puntos de conexión WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Windows Communication Foundation a Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [Instalación de Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [Message Queuing a Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [Seguridad de mensajes mediante Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
