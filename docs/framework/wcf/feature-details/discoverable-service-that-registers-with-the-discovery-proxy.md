---
description: 'Más información acerca de cómo: implementar un servicio reconocible que se registra con el proxy de detección'
title: Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección
ms.date: 03/30/2017
ms.assetid: eb275bc1-535b-44c8-b9f3-0b75e9aa473b
ms.openlocfilehash: 71991de6b7fd0180d4f87c2bfc48e99dc398fa53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802962"
---
# <a name="how-to-implement-a-discoverable-service-that-registers-with-the-discovery-proxy"></a><span data-ttu-id="36837-103">Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36837-103">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>

<span data-ttu-id="36837-104">Este tema es el segundo de cuatro temas que describe cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36837-104">This topic is the second of four topics that discusses how to implement a discovery proxy.</span></span> <span data-ttu-id="36837-105">En el tema anterior, [Cómo: implementar un proxy de detección](how-to-implement-a-discovery-proxy.md), ha implementado un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36837-105">In the previous topic, [How to: Implement a Discovery Proxy](how-to-implement-a-discovery-proxy.md), you implemented a discovery proxy.</span></span> <span data-ttu-id="36837-106">En este tema, creará un servicio WCF que envía mensajes de anuncio ( `Hello` y `Bye` ) al proxy de detección, lo que hace que se registre y anule su registro con el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36837-106">In this topic, you create a WCF service that sends announcement messages (`Hello` and `Bye`) to the discovery proxy, causing it to register and unregister itself with the discovery proxy.</span></span>

### <a name="to-define-the-service-contract"></a><span data-ttu-id="36837-107">Para definir el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="36837-107">To define the service contract</span></span>

1. <span data-ttu-id="36837-108">Agregue un nuevo proyecto de aplicación de consola a la solución `DiscoveryProxyExample` denominada `Service`.</span><span class="sxs-lookup"><span data-stu-id="36837-108">Add a new console application project to the `DiscoveryProxyExample` solution called `Service`.</span></span>

2. <span data-ttu-id="36837-109">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="36837-109">Add references to the following assemblies:</span></span>

    1. <span data-ttu-id="36837-110">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="36837-110">System.ServiceModel</span></span>

    2. <span data-ttu-id="36837-111">System.ServiceModel.Discovery</span><span class="sxs-lookup"><span data-stu-id="36837-111">System.ServiceModel.Discovery</span></span>

3. <span data-ttu-id="36837-112">Agregue una nueva clase al proyecto `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="36837-112">Add a new class to the project called `CalculatorService`.</span></span>

4. <span data-ttu-id="36837-113">Agregue las siguientes instrucciones de uso.</span><span class="sxs-lookup"><span data-stu-id="36837-113">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    ```

5. <span data-ttu-id="36837-114">Dentro de CalculatorService.cs, defina el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="36837-114">Within CalculatorService.cs, define the service contract.</span></span>

    ```csharp
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }
    ```

6. <span data-ttu-id="36837-115">También dentro de CalculatorService.cs, implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="36837-115">Also within CalculatorService.cs, implement the service contract.</span></span>

    ```csharp
    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
    ```

### <a name="to-host-the-service"></a><span data-ttu-id="36837-116">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="36837-116">To host the service</span></span>

1. <span data-ttu-id="36837-117">Abra el archivo Program.cs que se generó cuando creó el proyecto.</span><span class="sxs-lookup"><span data-stu-id="36837-117">Open the Program.cs file that was generated when you created the project.</span></span>

2. <span data-ttu-id="36837-118">Agregue las siguientes instrucciones de uso.</span><span class="sxs-lookup"><span data-stu-id="36837-118">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using System.ServiceModel.Discovery;
    ```

3. <span data-ttu-id="36837-119">Agregue el código siguiente en el método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="36837-119">Within the `Main()` method, add the following code:</span></span>

    ```csharp
    // Define the base address of the service
    Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
    // Define the endpoint address where announcement messages will be sent
    Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

    // Create the service host
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
    try
    {
        // Add a service endpoint
        ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
            new NetTcpBinding(), string.Empty);

        // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
        AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
            new EndpointAddress(announcementEndpointAddress));

        // Create a ServiceDiscoveryBehavior and add the announcement endpoint
        ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
        serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

        // Add the ServiceDiscoveryBehavior to the service host to make the service discoverable
        serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

        // Start listening for messages
        serviceHost.Open();

        Console.WriteLine("Calculator Service started at {0}", baseAddress);
        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate the service.");
        Console.WriteLine();
        Console.ReadLine();

        serviceHost.Close();
    }
    catch (CommunicationException e)
    {
        Console.WriteLine(e.Message);
    }
    catch (TimeoutException e)
    {
        Console.WriteLine(e.Message);
    }

    if (serviceHost.State != CommunicationState.Closed)
    {
        Console.WriteLine("Aborting the service...");
        serviceHost.Abort();
    }
    ```

<span data-ttu-id="36837-120">Ha completado la implementación de un servicio que se puede detectar.</span><span class="sxs-lookup"><span data-stu-id="36837-120">You have completed implementing a discoverable service.</span></span> <span data-ttu-id="36837-121">Continúe con [el procedimiento para implementar una aplicación cliente que use el proxy de detección para buscar un servicio](client-app-discovery-proxy-to-find-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="36837-121">Continue on to [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md).</span></span>

## <a name="example"></a><span data-ttu-id="36837-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36837-122">Example</span></span>

 <span data-ttu-id="36837-123">Esta es la lista completa del código empleado en este tema.</span><span class="sxs-lookup"><span data-stu-id="36837-123">This is the full listing of the code used in this topic.</span></span>

```csharp
// CalculatorService.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;

namespace Microsoft.Samples.Discovery
{
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }

    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
  
        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```csharp
// Program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
            try
            {
                ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
                    new NetTcpBinding(), string.Empty);

                // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
                    new EndpointAddress(announcementEndpointAddress));

                ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
                serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

                // Make the service discoverable
                serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

                serviceHost.Open();

                Console.WriteLine("Calculator Service started at {0}", baseAddress);
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                serviceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (serviceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                serviceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="36837-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="36837-124">See also</span></span>

- [<span data-ttu-id="36837-125">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="36837-125">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="36837-126">Procedimiento para implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36837-126">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="36837-127">Procedimiento para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="36837-127">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
