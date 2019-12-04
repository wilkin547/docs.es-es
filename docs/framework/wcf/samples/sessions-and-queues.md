---
title: Sesiones y colas
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 719212d908b9d5b5207dd5b4e7701ef903de31a0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715064"
---
# <a name="sessions-and-queues"></a><span data-ttu-id="8edb6-102">Sesiones y colas</span><span class="sxs-lookup"><span data-stu-id="8edb6-102">Sessions and Queues</span></span>
<span data-ttu-id="8edb6-103">Este ejemplo muestra cómo enviar y recibir un conjunto de mensajes relacionados en comunicación en cola sobre el transporte de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8edb6-103">This sample demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="8edb6-104">El ejemplo usa el enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="8edb6-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="8edb6-105">El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8edb6-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8edb6-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8edb6-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8edb6-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8edb6-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8edb6-108">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="8edb6-109">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8edb6-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8edb6-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8edb6-110">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 <span data-ttu-id="8edb6-111">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-111">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="8edb6-112">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-112">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="8edb6-113">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-113">The service receives messages from the queue.</span></span> <span data-ttu-id="8edb6-114">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-114">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="8edb6-115">A veces, un cliente envía un conjunto de mensajes relacionado con cada uno en un grupo.</span><span class="sxs-lookup"><span data-stu-id="8edb6-115">Sometimes, a client sends a set of messages that are related to each other in a group.</span></span> <span data-ttu-id="8edb6-116">Cuando los mensajes deben procesarse juntos o en un orden especificado, se puede utilizar una cola para agruparlos, para que los procesen una aplicación receptora única.</span><span class="sxs-lookup"><span data-stu-id="8edb6-116">When messages must be processed together or in a specified order, a queue can be used to group them together, for processing by a single receiving application.</span></span> <span data-ttu-id="8edb6-117">Esto es particularmente importante cuando hay varias aplicaciones receptoras en un grupo de servidores y es necesario garantizar que la misma aplicación receptora procesa un grupo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8edb6-117">This is particularly important when there are several receiving applications on a group of servers and it is necessary to ensure that a group of messages is processed by the same receiving application.</span></span> <span data-ttu-id="8edb6-118">Las sesiones en cola son un mecanismo utilizado para enviar y recibir un conjunto relacionado de mensajes que se deben procesar de repente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-118">Queued sessions are a mechanism used to send and receive a related set of messages that must get processed all at once.</span></span> <span data-ttu-id="8edb6-119">Las sesiones en cola necesitan que una transacción exhiba este patrón.</span><span class="sxs-lookup"><span data-stu-id="8edb6-119">Queued sessions require a transaction to exhibit this pattern.</span></span>  
  
 <span data-ttu-id="8edb6-120">En el ejemplo, el cliente envía varios mensajes al servicio como parte de una sesión dentro del ámbito de una transacción única.</span><span class="sxs-lookup"><span data-stu-id="8edb6-120">In the sample, the client sends a number of messages to the service as part of a session within the scope of a single transaction.</span></span>  
  
 <span data-ttu-id="8edb6-121">El contrato de servicio es `IOrderTaker`, que define un servicio unidireccional que es adecuado para usarse con colas.</span><span class="sxs-lookup"><span data-stu-id="8edb6-121">The service contract is `IOrderTaker`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="8edb6-122"><xref:System.ServiceModel.SessionMode> utilizado en el contrato mostrado en el código de ejemplo siguiente indica que los mensajes forman parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8edb6-122">The <xref:System.ServiceModel.SessionMode> used in the contract shown in the following sample code indicates that the messages are part of the session.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 <span data-ttu-id="8edb6-123">El servicio define las operaciones de servicio de tal manera que la primera operación da de alta en una transacción pero no la completa.</span><span class="sxs-lookup"><span data-stu-id="8edb6-123">The service defines service operations in such a way that the first operation enlists in a transaction but does not automatically complete the transaction.</span></span> <span data-ttu-id="8edb6-124">Las operaciones subsiguientes también dan de alta en la misma transacción pero no se completan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-124">Subsequent operations also enlist in the same transaction but do not automatically complete.</span></span> <span data-ttu-id="8edb6-125">La última operación en la sesión completa automáticamente la transacción.</span><span class="sxs-lookup"><span data-stu-id="8edb6-125">The last operation in the session automatically completes the transaction.</span></span> <span data-ttu-id="8edb6-126">Así, se utiliza la misma transacción para varias invocaciones de la operación en el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="8edb6-126">Thus, the same transaction is used for several operation invocations in the service contract.</span></span> <span data-ttu-id="8edb6-127">Si cualquiera de las operaciones produce una excepción, a continuación, la transacción se revierte y la sesión se pone de nuevo en la cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-127">If any of the operations throw an exception, then the transaction rolls back and the session is put back into the queue.</span></span> <span data-ttu-id="8edb6-128">En la realización correcta de la última operación, la transacción se confirma.</span><span class="sxs-lookup"><span data-stu-id="8edb6-128">Upon successful completion of the last operation, the transaction is committed.</span></span> <span data-ttu-id="8edb6-129">El servicio utiliza `PerSession` como <xref:System.ServiceModel.InstanceContextMode> para recibir todos los mensajes en una sesión en la misma instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="8edb6-129">The service uses `PerSession` as the <xref:System.ServiceModel.InstanceContextMode> to receive all messages in a session on the same instance of the service.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +   
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 <span data-ttu-id="8edb6-130">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="8edb6-130">The service is self hosted.</span></span> <span data-ttu-id="8edb6-131">Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano.</span><span class="sxs-lookup"><span data-stu-id="8edb6-131">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="8edb6-132">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="8edb6-132">This can be done manually or through code.</span></span> <span data-ttu-id="8edb6-133">En este ejemplo, el servicio contiene el código <xref:System.Messaging> para comprobar la existencia de la cola y la crea, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="8edb6-133">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="8edb6-134">El nombre de la cola se lee del archivo de configuración utilizando la clase <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="8edb6-134">The queue name is read from the configuration file using the <xref:System.Configuration.ConfigurationManager.AppSettings%2A> class.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();   
    }  
}  
```

 <span data-ttu-id="8edb6-135">El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8edb6-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="8edb6-136">El extremo para el servicio se define en la sección system.ServiceModel del archivo de configuración y especifica el enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="8edb6-136">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
<system.serviceModel>  
```  
  
 <span data-ttu-id="8edb6-137">El cliente crea un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="8edb6-137">The client creates a transaction scope.</span></span> <span data-ttu-id="8edb6-138">Se envían todos los mensajes en la sesión a la cola dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde todos los mensajes son correctos o se producen errores.</span><span class="sxs-lookup"><span data-stu-id="8edb6-138">All messages in the session are sent to the queue within the transaction scope, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="8edb6-139">La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="8edb6-139">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A>.</span></span>  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();                  
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> <span data-ttu-id="8edb6-140">Puede utilizar solo una transacción única para todos los mensajes en la sesión y deben enviarse todos los mensajes en la sesión antes de confirmar la transacción.</span><span class="sxs-lookup"><span data-stu-id="8edb6-140">You can use only a single transaction for all messages in the session and all messages in the session must be sent before committing the transaction.</span></span> <span data-ttu-id="8edb6-141">Al cerrar el cliente, se cierra la sesión.</span><span class="sxs-lookup"><span data-stu-id="8edb6-141">Closing the client closes the session.</span></span> <span data-ttu-id="8edb6-142">Por consiguiente, el cliente tiene que estar cerrado antes de que la transacción se complete para enviar todos los mensajes de la sesión a la cola.</span><span class="sxs-lookup"><span data-stu-id="8edb6-142">Therefore, the client has to be closed before the transaction is completed to send all messages in the session to the queue.</span></span>  
  
 <span data-ttu-id="8edb6-143">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="8edb6-143">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8edb6-144">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-144">You can see the service receive messages from the client.</span></span> <span data-ttu-id="8edb6-145">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-145">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="8edb6-146">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-146">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="8edb6-147">Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="8edb6-147">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>  
  
 <span data-ttu-id="8edb6-148">En el cliente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-148">On the client.</span></span>  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="8edb6-149">En el servicio.</span><span class="sxs-lookup"><span data-stu-id="8edb6-149">On the service.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8edb6-150">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8edb6-150">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8edb6-151">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8edb6-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8edb6-152">Para C#compilar C++, o Visual Basic edición .net de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8edb6-152">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="8edb6-153">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8edb6-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="8edb6-154">De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8edb6-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="8edb6-155">Hay dos propiedades pertinentes para la seguridad de transporte de MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` de forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="8edb6-155">There are two relevant properties for MSMQ transport security namely, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="8edb6-156">Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8edb6-156">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="8edb6-157">Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="8edb6-157">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="8edb6-158">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory</span><span class="sxs-lookup"><span data-stu-id="8edb6-158">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="8edb6-159">Si su equipo no es parte de un dominio o no tiene instalada la integración del directorio activo, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8edb6-159">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->      
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
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
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="8edb6-160">Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8edb6-160">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8edb6-161">Establecer el modo de seguridad en `None` es equivalente a establecer la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="8edb6-161">Setting security mode to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
