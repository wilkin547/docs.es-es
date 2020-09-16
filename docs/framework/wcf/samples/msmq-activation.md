---
title: Activación MSMQ
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 349eadb8f517993c343e81656204ad25e62ed931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555242"
---
# <a name="msmq-activation"></a><span data-ttu-id="35826-102">Activación MSMQ</span><span class="sxs-lookup"><span data-stu-id="35826-102">MSMQ Activation</span></span>

<span data-ttu-id="35826-103">Este ejemplo muestra cómo hospedar aplicaciones en el servicio de activación del proceso de Windows (WAS) que se lee en una cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="35826-103">This sample demonstrates how to host applications in Windows Process Activation Service (WAS) that are read from a message queue.</span></span> <span data-ttu-id="35826-104">Este ejemplo utiliza `netMsmqBinding` y se basa en el ejemplo de [comunicación bidireccional](two-way-communication.md) .</span><span class="sxs-lookup"><span data-stu-id="35826-104">This sample uses the `netMsmqBinding` and is based on the [Two-Way Communication](two-way-communication.md) sample.</span></span> <span data-ttu-id="35826-105">El servicio en este caso es una aplicación hospedada en web y el cliente es autohospedado y proporciona resultados a la consola para observar el estado de pedidos de compra enviados.</span><span class="sxs-lookup"><span data-stu-id="35826-105">The service in this case is a Web-hosted application and the client is self-hosted and outputs to the console to observe the status of purchase orders submitted.</span></span>

