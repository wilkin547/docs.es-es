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
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="517c7-103">Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF</span><span class="sxs-lookup"><span data-stu-id="517c7-103">How to: Exchange Queued Messages with WCF Endpoints</span></span>

<span data-ttu-id="517c7-104">Las colas garantizan que se pueda producir mensajería de confianza entre un cliente y un servicio de Windows Communication Foundation (WCF), incluso si el servicio no está disponible en el momento de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="517c7-104">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="517c7-105">Los procedimientos siguientes muestran cómo garantizar la comunicación duradera entre un cliente y un servicio mediante el enlace en cola estándar al implementar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="517c7-105">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="517c7-106">En esta sección se explica cómo usar <xref:System.ServiceModel.NetMsmqBinding> para la comunicación en cola entre un cliente WCF y un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="517c7-106">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="517c7-107">Para utilizar la puesta en cola en un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="517c7-107">To use queuing in a WCF service</span></span>  
  
1. <span data-ttu-id="517c7-108">Defina un contrato de servicios utilizando una interfaz marcado con <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="517c7-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="517c7-109">Marque las operaciones en la interfaz que forman parte del contrato de servicios con <xref:System.ServiceModel.OperationContractAttribute> y especifíquelas como unidireccionales porque no se devuelven respuestas al método.</span><span class="sxs-lookup"><span data-stu-id="517c7-109">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="517c7-110">El código siguiente proporciona un contrato de servicios de ejemplo y su definición de operación.</span><span class="sxs-lookup"><span data-stu-id="517c7-110">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. <span data-ttu-id="517c7-111">Si el contrato de servicio pasa los tipos definidos por el usuario, deberá definir los contratos de datos para esos tipos.</span><span class="sxs-lookup"><span data-stu-id="517c7-111">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="517c7-112">El ejemplo de código siguiente muestra dos contratos de datos, `PurchaseOrder` y `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="517c7-112">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="517c7-113">Estos dos tipos definen los datos que se envían al servicio.</span><span class="sxs-lookup"><span data-stu-id="517c7-113">These two types define data that is sent to the service.</span></span> <span data-ttu-id="517c7-114">(Tenga en cuenta que las clases que definen este contrato de datos también definen varios métodos.</span><span class="sxs-lookup"><span data-stu-id="517c7-114">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="517c7-115">Estos métodos no se consideran parte del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="517c7-115">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="517c7-116">Sólo esos miembros que estén declarados con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> forman parte del contrato de datos.)</span><span class="sxs-lookup"><span data-stu-id="517c7-116">Only those members that are declared with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. <span data-ttu-id="517c7-117">Implemente los métodos del contrato de servicios definidos en la interfaz en una clase.</span><span class="sxs-lookup"><span data-stu-id="517c7-117">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="517c7-118">Observe el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> colocado en el método `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="517c7-118">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="517c7-119">Esto especifica que se debe llamar a esta operación dentro de una transacción, y que esta finaliza automáticamente cuando se completa el método.</span><span class="sxs-lookup"><span data-stu-id="517c7-119">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4. <span data-ttu-id="517c7-120">Cree una cola transaccional utilizando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="517c7-120">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="517c7-121">Puede decidir crear la cola usando Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="517c7-121">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="517c7-122">En ese caso, asegúrese de crear una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="517c7-122">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. <span data-ttu-id="517c7-123">Defina <xref:System.ServiceModel.Description.ServiceEndpoint> en configuración que especifique la dirección de servicio y use el enlace <xref:System.ServiceModel.NetMsmqBinding> estándar.</span><span class="sxs-lookup"><span data-stu-id="517c7-123">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="517c7-124">Para obtener más información acerca del uso de la configuración de WCF, vea [configuración de servicios WCF](../configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="517c7-124">For more information about using WCF configuration, see [Configuring WCF services](../configuring-services.md).</span></span>  

6. <span data-ttu-id="517c7-125">Cree un host para el servicio `OrderProcessing` utilizando <xref:System.ServiceModel.ServiceHost> que lea los mensajes de la cola y los procese.</span><span class="sxs-lookup"><span data-stu-id="517c7-125">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="517c7-126">Abra el host de servicio para hacer que el servicio esté disponible.</span><span class="sxs-lookup"><span data-stu-id="517c7-126">Open the service host to make the service available.</span></span> <span data-ttu-id="517c7-127">Muestre un mensaje que indique al usuario que debe presionar una tecla para finalizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="517c7-127">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="517c7-128">Llame a `ReadLine` para esperar a que se presione una tecla y, a continuación, cierre el servicio.</span><span class="sxs-lookup"><span data-stu-id="517c7-128">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="517c7-129">Para crear un cliente para el servicio en cola</span><span class="sxs-lookup"><span data-stu-id="517c7-129">To create a client for the queued service</span></span>  
  
1. <span data-ttu-id="517c7-130">En el ejemplo siguiente se muestra cómo ejecutar la aplicación de hospedaje y utilizar la herramienta de Svcutil.exe para crear el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="517c7-130">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```console
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. <span data-ttu-id="517c7-131">Defina una clase <xref:System.ServiceModel.Description.ServiceEndpoint> en la configuración que especifique la dirección y use el enlace <xref:System.ServiceModel.NetMsmqBinding>, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="517c7-131">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  

3. <span data-ttu-id="517c7-132">Cree un ámbito de transacción para escribir en la cola transaccional, llame a la `SubmitPurchaseOrder` operación y cierre el cliente de WCF, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="517c7-132">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="517c7-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="517c7-133">Example</span></span>  

 <span data-ttu-id="517c7-134">Los ejemplos siguientes muestran el código de servicio, la aplicación de hospedaje, el archivo App.config y el código de cliente incluidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="517c7-134">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  

 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  

## <a name="see-also"></a><span data-ttu-id="517c7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="517c7-135">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- [<span data-ttu-id="517c7-136">Enlace MSMQ por transacciones</span><span class="sxs-lookup"><span data-stu-id="517c7-136">Transacted MSMQ Binding</span></span>](../samples/transacted-msmq-binding.md)
- [<span data-ttu-id="517c7-137">Las colas en WCF</span><span class="sxs-lookup"><span data-stu-id="517c7-137">Queuing in WCF</span></span>](queuing-in-wcf.md)
- [<span data-ttu-id="517c7-138">Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="517c7-138">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [<span data-ttu-id="517c7-139">Windows Communication Foundation a Message Queuing</span><span class="sxs-lookup"><span data-stu-id="517c7-139">Windows Communication Foundation to Message Queuing</span></span>](../samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="517c7-140">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="517c7-140">Installing Message Queuing (MSMQ)</span></span>](../samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="517c7-141">Message Queuing a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="517c7-141">Message Queuing to Windows Communication Foundation</span></span>](../samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="517c7-142">Seguridad de mensajes mediante Message Queuing</span><span class="sxs-lookup"><span data-stu-id="517c7-142">Message Security over Message Queuing</span></span>](../samples/message-security-over-message-queuing.md)
