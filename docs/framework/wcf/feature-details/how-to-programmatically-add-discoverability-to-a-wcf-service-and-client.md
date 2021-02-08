---
description: 'Más información sobre: Cómo: agregar detectabilidad a un servicio y un cliente WCF mediante programación'
title: Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: ad192c6fcc57a36d7001f230c98b1193c42262aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793719"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="ef43f-103">Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="ef43f-103">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>

<span data-ttu-id="ef43f-104">En este tema se explica cómo hacer que un servicio de Windows Communication Foundation (WCF) sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="ef43f-104">This topic explains how to make a Windows Communication Foundation (WCF) service discoverable.</span></span> <span data-ttu-id="ef43f-105">Se basa en el ejemplo de [host propio](../samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="ef43f-105">It is based on the [Self-Host](../samples/self-host.md) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="ef43f-106">Para configurar el ejemplo de servicio de host automático existente repara para la detección</span><span class="sxs-lookup"><span data-stu-id="ef43f-106">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1. <span data-ttu-id="ef43f-107">Abra la solución Self-Host en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="ef43f-107">Open the Self-Host solution in Visual Studio 2012.</span></span> <span data-ttu-id="ef43f-108">El ejemplo se encuentra en el directorio TechnologySamples\Basic\Service\Hosting\SelfHost.</span><span class="sxs-lookup"><span data-stu-id="ef43f-108">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2. <span data-ttu-id="ef43f-109">Agregue una referencia a `System.ServiceModel.Discovery.dll` al proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="ef43f-109">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="ef43f-110">Es posible que vea un mensaje de error que indica "System.</span><span class="sxs-lookup"><span data-stu-id="ef43f-110">You may see an error message saying "System.</span></span> <span data-ttu-id="ef43f-111">ServiceModel.Discovery.dll o una de sus dependencias requiere una versión posterior del .NET Framework que la especificada en el proyecto... " Si ve este mensaje, haga clic con el botón derecho en el proyecto en el Explorador de soluciones y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef43f-111">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the .NET Framework than the one specified in the project …" If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="ef43f-112">En la ventana **propiedades del proyecto** , asegúrese de que la versión de **.NET Framework de destino** sea [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef43f-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3. <span data-ttu-id="ef43f-113">Abra el archivo Service.cs y agregue la siguiente instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. <span data-ttu-id="ef43f-114">En el método `Main()`, dentro de la instrucción `using`, agregue una instancia <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ef43f-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
  
            // ...  
        }  
    }  
    ```  
  
     <span data-ttu-id="ef43f-115">La clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> especifica que el servicio al que se aplica es reconocible.</span><span class="sxs-lookup"><span data-stu-id="ef43f-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5. <span data-ttu-id="ef43f-116">Agregue <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al host de servicio justo después del código que agrega <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ef43f-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="ef43f-117">Este código especifica que los mensajes de detección se deberían enviar al extremo de detección de UDP estándar.</span><span class="sxs-lookup"><span data-stu-id="ef43f-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="ef43f-118">Para crear una aplicación cliente que usa la detección para llamar al servicio</span><span class="sxs-lookup"><span data-stu-id="ef43f-118">To create a client application that uses discovery to call the service</span></span>  
  
1. <span data-ttu-id="ef43f-119">Agregue a la solución una aplicación de consola nueva denominada `DiscoveryClientApp`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2. <span data-ttu-id="ef43f-120">Agregue una referencia a `System.ServiceModel.dll` y `System.ServiceModel.Discovery.dll`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3. <span data-ttu-id="ef43f-121">Copie los archivos GeneratedClient.cs y App.config del proyecto de cliente existente en el nuevo proyecto DiscoveryClientApp.</span><span class="sxs-lookup"><span data-stu-id="ef43f-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="ef43f-122">Para ello, haga clic con el botón derecho en los archivos del **Explorador de soluciones**, seleccione **copiar** y, a continuación, seleccione el proyecto **DiscoveryClientApp** , haga clic con el botón derecho y seleccione **pegar**.</span><span class="sxs-lookup"><span data-stu-id="ef43f-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4. <span data-ttu-id="ef43f-123">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="ef43f-123">Open Program.cs.</span></span>  
  
5. <span data-ttu-id="ef43f-124">Agregue las siguientes instrucciones `using`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. <span data-ttu-id="ef43f-125">Agregue un método estático llamado `FindCalculatorServiceAddress()` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="ef43f-126">Este método usa la detección para buscar el servicio `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7. <span data-ttu-id="ef43f-127">Dentro del método `FindCalculatorServiceAddress`, cree una instancia <xref:System.ServiceModel.Discovery.DiscoveryClient> nueva, pasando <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al constructor.</span><span class="sxs-lookup"><span data-stu-id="ef43f-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="ef43f-128">Esto indica a WCF que la <xref:System.ServiceModel.Discovery.DiscoveryClient> clase debe usar el extremo de detección de UDP estándar para enviar y recibir mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="ef43f-128">This tells WCF that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8. <span data-ttu-id="ef43f-129">En la línea siguiente, llame al método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> y especifique una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que contenga el contrato de servicios que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="ef43f-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="ef43f-130">En este caso, especifique `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="ef43f-131">Después de la llamada a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, compruebe si hay por lo menos un servicio coincidente y devuelva la clase <xref:System.ServiceModel.EndpointAddress> del primer servicio coincidente.</span><span class="sxs-lookup"><span data-stu-id="ef43f-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="ef43f-132">De lo contrario, devuelva `null`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-132">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="ef43f-133">Agregue un método estático llamado `InvokeCalculatorService` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="ef43f-134">Este método utiliza la dirección del extremo devuelta de `FindCalculatorServiceAddress` para llamar al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="ef43f-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="ef43f-135">Dentro del método `InvokeCalculatorService`, cree una instancia de la clase `CalculatorServiceClient`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="ef43f-136">Esta clase se define mediante el ejemplo [de host propio](../samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="ef43f-136">This class is defined by the [Self-Host](../samples/self-host.md) sample.</span></span> <span data-ttu-id="ef43f-137">Se ha generado mediante Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="ef43f-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="ef43f-138">En la línea siguiente, establezca la dirección del extremo del cliente en la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="ef43f-139">Inmediatamente después del código del paso anterior, llame a los métodos expuestos por el servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="ef43f-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
    ```  
  
