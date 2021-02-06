---
description: 'Más información acerca de: imperativo'
title: Imperativo
ms.date: 03/30/2017
ms.assetid: 4f7ce807-c0e4-407a-92a6-22abafb40b51
ms.openlocfilehash: ceaaf6d2bb196a50c0a9a096e39f9b6f78d63a11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631845"
---
# <a name="imperative"></a><span data-ttu-id="6f3a8-103">Imperativo</span><span class="sxs-lookup"><span data-stu-id="6f3a8-103">Imperative</span></span>

<span data-ttu-id="6f3a8-104">Este ejemplo muestra cómo definir un <xref:System.ServiceModel.WSHttpBinding> para un servicio que usa el código, en lugar de definir el enlace `wsHttpBinding` en la configuración.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-104">This sample demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span> <span data-ttu-id="6f3a8-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>

> [!NOTE]
> <span data-ttu-id="6f3a8-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="6f3a8-107">El código siguiente muestra cómo definir un enlace en el código de forma imperativa.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-107">The following code demonstrates how to define a binding imperatively in code.</span></span>

```csharp
public static void Main()
{
    WSHttpBinding binding = new WSHttpBinding();
    binding.Name = "binding1";
    binding.HostNameComparisonMode =
        HostNameComparisonMode.StrongWildcard;
    binding.Security.Mode = SecurityMode.Message;
    binding.ReliableSession.Enabled = false;
    binding.TransactionFlow = false;

    Uri baseAddress =
        new Uri("http://localhost:8000/servicemodelsamples/service");

    // Create a ServiceHost for the CalculatorService type and provide the base address.
    using(ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
    {
        serviceHost.AddServiceEndpoint(typeof(ICalculator),
                                       binding, baseAddress);
        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
        // Close the ServiceHostBase to shutdown the service.
        serviceHost.Close();
    }
}
```

 <span data-ttu-id="6f3a8-108">El cliente crea un canal para comunicarse con el servicio tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-108">The client creates a channel to communicate with the service as shown in the following sample code.</span></span>

```csharp
WSHttpBinding binding = new WSHttpBinding();
binding.Name = "binding1";
binding.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;
binding.Security.Mode = SecurityMode.Message;
binding.ReliableSession.Enabled = false;
binding.TransactionFlow = false;

String url = "http://localhost:8000/servicemodelsamples/service";
EndpointAddress address = new EndpointAddress(url);
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding,address);
ICalculator channel = channelFactory.CreateChannel();
```

 <span data-ttu-id="6f3a8-109">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-109">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6f3a8-110">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-110">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6f3a8-111">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f3a8-111">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="6f3a8-112">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6f3a8-112">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="6f3a8-113">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6f3a8-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="6f3a8-114">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6f3a8-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f3a8-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6f3a8-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-116">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6f3a8-117">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6f3a8-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6f3a8-118">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Imperative`
