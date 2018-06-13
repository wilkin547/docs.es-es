---
title: 'Cómo: Intercambiar mensajes en cola con puntos de conexión de WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: ab6ca46fad8ee1ededef5cc14a9654b79b2e6a8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494662"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="10d0e-102">Cómo: Intercambiar mensajes en cola con puntos de conexión de WCF</span><span class="sxs-lookup"><span data-stu-id="10d0e-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="10d0e-103">Las colas garantizan que puede producirse una mensajería de confianza entre un cliente y un servicio de Windows Communication Foundation (WCF), incluso si el servicio no está disponible en el momento de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="10d0e-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="10d0e-104">Los procedimientos siguientes muestran cómo garantizar una comunicación duradera entre un cliente y un servicio mediante el estándar de enlace en cola al implementar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="10d0e-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="10d0e-105">Esta sección explica cómo usar <xref:System.ServiceModel.NetMsmqBinding> para la comunicación en cola entre un cliente WCF y un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="10d0e-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="10d0e-106">Para utilizar la puesta en cola en un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="10d0e-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="10d0e-107">Defina un contrato de servicios utilizando una interfaz marcado con <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10d0e-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="10d0e-108">Marque las operaciones en la interfaz que forman parte del contrato de servicios con <xref:System.ServiceModel.OperationContractAttribute> y especifíquelas como unidireccionales porque no se devuelven respuestas al método.</span><span class="sxs-lookup"><span data-stu-id="10d0e-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="10d0e-109">El código siguiente proporciona un contrato de servicios de ejemplo y su definición de operación.</span><span class="sxs-lookup"><span data-stu-id="10d0e-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="10d0e-110">Si el contrato de servicio pasa los tipos definidos por el usuario, deberá definir los contratos de datos para esos tipos.</span><span class="sxs-lookup"><span data-stu-id="10d0e-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="10d0e-111">El ejemplo de código siguiente muestra dos contratos de datos, `PurchaseOrder` y `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="10d0e-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="10d0e-112">Estos dos tipos definen los datos que se envían al servicio.</span><span class="sxs-lookup"><span data-stu-id="10d0e-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="10d0e-113">(Tenga en cuenta que las clases que definen este contrato de datos también definen varios métodos.</span><span class="sxs-lookup"><span data-stu-id="10d0e-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="10d0e-114">Estos métodos no se consideran parte del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="10d0e-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="10d0e-115">Sólo esos miembros que estén declarados con el atributo `DataMember` forman parte del contrato de datos.)</span><span class="sxs-lookup"><span data-stu-id="10d0e-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="10d0e-116">Implemente los métodos del contrato de servicios definidos en la interfaz en una clase.</span><span class="sxs-lookup"><span data-stu-id="10d0e-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="10d0e-117">Observe el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> colocado en el método `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="10d0e-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="10d0e-118">Esto especifica que se debe llamar a esta operación dentro de una transacción, y que esta finaliza automáticamente cuando se completa el método.</span><span class="sxs-lookup"><span data-stu-id="10d0e-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="10d0e-119">Cree una cola transaccional utilizando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="10d0e-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="10d0e-120">Puede decidir crear la cola usando Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="10d0e-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="10d0e-121">En ese caso, asegúrese de crear una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="10d0e-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="10d0e-122">Defina <xref:System.ServiceModel.Description.ServiceEndpoint> en configuración que especifique la dirección de servicio y use el enlace <xref:System.ServiceModel.NetMsmqBinding> estándar.</span><span class="sxs-lookup"><span data-stu-id="10d0e-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="10d0e-123">Para obtener más información acerca del uso de configuración de WCF, vea [configuración de Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="10d0e-123">For more information about using WCF configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="10d0e-124">Cree un host para el servicio `OrderProcessing` utilizando <xref:System.ServiceModel.ServiceHost> que lea los mensajes de la cola y los procese.</span><span class="sxs-lookup"><span data-stu-id="10d0e-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="10d0e-125">Abra el host de servicio para hacer que el servicio esté disponible.</span><span class="sxs-lookup"><span data-stu-id="10d0e-125">Open the service host to make the service available.</span></span> <span data-ttu-id="10d0e-126">Muestre un mensaje que indique al usuario que debe presionar una tecla para finalizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="10d0e-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="10d0e-127">Llame a `ReadLine` para esperar a que se presione una tecla y, a continuación, cierre el servicio.</span><span class="sxs-lookup"><span data-stu-id="10d0e-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="10d0e-128">Para crear un cliente para el servicio en cola</span><span class="sxs-lookup"><span data-stu-id="10d0e-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="10d0e-129">En el ejemplo siguiente se muestra cómo ejecutar la aplicación de hospedaje y usar la herramienta Svcutil.exe para crear al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="10d0e-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="10d0e-130">Defina una clase <xref:System.ServiceModel.Description.ServiceEndpoint> en la configuración que especifique la dirección y use el enlace <xref:System.ServiceModel.NetMsmqBinding>, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="10d0e-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="10d0e-131">Cree un ámbito de transacción para escribir en la cola transaccional, llame a la `SubmitPurchaseOrder` operación y cierre el cliente WCF, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="10d0e-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="10d0e-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10d0e-132">Example</span></span>  
 <span data-ttu-id="10d0e-133">Los ejemplos siguientes muestran el código de servicio, la aplicación de hospedaje, el archivo App.config y el código de cliente incluidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="10d0e-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="10d0e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d0e-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="10d0e-135">Enlace MSMQ por transacciones</span><span class="sxs-lookup"><span data-stu-id="10d0e-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="10d0e-136">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="10d0e-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="10d0e-137">Intercambio de mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="10d0e-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="10d0e-138">Windows Communication Foundation a Message Queuing</span><span class="sxs-lookup"><span data-stu-id="10d0e-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="10d0e-139">Instalación de Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="10d0e-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="10d0e-140">Ejemplos de enlace de integración de puesta en cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="10d0e-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="10d0e-141">Message Queuing a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="10d0e-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="10d0e-142">Seguridad de mensajes mediante Message Queuing</span><span class="sxs-lookup"><span data-stu-id="10d0e-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
