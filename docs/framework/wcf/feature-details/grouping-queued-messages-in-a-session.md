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
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="3102a-102">Agrupación de los mensajes en cola de una sesión</span><span class="sxs-lookup"><span data-stu-id="3102a-102">Grouping Queued Messages in a Session</span></span>
<span data-ttu-id="3102a-103">Windows Communication Foundation (WCF) proporciona una sesión que le permite agrupar un conjunto de mensajes relacionados para el procesamiento por una aplicación receptora única.</span><span class="sxs-lookup"><span data-stu-id="3102a-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="3102a-104">Los mensajes que forman parte de una sesión deben formar parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="3102a-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="3102a-105">Dado que todos los mensajes forman parte de la misma transacción, si se producir un error al procesar un mensaje, se deshace la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="3102a-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="3102a-106">Las sesiones tienen comportamientos similares con respecto a las colas de mensajes no enviados y a las colas de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="3102a-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="3102a-107">El conjunto de propiedades Time to Live (TTL) establecido en un enlace de cola configurado para las sesiones se aplica a la sesión como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="3102a-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="3102a-108">Si solo se envían algunos de los mensajes en la sesión antes de que el TTL expire, la sesión completa se coloca en la cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="3102a-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="3102a-109">De manera similar, cuando se produce un error al enviar, en una sesión, los mensajes a una aplicación desde la cola de la aplicación, la sesión completa se coloca en la cola de mensajes dudosos (si está disponible).</span><span class="sxs-lookup"><span data-stu-id="3102a-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="3102a-110">Ejemplo de agrupación de mensajes</span><span class="sxs-lookup"><span data-stu-id="3102a-110">Message Grouping Example</span></span>  
 <span data-ttu-id="3102a-111">Un ejemplo donde agrupar los mensajes es útil es al implementar una aplicación de procesamiento de pedidos como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3102a-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="3102a-112">Por ejemplo, un cliente envía un pedido a esta aplicación que contiene varios elementos.</span><span class="sxs-lookup"><span data-stu-id="3102a-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="3102a-113">Por cada elemento, el cliente realiza una llamada al servicio, que resulta en el envío de un mensaje individual.</span><span class="sxs-lookup"><span data-stu-id="3102a-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="3102a-114">Es posible que el servidor A reciba el primer elemento y que el servidor B reciba el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="3102a-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="3102a-115">Cada vez que se agrega un elemento, el servidor que procesa ese elemento tiene que encontrar el pedido adecuado y agregar el elemento a él, lo que es altamente ineficaz.</span><span class="sxs-lookup"><span data-stu-id="3102a-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="3102a-116">Todavía se encuentra con tales ineficacias con un servidor único que administre todas las solicitudes, porque el servidor debe seguir todos los pedidos que se procesan actualmente y determinar a cuál de los nuevos elementos pertenece.</span><span class="sxs-lookup"><span data-stu-id="3102a-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="3102a-117">La agrupación de todas las solicitudes en un único pedido simplifica en gran medida la implementación de este tipo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3102a-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="3102a-118">La aplicación de cliente envía todos los elementos de un único pedido en una sesión, de modo que cuando el servicio procesa el pedido, procesa toda la sesión al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3102a-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="3102a-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="3102a-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="3102a-120">Para preparar un contrato de servicios para utilizar sesiones</span><span class="sxs-lookup"><span data-stu-id="3102a-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="3102a-121">Defina un contrato de servicios que requiera una sesión.</span><span class="sxs-lookup"><span data-stu-id="3102a-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="3102a-122">Hágalo mediante el atributo <xref:System.ServiceModel.OperationContractAttribute> y especificando:</span><span class="sxs-lookup"><span data-stu-id="3102a-122">Do this with the <xref:System.ServiceModel.OperationContractAttribute> attribute and by specifying:</span></span>  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="3102a-123">Marque las operaciones en el contrato como unidireccionales, porque estos métodos no devuelven nada.</span><span class="sxs-lookup"><span data-stu-id="3102a-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="3102a-124">Esto se realiza mediante el atributo <xref:System.ServiceModel.OperationContractAttribute> y especificando:</span><span class="sxs-lookup"><span data-stu-id="3102a-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute and by specifying:</span></span>  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="3102a-125">Implemente el contrato de servicios y especifique un `InstanceContextMode` de `PerSession`.</span><span class="sxs-lookup"><span data-stu-id="3102a-125">Implement the service contract and specify an `InstanceContextMode` of `PerSession`.</span></span> <span data-ttu-id="3102a-126">Esto solo instancia el servicio una vez por sesión.</span><span class="sxs-lookup"><span data-stu-id="3102a-126">This instantiates the service only once for each session.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="3102a-127">Cada operación del servicio requiere una transacción.</span><span class="sxs-lookup"><span data-stu-id="3102a-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="3102a-128">Especifique esto con el atributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3102a-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="3102a-129">La operación que completa la transacción también debería establecer `TransactionAutoComplete` en `true`.</span><span class="sxs-lookup"><span data-stu-id="3102a-129">The operation that completes the transaction should also set `TransactionAutoComplete` to `true`.</span></span>  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5. <span data-ttu-id="3102a-130">Configure un extremo que utilice el enlace `NetMsmqBinding` proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="3102a-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="3102a-131">Cree una cola transaccional utilizando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="3102a-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="3102a-132">También puede crear la cola utilizando Message Queuing (MSMQ) o MMC.</span><span class="sxs-lookup"><span data-stu-id="3102a-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="3102a-133">Si lo hace, cree una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="3102a-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="3102a-134">Cree un host del servicio para el servicio mediante el uso de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="3102a-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="3102a-135">Abra el host de servicio para hacer que el servicio esté disponible.</span><span class="sxs-lookup"><span data-stu-id="3102a-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="3102a-136">Cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="3102a-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="3102a-137">Para configurar un cliente</span><span class="sxs-lookup"><span data-stu-id="3102a-137">To set up a client</span></span>  
  
1. <span data-ttu-id="3102a-138">Cree un ámbito de la transacción para escribir en la cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="3102a-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="3102a-139">Crear el cliente WCF mediante el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta.</span><span class="sxs-lookup"><span data-stu-id="3102a-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="3102a-140">Realice el pedido.</span><span class="sxs-lookup"><span data-stu-id="3102a-140">Place the order.</span></span>  
  
4. <span data-ttu-id="3102a-141">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="3102a-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3102a-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3102a-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3102a-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="3102a-143">Description</span></span>  
 <span data-ttu-id="3102a-144">El siguiente ejemplo proporciona el código para el servicio `IProcessOrder` y para un cliente que utilice este servicio.</span><span class="sxs-lookup"><span data-stu-id="3102a-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="3102a-145">Muestra cómo WCF usa las sesiones en cola para proporcionar el comportamiento de agrupación.</span><span class="sxs-lookup"><span data-stu-id="3102a-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="3102a-146">Código del servicio</span><span class="sxs-lookup"><span data-stu-id="3102a-146">Code for the Service</span></span>  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="3102a-147">Código del cliente</span><span class="sxs-lookup"><span data-stu-id="3102a-147">Code for the Client</span></span>  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="3102a-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="3102a-148">See also</span></span>

- [<span data-ttu-id="3102a-149">Sesiones y colas</span><span class="sxs-lookup"><span data-stu-id="3102a-149">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [<span data-ttu-id="3102a-150">Información general de colas</span><span class="sxs-lookup"><span data-stu-id="3102a-150">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
