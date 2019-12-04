---
title: Dúplex
ms.date: 03/30/2017
helpviewer_keywords:
- Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
ms.openlocfilehash: 64036a1314bc3f60023cdc555fa1eaece7c687c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715142"
---
# <a name="duplex"></a><span data-ttu-id="5ba64-102">Dúplex</span><span class="sxs-lookup"><span data-stu-id="5ba64-102">Duplex</span></span>

<span data-ttu-id="5ba64-103">El ejemplo Dúplex muestra cómo definir e implementar un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="5ba64-103">The Duplex sample demonstrates how to define and implement a duplex contract.</span></span> <span data-ttu-id="5ba64-104">La comunicación dúplex se produce cuando un cliente establece una sesión con un servicio y da al servicio un canal en el que el servicio puede devolver los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ba64-104">Duplex communication occurs when a client establishes a session with a service and gives the service a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="5ba64-105">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5ba64-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="5ba64-106">Un contrato dúplex se define como un par de interfaces, una interfaz principal del cliente al servicio y una interfaz de devolución de llamada del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ba64-106">A duplex contract is defined as a pair of interfaces—a primary interface from the client to the service and a callback interface from the service to the client.</span></span> <span data-ttu-id="5ba64-107">En este ejemplo, la interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones matemáticas, calculando el resultado sobre una sesión.</span><span class="sxs-lookup"><span data-stu-id="5ba64-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating the result over a session.</span></span> <span data-ttu-id="5ba64-108">El servicio devuelve los resultados en la interfaz `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="5ba64-108">The service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="5ba64-109">Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span>

> [!NOTE]
> <span data-ttu-id="5ba64-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="5ba64-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="5ba64-111">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="5ba64-112">El contrato dúplex se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="5ba64-112">The duplex contract is defined as follows:</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,
                 CallbackContract=typeof(ICalculatorDuplexCallback))]
public interface ICalculatorDuplex
{
    [OperationContract(IsOneWay = true)]
    void Clear();
    [OperationContract(IsOneWay = true)]
    void AddTo(double n);
    [OperationContract(IsOneWay = true)]
    void SubtractFrom(double n);
    [OperationContract(IsOneWay = true)]
    void MultiplyBy(double n);
    [OperationContract(IsOneWay = true)]
    void DivideBy(double n);
}

public interface ICalculatorDuplexCallback
{
    [OperationContract(IsOneWay = true)]
    void Result(double result);
    [OperationContract(IsOneWay = true)]
    void Equation(string eqn);
}
```

<span data-ttu-id="5ba64-113">La clase `CalculatorService` implementa la interfaz principal `ICalculatorDuplex`.</span><span class="sxs-lookup"><span data-stu-id="5ba64-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="5ba64-114">El servicio utiliza el modo de instancia <xref:System.ServiceModel.InstanceContextMode.PerSession> para mantener el resultado para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="5ba64-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="5ba64-115">Una propiedad privada denominada `Callback` se utiliza para tener acceso al canal de devolución de llamadas hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="5ba64-115">A private property named `Callback` is used to access the callback channel to the client.</span></span> <span data-ttu-id="5ba64-116">El servicio utiliza la devolución de llamada para devolver los mensajes al cliente a través de la interfaz de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5ba64-116">The service uses the callback for sending messages back to the client through the callback interface.</span></span>

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorDuplex
{
    double result = 0.0D;
    string equation;

    public CalculatorService()
    {
        equation = result.ToString();
    }

    public void Clear()
    {
        Callback.Equation($"{equation} = {result}");
        equation = result.ToString();
    }

    public void AddTo(double n)
    {
        result += n;
        equation += $" + {n}";
        Callback.Result(result);
    }

    //...

    ICalculatorDuplexCallback Callback
    {
        get
        {
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();
        }
    }
}
```

<span data-ttu-id="5ba64-117">El cliente debe proporcionar una clase que implemente la interfaz de devolución de llamadas del contrato dúplex para recibir los mensajes del servicio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="5ba64-118">En el ejemplo, una clase `CallbackHandler` se define para implementar la interfaz `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="5ba64-118">In the sample, a `CallbackHandler` class is defined to implement the `ICalculatorDuplexCallback` interface.</span></span>

```csharp
public class CallbackHandler : ICalculatorDuplexCallback
{
   public void Result(double result)
   {
      Console.WriteLine("Result({0})", result);
   }

