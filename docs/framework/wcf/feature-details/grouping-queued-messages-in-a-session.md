---
title: "Agrupaci&#243;n de los mensajes en cola de una sesi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "colas [WCF]. agrupar los mensajes"
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Agrupaci&#243;n de los mensajes en cola de una sesi&#243;n
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona una sesión que le permite agrupar un conjunto de mensajes relacionados para que una única aplicación receptora los procese. Los mensajes que forman parte de una sesión deben formar parte de la misma transacción. Dado que todos los mensajes forman parte de la misma transacción, si se producir un error al procesar un mensaje, se deshace la sesión completa. Las sesiones tienen comportamientos similares con respecto a las colas de mensajes no enviados y a las colas de mensajes dudosos. El conjunto de propiedades Time to Live (TTL) establecido en un enlace de cola configurado para las sesiones se aplica a la sesión como un conjunto. Si solo se envían algunos de los mensajes en la sesión antes de que el TTL expire, la sesión completa se coloca en la cola de mensajes no enviados. De manera similar, cuando se produce un error al enviar, en una sesión, los mensajes a una aplicación desde la cola de la aplicación, la sesión completa se coloca en la cola de mensajes dudosos (si está disponible).  
  
## <a name="message-grouping-example"></a>Ejemplo de agrupación de mensajes  
 Un ejemplo donde agrupar los mensajes es útil es al implementar una aplicación de procesamiento de pedidos como un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Por ejemplo, un cliente envía un pedido a esta aplicación que contiene varios elementos. Por cada elemento, el cliente realiza una llamada al servicio, que resulta en el envío de un mensaje individual. Es posible que el servidor A reciba el primer elemento y que el servidor B reciba el segundo elemento. Cada vez que se agrega un elemento, el servidor que procesa ese elemento tiene que encontrar el pedido adecuado y agregar el elemento a él, lo que es altamente ineficaz. Todavía se encuentra con tales ineficacias con un servidor único que administre todas las solicitudes, porque el servidor debe seguir todos los pedidos que se procesan actualmente y determinar a cuál de los nuevos elementos pertenece. La agrupación de todas las solicitudes en un único pedido simplifica en gran medida la implementación de este tipo de aplicaciones. La aplicación de cliente envía todos los elementos de un único pedido en una sesión, de modo que cuando el servicio procesa el pedido, procesa toda la sesión al mismo tiempo. \  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>Para preparar un contrato de servicios para utilizar sesiones  
  
1.  Defina un contrato de servicios que requiera una sesión. Hacer esto con el <xref:System.ServiceModel.OperationContractAttribute> atributo y especificando:  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2.  Marque las operaciones en el contrato como unidireccionales, porque estos métodos no devuelven nada. Esto se realiza con la <xref:System.ServiceModel.OperationContractAttribute> atributo y especificando:  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3.  Implemente el contrato de servicios y especifique un `InstanceContextMode` de `PerSession`. Esto solo instancia el servicio una vez por sesión.  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4.  Cada operación del servicio requiere una transacción. Especifique esto con el <xref:System.ServiceModel.OperationBehaviorAttribute> atributo. La operación que completa la transacción también debería establecer `TransactionAutoComplete` en `true`.  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5.  Configure un extremo que utilice el enlace `NetProfileMsmqBinding` proporcionado por el sistema.  
  
6.  Crear una cola transaccional utilizando <xref:System.Messaging>. También puede crear la cola utilizando Message Queuing (MSMQ) o MMC. Si lo hace, cree una cola transaccional.  
  
7.  Crear un host de servicio para el servicio mediante <xref:System.ServiceModel.ServiceHost>.  
  
8.  Abra el host de servicio para hacer que el servicio esté disponible.  
  
9. Cierre el host de servicio.  
  
#### <a name="to-set-up-a-client"></a>Para configurar un cliente  
  
1.  Cree un ámbito de la transacción para escribir en la cola transaccional.  
  
2.  Crear la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente mediante la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta.  
  
3.  Realice el pedido.  
  
4.  Cierre el cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El siguiente ejemplo proporciona el código para el servicio `IProcessOrder` y para un cliente que utilice este servicio. Muestra cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza las sesiones en cola para proporcionar el comportamiento de la agrupación.  
  
### <a name="code-for-the-service"></a>Código del servicio  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  
  
  
  
### <a name="code-for-the-client"></a>Código del cliente  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  
  
  
  
## <a name="see-also"></a>Vea también  
 [Sesiones y colas](../../../../docs/framework/wcf/samples/sessions-and-queues.md)   
 [Información general de colas](../../../../docs/framework/wcf/feature-details/queues-overview.md)