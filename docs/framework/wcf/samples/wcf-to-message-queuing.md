---
description: 'Más información acerca de: Windows Communication Foundation a Message Queue Server'
title: Windows Communication Foundation a Message Queuing
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: ef4fe5f23b4ce462b13e12b706a3a72225a74f8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798191"
---
# <a name="windows-communication-foundation-to-message-queuing"></a><span data-ttu-id="e81dc-103">Windows Communication Foundation a Message Queuing</span><span class="sxs-lookup"><span data-stu-id="e81dc-103">Windows Communication Foundation to Message Queuing</span></span>

<span data-ttu-id="e81dc-104">Este ejemplo muestra cómo una aplicación Windows Communication Foundation (WCF) puede enviar un mensaje a una aplicación de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="e81dc-104">This sample demonstrates how a Windows Communication Foundation (WCF) application can send a message to a Message Queuing (MSMQ) application.</span></span> <span data-ttu-id="e81dc-105">El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="e81dc-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span> <span data-ttu-id="e81dc-106">El servicio y el cliente no tienen que estar ejecutándose al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e81dc-106">The service and client do not have to be running at the same time.</span></span>

 <span data-ttu-id="e81dc-107">El servicio recibe los mensajes de la cola y procesa las órdenes.</span><span class="sxs-lookup"><span data-stu-id="e81dc-107">The service receives messages from the queue and processes orders.</span></span> <span data-ttu-id="e81dc-108">El servicio crea una cola transaccional y establece un mensaje recibido por el controlador de mensajes, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-108">The service creates a transactional queue and sets up a message received message handler, as shown in the following sample code.</span></span>

```csharp
static void Main(string[] args)
{
    if (!MessageQueue.Exists(
              ConfigurationManager.AppSettings["queueName"]))
       MessageQueue.Create(
           ConfigurationManager.AppSettings["queueName"], true);
        //Connect to the queue
        MessageQueue Queue = new
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);
    Queue.ReceiveCompleted +=
                 new ReceiveCompletedEventHandler(ProcessOrder);
    Queue.BeginReceive();
    Console.WriteLine("Order Service is running");
    Console.ReadLine();
}
```

 <span data-ttu-id="e81dc-109">Cuando se recibe un mensaje en la cola, se invoca a `ProcessOrder` del controlador de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e81dc-109">When a message is received in the queue, the message handler `ProcessOrder` is invoked.</span></span>

```csharp
public static void ProcessOrder(Object source,
    ReceiveCompletedEventArgs asyncResult)
{
    try
    {
        // Connect to the queue.
        MessageQueue Queue = (MessageQueue)source;
        // End the asynchronous receive operation.
        System.Messaging.Message msg =
                     Queue.EndReceive(asyncResult.AsyncResult);
        msg.Formatter = new System.Messaging.XmlMessageFormatter(
                                new Type[] { typeof(PurchaseOrder) });
        PurchaseOrder po = (PurchaseOrder) msg.Body;
        Random statusIndexer = new Random();
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
        Console.WriteLine("Processing {0} ", po);
        Queue.BeginReceive();
    }
    catch (System.Exception ex)
    {
        Console.WriteLine(ex.Message);
    }

}
```

 <span data-ttu-id="e81dc-110">El servicio extrae `ProcessOrder` desde el cuerpo del mensaje de MSMQ y procesa la orden.</span><span class="sxs-lookup"><span data-stu-id="e81dc-110">The service extracts the `ProcessOrder` from the MSMQ message body, and processes the order.</span></span>

 <span data-ttu-id="e81dc-111">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-111">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="e81dc-112">El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e81dc-112">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span>

 <span data-ttu-id="e81dc-113">El cliente crea una orden de compra y la envía dentro del ámbito de una transacción, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-113">The client creates a purchase order and submits the purchase order within the scope of a transaction, as shown in the following sample code.</span></span>

