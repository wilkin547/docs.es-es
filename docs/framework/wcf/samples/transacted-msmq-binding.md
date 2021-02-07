---
description: 'Más información sobre: enlace de MSMQ con transacciones'
title: Enlace MSMQ por transacciones
ms.date: 03/30/2017
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
ms.openlocfilehash: 17fdcdb169c9e57c1a95d5aea4c79654e3739664
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668535"
---
# <a name="transacted-msmq-binding"></a><span data-ttu-id="8d74f-103">Enlace MSMQ por transacciones</span><span class="sxs-lookup"><span data-stu-id="8d74f-103">Transacted MSMQ Binding</span></span>

<span data-ttu-id="8d74f-104">Este ejemplo muestra cómo llevar a cabo la comunicación en cola por transacciones utilizando Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8d74f-104">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>

> [!NOTE]
> <span data-ttu-id="8d74f-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8d74f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="8d74f-106">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="8d74f-107">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="8d74f-108">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-108">The service receives messages from the queue.</span></span> <span data-ttu-id="8d74f-109">El servicio y el cliente no se tienen que estar ejecutando simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-109">The service and client, therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="8d74f-110">Cuando las transacciones se utilizan para enviar y recibir los mensajes, hay en realidad dos transacciones independientes.</span><span class="sxs-lookup"><span data-stu-id="8d74f-110">When transactions are used to send and receive messages, there are actually two separate transactions.</span></span> <span data-ttu-id="8d74f-111">Cuando el cliente envía los mensajes dentro del ámbito de una transacción, la transacción es local para el cliente y el administrador de cola del cliente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-111">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="8d74f-112">Cuando el servicio recibe los mensajes dentro del ámbito de la transacción, la transacción es local para el servicio y el administrador de cola receptor.</span><span class="sxs-lookup"><span data-stu-id="8d74f-112">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="8d74f-113">Es muy importante recordar que el cliente y el servicio no están participando en la misma transacción; más bien, están utilizando distintas transacciones al realizar sus operaciones (como enviar y recibir) con la cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-113">It is very important to remember that the client and the service are not participating in the same transaction; rather, they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>

<span data-ttu-id="8d74f-114">En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="8d74f-114">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="8d74f-115">El servicio recibe a continuación los mensajes enviados a la cola dentro del ámbito de la transacción definido por el servicio.</span><span class="sxs-lookup"><span data-stu-id="8d74f-115">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span>

<span data-ttu-id="8d74f-116">El contrato de servicios es `IOrderProcessor`, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-116">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span> <span data-ttu-id="8d74f-117">La interfaz define un servicio unidireccional que es conveniente para su uso con las colas.</span><span class="sxs-lookup"><span data-stu-id="8d74f-117">The interface defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

<span data-ttu-id="8d74f-118">El comportamiento del servicio define un comportamiento de la operación con `TransactionScopeRequired` definido en `true`.</span><span class="sxs-lookup"><span data-stu-id="8d74f-118">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="8d74f-119">Esto garantiza que los administradores de recursos a los que el método tiene acceso utilizan el mismo ámbito de la transacción usado para recuperar el mensaje de la cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-119">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="8d74f-120">También garantiza que si el método produce una excepción, el mensaje se devuelva a la cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-120">It also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="8d74f-121">Sin establecer este comportamiento de operación, un canal en cola crea una transacción para leer el mensaje de la cola y lo confirma automáticamente antes de la expedición de tal manera que si se produce un error en la operación, el mensaje se pierde.</span><span class="sxs-lookup"><span data-stu-id="8d74f-121">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before dispatch such that if the operation fails, the message is lost.</span></span> <span data-ttu-id="8d74f-122">El escenario más común es para que las operaciones de servicio den de alta en la transacción que se utiliza para leer el mensaje de la cola, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-122">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue, as demonstrated in the following code.</span></span>

```csharp
 // This service class that implements the service contract.
 // This added code writes output to the console window.
 public class OrderProcessorService : IOrderProcessor
 {
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
     public void SubmitPurchaseOrder(PurchaseOrder po)
     {
         Orders.Add(po);
         Console.WriteLine("Processing {0} ", po);
     }
  …
}
```

