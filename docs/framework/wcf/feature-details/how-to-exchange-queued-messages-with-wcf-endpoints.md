---
title: "Cómo: Intercambiar mensajes en cola con puntos de conexión de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4b52fe96bc88f09b807640dedcc54a8468dc26e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Cómo: Intercambiar mensajes en cola con puntos de conexión de WCF
Las colas garantizan que la mensajería de confianza puede tener lugar entre un cliente y un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], aun cuando el servicio no esté disponible en el momento de la comunicación. Los procedimientos siguientes muestran cómo garantizar una comunicación duradera entre un cliente y un servicio utilizando el enlace en cola estándar al implementar el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 En esta sección se explica cómo utilizar <xref:System.ServiceModel.NetMsmqBinding> para la comunicación en cola entre un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>Para utilizar la puesta en cola en un servicio WCF  
  
1.  Defina un contrato de servicios utilizando una interfaz marcado con <xref:System.ServiceModel.ServiceContractAttribute>. Marque las operaciones en la interfaz que forman parte del contrato de servicios con <xref:System.ServiceModel.OperationContractAttribute> y especifíquelas como unidireccionales porque no se devuelven respuestas al método. El código siguiente proporciona un contrato de servicios de ejemplo y su definición de operación.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  Si el contrato de servicio pasa los tipos definidos por el usuario, deberá definir los contratos de datos para esos tipos. El ejemplo de código siguiente muestra dos contratos de datos, `PurchaseOrder` y `PurchaseOrderLineItem`. Estos dos tipos definen los datos que se envían al servicio. (Tenga en cuenta que las clases que definen este contrato de datos también definen varios métodos. Estos métodos no se consideran parte del contrato de datos. Sólo esos miembros que estén declarados con el atributo `DataMember` forman parte del contrato de datos.)  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  Implemente los métodos del contrato de servicios definidos en la interfaz en una clase.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Observe el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> colocado en el método `SubmitPurchaseOrder`. Esto especifica que se debe llamar a esta operación dentro de una transacción, y que esta finaliza automáticamente cuando se completa el método.  
  
4.  Cree una cola transaccional utilizando <xref:System.Messaging>. Puede decidir crear la cola usando Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) en su lugar. En ese caso, asegúrese de crear una cola transaccional.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  Defina <xref:System.ServiceModel.Description.ServiceEndpoint> en configuración que especifique la dirección de servicio y use el enlace <xref:System.ServiceModel.NetMsmqBinding> estándar. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuración, consulte [configuración de Windows Communication Foundation Applications](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
  
  
6.  Cree un host para el servicio `OrderProcessing` utilizando <xref:System.ServiceModel.ServiceHost> que lea los mensajes de la cola y los procese. Abra el host de servicio para hacer que el servicio esté disponible. Muestre un mensaje que indique al usuario que debe presionar una tecla para finalizar el servicio. Llame a `ReadLine` para esperar a que se presione una tecla y, a continuación, cierre el servicio.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>Para crear un cliente para el servicio en cola  
  
1.  En el siguiente ejemplo se muestra cómo ejecutar la aplicación de hospedaje y cómo usar la herramienta Svcutil.exe para crear el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  Defina una clase <xref:System.ServiceModel.Description.ServiceEndpoint> en la configuración que especifique la dirección y use el enlace <xref:System.ServiceModel.NetMsmqBinding>, tal y como se muestra en el ejemplo siguiente.  
  
  
  
3.  Cree un ámbito de la transacción para escribir en la cola transaccional, llame a la operación `SubmitPurchaseOrder` y cierre el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], tal y como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran el código de servicio, la aplicación de hospedaje, el archivo App.config y el código de cliente incluidos en este ejemplo.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [Enlace MSMQ por transacciones](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [Las colas en WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Cómo: intercambiar mensajes con extremos de WCF y aplicaciones de Message Queuing](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [Instalar Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [Ejemplos de enlace de integración de puesta en cola de mensajes](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [Seguridad de mensajes mediante Message Queue Server](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