```csharp
// Create the purchase order
PurchaseOrder po = new PurchaseOrder();
// Fill in the details
...

OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");

MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    client.SubmitPurchaseOrder(ordermsg);
    scope.Complete();
}
Console.WriteLine("Order has been submitted:{0}", po);

//Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

 <span data-ttu-id="e81dc-114">El cliente utiliza un cliente personalizado en orden para enviar el mensaje de MSMQ a la cola.</span><span class="sxs-lookup"><span data-stu-id="e81dc-114">The client uses a custom client in-order to send the MSMQ message to the queue.</span></span> <span data-ttu-id="e81dc-115">Dado que la aplicación que recibe y procesa el mensaje es una aplicación MSMQ y no una aplicación WCF, no hay ningún contrato de servicio implícito entre las dos aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e81dc-115">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="e81dc-116">Así que no podemos crear ningún proxy utilizando la herramienta Svcutil.exe en este escenario.</span><span class="sxs-lookup"><span data-stu-id="e81dc-116">So, we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="e81dc-117">El cliente personalizado es esencialmente el mismo para todas las aplicaciones WCF que usan el `MsmqIntegration` enlace para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="e81dc-117">The custom client is essentially the same for all WCF applications that use the `MsmqIntegration` binding to send messages.</span></span> <span data-ttu-id="e81dc-118">A diferencia de otros clientes, no incluye ningún intervalo de operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="e81dc-118">Unlike other clients, it does not include a range of service operations.</span></span> <span data-ttu-id="e81dc-119">Solo es una operación de envío de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e81dc-119">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor
{
    public OrderProcessorClient(){}

    public OrderProcessorClient(string configurationName)
        : base(configurationName)
    { }

    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SubmitPurchaseOrder(msg);
    }
}
```

 <span data-ttu-id="e81dc-120">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="e81dc-120">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e81dc-121">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-121">You can see the service receive messages from the client.</span></span> <span data-ttu-id="e81dc-122">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-122">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="e81dc-123">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-123">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="e81dc-124">Por ejemplo, podría ejecutar el cliente, cerrarlo e iniciar el servicio y seguiría recibiendo sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="e81dc-124">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

> [!NOTE]
> <span data-ttu-id="e81dc-125">Este ejemplo requiere la instalación de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="e81dc-125">This sample requires the installation of Message Queuing.</span></span> <span data-ttu-id="e81dc-126">Vea las instrucciones de instalación en [Message Queue Server](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e81dc-126">See the installation instructions in [Message Queuing](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)).</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="e81dc-127">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e81dc-127">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="e81dc-128">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e81dc-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e81dc-129">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-129">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="e81dc-130">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="e81dc-130">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="e81dc-131">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e81dc-131">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="e81dc-132">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="e81dc-132">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="e81dc-133">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="e81dc-133">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="e81dc-134">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="e81dc-134">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="e81dc-135">Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nueva**  >  **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="e81dc-135">Right-click **Private Message Queues**, and then select **New** > **Private Queue**.</span></span>

    4. <span data-ttu-id="e81dc-136">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="e81dc-136">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="e81dc-137">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="e81dc-137">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="e81dc-138">Para compilar la edición de C# o Visual Basic de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e81dc-138">To build the C# or Visual Basic edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="e81dc-139">Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e81dc-139">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="e81dc-140">Ejecutar el ejemplo en todos los equipos</span><span class="sxs-lookup"><span data-stu-id="e81dc-140">Run the sample across computers</span></span>

1. <span data-ttu-id="e81dc-141">Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="e81dc-141">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="e81dc-142">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="e81dc-142">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="e81dc-143">En el archivo Client.exe.config, cambie la dirección del extremo del cliente para especificar el nombre del equipo servidor en lugar de ".".</span><span class="sxs-lookup"><span data-stu-id="e81dc-143">In the Client.exe.config file, change the client endpoint address to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="e81dc-144">En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e81dc-144">On the service computer, launch Service.exe from a command prompt.</span></span>

5. <span data-ttu-id="e81dc-145">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e81dc-145">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e81dc-146">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e81dc-146">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e81dc-147">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e81dc-147">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e81dc-148">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e81dc-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e81dc-149">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e81dc-149">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`

## <a name="see-also"></a><span data-ttu-id="e81dc-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="e81dc-150">See also</span></span>

- [<span data-ttu-id="e81dc-151">Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="e81dc-151">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- <span data-ttu-id="e81dc-152">[Message Queue Server](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e81dc-152">[Message Queuing](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
