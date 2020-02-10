---
title: Control de mensajes dudosos en MSMQ 4,0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: 0a9d4ec9657bacdbcb1273791dc7a593a9565c25
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094961"
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="a7290-102">Control de mensajes dudosos en MSMQ 4,0</span><span class="sxs-lookup"><span data-stu-id="a7290-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="a7290-103">Este ejemplo muestra cómo administrar los mensajes dudosos en un servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="a7290-104">Este ejemplo se basa en el ejemplo de [enlace de MSMQ de transacciones](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="a7290-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="a7290-105">Este ejemplo utiliza `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="a7290-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="a7290-106">El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="a7290-107">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="a7290-108">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="a7290-109">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-109">The service receives messages from the queue.</span></span> <span data-ttu-id="a7290-110">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="a7290-111">Un mensaje dudoso es aquel que se lee repetidamente desde una cola cuando el servicio que lo lee no puede procesarlo y, por consiguiente, termina la transacción en la que se lee el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="a7290-112">En tales casos, se intenta de nuevo leer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="a7290-113">En teoría, esta acción puede continuar indefinidamente si hay un problema con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="a7290-114">Esto solo puede ocurrir cuando se usan transacciones para leer de la cola e invocar la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-114">This can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>

 <span data-ttu-id="a7290-115">Según la versión de MSMQ, NetMsmqBinding admite la detección limitada para detectar los mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="a7290-116">Una vez detectado el mensaje como dudoso, podrá administrarse de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="a7290-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="a7290-117">De nuevo, según la versión de MSMQ, NetMsmqBinding admite desde el manejo limitado hasta un manejo completo de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>

 <span data-ttu-id="a7290-118">En este ejemplo se muestran las instalaciones limitadas de envenenamiento proporcionadas en la plataforma Windows Server 2003 y Windows XP, así como las funciones de envenenamiento completo que se proporcionan en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a7290-118">This sample illustrates the limited poison facilities provided on Windows Server 2003 and Windows XP platform and the full poison facilities provided on Windows Vista.</span></span> <span data-ttu-id="a7290-119">En ambos ejemplos, el objetivo es trasladar el mensaje dudoso fuera de la cola a otra cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-119">In both samples, the objective is to move the poison message out of the queue to another queue.</span></span> <span data-ttu-id="a7290-120">Después, un servicio de mensajes dudosos puede atender a esa cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-120">That queue can then be serviced by a poison message service.</span></span>

## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="a7290-121">MSMQ v4.0 Ejemplo de Manejo de Mensajes Dudosos</span><span class="sxs-lookup"><span data-stu-id="a7290-121">MSMQ v4.0 Poison Handling Sample</span></span>
 <span data-ttu-id="a7290-122">En Windows Vista, MSMQ proporciona una utilidad de subcola dudoso que se puede usar para almacenar mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-122">In Windows Vista, MSMQ provides a poison subqueue facility that can be used to store poison messages.</span></span> <span data-ttu-id="a7290-123">Este ejemplo muestra el procedimiento recomendado para tratar los mensajes dudosos mediante Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a7290-123">This sample demonstrates the best practice of dealing with poison messages using Windows Vista.</span></span>

 <span data-ttu-id="a7290-124">La detección de mensajes dudosos en Windows Vista es sofisticada.</span><span class="sxs-lookup"><span data-stu-id="a7290-124">The poison message detection in Windows Vista is sophisticated.</span></span> <span data-ttu-id="a7290-125">Hay 3 propiedades que ayudan con la detección.</span><span class="sxs-lookup"><span data-stu-id="a7290-125">There are 3 properties that help with detection.</span></span> <span data-ttu-id="a7290-126"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> es el número de veces que un mensaje determinado se relee de la cola y se envía a la aplicación para ser procesado.</span><span class="sxs-lookup"><span data-stu-id="a7290-126">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="a7290-127">Un mensaje se relee de la cola cuando se pone de nuevo en la cola porque el mensaje no se puede enviar a la aplicación o la aplicación revierte la transacción en la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-127">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="a7290-128"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> es el número de veces que el mensaje se mueve a la cola de reintento.</span><span class="sxs-lookup"><span data-stu-id="a7290-128"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="a7290-129">Cuando se localiza <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>, el mensaje se mueve a la cola de reintento.</span><span class="sxs-lookup"><span data-stu-id="a7290-129">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="a7290-130">La propiedad <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> es el retraso tras el que el mensaje se devuelve de la cola de reintento a la cola principal.</span><span class="sxs-lookup"><span data-stu-id="a7290-130">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="a7290-131">La propiedad <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> se restablece en 0.</span><span class="sxs-lookup"><span data-stu-id="a7290-131">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="a7290-132">El mensaje se vuelve a intentar.</span><span class="sxs-lookup"><span data-stu-id="a7290-132">The message is tried again.</span></span> <span data-ttu-id="a7290-133">Si se ha producir un error en todos los intentos para leer el mensaje, entonces el mensaje se marca como dudoso.</span><span class="sxs-lookup"><span data-stu-id="a7290-133">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>

 <span data-ttu-id="a7290-134">Una vez marcado como dudoso, el mensaje se trata según los valores en la enumeración <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7290-134">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="a7290-135">Para reiterar los valores posibles:</span><span class="sxs-lookup"><span data-stu-id="a7290-135">To reiterate the possible values:</span></span>

- <span data-ttu-id="a7290-136">Fault (valor predeterminado): para indicar que el error está en el agente de escucha y en el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-136">Fault (default): To fault the listener and also the service host.</span></span>

- <span data-ttu-id="a7290-137">Drop: para quitar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-137">Drop: To drop the message.</span></span>

- <span data-ttu-id="a7290-138">Move: para pasar el mensaje a la subcola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-138">Move: To move the message to the poison message subqueue.</span></span> <span data-ttu-id="a7290-139">Este valor solo está disponible en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a7290-139">This value is available only on Windows Vista.</span></span>

- <span data-ttu-id="a7290-140">Reject: para rechazar el mensaje, devolviéndolo a la cola de mensajes con problemas de entrega del remitente.</span><span class="sxs-lookup"><span data-stu-id="a7290-140">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="a7290-141">Este valor solo está disponible en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a7290-141">This value is available only on Windows Vista.</span></span>

 <span data-ttu-id="a7290-142">El ejemplo muestra cómo usar el desecho de `Move` para el mensaje dudoso.</span><span class="sxs-lookup"><span data-stu-id="a7290-142">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="a7290-143">`Move` hace que el mensaje se mueva a la subcola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-143">`Move` causes the message to move to the poison subqueue.</span></span>

 <span data-ttu-id="a7290-144">El contrato de servicio es `IOrderProcessor`, que define un servicio unidireccional que es adecuado para usarse con colas.</span><span class="sxs-lookup"><span data-stu-id="a7290-144">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="a7290-145">La operación de servicio muestra un mensaje que indica que está procesando la orden.</span><span class="sxs-lookup"><span data-stu-id="a7290-145">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="a7290-146">Para mostrar la funcionalidad del mensaje dudoso, la operación de servicio `SubmitPurchaseOrder` produce una excepción para revertir la transacción en una invocación aleatoria del servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-146">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to roll back the transaction on a random invocation of the service.</span></span> <span data-ttu-id="a7290-147">Esto provoca que el mensaje se vuelva a poner en la cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-147">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="a7290-148">Finalmente, el mensaje se marca como dudoso.</span><span class="sxs-lookup"><span data-stu-id="a7290-148">Eventually the message is marked as poison.</span></span> <span data-ttu-id="a7290-149">La configuración se establece para trasladar el mensaje dudoso a la subcola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-149">The configuration is set to move the poison message to the poison subqueue.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    static Random r = new Random(137);

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {

        int randomNumber = r.Next(10);

        if (randomNumber % 2 == 0)
        {
            Orders.Add(po);
            Console.WriteLine("Processing {0} ", po);
        }
        else
        {
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);
            Console.WriteLine();
            throw new Exception("Cannot process purchase order: " + po.PONumber);
        }
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted");
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Get MSMQ queue name from app settings in configuration.
        string queueName = ConfigurationManager.AppSettings["queueName"];

        // Create the transacted MSMQ queue if necessary.
        if (!System.Messaging.MessageQueue.Exists(queueName))
            System.Messaging.MessageQueue.Create(queueName, true);

        // Get the base address that is used to listen for WS-MetaDataExchange requests.
        // This is useful to generate a proxy for the client.
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        if(serviceHost.State != CommunicationState.Faulted) {
            serviceHost.Close();
        }

    }
}
```

 <span data-ttu-id="a7290-150">La configuración de servicio incluye las siguientes propiedades de mensaje dudoso: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, y `receiveErrorHandling` tal y como se muestra en el archivo de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7290-150">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>
  </appSettings>
  <system.serviceModel>
    <services>
      <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"
                  binding="netMsmqBinding"
                  bindingConfiguration="PoisonBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <bindings>
      <netMsmqBinding>
        <binding name="PoisonBinding"
                 receiveRetryCount="0"
                 maxRetryCycles="1"
                 retryCycleDelay="00:00:05"
                 receiveErrorHandling="Move">
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="a7290-151">Procesamiento de los mensajes de la cola de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="a7290-151">Processing messages from the poison message queue</span></span>
 <span data-ttu-id="a7290-152">El servicio de mensajes dudosos lee los mensajes desde la cola de mensajes dudosos final y los procesa.</span><span class="sxs-lookup"><span data-stu-id="a7290-152">The poison message service reads messages from the final poison message queue and processes them.</span></span>

 <span data-ttu-id="a7290-153">Los mensajes en la cola de mensajes dudosos son los que se dirigen al servicio que está procesando el mensaje, que podría ser diferente del extremo de servicio de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-153">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="a7290-154">Por lo tanto, cuando el servicio de mensajes dudosos Lee los mensajes de la cola, el nivel de canal de WCF encuentra la desigualdad en los extremos y no envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-154">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="a7290-155">En este caso, el mensaje se dirige al servicio de procesamiento de pedidos pero está siendo recibido por el servicio de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-155">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="a7290-156">Para continuar recibiendo el mensaje aun cuando se dirige a un punto de conexión diferente, debemos agregar `ServiceBehavior` para filtrar las direcciones en las que el criterio de coincidencia sea coincidir con cualquier punto de conexión de servicio al que se dirija el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-156">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="a7290-157">Esto es necesario para procesar correctamente los mensajes que lee desde la cola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-157">This is required to successfully process messages that you read from the poison message queue.</span></span>

 <span data-ttu-id="a7290-158">La propia implementación de servicio de los mensajes dudosos es muy similar a la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="a7290-158">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="a7290-159">Implementa el contrato y procesa los pedidos.</span><span class="sxs-lookup"><span data-stu-id="a7290-159">It implements the contract and processes the orders.</span></span> <span data-ttu-id="a7290-160">El ejemplo de código es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7290-160">The code example is as follows.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted...exiting app");
        Environment.Exit(1);
    }

    // Host the service within this EXE console application.
    public static void Main()
    {

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The poison message service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHostBase to shutdown the service.
        if(serviceHost.State != CommunicationState.Faulted)
        {
            serviceHost.Close();
        }
    }
