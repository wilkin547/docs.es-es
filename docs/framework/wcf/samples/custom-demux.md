---
title: Demux personalizado
ms.date: 03/30/2017
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
ms.openlocfilehash: e88672f152b87740feef1345b3eac213916a1527
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805569"
---
# <a name="custom-demux"></a><span data-ttu-id="7f217-102">Demux personalizado</span><span class="sxs-lookup"><span data-stu-id="7f217-102">Custom Demux</span></span>
<span data-ttu-id="7f217-103">Este ejemplo muestra cómo se pueden asignar los encabezados de mensaje MSMQ para diferentes operaciones de servicio para que los servicios de Windows Communication Foundation (WCF) que utilizan <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> no están limitados a utilizar una operación de servicio como se muestra en el [ Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) y [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7f217-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that Windows Communication Foundation (WCF) services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="7f217-104">El servicio de este ejemplo es una aplicación de consola autohospedada que permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="7f217-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="7f217-105">El contrato de servicio es `IOrderProcessor`, y define un servicio unidireccional que es adecuado para usarse con colas.</span><span class="sxs-lookup"><span data-stu-id="7f217-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 <span data-ttu-id="7f217-106">Un mensaje de MSMQ no tiene un encabezado Acción.</span><span class="sxs-lookup"><span data-stu-id="7f217-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="7f217-107">No es posible asignar automáticamente los mensajes de MSMQ diferentes a los contratos de operación.</span><span class="sxs-lookup"><span data-stu-id="7f217-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="7f217-108">Además, solo puede haber un contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="7f217-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="7f217-109">Para superar esta limitación, el servicio implementa el método <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> de la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="7f217-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="7f217-110">El método <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> permite al servicio asignar un encabezado determinado del mensaje a una operación del servicio determinada.</span><span class="sxs-lookup"><span data-stu-id="7f217-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="7f217-111">En este ejemplo, el encabezado de etiqueta del mensaje está asignado a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="7f217-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="7f217-112">El parámetro `Name` del contrato de operación determina qué operación del servicio se debe enviar para una etiqueta del mensaje determinada.</span><span class="sxs-lookup"><span data-stu-id="7f217-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="7f217-113">Por ejemplo, si el encabezado de etiqueta del mensaje contiene "SubmitPurchaseOrder", se invoca la operación de servicio de "SubmitPurchaseOrder."</span><span class="sxs-lookup"><span data-stu-id="7f217-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 <span data-ttu-id="7f217-114">El servicio debe implementar el método <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> de la interfaz <xref:System.ServiceModel.Description.IContractBehavior> como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f217-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="7f217-115">Esto aplica el `OperationSelector` personalizado a la expedición del marco de trabajo del servicio en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f217-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 <span data-ttu-id="7f217-116">Un mensaje debe atravesar <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> del distribuidor antes de llegar al OperationSelector.</span><span class="sxs-lookup"><span data-stu-id="7f217-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="7f217-117">De forma predeterminada se rechaza un mensaje si su acción no se puede buscar en cualquier contrato implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="7f217-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="7f217-118">Para evitar esta comprobación, implementamos un <xref:System.ServiceModel.Description.IEndpointBehavior> denominado `MatchAllFilterBehavior`, que permite a cualquier mensaje atravesar `ContractFilter` aplicando el <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> como sigue.</span><span class="sxs-lookup"><span data-stu-id="7f217-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 <span data-ttu-id="7f217-119">Cuando el servicio recibe un mensaje, la operación del servicio adecuada se envía utilizando la información proporcionada por el encabezado de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7f217-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="7f217-120">El cuerpo del mensaje se deserializa en un objeto `PurchaseOrder`, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f217-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 <span data-ttu-id="7f217-121">El servicio es autohospedado.</span><span class="sxs-lookup"><span data-stu-id="7f217-121">The service is self-hosted.</span></span> <span data-ttu-id="7f217-122">Al utilizar el MSMQ, se debe crear la cola que se utiliza de antemano.</span><span class="sxs-lookup"><span data-stu-id="7f217-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="7f217-123">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="7f217-123">This can be done manually or through code.</span></span> <span data-ttu-id="7f217-124">En este ejemplo, el servicio contiene el código para comprobar la existencia de la cola y crearla si no existe.</span><span class="sxs-lookup"><span data-stu-id="7f217-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="7f217-125">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f217-125">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
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

 <span data-ttu-id="7f217-126">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f217-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f217-127">El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7f217-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="7f217-128">La dirección del extremo WCF especifica un esquema msmq.formatname y utiliza localhost para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="7f217-128">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="7f217-129">Lo que sigue al esquema es una dirección de cola con el formato apropiado según las instrucciones de direccionamiento del nombre de formato de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7f217-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="7f217-130">Este ejemplo requiere la instalación de [Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=95143).</span><span class="sxs-lookup"><span data-stu-id="7f217-130">This sample requires the installation of [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="7f217-131">Inicie el servicio y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="7f217-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="7f217-132">El siguiente resultado se ve en el cliente.</span><span class="sxs-lookup"><span data-stu-id="7f217-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="7f217-133">El resultado siguiente se debe ver en el servicio.</span><span class="sxs-lookup"><span data-stu-id="7f217-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7f217-134">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f217-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7f217-135">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7f217-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="7f217-136">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="7f217-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="7f217-137">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="7f217-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="7f217-138">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7f217-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="7f217-139">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="7f217-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="7f217-140">Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f217-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="7f217-141">Expanda el **características** ficha.</span><span class="sxs-lookup"><span data-stu-id="7f217-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="7f217-142">Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="7f217-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="7f217-143">Compruebe el **transaccional** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7f217-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="7f217-144">Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="7f217-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="7f217-145">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7f217-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="7f217-146">Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7f217-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="7f217-147">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="7f217-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="7f217-148">Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="7f217-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="7f217-149">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="7f217-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="7f217-150">En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".</span><span class="sxs-lookup"><span data-stu-id="7f217-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="7f217-151">En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7f217-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="7f217-152">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7f217-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f217-153">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7f217-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7f217-154">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7f217-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7f217-155">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7f217-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7f217-156">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7f217-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="7f217-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f217-157">See Also</span></span>  
 [<span data-ttu-id="7f217-158">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="7f217-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="7f217-159">Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="7f217-159">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=95143)
