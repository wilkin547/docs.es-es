---
description: 'Más información acerca de: correlación de mensajes'
title: Correlación del mensaje
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: e38e2e8d6936132e165fd3372ac57fef27240d1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704035"
---
# <a name="message-correlation"></a><span data-ttu-id="bf279-103">Correlación del mensaje</span><span class="sxs-lookup"><span data-stu-id="bf279-103">Message Correlation</span></span>

<span data-ttu-id="bf279-104">Este ejemplo muestra cómo una aplicación de Message Queuing (MSMQ) puede enviar un mensaje de MSMQ a un servicio de Windows Communication Foundation (WCF) y cómo se pueden correlacionar los mensajes entre las aplicaciones del remitente y el receptor en un escenario de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf279-104">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="bf279-105">Este ejemplo utiliza el enlace msmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="bf279-105">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="bf279-106">El servicio en este caso es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="bf279-106">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="bf279-107">k</span><span class="sxs-lookup"><span data-stu-id="bf279-107">k</span></span>

 <span data-ttu-id="bf279-108">El servicio procesa el mensaje recibido del remitente y envía de vuelta un mensaje de respuesta al remitente.</span><span class="sxs-lookup"><span data-stu-id="bf279-108">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="bf279-109">El remitente pone en correlación la respuesta que recibió con la solicitud que envió en un principio.</span><span class="sxs-lookup"><span data-stu-id="bf279-109">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="bf279-110">Las propiedades `MessageID` y `CorrelationID` del mensaje se utilizan para poner en correlación los mensajes de respuesta y solicitud.</span><span class="sxs-lookup"><span data-stu-id="bf279-110">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>

 <span data-ttu-id="bf279-111">El contrato de servicio `IOrderProcessor` define una operación de servicio unidireccional que sea adecuada para su uso cuando se coloque en la cola.</span><span class="sxs-lookup"><span data-stu-id="bf279-111">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="bf279-112">Un mensaje de MSMQ no tiene un encabezado Acción, por lo que no es posible asignar automáticamente distintos mensajes de MSMQ a los contratos de operación.</span><span class="sxs-lookup"><span data-stu-id="bf279-112">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="bf279-113">Por consiguiente, puede haber solo un contrato de operación en este caso.</span><span class="sxs-lookup"><span data-stu-id="bf279-113">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="bf279-114">Si desea definir más contratos de operación en el servicio, la aplicación debe proporcionar información como qué encabezado en el mensaje de MSMQ (por ejemplo, la etiqueta o correlationID) se puede utilizar para decidir qué contrato de operación enviar.</span><span class="sxs-lookup"><span data-stu-id="bf279-114">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="bf279-115">El mensaje de MSMQ no contiene información sobre qué encabezados están asignados a los distintos parámetros del contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="bf279-115">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="bf279-116">Por consiguiente, puede haber solo un parámetro en el contrato de la operación.</span><span class="sxs-lookup"><span data-stu-id="bf279-116">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="bf279-117">El parámetro es de tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> , que contiene el mensaje de MSMQ subyacente.</span><span class="sxs-lookup"><span data-stu-id="bf279-117">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, which contains the underlying MSMQ message.</span></span> <span data-ttu-id="bf279-118">El tipo "T" en la clase `MsmqMessage<T>` representa los datos que se serializan en el cuerpo del mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="bf279-118">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="bf279-119">En este ejemplo, el tipo `PurchaseOrder` se serializa en el cuerpo del mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="bf279-119">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="bf279-120">La operación del servicio procesa la orden de compra, muestra su contenido y su estado en la ventana de la consola del servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-120">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="bf279-121"><xref:System.ServiceModel.OperationBehaviorAttribute> configura la operación que dar de alta en una transacción con la cola y marcar la transacción como completada cuando vuelve la operación.</span><span class="sxs-lookup"><span data-stu-id="bf279-121">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="bf279-122">`PurchaseOrder` contiene los detalles de la orden que debe ser procesada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-122">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>