   public void Equation(string equation)
   {
      Console.WriteLine("Equation({0}", equation);
   }
}
```

<span data-ttu-id="5ba64-119">El proxy que se genera para un contrato dúplex requiere que se proporcione un<xref:System.ServiceModel.InstanceContext> en la construcción.</span><span class="sxs-lookup"><span data-stu-id="5ba64-119">The proxy that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> to be provided upon construction.</span></span> <span data-ttu-id="5ba64-120">Esta <xref:System.ServiceModel.InstanceContext> se utiliza como sitio para un objeto que implementa la interfaz de devolución de llamadas y administra mensajes que se devuelven desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-120">This <xref:System.ServiceModel.InstanceContext> is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="5ba64-121">Se construye un<xref:System.ServiceModel.InstanceContext> con una instancia de la clase `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="5ba64-121">An <xref:System.ServiceModel.InstanceContext> is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="5ba64-122">Este objeto administra mensajes enviados desde el servicio al cliente en la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5ba64-122">This object handles messages sent from the service to the client on the callback interface.</span></span>

```csharp
// Construct InstanceContext to handle messages on callback interface.
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());

// Create a client.
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);

Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");
Console.WriteLine();

// Call the AddTo service operation.
double value = 100.00D;
client.AddTo(value);

// Call the SubtractFrom service operation.
value = 50.00D;
client.SubtractFrom(value);

// Call the MultiplyBy service operation.
value = 17.65D;
client.MultiplyBy(value);

// Call the DivideBy service operation.
value = 2.00D;
client.DivideBy(value);

// Complete equation.
client.Clear();

Console.ReadLine();

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();
```

<span data-ttu-id="5ba64-123">La configuración del servicio se ha modificado para proporcionar un enlace que admita comunicación de la sesión y comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="5ba64-123">The configuration has been modified to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="5ba64-124">El elemento `wsDualHttpBinding` admite la comunicación de la sesión y permite la comunicación dúplex proporcionando conexiones HTTP duales, una para cada dirección.</span><span class="sxs-lookup"><span data-stu-id="5ba64-124">The `wsDualHttpBinding` supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span> <span data-ttu-id="5ba64-125">En el servicio, la única diferencia en configuración es el enlace que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5ba64-125">On the service, the only difference in configuration is the binding that is used.</span></span> <span data-ttu-id="5ba64-126">En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ba64-126">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>

```xml
<client>
  <endpoint name=""
            address="http://localhost/servicemodelsamples/service.svc"
            binding="wsDualHttpBinding"
            bindingConfiguration="DuplexBinding"
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
</client>

<bindings>
  <!-- Configure a binding that support duplex communication. -->
  <wsDualHttpBinding>
    <binding name="DuplexBinding"
             clientBaseAddress="http://localhost:8000/myClient/">
    </binding>
  </wsDualHttpBinding>
</bindings>
```

<span data-ttu-id="5ba64-127">Al ejecutar el ejemplo, se ven los mensajes que se devuelven al cliente en la interfaz de devolución de llamada que se envía desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-127">When you run the sample, you see the messages that are returned to the client on the callback interface that is sent from the service.</span></span> <span data-ttu-id="5ba64-128">Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="5ba64-128">Each intermediate result is displayed, followed by the entire equation upon the completion of all operations.</span></span> <span data-ttu-id="5ba64-129">Presione Entrar para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="5ba64-129">Press ENTER to shut down the client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5ba64-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ba64-130">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5ba64-131">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ba64-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="5ba64-132">Para C#compilar C++, o Visual Basic edición .net de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ba64-132">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="5ba64-133">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ba64-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5ba64-134">Al ejecutar el cliente en una configuración de equipo cruzado, asegúrese de reemplazar "localhost" en el atributo `address` del [\<extremo de \<elemento > cliente](../../configure-apps/file-schema/wcf/endpoint-of-client.md) y el atributo `clientBaseAddress` del elemento\<[enlace](../../configure-apps/file-schema/wcf/bindings.md) > del elemento\<[wsDualHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) > por el nombre del equipo adecuado, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="5ba64-134">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown in the following:</span></span>

    ```xml
    <client>
        <endpoint name = ""
        address="http://service_machine_name/servicemodelsamples/service.svc"
        ... />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```

> [!IMPORTANT]
> <span data-ttu-id="5ba64-135">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5ba64-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5ba64-136">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5ba64-136">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5ba64-137">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ba64-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5ba64-138">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5ba64-138">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`