14. <span data-ttu-id="ef43f-140">Agregue el código al método `Main()` de la clase `Program` para llamar a `FindCalculatorServiceAddress`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="ef43f-141">En la línea siguiente, llame a `InvokeCalculatorService()` y pase la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="ef43f-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="ef43f-142">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ef43f-142">To test the application</span></span>  
  
1. <span data-ttu-id="ef43f-143">Abra un símbolo del sistema elevado y ejecute Service.exe.</span><span class="sxs-lookup"><span data-stu-id="ef43f-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2. <span data-ttu-id="ef43f-144">Abra un símbolo del sistema y ejecute Discoveryclientapp.exe.</span><span class="sxs-lookup"><span data-stu-id="ef43f-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3. <span data-ttu-id="ef43f-145">El resultado de service.exe debería ser el siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef43f-145">The output from service.exe should look like the following output.</span></span>  
  
    ```output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4. <span data-ttu-id="ef43f-146">El resultado de Discoveryclientapp.exe debería ser el siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef43f-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="ef43f-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef43f-147">Example</span></span>  

 <span data-ttu-id="ef43f-148">A continuación, se muestra una lista completa del código de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef43f-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="ef43f-149">Dado que este código se basa en el ejemplo de [host propio](../samples/self-host.md) , solo se muestran los archivos que se han modificado.</span><span class="sxs-lookup"><span data-stu-id="ef43f-149">Because this code is based on the [Self-Host](../samples/self-host.md) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="ef43f-150">Para obtener más información sobre el ejemplo de Self-Host, vea [instrucciones de configuración](../samples/set-up-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="ef43f-150">For more information about the Self-Host sample, see [Setup Instructions](../samples/set-up-instructions.md).</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="ef43f-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef43f-151">See also</span></span>

- [<span data-ttu-id="ef43f-152">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="ef43f-152">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="ef43f-153">Modelo de objetos de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="ef43f-153">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)
