---
description: 'Más información acerca de: comunicación Two-Way'
title: Comunicación bidireccional
ms.date: 03/30/2017
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
ms.openlocfilehash: 8e7f87c6ecd672d270a673a8e933e3c9ed4b5c00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798256"
---
# <a name="two-way-communication"></a><span data-ttu-id="9c801-103">Comunicación bidireccional</span><span class="sxs-lookup"><span data-stu-id="9c801-103">Two-Way Communication</span></span>

<span data-ttu-id="9c801-104">Este ejemplo muestra cómo llevar a cabo la comunicación en cola bidireccional sobre MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9c801-104">This sample demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span> <span data-ttu-id="9c801-105">El ejemplo usa el enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="9c801-105">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="9c801-106">En este caso, el servicio es una aplicación de consola hospedada en sí misma que permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="9c801-106">In this case, the service is a self-hosted console application that allows you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c801-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9c801-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9c801-108">Este ejemplo se basa en el [enlace MSMQ de transacción](transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="9c801-108">This sample is based on the [Transacted MSMQ Binding](transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="9c801-109">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="9c801-109">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="9c801-110">El cliente envía los mensajes a una cola y el servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="9c801-110">The client sends messages to a queue, and the service receives messages from the queue.</span></span> <span data-ttu-id="9c801-111">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="9c801-111">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="9c801-112">Este ejemplo muestra la comunicación bidireccional mediante las colas.</span><span class="sxs-lookup"><span data-stu-id="9c801-112">This sample demonstrates 2-way communication using queues.</span></span> <span data-ttu-id="9c801-113">El cliente envía los pedidos de compra a la cola desde dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="9c801-113">The client sends purchase orders to the queue from within the scope of a transaction.</span></span> <span data-ttu-id="9c801-114">El servicio recibe las órdenes, procesa la orden y, a continuación, llama de nuevo al cliente con el estado de la orden desde la cola dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="9c801-114">The service receives the orders, processes the order and then calls back the client with the status of the order from the queue within the scope of a transaction.</span></span> <span data-ttu-id="9c801-115">Para facilitar la comunicación bidireccional, tanto el cliente como el servicio utilizan las colas para poner en cola los pedidos de compra y el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-115">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>  
  
 <span data-ttu-id="9c801-116">El contrato de servicios `IOrderProcessor` define operaciones de servicio unidireccionales que satisfacen el uso de poner en cola.</span><span class="sxs-lookup"><span data-stu-id="9c801-116">The service contract `IOrderProcessor` defines one-way service operations that suit the use of queuing.</span></span> <span data-ttu-id="9c801-117">La operación del servicio incluye el punto de conexión de la respuesta para utilizarlo para enviar los estados del orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-117">The service operation includes the reply endpoint to use to send the order statuses to.</span></span> <span data-ttu-id="9c801-118">El punto de conexión de la respuesta es el URI de la cola para devolver el estado de la orden al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c801-118">The reply endpoint is the URI of the queue to send the order status back to the client.</span></span> <span data-ttu-id="9c801-119">La aplicación de procesamiento de orden implementa este contrato.</span><span class="sxs-lookup"><span data-stu-id="9c801-119">The order processing application implements this contract.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string
                                  reportOrderStatusTo);  
}
```
  
 <span data-ttu-id="9c801-120">El cliente especifica el contrato de la respuesta para enviar el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-120">The reply contract to send order status is specified by the client.</span></span> <span data-ttu-id="9c801-121">El cliente implementa el contrato del estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-121">The client implements the order status contract.</span></span> <span data-ttu-id="9c801-122">El servicio utiliza el proxy generado de este contrato para devolver el estado de la orden al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c801-122">The service uses the generated proxy of this contract to send order status back to the client.</span></span>  

```csharp
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```

 <span data-ttu-id="9c801-123">La operación del servicio procesa el pedido de compra enviado.</span><span class="sxs-lookup"><span data-stu-id="9c801-123">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="9c801-124"><xref:System.ServiceModel.OperationBehaviorAttribute> se aplica a la operación del servicio para especificar la inscripción automática en una transacción que se utiliza para recibir el mensaje de la cola y la realización automática de transacciones en la realización de la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c801-124">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in a transaction that is used to receive the message from the queue and automatic completion of transactions on completion of the service operation.</span></span> <span data-ttu-id="9c801-125">La clase `Orders` encapsula la funcionalidad del procesamiento de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-125">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="9c801-126">En este caso, agrega el pedido de compra a un diccionario.</span><span class="sxs-lookup"><span data-stu-id="9c801-126">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="9c801-127">La transacción en la que la operación del servicio se dio de alta está disponible para las operaciones en la clase `Orders`.</span><span class="sxs-lookup"><span data-stu-id="9c801-127">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>  
  
 <span data-ttu-id="9c801-128">La operación del servicio, además de procesar el pedido de compra enviado, responde de nuevo al cliente en el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-128">The service operation, in addition to processing the submitted purchase order, replies back to the client on the status of the order.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```

 <span data-ttu-id="9c801-129">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c801-129">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="9c801-130">Los extremos para el servicio se definen en la sección de System.ServiceModel del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c801-130">The endpoint for the service is defined in the System.ServiceModel section of the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c801-131">El nombre de cola de MSMQ y la dirección de extremo utilizan convenciones de direccionamiento ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="9c801-131">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="9c801-132">El nombre de la cola MSMQ utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9c801-132">The MSMQ queue name uses a dot (.) for the local machine and backslash separators in its path.</span></span> <span data-ttu-id="9c801-133">La dirección del punto de conexión de Windows Communication Foundation (WCF) especifica un esquema net. MSMQ:, usa el "localhost" para el equipo local y utiliza barras diagonales en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9c801-133">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine, and uses forward slashes in its path.</span></span> <span data-ttu-id="9c801-134">Para leer de una cola que se hospeda en el equipo remoto, reemplace el "." y el “host local” por el nombre del equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="9c801-134">To read from a queue that is hosted on the remote machine, replace the "." and "localhost" to the remote machine name.</span></span>  
  
 <span data-ttu-id="9c801-135">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="9c801-135">The service is self hosted.</span></span> <span data-ttu-id="9c801-136">Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano.</span><span class="sxs-lookup"><span data-stu-id="9c801-136">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="9c801-137">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="9c801-137">This can be done manually or through code.</span></span> <span data-ttu-id="9c801-138">En este ejemplo, el servicio comprueba la existencia de la cola y la crea si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9c801-138">In this sample, the service checks for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="9c801-139">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c801-139">The queue name is read from the configuration file.</span></span> <span data-ttu-id="9c801-140">La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) utiliza la dirección base para generar el proxy en el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c801-140">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
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
    }  
}  
```

 <span data-ttu-id="9c801-141">El cliente crea un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="9c801-141">The client creates a transaction.</span></span> <span data-ttu-id="9c801-142">La comunicación con la cola tiene lugar dentro del ámbito de la transacción, produciendo que se tratae como una unidad atómica donde todos los mensajes tienen éxito o no dan error.</span><span class="sxs-lookup"><span data-stu-id="9c801-142">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span>  

```csharp
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```

 <span data-ttu-id="9c801-143">El código de cliente implementa el contrato`IOrderStatus` para recibir el estado de la orden del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c801-143">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="9c801-144">En este caso, imprime el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-144">In this case, it prints out the order status.</span></span>  

```csharp
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,
                                                           status);  
    }  
}  
```

 <span data-ttu-id="9c801-145">La cola de estado de la orden se crea en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="9c801-145">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="9c801-146">La configuración del cliente incluye la configuración del servicio del estado de la orden para hospedar el servicio del estado de la orden, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c801-146">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
              binding="netMsmqBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="9c801-147">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c801-147">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="9c801-148">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c801-148">You can see the service receive messages from the client.</span></span> <span data-ttu-id="9c801-149">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c801-149">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="9c801-150">El servicio muestra la información del pedido de compra e indica que se está devolviendo el estado de la orden a la cola de estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="9c801-150">The service displays the purchase order information and indicates it is sending back the order status to the order status queue.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 <span data-ttu-id="9c801-151">El cliente muestra la información del estado de la orden enviada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c801-151">The client displays the order status information sent by the service.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9c801-152">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c801-152">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9c801-153">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c801-153">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9c801-154">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c801-154">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9c801-155">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c801-155">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9c801-156">Si utiliza Svcutil.exe para recompilar la configuración de este ejemplo, asegúrese de que modifica los nombres del punto de conexión en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c801-156">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint names in the client configuration to match the client code.</span></span>  
  
 <span data-ttu-id="9c801-157">De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9c801-157">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="9c801-158">Hay dos propiedades pertinentes para la seguridad de transporte de MSMQ y, de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign` .</span><span class="sxs-lookup"><span data-stu-id="9c801-158">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="9c801-159">Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9c801-159">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="9c801-160">Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="9c801-160">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="9c801-161">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory</span><span class="sxs-lookup"><span data-stu-id="9c801-161">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="9c801-162">Si su equipo no es parte de un dominio o no tiene la integración del directorio activo instalada, desactive la seguridad de transporte, estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c801-162">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2. <span data-ttu-id="9c801-163">Al desactivar la seguridad para una configuración del cliente, se genera lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c801-163">Turning off security for a client configuration generates the following:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
                    binding="netMsmqBinding"
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3. <span data-ttu-id="9c801-164">El servicio para este ejemplo crea un enlace en `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="9c801-164">The service for this sample creates a binding in the `OrderProcessorService`.</span></span> <span data-ttu-id="9c801-165">Agregue una línea de código una vez se haya creado instancias para el enlace para establecer el modo de seguridad en `None`.</span><span class="sxs-lookup"><span data-stu-id="9c801-165">Add a line of code after the binding is instantiated to set the security mode to `None`.</span></span>  
  
    ```csharp
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4. <span data-ttu-id="9c801-166">Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9c801-166">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9c801-167">Establecer `security mode` en `None` es equivalente a definir la seguridad de la propiedad <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> o `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="9c801-167">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> or `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9c801-168">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9c801-168">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9c801-169">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9c801-169">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="9c801-170">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9c801-170">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9c801-171">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9c801-171">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
