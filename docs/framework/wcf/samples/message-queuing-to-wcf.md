---
description: 'Más información acerca de: Message Queue Server para Windows Communication Foundation'
title: Message Queuing a Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
ms.openlocfilehash: 53c535379584bcb8fa50d1b550f87ea7acc15175
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704009"
---
# <a name="message-queuing-to-windows-communication-foundation"></a><span data-ttu-id="df0eb-103">Message Queuing a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="df0eb-103">Message Queuing to Windows Communication Foundation</span></span>

<span data-ttu-id="df0eb-104">Este ejemplo muestra cómo una aplicación de Message Queuing (MSMQ) puede enviar un mensaje de MSMQ a un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="df0eb-104">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="df0eb-105">El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="df0eb-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="df0eb-106">El contrato de servicio es `IOrderProcessor`, que define un servicio unidireccional que es adecuado para usarse con colas.</span><span class="sxs-lookup"><span data-stu-id="df0eb-106">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="df0eb-107">Un mensaje de MSMQ no tiene un encabezado Acción, por lo que no es posible asignar automáticamente distintos mensajes de MSMQ a los contratos de operación.</span><span class="sxs-lookup"><span data-stu-id="df0eb-107">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="df0eb-108">Además, solo puede haber un contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="df0eb-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="df0eb-109">Si desea definir más de un contrato de operación para el servicio, la aplicación debe proporcionar información como qué encabezado en el mensaje de MSMQ (por ejemplo, la etiqueta o correlationID) se puede utilizar para decidir qué contrato de operación distribuir.</span><span class="sxs-lookup"><span data-stu-id="df0eb-109">If you want to define more than one operation contract for the service, the application must provide information as to which header in the MSMQ message (for example, the label or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="df0eb-110">El mensaje de MSMQ no contiene información sobre qué encabezados están asignados a los distintos parámetros del contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="df0eb-110">The MSMQ message does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="df0eb-111">El parámetro es de tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), que contiene el mensaje de MSMQ subyacente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-111">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), which contains the underlying MSMQ message.</span></span> <span data-ttu-id="df0eb-112">El tipo "T" en la clase <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) representa los datos que se serializan en el cuerpo del mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="df0eb-112">The type "T" in the <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="df0eb-113">En este ejemplo, el tipo `PurchaseOrder` se serializa en el cuerpo del mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="df0eb-113">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

 <span data-ttu-id="df0eb-114">El código de ejemplo siguiente muestra el contrato de servicio del servicio de procesamiento de órdenes.</span><span class="sxs-lookup"><span data-stu-id="df0eb-114">The following sample code shows the service contract of the order processing service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="df0eb-115">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="df0eb-115">The service is self hosted.</span></span> <span data-ttu-id="df0eb-116">Al utilizar MSMQ, la cola usada debe crearse de antemano.</span><span class="sxs-lookup"><span data-stu-id="df0eb-116">When using MSMQ, the queue used must be created in advance.</span></span> <span data-ttu-id="df0eb-117">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="df0eb-117">This can be done manually or through code.</span></span> <span data-ttu-id="df0eb-118">En este ejemplo, el servicio comprueba la existencia de la cola y la crea si es necesario.</span><span class="sxs-lookup"><span data-stu-id="df0eb-118">In this sample, the service checks for the existence of the queue and creates it if required.</span></span> <span data-ttu-id="df0eb-119">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="df0eb-119">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
    // Get the MSMQ queue name from the application settings in
    // configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];
    // Create the MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);
    …
}
```

 <span data-ttu-id="df0eb-120">El servicio crea y abre un <xref:System.ServiceModel.ServiceHost> para `OrderProcessorService`, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-120">The service creates and opens a <xref:System.ServiceModel.ServiceHost> for the `OrderProcessorService`, as shown in the following sample code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
    serviceHost.Open();
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
    serviceHost.Close();
}
```

 <span data-ttu-id="df0eb-121">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-121">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="df0eb-122">El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="df0eb-122">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="df0eb-123">La dirección del extremo de WCF especifica un esquema MSMQ. FormatName y utiliza localhost para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="df0eb-123">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="df0eb-124">La dirección de la cola para las directrices de direccionamiento del nombre de formato de MSMQ sigue el esquema msmq.formatname.</span><span class="sxs-lookup"><span data-stu-id="df0eb-124">The address of the queue for each MSMQ Format Name addressing guidelines follows the msmq.formatname scheme.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="df0eb-125">La aplicación cliente es una aplicación MSMQ que utiliza el método <xref:System.Messaging.MessageQueue.Send%2A> para enviar un mensaje duradero y un mensaje transaccional a la cola, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-125">The client application is an MSMQ application that uses the <xref:System.Messaging.MessageQueue.Send%2A> method to send a durable and transactional message to the queue, as shown in the following sample code.</span></span>

