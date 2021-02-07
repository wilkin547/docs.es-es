---
description: 'Más información sobre: comunicación en cola volátil'
title: Comunicación en cola volátil
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: 8ced65dc28719416fb9b1059d2be8f29315013b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755725"
---
# <a name="volatile-queued-communication"></a><span data-ttu-id="3eafc-103">Comunicación en cola volátil</span><span class="sxs-lookup"><span data-stu-id="3eafc-103">Volatile Queued Communication</span></span>

<span data-ttu-id="3eafc-104">Este ejemplo muestra cómo realizar la comunicación en cola volátil sobre el transporte de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="3eafc-104">This sample demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="3eafc-105">Este ejemplo utiliza <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="3eafc-105">This sample uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="3eafc-106">El servicio en este caso es una aplicación de consola hospedada a sí misma que le permite observar el servicio que recibe los mensajes en cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-106">The service in this case is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="3eafc-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="3eafc-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="3eafc-108">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-108">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="3eafc-109">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-109">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="3eafc-110">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-110">The service receives messages from the queue.</span></span> <span data-ttu-id="3eafc-111">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-111">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="3eafc-112">Al enviar un mensaje sin garantías, MSMQ solo realiza un esfuerzo para entregar el mensaje, a diferencia de las garantías de tipo "exactamente una vez" donde MSMQ garantiza que se entrega el mensaje o, si no se puede, le informa de que el mensaje no puede entregarse.</span><span class="sxs-lookup"><span data-stu-id="3eafc-112">When you send a message with no assurances, MSMQ only makes a best effort to deliver the message, unlike with Exactly Once assurances where MSMQ ensures that the message gets delivered or, if it cannot be delivered, lets you know that the message cannot be delivered.</span></span>

<span data-ttu-id="3eafc-113">En ciertos escenarios, puede desear enviar un mensaje volátil sin garantías sobre una cola, cuando una entrega a tiempo es más importante que perder los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3eafc-113">In certain scenarios, you may want to send a volatile message with no assurances over a queue, when timely delivery is more important than losing messages.</span></span> <span data-ttu-id="3eafc-114">Los mensajes volátiles no sobreviven a los bloqueos del administrador de la cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-114">Volatile messages do not survive queue manager crashes.</span></span> <span data-ttu-id="3eafc-115">Por consiguiente, si el administrador de cola se bloquea, la cola no transaccional utilizada para almacenar los mensajes volátiles sobrevive pero los mensajes no porque no están almacenados en el disco.</span><span class="sxs-lookup"><span data-stu-id="3eafc-115">Therefore if the queue manager crashes, the non-transactional queue used to store volatile messages survives but the messages themselves do not because the messages are not stored on the disk.</span></span>

> [!NOTE]
> <span data-ttu-id="3eafc-116">No puede enviar mensajes volátiles sin garantías dentro del ámbito de una transacción utilizando MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3eafc-116">You cannot send volatile messages with no assurances within the scope of a transaction using MSMQ.</span></span> <span data-ttu-id="3eafc-117">También debe crear una cola no transaccional para enviar mensajes volátiles.</span><span class="sxs-lookup"><span data-stu-id="3eafc-117">You also must create a non-transactional queue to send volatile messages.</span></span>

<span data-ttu-id="3eafc-118">El contrato de servicios en este ejemplo es `IStockTicker` que define servicios unidireccionales que se adaptan mejor a su uso con la cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-118">The service contract in this sample is `IStockTicker` that defines one-way services that are best suited for use with queuing.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

<span data-ttu-id="3eafc-119">La operación de servicio muestra el símbolo y precios del tablero de cotizaciones, tal y como se muestra en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3eafc-119">The service operation displays the stock ticker symbol and price, as shown in the following sample code:</span></span>

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

<span data-ttu-id="3eafc-120">El servicio se hospeda en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="3eafc-120">The service is self hosted.</span></span> <span data-ttu-id="3eafc-121">Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano.</span><span class="sxs-lookup"><span data-stu-id="3eafc-121">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="3eafc-122">Esto se puede hacer manualmente o a través de código.</span><span class="sxs-lookup"><span data-stu-id="3eafc-122">This can be done manually or through code.</span></span> <span data-ttu-id="3eafc-123">En este ejemplo, el servicio contiene el código para comprobar la existencia de la cola y crearla si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="3eafc-123">In this sample, the service contains code to check for the existence of the queue and create it if required.</span></span> <span data-ttu-id="3eafc-124">El nombre de la cola se lee del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3eafc-124">The queue name is read from the configuration file.</span></span> <span data-ttu-id="3eafc-125">La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) utiliza la dirección base para generar el proxy para el servicio.</span><span class="sxs-lookup"><span data-stu-id="3eafc-125">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy for the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
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

<span data-ttu-id="3eafc-126">El nombre de cola de MSMQ se especifica en la sección appSettings del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3eafc-126">The MSMQ queue name is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="3eafc-127">El extremo para el servicio se define en la sección system.ServiceModel del archivo de configuración y especifica el enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="3eafc-127">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>

> [!NOTE]
> <span data-ttu-id="3eafc-128">El nombre de la cola usa un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso al crear una cola mediante <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="3eafc-128">The queue name uses a dot (.) for the local machine and backslash separators in its path when creating a queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="3eafc-129">La dirección del punto de conexión de Windows Communication Foundation (WCF) especifica un esquema net. MSMQ:, usa el "localhost" para el equipo local y las barras diagonales en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3eafc-129">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine and forward slashes in its path.</span></span>

<span data-ttu-id="3eafc-130">Las garantías y duración o la volatilidad de los mensajes también se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="3eafc-130">The assurances and durability or volatility of messages are also specified in the configuration.</span></span>

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

<span data-ttu-id="3eafc-131">Dado que el ejemplo envía los mensajes en cola utilizando una cola no transaccional, los mensajes con transacciones no se pueden enviar a la cola.</span><span class="sxs-lookup"><span data-stu-id="3eafc-131">Because the sample sends queued messages by using a non-transactional queue, transacted messages cannot be sent to the queue.</span></span>

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

<span data-ttu-id="3eafc-132">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="3eafc-132">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="3eafc-133">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="3eafc-133">You can see the service receive messages from the client.</span></span> <span data-ttu-id="3eafc-134">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="3eafc-134">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="3eafc-135">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="3eafc-135">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="3eafc-136">Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="3eafc-136">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3eafc-137">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3eafc-137">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3eafc-138">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3eafc-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3eafc-139">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3eafc-139">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="3eafc-140">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3eafc-140">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

<span data-ttu-id="3eafc-141">De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="3eafc-141">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="3eafc-142">Hay dos propiedades pertinentes para la seguridad de transporte de MSMQ y, de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign` .</span><span class="sxs-lookup"><span data-stu-id="3eafc-142">There are two pertinent properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="3eafc-143">Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3eafc-143">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="3eafc-144">Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="3eafc-144">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="3eafc-145">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory</span><span class="sxs-lookup"><span data-stu-id="3eafc-145">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>

1. <span data-ttu-id="3eafc-146">Si su equipo no es parte de un dominio o no tiene la integración del directorio activo instalada, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en el código de configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3eafc-146">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code:</span></span>

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="3eafc-147">Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3eafc-147">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3eafc-148">Establecer `security mode` en `None` es equivalente a definir la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="3eafc-148">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3eafc-149">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3eafc-149">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3eafc-150">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3eafc-150">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3eafc-151">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3eafc-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3eafc-152">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="3eafc-152">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
