---
description: 'Más información acerca de cómo: intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server'
title: Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 0b8f315b00960ec87e68e9e2b11ac9b273dbbf93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704620"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server

Puede integrar aplicaciones de Message Queuing (MSMQ) existentes con aplicaciones Windows Communication Foundation (WCF) mediante el enlace de integración de MSMQ para convertir mensajes de MSMQ a y desde mensajes de WCF. Esto le permite llamar a aplicaciones de receptor de MSMQ desde clientes de WCF, así como llamar a servicios WCF desde aplicaciones de remitente MSMQ.  
  
 En esta sección, se explica cómo usar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un cliente WCF y un servicio de aplicación MSMQ escrito con System. Messaging y (2) un cliente de aplicación MSMQ y un servicio WCF.  
  
 Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de receptor de MSMQ desde un cliente de WCF, vea el ejemplo de [Windows Communication Foundation a Message Queue Server](../samples/wcf-to-message-queuing.md) .  
  
 Para obtener un ejemplo completo que muestra cómo llamar a un servicio WCF desde un cliente MSMQ, vea el ejemplo de [Message Queue Server para Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ  
  
1. Defina una interfaz que defina el contrato de servicio para el servicio WCF que recibe los mensajes en cola de una aplicación de remitente MSMQ, tal como se muestra en el código de ejemplo siguiente.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Implemente la interfaz y aplique el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase, como se muestra en el código de ejemplo siguiente.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Cree un archivo de configuración que especifique <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Cree una instancia de un objeto <xref:System.ServiceModel.ServiceHost> que utilice el enlace configurado.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ  
  
1. Defina una interfaz que defina el contrato de servicio para el cliente de WCF que envía los mensajes en cola al receptor de MSMQ, tal y como se muestra en el código de ejemplo siguiente.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Defina una clase de cliente que el cliente de WCF use para llamar al receptor de MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general de colas](queues-overview.md)
- [Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Windows Communication Foundation a Message Queuing](../samples/wcf-to-message-queuing.md)
- [Instalar Message Queuing (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Message Queuing a Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Seguridad de mensajes mediante Message Queuing](../samples/message-security-over-message-queuing.md)