```

 <span data-ttu-id="a7290-161">A diferencia del servicio de procesamiento de pedidos que lee los mensajes de la cola de pedidos, el servicio de mensajes dudosos Lee los mensajes de la subcola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-161">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison subqueue.</span></span> <span data-ttu-id="a7290-162">La cola de mensajes dudosos es una subcola de la cola principal, se denomina "dudoso" y MSMQ la genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a7290-162">The poison queue is a subqueue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="a7290-163">Para obtener acceso a él, proporcione el nombre de la cola principal seguido de un ";" y el nombre de la subcola, en este caso, "dudoso", como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7290-163">To access it, provide the main queue name followed by a ";" and the subqueue name, in this case -"poison", as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="a7290-164">En el ejemplo para MSMQ v3.0, el nombre de la cola de mensajes dudosos no es ninguna subcola, sino la cola a la que movimos el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-164">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >
        </endpoint>
      </service>
    </services>

  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="a7290-165">Al ejecutar el ejemplo, se muestra el cliente, el servicio y las actividades del servicio de mensajes dudosos en las ventanas de la consola.</span><span class="sxs-lookup"><span data-stu-id="a7290-165">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="a7290-166">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7290-166">You can see the service receive messages from the client.</span></span> <span data-ttu-id="a7290-167">Presione ENTRAR en cada ventana de la consola para cerrar los servicios.</span><span class="sxs-lookup"><span data-stu-id="a7290-167">Press ENTER in each console window to shut down the services.</span></span>

 <span data-ttu-id="a7290-168">El servicio empieza ejecutándose, procesando los pedidos y, de forma aleatoria, se inicia para terminar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a7290-168">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="a7290-169">Si el mensaje indica que ha procesado el pedido, puede ejecutar de nuevo el cliente para enviar otro mensaje hasta que vea que el servicio ha terminado realmente un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7290-169">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="a7290-170">Según los valores configurados para los mensajes dudosos, se intenta una vez el procesamiento del mensaje antes de moverlo a la cola final de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-170">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
```

 <span data-ttu-id="a7290-171">Inicie el servicio de mensajes dudosos para leer el mensaje dudoso de la cola de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a7290-171">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="a7290-172">En este ejemplo, el servicio de mensajes dudosos lee el mensaje y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="a7290-172">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="a7290-173">Podría ver que el servicio de mensajes dudosos lee el pedido de compra terminado y dudoso.</span><span class="sxs-lookup"><span data-stu-id="a7290-173">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a7290-174">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7290-174">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="a7290-175">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a7290-175">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="a7290-176">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="a7290-176">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="a7290-177">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="a7290-177">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="a7290-178">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a7290-178">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="a7290-179">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="a7290-179">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="a7290-180">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="a7290-180">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="a7290-181">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="a7290-181">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="a7290-182">Haga clic con el botón secundario en **colas de mensajes privadas**y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="a7290-182">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="a7290-183">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="a7290-183">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="a7290-184">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="a7290-184">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="a7290-185">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a7290-185">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="a7290-186">Para ejecutar el ejemplo en una configuración de un solo equipo o entre equipos, cambie los nombres de cola para que reflejen el nombre de host real en lugar del host local y siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a7290-186">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

 <span data-ttu-id="a7290-187">De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a7290-187">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="a7290-188">Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="a7290-188">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="a7290-189">De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="a7290-189">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="a7290-190">Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio.</span><span class="sxs-lookup"><span data-stu-id="a7290-190">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="a7290-191">Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".</span><span class="sxs-lookup"><span data-stu-id="a7290-191">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="a7290-192">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a7290-192">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="a7290-193">Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7290-193">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="a7290-194">Asegúrese de que el extremo está asociado al enlace definiendo el atributo bindingConfiguration del extremo.</span><span class="sxs-lookup"><span data-stu-id="a7290-194">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>

2. <span data-ttu-id="a7290-195">Asegúrese de cambiar la configuración en PoisonMessageServer, el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7290-195">Ensure that you change the configuration on the PoisonMessageServer, server, and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7290-196">Establecer `security mode` en `None` es equivalente a definir la seguridad de `MsmqAuthenticationMode`, `MsmqProtectionLevel` y `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="a7290-196">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3. <span data-ttu-id="a7290-197">Para que el intercambio de metadatos para funcionar, registramos una dirección URL con enlace de http.</span><span class="sxs-lookup"><span data-stu-id="a7290-197">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="a7290-198">Esto requiere que el servicio se ejecute en una ventana de comandos elevada.</span><span class="sxs-lookup"><span data-stu-id="a7290-198">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="a7290-199">De lo contrario, obtendrá una excepción como: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span><span class="sxs-lookup"><span data-stu-id="a7290-199">Otherwise, you get an exception such as: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a7290-200">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a7290-200">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a7290-201">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a7290-201">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a7290-202">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7290-202">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7290-203">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a7290-203">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
