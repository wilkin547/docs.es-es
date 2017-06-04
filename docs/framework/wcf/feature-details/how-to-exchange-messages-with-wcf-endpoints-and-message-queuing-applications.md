---
title: "C&#243;mo: Intercambiar mensajes con puntos de conexi&#243;n de WCF y aplicaciones de Message Queuing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# C&#243;mo: Intercambiar mensajes con puntos de conexi&#243;n de WCF y aplicaciones de Message Queuing
Puede integrar aplicaciones Message Queuing existentes (MSMQ) con aplicaciones de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizando el enlace de integración de MSMQ para convertir los mensajes de MSMQ a y desde mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Esto le permite llamar a aplicaciones de receptor de MSMQ desde clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], así como llamar a servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde aplicaciones de remitente de MSMQ.  
  
 En esta sección se explica cómo usar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente y un servicio de aplicación de MSMQ escrito al usar System.Messaging y (2) un cliente de aplicación de MSMQ y un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio.  
  
 Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de recepción MSMQ desde una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente, consulte la [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplo.  
  
 Para obtener un ejemplo completo que muestra cómo llamar a un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio desde un cliente MSMQ, consulte la [Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) ejemplo.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ  
  
1.  Defina una interfaz que defina el contrato de servicio para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que recibe los mensajes en cola desde una aplicación remitente de MSMQ, como se muestra en el siguiente ejemplo de código.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  Implemente la interfaz y aplique el <xref:System.ServiceModel.ServiceBehaviorAttribute> atributo a la clase, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  Crear un archivo de configuración que especifica la <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  
  
  
  
4.  Crear una instancia de un <xref:System.ServiceModel.ServiceHost> objeto que utiliza el enlace configurado.  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ  
  
1.  Defina una interfaz que defina el contrato de servicio para el cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que envía mensajes en cola al receptor de MSMQ, como se muestra en el código de ejemplo siguiente.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  Defina una clase de cliente que el cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usará para llamar al receptor de MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vea también  
 [Información general de colas](../../../../docs/framework/wcf/feature-details/queues-overview.md)   
 [Cómo: intercambiar mensajes con extremos de WCF en cola](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)   
 [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)   
 [Instalar Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)   
 [Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)   
 [Seguridad de mensajes mediante Message Queue Server](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)