```csharp
// Service class that implements the service contract.
public class OrderProcessorService : IOrderProcessor
{
   [OperationBehavior(TransactionScopeRequired = true,
          TransactionAutoComplete = true)]
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)
   {
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;
       Random statusIndexer = new Random();
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
       Console.WriteLine("Processing {0} ", po);
       //Send a response to the client that the order has been received
         and is pending fullfillment.
       SendResponse(ordermsg);
    }

    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)
    {
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");

        //Set the correlation ID such that the client can correlate the response to the order.
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);
        orderResponsemsg.CorrelationId = ordermsg.Id;
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.SendOrderResponse(orderResponsemsg);
            scope.Complete();
        }

        client.Close();
    }
}
```

 <span data-ttu-id="bf279-123">El servicio utiliza un `OrderResponseClient` de cliente personalizado para enviar el mensaje de MSMQ a la cola.</span><span class="sxs-lookup"><span data-stu-id="bf279-123">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="bf279-124">Dado que la aplicación que recibe y procesa el mensaje es una aplicación MSMQ y no una aplicación WCF, no hay ningún contrato de servicio implícito entre las dos aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bf279-124">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="bf279-125">Así que no podemos crear ningún proxy utilizando la herramienta Svcutil.exe en este escenario.</span><span class="sxs-lookup"><span data-stu-id="bf279-125">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="bf279-126">El proxy personalizado es esencialmente el mismo para todas las aplicaciones WCF que usan el `msmqIntegrationBinding` enlace para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="bf279-126">The custom proxy is essentially the same for all WCF applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="bf279-127">A diferencia de otros servidores proxy, no incluye ningún intervalo de operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-127">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="bf279-128">Solo es una operación de envío de mensaje.</span><span class="sxs-lookup"><span data-stu-id="bf279-128">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderResponse
{

    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse
{

    public OrderResponseClient()
    { }

    public OrderResponseClient(string configurationName)
        : base(configurationName)
    { }

    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SendOrderResponse(msg);
    }
}
```

 <span data-ttu-id="bf279-129">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="bf279-129">The service is self hosted.</span></span> <span data-ttu-id="bf279-130">Al utilizar el transporte de integración de MSMQ, se debe crear con antelación la cola utilizada.</span><span class="sxs-lookup"><span data-stu-id="bf279-130">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="bf279-131">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="bf279-131">This can be done manually or through code.</span></span> <span data-ttu-id="bf279-132">En este ejemplo, el servicio contiene el código <xref:System.Messaging> para comprobar la existencia de la cola y crearla si fuera necesaria.</span><span class="sxs-lookup"><span data-stu-id="bf279-132">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="bf279-133">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf279-133">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
       // Get the MSMQ queue name from application settings in configuration.
      string queueName =
                ConfigurationManager.AppSettings["orderQueueName"];
      // Create the transacted MSMQ queue if necessary.
      if (!MessageQueue.Exists(queueName))
                MessageQueue.Create(queueName, true);
     // Create a ServiceHost for the OrderProcessorService type.
     using (ServiceHost serviceHost = new
                   ServiceHost(typeof(OrderProcessorService)))
     {
            serviceHost.Open();
            // The service can now be accessed.
            Console.WriteLine("The service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.ReadLine();
            // Close the ServiceHost to shutdown the service.
            serviceHost.Close();
      }
}
```

 <span data-ttu-id="bf279-134">La cola de MSMQ a la que se envían las solicitudes de la orden se especifica en la sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf279-134">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="bf279-135">Los puntos de conexión de servicio y cliente se definen en la sección de system.ServiceModel del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf279-135">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="bf279-136">Ambos especifican el enlace `msmqIntegrationbinding`.</span><span class="sxs-lookup"><span data-stu-id="bf279-136">Both specify the `msmqIntegrationbinding` binding.</span></span>

```xml
<appSettings>
  <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>

<system.serviceModel>
  <client>
    <endpoint    name="OrderResponseEndpoint"
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"
              binding="msmqIntegrationBinding"
              bindingConfiguration="OrderProcessorBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">
    </endpoint>
  </client>

  <services>
    <service
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"
                            binding="msmqIntegrationBinding"
                bindingConfiguration="OrderProcessorBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">
      </endpoint>
    </service>
  </services>

  <bindings>
    <msmqIntegrationBinding>
      <binding name="OrderProcessorBinding" >
        <security mode="None" />
      </binding>
    </msmqIntegrationBinding>
  </bindings>

</system.serviceModel>
```

 <span data-ttu-id="bf279-137">La aplicación cliente utiliza <xref:System.Messaging> para enviar un mensaje duradero y transaccional a la cola.</span><span class="sxs-lookup"><span data-stu-id="bf279-137">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="bf279-138">El cuerpo del mensaje contiene la orden de compra.</span><span class="sxs-lookup"><span data-stu-id="bf279-138">The message's body contains the purchase order.</span></span>

