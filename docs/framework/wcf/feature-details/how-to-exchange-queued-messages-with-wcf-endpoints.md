---
description: 'Más información acerca de cómo: intercambiar mensajes en cola con puntos de conexión de WCF'
title: Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: fe7195719c57454cb0035c1b6f06134cf3380a46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802897"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF

Las colas garantizan que se pueda producir mensajería de confianza entre un cliente y un servicio de Windows Communication Foundation (WCF), incluso si el servicio no está disponible en el momento de la comunicación. Los procedimientos siguientes muestran cómo garantizar la comunicación duradera entre un cliente y un servicio mediante el enlace en cola estándar al implementar el servicio WCF.  
  
 En esta sección se explica cómo usar <xref:System.ServiceModel.NetMsmqBinding> para la comunicación en cola entre un cliente WCF y un servicio WCF.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>Para utilizar la puesta en cola en un servicio WCF  
  
1. Defina un contrato de servicios utilizando una interfaz marcado con <xref:System.ServiceModel.ServiceContractAttribute>. Marque las operaciones en la interfaz que forman parte del contrato de servicios con <xref:System.ServiceModel.OperationContractAttribute> y especifíquelas como unidireccionales porque no se devuelven respuestas al método. El código siguiente proporciona un contrato de servicios de ejemplo y su definición de operación.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. Si el contrato de servicio pasa los tipos definidos por el usuario, deberá definir los contratos de datos para esos tipos. El ejemplo de código siguiente muestra dos contratos de datos, `PurchaseOrder` y `PurchaseOrderLineItem`. Estos dos tipos definen los datos que se envían al servicio. (Tenga en cuenta que las clases que definen este contrato de datos también definen varios métodos. Estos métodos no se consideran parte del contrato de datos. Sólo esos miembros que estén declarados con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> forman parte del contrato de datos.)  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. Implemente los métodos del contrato de servicios definidos en la interfaz en una clase.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Observe el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> colocado en el método `SubmitPurchaseOrder`. Esto especifica que se debe llamar a esta operación dentro de una transacción, y que esta finaliza automáticamente cuando se completa el método.  
  
4. Cree una cola transaccional utilizando <xref:System.Messaging>. Puede decidir crear la cola usando Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) en su lugar. En ese caso, asegúrese de crear una cola transaccional.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. Defina <xref:System.ServiceModel.Description.ServiceEndpoint> en configuración que especifique la dirección de servicio y use el enlace <xref:System.ServiceModel.NetMsmqBinding> estándar. Para obtener más información acerca del uso de la configuración de WCF, vea [configuración de servicios WCF](../configuring-services.md).  

6. Cree un host para el servicio `OrderProcessing` utilizando <xref:System.ServiceModel.ServiceHost> que lea los mensajes de la cola y los procese. Abra el host de servicio para hacer que el servicio esté disponible. Muestre un mensaje que indique al usuario que debe presionar una tecla para finalizar el servicio. Llame a `ReadLine` para esperar a que se presione una tecla y, a continuación, cierre el servicio.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>Para crear un cliente para el servicio en cola  
  
1. En el ejemplo siguiente se muestra cómo ejecutar la aplicación de hospedaje y utilizar la herramienta de Svcutil.exe para crear el cliente de WCF.  
  
    ```console
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. Defina una clase <xref:System.ServiceModel.Description.ServiceEndpoint> en la configuración que especifique la dirección y use el enlace <xref:System.ServiceModel.NetMsmqBinding>, tal y como se muestra en el ejemplo siguiente.  

3. Cree un ámbito de transacción para escribir en la cola transaccional, llame a la `SubmitPurchaseOrder` operación y cierre el cliente de WCF, como se muestra en el ejemplo siguiente.  
  
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

- <xref:System.ServiceModel.NetMsmqBinding>
- [Enlace MSMQ por transacciones](../samples/transacted-msmq-binding.md)
- [Las colas en WCF](queuing-in-wcf.md)
- [Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Windows Communication Foundation a Message Queuing](../samples/wcf-to-message-queuing.md)
- [Instalar Message Queuing (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Message Queuing a Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Seguridad de mensajes mediante Message Queuing](../samples/message-security-over-message-queuing.md)