<span data-ttu-id="8d74f-123">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="8d74f-123">The service is self hosted.</span></span> <span data-ttu-id="8d74f-124">Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano.</span><span class="sxs-lookup"><span data-stu-id="8d74f-124">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="8d74f-125">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="8d74f-125">This can be done manually or through code.</span></span> <span data-ttu-id="8d74f-126">En este ejemplo, el servicio contiene el código para comprobar la existencia de la cola y crearla si no existe.</span><span class="sxs-lookup"><span data-stu-id="8d74f-126">In this sample, the service contains code to check for the existence of the queue and create the queue if it does not exist.</span></span> <span data-ttu-id="8d74f-127">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d74f-127">The queue name is read from the configuration file.</span></span> <span data-ttu-id="8d74f-128">La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) utiliza la dirección base para generar el proxy en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8d74f-128">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get the MSMQ queue name from appSettings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);

    // Create a ServiceHost for the OrderProcessorService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shut down the service.
        serviceHost.Close();
    }
}
```

<span data-ttu-id="8d74f-129">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-129">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="8d74f-130">El nombre de la cola usa un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso al crear la cola mediante <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="8d74f-130">The queue name uses a dot (.) for the local computer and backslash separators in its path when creating the queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="8d74f-131">El extremo Windows Communication Foundation (WCF) utiliza la dirección de la cola con el esquema net. MSMQ, usa "localhost" para indicar el equipo local y utiliza barras diagonales en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8d74f-131">The Windows Communication Foundation (WCF) endpoint uses the queue address with net.msmq scheme, uses "localhost" to denote the local computer, and uses forward slashes in its path.</span></span>

<span data-ttu-id="8d74f-132">El cliente crea un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="8d74f-132">The client creates a transaction scope.</span></span> <span data-ttu-id="8d74f-133">La comunicación con la cola tiene lugar dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde se envían todos los mensajes a la cola o no se envía ninguno.</span><span class="sxs-lookup"><span data-stu-id="8d74f-133">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="8d74f-134">La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A> en el ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="8d74f-134">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>

```csharp
// Create a client.
OrderProcessorClient client = new OrderProcessorClient();

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

// Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    // Make a queued call to submit the purchase order.
    client.SubmitPurchaseOrder(po);
    // Complete the transaction.
    scope.Complete();
}

// Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="8d74f-135">Para comprobar que las transacciones están funcionando, modifique el cliente marcando como comentario el ámbito de transacción tal y como se muestra en el siguiente código de ejemplo, recompile la solución y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-135">To verify that transactions are working, modify the client by commenting the transaction scope as shown in the following sample code, rebuild the solution, and run the client.</span></span>

```csharp
//scope.Complete();
```

<span data-ttu-id="8d74f-136">Dado que no se completa la transacción, los mensajes no se envían a la cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-136">Because the transaction is not completed, the messages are not sent to the queue.</span></span>

<span data-ttu-id="8d74f-137">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="8d74f-137">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8d74f-138">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-138">You can see the service receive messages from the client.</span></span> <span data-ttu-id="8d74f-139">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-139">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="8d74f-140">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-140">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="8d74f-141">Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="8d74f-141">You can run the client, shut it down, and then start up the service and it still receives the messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8d74f-142">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d74f-142">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="8d74f-143">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8d74f-143">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="8d74f-144">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="8d74f-144">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="8d74f-145">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="8d74f-145">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="8d74f-146">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8d74f-146">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="8d74f-147">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="8d74f-147">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="8d74f-148">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="8d74f-148">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="8d74f-149">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="8d74f-149">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="8d74f-150">Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="8d74f-150">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="8d74f-151">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="8d74f-151">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="8d74f-152">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="8d74f-152">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="8d74f-153">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8d74f-153">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="8d74f-154">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8d74f-154">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

<span data-ttu-id="8d74f-155">De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8d74f-155">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="8d74f-156">Hay dos propiedades importantes para la seguridad del transporte de MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d74f-156">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span></span> <span data-ttu-id="8d74f-157">De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="8d74f-157">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="8d74f-158">Para MSMQ proporcionar la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de Active Directory para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8d74f-158">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the Active Directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="8d74f-159">Si ejecuta este ejemplo en un equipo que no satisface estos criterios, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="8d74f-159">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="8d74f-160">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin la integración de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d74f-160">To run the sample on a computer joined to a workgroup or without Active Directory integration</span></span>

1. <span data-ttu-id="8d74f-161">Si su equipo no es parte de un dominio o no tiene la integración Active Directory instalada, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en el código de configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d74f-161">If your computer is not part of a domain or does not have Active Directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code.</span></span>

    ```xml
    <system.serviceModel>
      <services>
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"
                 behaviorConfiguration="OrderProcessorServiceBehavior">
          <host>
            <baseAddresses>
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
            </baseAddresses>
          </host>
          <!-- Define NetMsmqEndpoint. -->
          <endpoint
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"
              binding="netMsmqBinding"
              bindingConfiguration="Binding1"
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
          <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
          <endpoint address="mex"
                    binding="mexHttpBinding"
                    contract="IMetadataExchange" />
        </service>
      </services>

      <bindings>
        <netMsmqBinding>
          <binding name="Binding1">
            <security mode="None" />
          </binding>
        </netMsmqBinding>
      </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="OrderProcessorServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="8d74f-162">Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8d74f-162">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d74f-163">Establecer `security mode` en `None` es equivalente a definir la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="8d74f-163">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d74f-164">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8d74f-164">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8d74f-165">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8d74f-165">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="8d74f-166">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8d74f-166">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d74f-167">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8d74f-167">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`