```csharp
//Connect to the queue.
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);

// Create the purchase order.
PurchaseOrder po = new PurchaseOrder();
po.CustomerId = "somecustomer.com";
po.PONumber = Guid.NewGuid().ToString();

PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
lineItem1.ProductId = "Blue Widget";
lineItem1.Quantity = 54;
lineItem1.UnitCost = 29.99F;

PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
lineItem2.ProductId = "Red Widget";
lineItem2.Quantity = 890;
lineItem2.UnitCost = 45.89F;

po.orderLineItems = new PurchaseOrderLineItem[2];
po.orderLineItems[0] = lineItem1;
po.orderLineItems[1] = lineItem2;

// Submit the purchase order.
Message msg = new Message();
msg.Body = po;
//Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{

    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
    // Complete the transaction.
    scope.Complete();

}
Console.WriteLine("Placed the order:{0}", po);
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="df0eb-126">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="df0eb-126">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="df0eb-127">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-127">You can see the service receive messages from the client.</span></span> <span data-ttu-id="df0eb-128">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-128">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="df0eb-129">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-129">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="df0eb-130">Por ejemplo, podría ejecutar el cliente, cerrarlo e iniciar el servicio y seguiría recibiendo sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="df0eb-130">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="df0eb-131">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="df0eb-131">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="df0eb-132">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="df0eb-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="df0eb-133">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-133">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="df0eb-134">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="df0eb-134">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="df0eb-135">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="df0eb-135">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="df0eb-136">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="df0eb-136">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="df0eb-137">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="df0eb-137">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="df0eb-138">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="df0eb-138">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="df0eb-139">Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="df0eb-139">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="df0eb-140">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="df0eb-140">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="df0eb-141">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="df0eb-141">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="df0eb-142">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="df0eb-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="df0eb-143">Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="df0eb-143">To run the sample in a single- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="df0eb-144">Ejecutar el ejemplo en todos los equipos</span><span class="sxs-lookup"><span data-stu-id="df0eb-144">Run the sample across computers</span></span>

1. <span data-ttu-id="df0eb-145">Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="df0eb-145">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="df0eb-146">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="df0eb-146">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="df0eb-147">En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".</span><span class="sxs-lookup"><span data-stu-id="df0eb-147">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="df0eb-148">En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="df0eb-148">On the service computer, launch Service.exe from a command prompt.</span></span>

5. <span data-ttu-id="df0eb-149">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="df0eb-149">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df0eb-150">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="df0eb-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="df0eb-151">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="df0eb-151">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="df0eb-152">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="df0eb-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="df0eb-153">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="df0eb-153">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`

## <a name="see-also"></a><span data-ttu-id="df0eb-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="df0eb-154">See also</span></span>

- [<span data-ttu-id="df0eb-155">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="df0eb-155">Queues in WCF</span></span>](../feature-details/queues-in-wcf.md)
- [<span data-ttu-id="df0eb-156">Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="df0eb-156">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- <span data-ttu-id="df0eb-157">[Message Queue Server](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="df0eb-157">[Message Queuing](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