```csharp
static void PlaceOrder()
{
    //Connect to the queue
    MessageQueue orderQueue =
            new MessageQueue(
                    ConfigurationManager.AppSettings["orderQueueName"])
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

    Message msg = new Message();
    msg.UseDeadLetterQueue = true;
    msg.Body = po;

    //Create a transaction scope.
    using (TransactionScope scope = new
     TransactionScope(TransactionScopeOption.Required))
    {
        // Submit the purchase order.
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
        // Complete the transaction.
        scope.Complete();
    }
    //Save the messageID for order response correlation.
    orderMessageID = msg.Id;
    Console.WriteLine("Placed the order, waiting for response...");
}
```

 <span data-ttu-id="bf279-139">La cola de MSMQ de la que se reciben las respuestas del pedido se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf279-139">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="bf279-140">El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bf279-140">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="bf279-141">La dirección del extremo WCF especifica un esquema MSMQ. FormatName y utiliza "localhost" para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="bf279-141">The WCF endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="bf279-142">Un nombre con el formato correcto sigue el esquema msmq.formatname en el URI según especifica MSMQ.</span><span class="sxs-lookup"><span data-stu-id="bf279-142">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="bf279-143">La aplicación cliente guarda `messageID` del mensaje de solicitud de la orden que envía al servicio y espera una respuesta de éste.</span><span class="sxs-lookup"><span data-stu-id="bf279-143">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="bf279-144">Una vez que la respuesta llega a la cola, el cliente la pone en correlación con el mensaje de la orden que envió utilizando la propiedad `correlationID` del mensaje, que contiene el `messageID` del mensaje de la orden que el cliente envió al servicio en un principio.</span><span class="sxs-lookup"><span data-stu-id="bf279-144">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>

```csharp
static void DisplayOrderStatus()
{
    MessageQueue orderResponseQueue = new
     MessageQueue(ConfigurationManager.AppSettings
                  ["orderResponseQueueName"]);
    //Create a transaction scope.
    bool responseReceived = false;
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;
    while (!responseReceived)
    {
       Message responseMsg;
       using (TransactionScope scope2 = new
         TransactionScope(TransactionScopeOption.Required))
       {
          //Receive the Order Response message.
          responseMsg =
              orderResponseQueue.Receive
                   (MessageQueueTransactionType.Automatic);
          scope2.Complete();
     }
     responseMsg.Formatter = new
     System.Messaging.XmlMessageFormatter(new Type[] {
         typeof(PurchaseOrder) });
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;
    //Check if the response is for the order placed.
    if (orderMessageID == responseMsg.CorrelationId)
    {
       responseReceived = true;
       Console.WriteLine("Status of current Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
    else
    {
       Console.WriteLine("Status of previous Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
  }
}
```

 <span data-ttu-id="bf279-145">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-145">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="bf279-146">Podrá observar que el servicio recibe los mensajes del cliente y envía una respuesta a éste.</span><span class="sxs-lookup"><span data-stu-id="bf279-146">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="bf279-147">El cliente muestra la respuesta recibida del servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-147">The client displays the response received from the service.</span></span> <span data-ttu-id="bf279-148">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="bf279-148">Press ENTER in each console window to shut down the service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="bf279-149">Este ejemplo requiere la instalación de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="bf279-149">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="bf279-150">Vea las instrucciones de instalación de MSMQ en el sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="bf279-150">See the MSMQ installation instructions in the See Also section.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="bf279-151">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf279-151">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="bf279-152">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bf279-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="bf279-153">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="bf279-153">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="bf279-154">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="bf279-154">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="bf279-155">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="bf279-155">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="bf279-156">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="bf279-156">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="bf279-157">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="bf279-157">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="bf279-158">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="bf279-158">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="bf279-159">Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="bf279-159">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="bf279-160">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="bf279-160">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="bf279-161">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="bf279-161">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="bf279-162">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bf279-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="bf279-163">Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bf279-163">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="bf279-164">Ejecutar el ejemplo en todos los equipos</span><span class="sxs-lookup"><span data-stu-id="bf279-164">Run the sample across computers</span></span>

1. <span data-ttu-id="bf279-165">Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="bf279-165">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="bf279-166">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="bf279-166">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="bf279-167">En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".</span><span class="sxs-lookup"><span data-stu-id="bf279-167">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="bf279-168">En el archivo Service.exe.config, cambie la dirección del extremo del cliente para especificar el nombre del equipo cliente en lugar de ".".</span><span class="sxs-lookup"><span data-stu-id="bf279-168">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>

5. <span data-ttu-id="bf279-169">En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bf279-169">On the service computer, launch Service.exe from a command prompt.</span></span>

6. <span data-ttu-id="bf279-170">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bf279-170">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf279-171">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bf279-171">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bf279-172">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bf279-172">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="bf279-173">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bf279-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bf279-174">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bf279-174">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a><span data-ttu-id="bf279-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf279-175">See also</span></span>

- [<span data-ttu-id="bf279-176">Las colas en WCF</span><span class="sxs-lookup"><span data-stu-id="bf279-176">Queuing in WCF</span></span>](../feature-details/queuing-in-wcf.md)
- <span data-ttu-id="bf279-177">[Message Queue Server](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="bf279-177">[Message Queuing](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
