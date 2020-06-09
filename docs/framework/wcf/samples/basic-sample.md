---
title: Ejemplo básico
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: db560ec7dea3912ecec8d84943cc9a01512d1f33
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575776"
---
# <a name="basic-sample"></a><span data-ttu-id="e86c4-102">Ejemplo básico</span><span class="sxs-lookup"><span data-stu-id="e86c4-102">Basic Sample</span></span>

<span data-ttu-id="e86c4-103">En este ejemplo se muestra cómo hacer que un servicio se pueda detectar y cómo buscar y llamar a un servicio detectable.</span><span class="sxs-lookup"><span data-stu-id="e86c4-103">This sample shows how to make a service discoverable and how to search for and call a discoverable service.</span></span> <span data-ttu-id="e86c4-104">Este ejemplo se compone de dos proyectos: servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="e86c4-104">This sample is composed of two projects: service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="e86c4-105">En él se implementa la detección en el código.</span><span class="sxs-lookup"><span data-stu-id="e86c4-105">This sample implements discovery in code.</span></span>  <span data-ttu-id="e86c4-106">Para obtener un ejemplo que implementa la detección en la configuración, vea [Configuration (configuración](configuration-sample.md)).</span><span class="sxs-lookup"><span data-stu-id="e86c4-106">For a sample that implements discovery in configuration, see [Configuration](configuration-sample.md).</span></span>

## <a name="service"></a><span data-ttu-id="e86c4-107">web de Office</span><span class="sxs-lookup"><span data-stu-id="e86c4-107">Service</span></span>

<span data-ttu-id="e86c4-108">Se trata de la implementación de un servicio de calculadora sencillo.</span><span class="sxs-lookup"><span data-stu-id="e86c4-108">This is a simple calculator service implementation.</span></span> <span data-ttu-id="e86c4-109">El código relacionado con la detección se puede encontrar en `Main` donde un objeto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> se agrega al host del servicio y un objeto <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> se agrega como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="e86c4-109">The discovery related code can be found in `Main` where a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is added to the service host and a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is added as shown in the following code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new
      WSHttpBinding(), String.Empty);

    // Make the service discoverable over UDP multicast
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    serviceHost.Open();
    // ...
}
```

## <a name="client"></a><span data-ttu-id="e86c4-110">Cliente</span><span class="sxs-lookup"><span data-stu-id="e86c4-110">Client</span></span>

<span data-ttu-id="e86c4-111">El cliente usa un objeto <xref:System.ServiceModel.Discovery.DynamicEndpoint> para localizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e86c4-111">The client uses a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to locate the service.</span></span> <span data-ttu-id="e86c4-112">El <xref:System.ServiceModel.Discovery.DynamicEndpoint>, un extremo estándar, resuelve el extremo del servicio cuando se abre el cliente.</span><span class="sxs-lookup"><span data-stu-id="e86c4-112">The <xref:System.ServiceModel.Discovery.DynamicEndpoint>, a standard endpoint, resolves the endpoint of the service when the client is opened.</span></span> <span data-ttu-id="e86c4-113">En este caso, el <xref:System.ServiceModel.Discovery.DynamicEndpoint> busca el servicio según el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="e86c4-113">In this case, the <xref:System.ServiceModel.Discovery.DynamicEndpoint> looks for the service based on the service contract.</span></span> <span data-ttu-id="e86c4-114">El <xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la búsqueda a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e86c4-114">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> conducts the search over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> by default.</span></span> <span data-ttu-id="e86c4-115">Cuando localiza un punto de conexión de servicio, el cliente se conecta a ese servicio a través del enlace especificado.</span><span class="sxs-lookup"><span data-stu-id="e86c4-115">Once it locates a service endpoint, the client connects to that service over the specified binding.</span></span>

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

<span data-ttu-id="e86c4-116">El cliente define un método denominado `InvokeCalculatorService` que utiliza la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="e86c4-116">The client defines a method called `InvokeCalculatorService` that uses the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to search for services.</span></span> <span data-ttu-id="e86c4-117"><xref:System.ServiceModel.Discovery.DynamicEndpoint> hereda de <xref:System.ServiceModel.Description.ServiceEndpoint>, de modo que se pueda pasar al método `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="e86c4-117">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> inherits from <xref:System.ServiceModel.Description.ServiceEndpoint>, so it can be passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="e86c4-118">A continuación, el ejemplo utiliza <xref:System.ServiceModel.Discovery.DynamicEndpoint> para crear una instancia de `CalculatorServiceClient` y llama a diversas operaciones del servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="e86c4-118">The example then uses the <xref:System.ServiceModel.Discovery.DynamicEndpoint> to create an instance of `CalculatorServiceClient` and calls the various operations of the calculator service.</span></span>

```csharp
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)
{
   // Create a client
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);

   Console.WriteLine("Invoking CalculatorService");
   Console.WriteLine();

   double value1 = 100.00D;
   double value2 = 15.99D;

   // Call the Add service operation.
   double result = client.Add(value1, value2);
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

   // Call the Subtract service operation.
   result = client.Subtract(value1, value2);
   Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

   // Call the Multiply service operation.
   result = client.Multiply(value1, value2);
   Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

   // Call the Divide service operation.
   result = client.Divide(value1, value2);
   Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
   Console.WriteLine();

   //Closing the client gracefully closes the connection and cleans up resources
   client.Close();
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="e86c4-119">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e86c4-119">To use this sample</span></span>

1. <span data-ttu-id="e86c4-120">Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="e86c4-120">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="e86c4-121">Para obtener más información, consulte [configuración de http y https](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="e86c4-121">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="e86c4-122">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="e86c4-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="e86c4-123">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="e86c4-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="e86c4-124">Con Visual Studio 2012, abra Basic. sln y compile el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e86c4-124">Using Visual Studio 2012, open the Basic.sln and build the sample.</span></span>

3. <span data-ttu-id="e86c4-125">Ejecute la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="e86c4-125">Run the service.exe application.</span></span>

4. <span data-ttu-id="e86c4-126">Después de que se inicie el servicio, ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="e86c4-126">After the service has started, run the client.exe.</span></span>

5. <span data-ttu-id="e86c4-127">Observe que el cliente pudo encontrar el servicio sin conocer su dirección.</span><span class="sxs-lookup"><span data-stu-id="e86c4-127">Observe that the client was able to find the service without knowing its address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e86c4-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e86c4-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e86c4-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e86c4-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e86c4-130">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e86c4-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e86c4-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e86c4-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
