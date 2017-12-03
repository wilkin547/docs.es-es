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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6c50d9c6740b0c680e349a71bf4b3bdece2b34f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="ce517-102">Cómo: Intercambiar mensajes en cola con puntos de conexión de WCF</span><span class="sxs-lookup"><span data-stu-id="ce517-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="ce517-103">Las colas garantizan que la mensajería de confianza puede tener lugar entre un cliente y un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], aun cuando el servicio no esté disponible en el momento de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="ce517-103">Queues ensure that reliable messaging can occur between a client and a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="ce517-104">Los procedimientos siguientes muestran cómo garantizar una comunicación duradera entre un cliente y un servicio utilizando el enlace en cola estándar al implementar el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce517-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="ce517-105">En esta sección se explica cómo utilizar <xref:System.ServiceModel.NetMsmqBinding> para la comunicación en cola entre un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce517-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="ce517-106">Para utilizar la puesta en cola en un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ce517-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="ce517-107">Defina un contrato de servicios utilizando una interfaz marcado con <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ce517-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="ce517-108">Marque las operaciones en la interfaz que forman parte del contrato de servicios con <xref:System.ServiceModel.OperationContractAttribute> y especifíquelas como unidireccionales porque no se devuelven respuestas al método.</span><span class="sxs-lookup"><span data-stu-id="ce517-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="ce517-109">El código siguiente proporciona un contrato de servicios de ejemplo y su definición de operación.</span><span class="sxs-lookup"><span data-stu-id="ce517-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="ce517-110">Si el contrato de servicio pasa los tipos definidos por el usuario, deberá definir los contratos de datos para esos tipos.</span><span class="sxs-lookup"><span data-stu-id="ce517-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="ce517-111">El ejemplo de código siguiente muestra dos contratos de datos, `PurchaseOrder` y `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="ce517-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="ce517-112">Estos dos tipos definen los datos que se envían al servicio.</span><span class="sxs-lookup"><span data-stu-id="ce517-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="ce517-113">(Tenga en cuenta que las clases que definen este contrato de datos también definen varios métodos.</span><span class="sxs-lookup"><span data-stu-id="ce517-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="ce517-114">Estos métodos no se consideran parte del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="ce517-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="ce517-115">Sólo esos miembros que estén declarados con el atributo `DataMember` forman parte del contrato de datos.)</span><span class="sxs-lookup"><span data-stu-id="ce517-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="ce517-116">Implemente los métodos del contrato de servicios definidos en la interfaz en una clase.</span><span class="sxs-lookup"><span data-stu-id="ce517-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="ce517-117">Observe el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> colocado en el método `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="ce517-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="ce517-118">Esto especifica que se debe llamar a esta operación dentro de una transacción, y que esta finaliza automáticamente cuando se completa el método.</span><span class="sxs-lookup"><span data-stu-id="ce517-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="ce517-119">Cree una cola transaccional utilizando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="ce517-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="ce517-120">Puede decidir crear la cola usando Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ce517-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="ce517-121">En ese caso, asegúrese de crear una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="ce517-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="ce517-122">Defina <xref:System.ServiceModel.Description.ServiceEndpoint> en configuración que especifique la dirección de servicio y use el enlace <xref:System.ServiceModel.NetMsmqBinding> estándar.</span><span class="sxs-lookup"><span data-stu-id="ce517-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ce517-123">usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuración, consulte [configuración de Windows Communication Foundation Applications](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="ce517-123"> using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="ce517-124">Cree un host para el servicio `OrderProcessing` utilizando <xref:System.ServiceModel.ServiceHost> que lea los mensajes de la cola y los procese.</span><span class="sxs-lookup"><span data-stu-id="ce517-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="ce517-125">Abra el host de servicio para hacer que el servicio esté disponible.</span><span class="sxs-lookup"><span data-stu-id="ce517-125">Open the service host to make the service available.</span></span> <span data-ttu-id="ce517-126">Muestre un mensaje que indique al usuario que debe presionar una tecla para finalizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce517-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="ce517-127">Llame a `ReadLine` para esperar a que se presione una tecla y, a continuación, cierre el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce517-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="ce517-128">Para crear un cliente para el servicio en cola</span><span class="sxs-lookup"><span data-stu-id="ce517-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="ce517-129">En el siguiente ejemplo se muestra cómo ejecutar la aplicación de hospedaje y cómo usar la herramienta Svcutil.exe para crear el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce517-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="ce517-130">Defina una clase <xref:System.ServiceModel.Description.ServiceEndpoint> en la configuración que especifique la dirección y use el enlace <xref:System.ServiceModel.NetMsmqBinding>, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce517-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="ce517-131">Cree un ámbito de la transacción para escribir en la cola transaccional, llame a la operación `SubmitPurchaseOrder` y cierre el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce517-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="ce517-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce517-132">Example</span></span>  
 <span data-ttu-id="ce517-133">Los ejemplos siguientes muestran el código de servicio, la aplicación de hospedaje, el archivo App.config y el código de cliente incluidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce517-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="ce517-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce517-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="ce517-135">Enlace MSMQ por transacciones</span><span class="sxs-lookup"><span data-stu-id="ce517-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="ce517-136">Las colas en WCF</span><span class="sxs-lookup"><span data-stu-id="ce517-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="ce517-137">Cómo: intercambiar mensajes con extremos de WCF y aplicaciones de Message Queuing</span><span class="sxs-lookup"><span data-stu-id="ce517-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="ce517-138">Windows Communication Foundation a Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="ce517-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="ce517-139">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="ce517-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="ce517-140">Ejemplos de enlace de integración de puesta en cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="ce517-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="ce517-141">Message Queue Server de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ce517-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="ce517-142">Seguridad de mensajes mediante Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="ce517-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