> [!NOTE]
> <span data-ttu-id="35826-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="35826-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="35826-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="35826-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="35826-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="35826-108">Check for the following (default) directory before continuing.</span></span>
>
> <span data-ttu-id="35826-109">\<InstallDrive>: \ WF_WCF_Samples</span><span class="sxs-lookup"><span data-stu-id="35826-109">\<InstallDrive>:\WF_WCF_Samples</span></span>
>
> <span data-ttu-id="35826-110">Si este directorio no existe, vaya a los [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos y WCF.</span><span class="sxs-lookup"><span data-stu-id="35826-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all WCF and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35826-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="35826-111">This sample is located in the following directory.</span></span>
>
> <span data-ttu-id="35826-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span><span class="sxs-lookup"><span data-stu-id="35826-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span></span>

<span data-ttu-id="35826-113">Windows Process Activation Service (WAS), el nuevo mecanismo de activación de procesos para Windows Server 2008, proporciona características similares a las de IIS que anteriormente solo estaban disponibles para aplicaciones basadas en HTTP a aplicaciones que usan protocolos que no son HTTP.</span><span class="sxs-lookup"><span data-stu-id="35826-113">Windows Process Activation Service (WAS), the new process activation mechanism for Windows Server 2008, provides IIS-like features that were previously only available to HTTP-based applications to applications that use non-HTTP protocols.</span></span> <span data-ttu-id="35826-114">Windows Communication Foundation (WCF) usa la interfaz del adaptador del agente de escucha para comunicar las solicitudes de activación que se reciben a través de los protocolos no HTTP admitidos por WCF, como TCP, canalizaciones con nombre y MSMQ.</span><span class="sxs-lookup"><span data-stu-id="35826-114">Windows Communication Foundation (WCF) uses the Listener Adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, Named Pipes, and MSMQ.</span></span> <span data-ttu-id="35826-115">La funcionalidad para recibir solicitudes a través de protocolos no http está hospedada por servicios de Windows administrados que se ejecutan en SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="35826-115">The functionality for receiving requests over non-HTTP protocols is hosted by managed Windows services running in SMSvcHost.exe.</span></span>

<span data-ttu-id="35826-116">El servicio Net.Msmq Listener Adapter (NetMsmqActivator) activa aplicaciones en cola basadas en mensajes en la cola.</span><span class="sxs-lookup"><span data-stu-id="35826-116">The Net.Msmq Listener Adapter service (NetMsmqActivator) activates queued applications based on messages in the queue.</span></span>

<span data-ttu-id="35826-117">El cliente envía los pedidos de compra al servicio desde dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="35826-117">The client sends purchase orders to the service from within the scope of a transaction.</span></span> <span data-ttu-id="35826-118">El servicio recibe las órdenes en una transacción y las procesa.</span><span class="sxs-lookup"><span data-stu-id="35826-118">The service receives the orders in a transaction and processes them.</span></span> <span data-ttu-id="35826-119">El servicio llama a continuación de nuevo al cliente con el estado del orden.</span><span class="sxs-lookup"><span data-stu-id="35826-119">The service then calls back the client with the status of the order.</span></span> <span data-ttu-id="35826-120">Para facilitar la comunicación bidireccional, tanto el cliente como el servicio utilizan las colas para poner en cola los pedidos de compra y el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-120">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>

<span data-ttu-id="35826-121">El contrato de servicio `IOrderProcessor` define operaciones de servicio unidireccionales que funcionan en cola.</span><span class="sxs-lookup"><span data-stu-id="35826-121">The service contract `IOrderProcessor` defines the one-way service operations that work with queuing.</span></span> <span data-ttu-id="35826-122">La operación del servicio utiliza el extremo de respuesta para enviar estados de orden al cliente.</span><span class="sxs-lookup"><span data-stu-id="35826-122">The service operation uses the reply endpoint to send order statuses to the client.</span></span> <span data-ttu-id="35826-123">La dirección de punto de conexión de la respuesta es el URI de la cola utilizado para devolver el estado del orden al cliente.</span><span class="sxs-lookup"><span data-stu-id="35826-123">The reply endpoint's address is the URI of the queue used to send the order status back to the client.</span></span> <span data-ttu-id="35826-124">La aplicación de procesamiento de orden implementa este contrato.</span><span class="sxs-lookup"><span data-stu-id="35826-124">The order processing application implements this contract.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

<span data-ttu-id="35826-125">El cliente especifica el contrato de la respuesta para enviar el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-125">The reply contract to send order status to is specified by the client.</span></span> <span data-ttu-id="35826-126">El cliente implementa el contrato del estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-126">The client implements the order status contract.</span></span> <span data-ttu-id="35826-127">El servicio utiliza el cliente generado de este contrato para devolver el estado de la orden al cliente.</span><span class="sxs-lookup"><span data-stu-id="35826-127">The service uses the generated client of this contract to send order status back to the client.</span></span>

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

<span data-ttu-id="35826-128">La operación del servicio procesa el pedido de compra enviado.</span><span class="sxs-lookup"><span data-stu-id="35826-128">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="35826-129"><xref:System.ServiceModel.OperationBehaviorAttribute> se aplica a la operación del servicio para especificar la inscripción automática en la transacción que se utiliza para recibir el mensaje de la cola y la realización automática de la transacción en la realización de la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="35826-129">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in the transaction that is used to receive the message from the queue and automatic completion of the transaction on completion of the service operation.</span></span> <span data-ttu-id="35826-130">La clase `Orders` encapsula la funcionalidad del procesamiento de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-130">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="35826-131">En este caso, agrega el pedido de compra a un diccionario.</span><span class="sxs-lookup"><span data-stu-id="35826-131">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="35826-132">La transacción en la que la operación del servicio se dio de alta está disponible para las operaciones en la clase `Orders`.</span><span class="sxs-lookup"><span data-stu-id="35826-132">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>

<span data-ttu-id="35826-133">La operación del servicio, además de procesar el pedido de compra enviado, responde de nuevo al cliente acerca del estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-133">The service operation, in addition to processing the submitted purchase order, replies back to the client about the status of the order.</span></span>

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

<span data-ttu-id="35826-134">El enlace de cliente que se ha de utilizar se especifica utilizando un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="35826-134">The client binding to use is specified using a configuration file.</span></span>

<span data-ttu-id="35826-135">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="35826-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="35826-136">El punto de conexión para el servicio se define en la sección de System.ServiceModel del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="35826-136">The endpoint for the service is defined in the System.serviceModel section of the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="35826-137">El nombre de cola de MSMQ y la dirección de extremo utilizan convenciones de direccionamiento ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="35826-137">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="35826-138">El nombre de la cola de MSMQ utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="35826-138">The MSMQ queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="35826-139">La dirección del extremo de WCF especifica un esquema net. MSMQ:, usa el "localhost" para el equipo local y utiliza barras diagonales en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="35826-139">The WCF endpoint address specifies a net.msmq: scheme, uses "localhost" for the local computer, and uses forward slashes in its path.</span></span> <span data-ttu-id="35826-140">Para leer de una cola que se hospeda en el equipo remoto, reemplace "." y “localhost” con el nombre del equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="35826-140">To read from a queue that is hosted on the remote computer, replace the "." and "localhost" to the remote computer name.</span></span>

<span data-ttu-id="35826-141">Se utiliza un archivo .svc con el nombre de la clase para hospedar el código del servicio en WAS.</span><span class="sxs-lookup"><span data-stu-id="35826-141">A .svc file with the name of the class is used to host the service code in WAS.</span></span>

<span data-ttu-id="35826-142">El propio archivo Service.svc contiene una directiva para crear `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="35826-142">The Service.svc file itself contains a directive to create the `OrderProcessorService`.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

<span data-ttu-id="35826-143">El archivo Service.svc también contiene una directiva de ensamblado para asegurar que se carga System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="35826-143">The Service.svc file also contains an assembly directive to ensure that System.Transactions.dll is loaded.</span></span>

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

<span data-ttu-id="35826-144">El cliente crea un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="35826-144">The client creates a transaction scope.</span></span> <span data-ttu-id="35826-145">La comunicación con el servicio tiene lugar dentro del ámbito de la transacción, produciendo que se trate como una unidad atómica donde todos los mensajes tienen éxito o dan error.</span><span class="sxs-lookup"><span data-stu-id="35826-145">Communication with the service takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="35826-146">La transacción se confirma llamando a `Complete` en el ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="35826-146">The transaction is committed by calling `Complete` on the transaction scope.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

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
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

<span data-ttu-id="35826-147">El código de cliente implementa el contrato`IOrderStatus` para recibir el estado de la orden del servicio.</span><span class="sxs-lookup"><span data-stu-id="35826-147">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="35826-148">En este caso, imprime el estado de la orden.</span><span class="sxs-lookup"><span data-stu-id="35826-148">In this case, it prints out the order status.</span></span>

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

<span data-ttu-id="35826-149">La cola de estado de la orden se crea en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="35826-149">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="35826-150">La configuración del cliente incluye la configuración del servicio del estado de la orden para hospedar el servicio del estado de la orden, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="35826-150">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

<span data-ttu-id="35826-151">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="35826-151">When you run the sample, the client and service activities are displayed in both the server and client console windows.</span></span> <span data-ttu-id="35826-152">Puede ver que el servidor recibe mensajes desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="35826-152">You can see the server receive messages from the client.</span></span> <span data-ttu-id="35826-153">Presione Entrar en cada ventana de la consola para cerrar el servidor y el cliente.</span><span class="sxs-lookup"><span data-stu-id="35826-153">Press ENTER in each console window to shut down the server and client.</span></span>

<span data-ttu-id="35826-154">El cliente muestra la información del estado de la orden enviada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="35826-154">The client displays the order status information sent by the server:</span></span>

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="35826-155">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="35826-155">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="35826-156">Asegúrese de que IIS 7,0 está instalado, ya que es necesario para la activación WAS.</span><span class="sxs-lookup"><span data-stu-id="35826-156">Ensure that IIS 7.0 is installed, as it is required for WAS activation.</span></span>

2. <span data-ttu-id="35826-157">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35826-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span> <span data-ttu-id="35826-158">Además, debe instalar los componentes de activación que no son HTTP de WCF:</span><span class="sxs-lookup"><span data-stu-id="35826-158">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="35826-159">En el menú **Inicio**, elija **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="35826-159">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="35826-160">Seleccione **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="35826-160">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="35826-161">Haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="35826-161">Click **Turn Windows Features on or off**.</span></span>

    4. <span data-ttu-id="35826-162">En **Resumen de características**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="35826-162">Under **Features Summary**, click **Add Features**.</span></span>

    5. <span data-ttu-id="35826-163">Expanda el nodo **Microsoft .NET Framework 3,0** y compruebe la **Windows Communication Foundation característica activación no http** .</span><span class="sxs-lookup"><span data-stu-id="35826-163">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="35826-164">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35826-164">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="35826-165">Ejecute el cliente ejecutando client.exe de una ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="35826-165">Run the client by executing client.exe from a command window.</span></span> <span data-ttu-id="35826-166">Esto crea la cola y envía un mensaje a la misma.</span><span class="sxs-lookup"><span data-stu-id="35826-166">This creates the queue and sends a message to it.</span></span> <span data-ttu-id="35826-167">Deje que el cliente se ejecute para ver el resultado del servicio que lee el mensaje</span><span class="sxs-lookup"><span data-stu-id="35826-167">Leave the client running to see the result of the service reading the message</span></span>

5. <span data-ttu-id="35826-168">El servicio de activación MSMQ se ejecuta como servicio de red de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="35826-168">The MSMQ activation service runs as Network Service by default.</span></span> <span data-ttu-id="35826-169">Por consiguiente, la cola que se utiliza para activar la aplicación debe tener permisos de recepción y lectura para el Servicio de la Red.</span><span class="sxs-lookup"><span data-stu-id="35826-169">Therefore, the queue that is used to activate the application must have receive and peek permissions for Network Service.</span></span> <span data-ttu-id="35826-170">Esto se puede agregar utilizando el MMC de Message Queuing:</span><span class="sxs-lookup"><span data-stu-id="35826-170">This can be added by using the Message Queuing MMC:</span></span>

    1. <span data-ttu-id="35826-171">En el menú **Inicio** , haga clic en **Ejecutar**, escriba `Compmgmt.msc` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="35826-171">From the **Start** menu, click **Run**, then type `Compmgmt.msc` and press ENTER.</span></span>

    2. <span data-ttu-id="35826-172">En **servicios y aplicaciones**, expanda **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="35826-172">Under **Services and Applications**, expand **Message Queuing**.</span></span>

    3. <span data-ttu-id="35826-173">Haga clic en **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="35826-173">Click **Private Queues**.</span></span>

    4. <span data-ttu-id="35826-174">Haga clic con el botón secundario en la cola (servicemodelsamples/Service. SVC) y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="35826-174">Right-click the queue (servicemodelsamples/Service.svc) and choose **Properties**.</span></span>

    5. <span data-ttu-id="35826-175">En la pestaña **seguridad** , haga clic en **Agregar** y proporcione permisos de lectura y recepción al servicio de red.</span><span class="sxs-lookup"><span data-stu-id="35826-175">On the **Security** tab, click **Add** and give peek and receive permissions to Network Service.</span></span>

6. <span data-ttu-id="35826-176">Configure el Windows Process Activation Service (WAS) para admitir la activación de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="35826-176">Configure the Windows Process Activation Service (WAS) to support MSMQ activation.</span></span>

    <span data-ttu-id="35826-177">Para su comodidad, los dos pasos siguientes se implementan en un archivo por lotes denominado AddMsmqSiteBinding.cmd que se encuentra en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35826-177">As a convenience, the following steps are implemented in a batch file called AddMsmqSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="35826-178">Para admitir la activación de net.msmq, el sitio web predeterminado debe enlazarse primero al protocolo net.msmq.</span><span class="sxs-lookup"><span data-stu-id="35826-178">To support net.msmq activation, the default Web site must first be bound to the net.msmq protocol.</span></span> <span data-ttu-id="35826-179">Esto se puede hacer utilizando appcmd.exe, que se instala con el conjunto de herramientas de administración de IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="35826-179">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="35826-180">Desde un símbolo del sistema con permisos elevados (administrador), ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="35826-180">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="35826-181">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="35826-181">This command is a single line of text.</span></span>

        <span data-ttu-id="35826-182">Este comando agrega un enlace del sitio de net.msmq al sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="35826-182">This command adds a net.msmq site binding to the default Web site.</span></span>

    2. <span data-ttu-id="35826-183">Aunque todas las aplicaciones dentro de un sitio comparten un enlace net.msmq común, cada aplicación puede habilitar la compatibilidad con net.msmq individualmente.</span><span class="sxs-lookup"><span data-stu-id="35826-183">Although all applications within a site share a common net.msmq binding, each application can enable net.msmq support individually.</span></span> <span data-ttu-id="35826-184">Para habilitar net.msmq para la aplicación /servicemodelsamples, ejecute el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="35826-184">To enable net.msmq for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > <span data-ttu-id="35826-185">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="35826-185">This command is a single line of text.</span></span>

        <span data-ttu-id="35826-186">Este comando permite tener acceso a la aplicación/servicemodelsamples mediante `http://localhost/servicemodelsamples` y `net.msmq://localhost/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="35826-186">This command enables the /servicemodelsamples application to be accessed using `http://localhost/servicemodelsamples` and `net.msmq://localhost/servicemodelsamples`.</span></span>

7. <span data-ttu-id="35826-187">Si no lo ha hecho previamente, asegúrese de que el servicio de activación MSMQ está habilitado.</span><span class="sxs-lookup"><span data-stu-id="35826-187">If you have not done so previously, ensure that the MSMQ activation service is enabled.</span></span> <span data-ttu-id="35826-188">En el menú **Inicio** , haga clic en **Ejecutar**y escriba `Services.msc` .</span><span class="sxs-lookup"><span data-stu-id="35826-188">From the **Start** menu, click **Run**, and type `Services.msc`.</span></span> <span data-ttu-id="35826-189">Busque en la lista de servicios el **adaptador de escucha net. MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="35826-189">Search the list of services for the **Net.Msmq Listener Adapter**.</span></span> <span data-ttu-id="35826-190">Haga clic con el botón secundario y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="35826-190">Right-click and select **Properties**.</span></span> <span data-ttu-id="35826-191">Establezca el **tipo de inicio** en **automático**, haga clic en **aplicar** y haga clic en el botón **iniciar** .</span><span class="sxs-lookup"><span data-stu-id="35826-191">Set the **Startup Type** to **Automatic**, click **Apply** and click the **Start** button.</span></span> <span data-ttu-id="35826-192">Este paso solo debe realizarse una vez antes del primer uso del servicio de Adaptador de escucha Net.Msmq.</span><span class="sxs-lookup"><span data-stu-id="35826-192">This step must only be done once prior to the first usage of the Net.Msmq Listener Adapter service.</span></span>

8. <span data-ttu-id="35826-193">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35826-193">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="35826-194">Además, cambie el código en el cliente que envía el pedido de compra para reflejar el nombre de equipo en el URI de la cola al enviar el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="35826-194">Additionally, change the code on the client that submits the purchase order to reflect the computer name in the URI of the queue when submitting the purchase order.</span></span> <span data-ttu-id="35826-195">Use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="35826-195">Use the following code:</span></span>

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. <span data-ttu-id="35826-196">Quite el enlace del sitio de net.msmq que ha agregado para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35826-196">Remove the net.msmq site binding you added for this sample.</span></span>

    <span data-ttu-id="35826-197">Para su comodidad, los pasos siguientes se implementan en un archivo de información denominado RemoveMsmqSiteBinding.cmd que se encuentra en el directorio de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="35826-197">As a convenience, the following steps are implemented in a batch file called RemoveMsmqSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="35826-198">Quite net.msmq de la lista de protocolos habilitados ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="35826-198">Remove net.msmq from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="35826-199">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="35826-199">This command is a single line of text.</span></span>

    2. <span data-ttu-id="35826-200">Quitar el enlace del sitio de net.msmq ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="35826-200">Remove the net.msmq site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="35826-201">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="35826-201">This command is a single line of text.</span></span>

    > [!WARNING]
    > <span data-ttu-id="35826-202">Al ejecutar el archivo por lotes, se restablecerá DefaultAppPool para que se ejecute utilizando la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35826-202">Running the batch file will reset the DefaultAppPool to run using .NET Framework version 2.0.</span></span>

<span data-ttu-id="35826-203">De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada.</span><span class="sxs-lookup"><span data-stu-id="35826-203">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="35826-204">Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="35826-204">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="35826-205">De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="35826-205">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="35826-206">Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio.</span><span class="sxs-lookup"><span data-stu-id="35826-206">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="35826-207">Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".</span><span class="sxs-lookup"><span data-stu-id="35826-207">If you run this sample on a computer that is not part of a domain, the following error is received: "User's internal message queuing certificate does not exist".</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="35826-208">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35826-208">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="35826-209">Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en cero, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="35826-209">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to none as shown in the following sample configuration.</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. <span data-ttu-id="35826-210">Cambie la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35826-210">Change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35826-211">Establecer `security mode` en `None` es equivalente a definir `MsmqAuthenticationMode`, `MsmqProtectionLevel` y la seguridad de `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="35826-211">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

3. <span data-ttu-id="35826-212">Para habilitar la activación en un equipo combinado a un grupo de trabajo, el servicio de activación y el proceso de trabajador se deben ejecutar con una cuenta de usuario concreta (debe ser la misma para ambos) y la cola debe tener ACL para la cuenta de usuario concreta.</span><span class="sxs-lookup"><span data-stu-id="35826-212">To enable activation in a computer joined to a workgroup, both the activation service and the worker process must be run with a specific user account (must be same for both) and the queue must have ACLs for the specific user account.</span></span>

     <span data-ttu-id="35826-213">Para cambiar la identidad bajo la que el proceso de trabajador se ejecuta:</span><span class="sxs-lookup"><span data-stu-id="35826-213">To change the identity that the worker process runs under:</span></span>

    1. <span data-ttu-id="35826-214">Ejecute Inetmgr.exe.</span><span class="sxs-lookup"><span data-stu-id="35826-214">Run Inetmgr.exe.</span></span>

    2. <span data-ttu-id="35826-215">En **grupos de aplicaciones**, haga clic con el botón derecho en el **AppPool** (normalmente, **DefaultAppPool**) y elija **establecer valores predeterminados de grupo de aplicaciones..**..</span><span class="sxs-lookup"><span data-stu-id="35826-215">Under **Application Pools**, right-click the **AppPool** (typically **DefaultAppPool**) and choose **Set Application Pool Defaults…**.</span></span>

    3. <span data-ttu-id="35826-216">Cambie las propiedades Identity para utilizar la cuenta de usuario concreta.</span><span class="sxs-lookup"><span data-stu-id="35826-216">Change the Identity properties to use the specific user account.</span></span>

     <span data-ttu-id="35826-217">Para cambiar la identidad bajo la que el Servicio de Activación se ejecuta:</span><span class="sxs-lookup"><span data-stu-id="35826-217">To change the identity that the Activation Service runs under:</span></span>

    1. <span data-ttu-id="35826-218">Ejecute Services.msc.</span><span class="sxs-lookup"><span data-stu-id="35826-218">Run Services.msc.</span></span>

    2. <span data-ttu-id="35826-219">Haga clic con el botón secundario en el **adaptador net. MsmqListener**y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="35826-219">Right-click the **Net.MsmqListener Adapter**, and choose **Properties**.</span></span>

4. <span data-ttu-id="35826-220">Cambie la cuenta en la pestaña **Inicio de sesión** .</span><span class="sxs-lookup"><span data-stu-id="35826-220">Change the account in the **LogOn** tab.</span></span>

5. <span data-ttu-id="35826-221">En un grupo de trabajo, el servicio se debe ejecutar también utilizando un token sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="35826-221">In workgroup, the service must also run using an unrestricted token.</span></span> <span data-ttu-id="35826-222">Para ello, ejecute lo siguiente en una ventana de comandos:</span><span class="sxs-lookup"><span data-stu-id="35826-222">To do this, run the following in a command window:</span></span>

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a><span data-ttu-id="35826-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="35826-223">See also</span></span>

- <span data-ttu-id="35826-224">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="35826-224">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
