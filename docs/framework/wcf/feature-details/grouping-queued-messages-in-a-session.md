---
title: Agrupación de los mensajes en cola de una sesión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 37f0874ea99ee928e49a54a3e6a05ea4ef06f84e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294670"
---
# <a name="grouping-queued-messages-in-a-session"></a>Agrupación de los mensajes en cola de una sesión
Windows Communication Foundation (WCF) proporciona una sesión que le permite agrupar un conjunto de mensajes relacionados para el procesamiento por una aplicación receptora única. Los mensajes que forman parte de una sesión deben formar parte de la misma transacción. Dado que todos los mensajes forman parte de la misma transacción, si se producir un error al procesar un mensaje, se deshace la sesión completa. Las sesiones tienen comportamientos similares con respecto a las colas de mensajes no enviados y a las colas de mensajes dudosos. El conjunto de propiedades Time to Live (TTL) establecido en un enlace de cola configurado para las sesiones se aplica a la sesión como un conjunto. Si solo se envían algunos de los mensajes en la sesión antes de que el TTL expire, la sesión completa se coloca en la cola de mensajes no enviados. De manera similar, cuando se produce un error al enviar, en una sesión, los mensajes a una aplicación desde la cola de la aplicación, la sesión completa se coloca en la cola de mensajes dudosos (si está disponible).  
  
## <a name="message-grouping-example"></a>Ejemplo de agrupación de mensajes  
 Un ejemplo donde agrupar los mensajes es útil es al implementar una aplicación de procesamiento de pedidos como un servicio WCF. Por ejemplo, un cliente envía un pedido a esta aplicación que contiene varios elementos. Por cada elemento, el cliente realiza una llamada al servicio, que resulta en el envío de un mensaje individual. Es posible que el servidor A reciba el primer elemento y que el servidor B reciba el segundo elemento. Cada vez que se agrega un elemento, el servidor que procesa ese elemento tiene que encontrar el pedido adecuado y agregar el elemento a él, lo que es altamente ineficaz. Todavía se encuentra con tales ineficacias con un servidor único que administre todas las solicitudes, porque el servidor debe seguir todos los pedidos que se procesan actualmente y determinar a cuál de los nuevos elementos pertenece. La agrupación de todas las solicitudes en un único pedido simplifica en gran medida la implementación de este tipo de aplicaciones. La aplicación de cliente envía todos los elementos de un único pedido en una sesión, de modo que cuando el servicio procesa el pedido, procesa toda la sesión al mismo tiempo. \  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>Para preparar un contrato de servicios para utilizar sesiones  
  
1. Defina un contrato de servicios que requiera una sesión. Hágalo mediante el atributo <xref:System.ServiceModel.OperationContractAttribute> y especificando:  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2. Marque las operaciones en el contrato como unidireccionales, porque estos métodos no devuelven nada. Esto se realiza mediante el atributo <xref:System.ServiceModel.OperationContractAttribute> y especificando:  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. Implemente el contrato de servicios y especifique un `InstanceContextMode` de `PerSession`. Esto solo instancia el servicio una vez por sesión.  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. Cada operación del servicio requiere una transacción. Especifique esto con el atributo <xref:System.ServiceModel.OperationBehaviorAttribute>. La operación que completa la transacción también debería establecer `TransactionAutoComplete` en `true`.  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5. Configure un extremo que utilice el enlace `NetMsmqBinding` proporcionado por el sistema.  
  
6. Cree una cola transaccional utilizando <xref:System.Messaging>. También puede crear la cola utilizando Message Queuing (MSMQ) o MMC. Si lo hace, cree una cola transaccional.  
  
7. Cree un host del servicio para el servicio mediante el uso de <xref:System.ServiceModel.ServiceHost>.  
  
8. Abra el host de servicio para hacer que el servicio esté disponible.  
  
9. Cierre el host de servicio.  
  
#### <a name="to-set-up-a-client"></a>Para configurar un cliente  
  
1. Cree un ámbito de la transacción para escribir en la cola transaccional.  
  
2. Crear el cliente WCF mediante el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta.  
  
3. Realice el pedido.  
  
4. Cierre al cliente WCF.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El siguiente ejemplo proporciona el código para el servicio `IProcessOrder` y para un cliente que utilice este servicio. Muestra cómo WCF usa las sesiones en cola para proporcionar el comportamiento de agrupación.  
  
### <a name="code-for-the-service"></a>Código del servicio  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a>Código del cliente  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a>Vea también

- [Sesiones y colas](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [Información general de colas](../../../../docs/framework/wcf/feature-details/queues-overview.md)
