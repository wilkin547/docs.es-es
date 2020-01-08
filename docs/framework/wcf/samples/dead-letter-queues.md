---
title: Colas con problemas de entrega
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: d493aba9a3f7a51824243fe8d06441ab563b2261
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344537"
---
# <a name="dead-letter-queues"></a><span data-ttu-id="16ea8-102">Colas con problemas de entrega</span><span class="sxs-lookup"><span data-stu-id="16ea8-102">Dead Letter Queues</span></span>
<span data-ttu-id="16ea8-103">Este ejemplo muestra cómo administrar y procesar mensajes que han producido errores en la entrega.</span><span class="sxs-lookup"><span data-stu-id="16ea8-103">This sample demonstrates how to handle and process messages that have failed delivery.</span></span> <span data-ttu-id="16ea8-104">Se basa en el ejemplo de [enlace de MSMQ de transacciones](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="16ea8-104">It is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="16ea8-105">El ejemplo usa el enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="16ea8-105">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="16ea8-106">El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="16ea8-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="16ea8-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="16ea8-108">Este ejemplo muestra cada cola de mensajes con problemas de entrega de la aplicación que solo está disponible en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="16ea8-108">This sample demonstrates each application dead letter queue that is only available on Windows Vista.</span></span> <span data-ttu-id="16ea8-109">El ejemplo se puede modificar para usar las colas predeterminadas de todo el sistema para MSMQ 3,0 en Windows Server 2003 y [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16ea8-109">The sample can be modified to use the default system-wide queues for MSMQ 3.0 on Windows Server 2003 and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>

 <span data-ttu-id="16ea8-110">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-110">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="16ea8-111">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-111">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="16ea8-112">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-112">The service receives messages from the queue.</span></span> <span data-ttu-id="16ea8-113">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-113">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="16ea8-114">Dado que la comunicación en cola puede implicar una cierta cantidad de inactividad, quizá prefiera asociar un valor de período de vida en el mensaje para asegurarse de que el mensaje no se entrega a la aplicación si se ha pasado de hora.</span><span class="sxs-lookup"><span data-stu-id="16ea8-114">Because queued communication can involve a certain amount of dormancy, you may want to associate a time-to-live value on the message to ensure that the message does not get delivered to the application if it has gone past the time.</span></span> <span data-ttu-id="16ea8-115">Hay también casos, donde si la entrega del mensaje ha fallado se debe notificar a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="16ea8-115">There are also cases, where an application must be informed whether a message failed delivery.</span></span> <span data-ttu-id="16ea8-116">En todos estos casos, como cuando el período de vida del mensaje ha expirado o la entrega del mensaje ha fallado, el mensaje se coloca en una cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-116">In all of these cases, such as when the time-to-live on the message has expired or the message failed delivery, the message is put in a dead letter queue.</span></span> <span data-ttu-id="16ea8-117">La aplicación emisora puede leer en la cola mensajes no entregados y emprender acciones de corrección que van desde no realizar ninguna acción hasta corregir las razones del error de la entrega y reenviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="16ea8-117">The sending application can then read the messages in the dead-letter queue and take corrective actions that range from no action to correcting the reasons for failed delivery and resending the message.</span></span>

 <span data-ttu-id="16ea8-118">La cola de mensajes no enviados en el enlace `NetMsmqBinding` se expresa en las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="16ea8-118">The dead-letter queue in the `NetMsmqBinding` binding is expressed in the following properties:</span></span>

- <span data-ttu-id="16ea8-119">La propiedad <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> expresa el tipo de cola de mensajes no enviados requerido por el cliente.</span><span class="sxs-lookup"><span data-stu-id="16ea8-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> property to express the kind of dead-letter queue required by the client.</span></span> <span data-ttu-id="16ea8-120">Esta enumeración tiene los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="16ea8-120">This enumeration has the following values:</span></span>

- <span data-ttu-id="16ea8-121">`None`: el cliente no requiere la cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-121">`None`: No dead-letter queue is required by the client.</span></span>

- <span data-ttu-id="16ea8-122">`System`: La cola de mensajes no enviados del sistema se utiliza para guardar los mensajes no entregados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-122">`System`: The system dead-letter queue is used to store dead messages.</span></span> <span data-ttu-id="16ea8-123">Todas las aplicaciones que se ejecutan en el equipo comparten la cola de mensajes no enviados del sistema.</span><span class="sxs-lookup"><span data-stu-id="16ea8-123">The system dead-letter queue is shared by all applications running on the computer.</span></span>

- <span data-ttu-id="16ea8-124">`Custom`: una cola de mensajes no enviados personalizada especificada con la propiedad <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> se utiliza para almacenar los mensajes no entregados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-124">`Custom`: A custom dead-letter queue specified using the <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property is used to store dead messages.</span></span> <span data-ttu-id="16ea8-125">Esta característica solo está disponible en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="16ea8-125">This feature is only available on Windows Vista.</span></span> <span data-ttu-id="16ea8-126">Se utiliza cuando la aplicación debe utilizar su propia cola de mensajes no enviados en lugar de compartirla con otras aplicaciones que se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="16ea8-126">This is used when the application must use its own dead letter queue instead of sharing it with other applications running on the same computer.</span></span>

- <span data-ttu-id="16ea8-127">La propiedad <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> expresa la cola concreta que se debe utilizar como cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property to express the specific queue to use as a dead-letter queue.</span></span> <span data-ttu-id="16ea8-128">Solo está disponible en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="16ea8-128">This is available only in Windows Vista.</span></span>

 <span data-ttu-id="16ea8-129">En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción y especifica un valor arbitrariamente bajo para el "período de vida" para estos mensajes (aproximadamente 2 segundos).</span><span class="sxs-lookup"><span data-stu-id="16ea8-129">In this sample, the client sends a batch of messages to the service from within the scope of a transaction and specifies an arbitrarily low value for "time-to-live" for these messages (about 2 seconds).</span></span> <span data-ttu-id="16ea8-130">El cliente también especifica una cola de mensajes no enviados personalizada utilizada para poner en cola los mensajes que han expirado.</span><span class="sxs-lookup"><span data-stu-id="16ea8-130">The client also specifies a custom dead-letter queue to use to enqueue the messages that have expired.</span></span>

 <span data-ttu-id="16ea8-131">La aplicación del cliente puede leer los mensajes en la cola de mensajes no enviados e intentar enviar el mensaje o corregir el error que causó que el mensaje original fuera colocado en la cola de mensajes no enviados y enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="16ea8-131">The client application can read the messages in the dead-letter queue and either retry sending the message or correct the error that caused the original message to be placed in the dead-letter queue and send the message.</span></span> <span data-ttu-id="16ea8-132">En el ejemplo, el cliente muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="16ea8-132">In the sample, the client displays an error message.</span></span>

 <span data-ttu-id="16ea8-133">El contrato de servicios es `IOrderProcessor`, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="16ea8-133">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="16ea8-134">El código de servicio en el ejemplo es el del [enlace MSMQ de transacción](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="16ea8-134">The service code in the sample is that of the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>

 <span data-ttu-id="16ea8-135">La comunicación con el servicio tiene lugar dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="16ea8-135">Communication with the service takes place within the scope of a transaction.</span></span> <span data-ttu-id="16ea8-136">El servicio lee los mensajes de la cola, realiza la operación y, a continuación, muestra los resultados de la operación.</span><span class="sxs-lookup"><span data-stu-id="16ea8-136">The service reads messages from the queue, performs the operation and then displays the results of the operation.</span></span> <span data-ttu-id="16ea8-137">La aplicación también crea una cola de mensajes no enviados para mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-137">The application also creates a dead-letter queue for dead-letter messages.</span></span>

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
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

        //Create a transaction scope.
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 <span data-ttu-id="16ea8-138">La configuración del cliente especifica una duración corta para que el mensaje alcance el servicio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-138">The client's configuration specifies a short duration for the message to reach the service.</span></span> <span data-ttu-id="16ea8-139">Si el mensaje no se puede transmitir dentro de la duración especificada, el mensaje expira y se mueve a la cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-139">If the message cannot be transmitted within the duration specified, the message expires and is moved to the dead-letter queue.</span></span>

> [!NOTE]
> <span data-ttu-id="16ea8-140">Es posible que el cliente entregue el mensaje a la cola del servicio dentro de la hora especificada.</span><span class="sxs-lookup"><span data-stu-id="16ea8-140">It is possible for the client to deliver the message to the service queue within the specified time.</span></span> <span data-ttu-id="16ea8-141">Para asegurarse de ver el servicio de mensajes no enviados en acción, se debe ejecutar el cliente antes de iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-141">To ensure you see the dead-letter service in action, you should run the client before starting the service.</span></span> <span data-ttu-id="16ea8-142">El mensaje espera y se entrega al servicio de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-142">The message times out and is delivered to the dead-letter service.</span></span>

 <span data-ttu-id="16ea8-143">La aplicación debe definir qué cola utilizar como su cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-143">The application must define which queue to use as its dead-letter queue.</span></span> <span data-ttu-id="16ea8-144">Si no se especifica ninguna cola, la cola de mensajes transaccionales no enviados para todo el sistema predeterminada se utiliza para poner en la cola los mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-144">If no queue is specified, the default system-wide transactional dead-letter queue is used to queue dead messages.</span></span> <span data-ttu-id="16ea8-145">En este ejemplo, la aplicación cliente especifica su propia cola de mensajes no enviados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="16ea8-145">In this example, the client application specifies its own application dead-letter queue.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 <span data-ttu-id="16ea8-146">El servicio de mensajes no enviados lee los mensajes de la cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-146">The dead-letter message service reads messages from the dead-letter queue.</span></span> <span data-ttu-id="16ea8-147">El servicio de mensajes no enviados implementa el contrato `IOrderProcessor`.</span><span class="sxs-lookup"><span data-stu-id="16ea8-147">The dead-letter message service implements the `IOrderProcessor` contract.</span></span> <span data-ttu-id="16ea8-148">Sin embargo, su implementación no es procesar las órdenes.</span><span class="sxs-lookup"><span data-stu-id="16ea8-148">Its implementation however is not to process orders.</span></span> <span data-ttu-id="16ea8-149">El servicio de mensajes no enviados es un servicio del cliente y no tiene facilidad para procesar las órdenes.</span><span class="sxs-lookup"><span data-stu-id="16ea8-149">The dead-letter message service is a client service and does not have the facility to process orders.</span></span>

> [!NOTE]
> <span data-ttu-id="16ea8-150">La cola de mensajes no enviados es una cola del cliente y es local al administrador de cola del cliente.</span><span class="sxs-lookup"><span data-stu-id="16ea8-150">The dead-letter queue is a client queue and is local to the client queue manager.</span></span>

 <span data-ttu-id="16ea8-151">La implementación de servicio de mensajes no enviados comprueba la razón por la que un mensaje no se ha enviado y toma medidas de corrección.</span><span class="sxs-lookup"><span data-stu-id="16ea8-151">The dead-letter message service implementation checks for the reason a message failed delivery and takes corrective measures.</span></span> <span data-ttu-id="16ea8-152">La razón de un error en el envío del mensaje se captura en dos enumeraciones, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> y <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span><span class="sxs-lookup"><span data-stu-id="16ea8-152">The reason for a message failure is captured in two enumerations, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> and <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span></span> <span data-ttu-id="16ea8-153">Se puede recuperar el <xref:System.ServiceModel.Channels.MsmqMessageProperty> de <xref:System.ServiceModel.OperationContext> como se muestra en el código muestra siguiente:</span><span class="sxs-lookup"><span data-stu-id="16ea8-153">You can retrieve the <xref:System.ServiceModel.Channels.MsmqMessageProperty> from the <xref:System.ServiceModel.OperationContext> as shown in the following sample code:</span></span>

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 <span data-ttu-id="16ea8-154">Los mensajes en la cola de mensajes no enviados son mensajes que se dirigen al servicio que está procesando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="16ea8-154">Messages in the dead-letter queue are messages that are addressed to the service that is processing the message.</span></span> <span data-ttu-id="16ea8-155">Por lo tanto, cuando el servicio de mensajes no enviados Lee los mensajes de la cola, el nivel de canal de Windows Communication Foundation (WCF) detecta la falta de coincidencia en los extremos y no envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="16ea8-155">Therefore, when the dead-letter message service reads messages from the queue, the Windows Communication Foundation (WCF) channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="16ea8-156">En este caso, el mensaje se dirige al servicio de procesamiento de la orden, pero quien lo recibe es el servicio de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-156">In this case, the message is addressed to the order processing service but is received by the dead-letter message service.</span></span> <span data-ttu-id="16ea8-157">Para recibir un mensaje que se dirige a un punto de conexión diferente, una dirección se filtra para coincidir con cualquier dirección especificada en `ServiceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="16ea8-157">To receive a message that is addressed to a different endpoint, an address filter to match any address is specified in the `ServiceBehavior`.</span></span> <span data-ttu-id="16ea8-158">Esto se exigen para procesar correctamente los mensajes que se leen de la cola de mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="16ea8-158">This is required to successfully process messages that are read from the dead-letter queue.</span></span>

 <span data-ttu-id="16ea8-159">En este ejemplo, el servicio de mensajes con problemas de entrega reenvía el mensaje si el motivo del error es que el mensaje ha agotado el tiempo de espera. Por todas las demás razones, muestra el error de entrega, tal como se muestra en el siguiente código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16ea8-159">In this sample, the dead-letter message service resends the message if the reason for failure is that the message timed out. For all other reasons, it displays the delivery failure, as shown in the following sample code:</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 <span data-ttu-id="16ea8-160">El ejemplo siguiente muestra la configuración para un mensaje no enviado:</span><span class="sxs-lookup"><span data-stu-id="16ea8-160">The following sample shows the configuration for a dead-letter message:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="16ea8-161">Para ejecutar el ejemplo, hay 3 aplicaciones ejecutables para ejecutar para ver cómo la cola de mensajes no enviados funciona para cada aplicación; el cliente, el servicio y el servicio de mensajes no enviados que lee de la cola de mensajes no enviados para cada aplicación y reenvían el mensaje al servicio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-161">In running the sample, there are 3 executables to run to see how the dead-letter queue works for each application; the client, service and a dead-letter service that reads from the dead-letter queue for each application and resends the message to the service.</span></span> <span data-ttu-id="16ea8-162">Todos son las aplicaciones de consola con el resultado de ventanas de consola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-162">All are console applications with output in console windows.</span></span>

> [!NOTE]
> <span data-ttu-id="16ea8-163">Debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="16ea8-163">Because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="16ea8-164">Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="16ea8-164">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="16ea8-165">Se debe iniciar el servicio y apagarlo para que se pueda crear la cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-165">You should start the service and shut it down so that the queue can be created.</span></span>

 <span data-ttu-id="16ea8-166">Al ejecutar el cliente, el cliente muestra el mensaje:</span><span class="sxs-lookup"><span data-stu-id="16ea8-166">When running the client, the client displays the message:</span></span>

```console
Press <ENTER> to terminate client.
```

 <span data-ttu-id="16ea8-167">El cliente intentó enviar el mensaje pero con un tiempo de espera corto, el mensaje expiró y se puso en la cola, y ahora se encuentra en la cola de mensajes no enviados para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="16ea8-167">The client attempted to send the message but with a short timeout, the message expired and is now queued in the dead-letter queue for each application.</span></span>

 <span data-ttu-id="16ea8-168">Ejecute a continuación el servicio de mensajes no enviados, que lee el mensaje y muestra el código del error y reenvía de nuevo el mensaje al servicio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-168">You then run the dead-letter service, which reads the message and displays the error code and resends the message back to the service.</span></span>

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 <span data-ttu-id="16ea8-169">El servicio se inicia y, a continuación, lee el mensaje reenviado y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="16ea8-169">The service starts and then reads the resent message and processes it.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="16ea8-170">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="16ea8-170">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="16ea8-171">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="16ea8-171">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="16ea8-172">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="16ea8-172">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="16ea8-173">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="16ea8-173">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="16ea8-174">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="16ea8-174">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="16ea8-175">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="16ea8-175">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="16ea8-176">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="16ea8-176">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="16ea8-177">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="16ea8-177">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="16ea8-178">Haga clic con el botón secundario en **colas de mensajes privadas**y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="16ea8-178">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="16ea8-179">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="16ea8-179">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="16ea8-180">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="16ea8-180">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="16ea8-181">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="16ea8-181">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="16ea8-182">Para ejecutar el ejemplo en una configuración de un solo equipo o entre equipos, cambie los nombres de cola de forma adecuada, reemplazando localhost por el nombre completo del equipo y siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="16ea8-182">To run the sample in a single- or cross-computer configuration change queue names appropriately, replacing localhost with full name of the computer and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="16ea8-183">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo</span><span class="sxs-lookup"><span data-stu-id="16ea8-183">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="16ea8-184">Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16ea8-184">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="16ea8-185">Asegúrese de que el punto de conexión está asociado con el enlace definiendo el atributo `bindingConfiguration` del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="16ea8-185">Ensure the endpoint is associated with the binding by setting the endpoint's `bindingConfiguration` attribute.</span></span>

2. <span data-ttu-id="16ea8-186">Asegúrese de que cambia la configuración en el servidor DeadLetterService y en el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="16ea8-186">Ensure that you change the configuration on the DeadLetterService, server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16ea8-187">Establecer `security mode` en `None` es equivalente a definir `MsmqAuthenticationMode`, `MsmqProtectionLevel` y la seguridad de `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="16ea8-187">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

## <a name="comments"></a><span data-ttu-id="16ea8-188">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16ea8-188">Comments</span></span>
 <span data-ttu-id="16ea8-189">De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada.</span><span class="sxs-lookup"><span data-stu-id="16ea8-189">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="16ea8-190">Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="16ea8-190">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="16ea8-191">De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="16ea8-191">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="16ea8-192">Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-192">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="16ea8-193">Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".</span><span class="sxs-lookup"><span data-stu-id="16ea8-193">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16ea8-194">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="16ea8-194">The samples may already be installed on your computer.</span></span> <span data-ttu-id="16ea8-195">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="16ea8-195">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="16ea8-196">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16ea8-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16ea8-197">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="16ea8-197">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
