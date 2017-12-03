---
title: "Cómo: Agregar detectabilidad mediante programación a un cliente y un servicio de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11d5b00113f9b44d1d77d00dd541bc602afcb405
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="5351a-102">Cómo: Agregar detectabilidad mediante programación a un cliente y un servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="5351a-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="5351a-103">En este tema, se explica cómo hacer un que un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="5351a-103">This topic explains how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span> <span data-ttu-id="5351a-104">Se basa en el [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5351a-104">It is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="5351a-105">Para configurar el ejemplo de servicio de host automático existente repara para la detección</span><span class="sxs-lookup"><span data-stu-id="5351a-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1.  <span data-ttu-id="5351a-106">Abra la solución de host automático en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5351a-106">Open the Self-Host solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="5351a-107">El ejemplo se encuentra en el directorio TechnologySamples\Basic\Service\Hosting\SelfHost.</span><span class="sxs-lookup"><span data-stu-id="5351a-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2.  <span data-ttu-id="5351a-108">Agregue una referencia a `System.ServiceModel.Discovery.dll` al proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="5351a-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="5351a-109">Verá un mensaje de error que dice "System.</span><span class="sxs-lookup"><span data-stu-id="5351a-109">You may see an error message saying "System.</span></span> <span data-ttu-id="5351a-110">ServiceModel.Discovery.dll, o una de sus dependencias requiere una versión posterior de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] a la especificada en el proyecto... "</span><span class="sxs-lookup"><span data-stu-id="5351a-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] than the one specified in the project …"</span></span> <span data-ttu-id="5351a-111">Si ve este mensaje, haga clic en el proyecto en el Explorador de soluciones y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5351a-111">If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="5351a-112">En el **propiedades del proyecto** ventana, asegúrese de que el **.NET Framework de destino** es [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5351a-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3.  <span data-ttu-id="5351a-113">Abra el archivo Service.cs y agregue la siguiente instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="5351a-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  <span data-ttu-id="5351a-114">En el método `Main()`, dentro de la instrucción `using`, agregue una instancia <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="5351a-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
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
  
     <span data-ttu-id="5351a-115">La clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> especifica que el servicio al que se aplica es reconocible.</span><span class="sxs-lookup"><span data-stu-id="5351a-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5.  <span data-ttu-id="5351a-116">Agregue <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al host de servicio justo después del código que agrega <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5351a-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="5351a-117">Este código especifica que los mensajes de detección se deberían enviar al extremo de detección de UDP estándar.</span><span class="sxs-lookup"><span data-stu-id="5351a-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="5351a-118">Para crear una aplicación cliente que usa la detección para llamar al servicio</span><span class="sxs-lookup"><span data-stu-id="5351a-118">To create a client application that uses discovery to call the service</span></span>  
  
1.  <span data-ttu-id="5351a-119">Agregue a la solución una aplicación de consola nueva denominada `DiscoveryClientApp`.</span><span class="sxs-lookup"><span data-stu-id="5351a-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2.  <span data-ttu-id="5351a-120">Agregue una referencia a `System.ServiceModel.dll` y `System.ServiceModel.Discovery.dll`.</span><span class="sxs-lookup"><span data-stu-id="5351a-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3.  <span data-ttu-id="5351a-121">Copie los archivos GeneratedClient.cs y App.config del proyecto de cliente existente en el nuevo proyecto DiscoveryClientApp.</span><span class="sxs-lookup"><span data-stu-id="5351a-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="5351a-122">Para ello, haga clic en los archivos de la **el Explorador de soluciones**, seleccione **copia**y, a continuación, seleccione la **DiscoveryClientApp** del proyecto, haga clic en y seleccione **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="5351a-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4.  <span data-ttu-id="5351a-123">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="5351a-123">Open Program.cs.</span></span>  
  
5.  <span data-ttu-id="5351a-124">Agregue las instrucciones `using` siguientes.</span><span class="sxs-lookup"><span data-stu-id="5351a-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  <span data-ttu-id="5351a-125">Agregue un método estático llamado `FindCalculatorServiceAddress()` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="5351a-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="5351a-126">Este método usa la detección para buscar el servicio `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="5351a-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7.  <span data-ttu-id="5351a-127">Dentro del método `FindCalculatorServiceAddress`, cree una instancia <xref:System.ServiceModel.Discovery.DiscoveryClient> nueva, pasando <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al constructor.</span><span class="sxs-lookup"><span data-stu-id="5351a-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="5351a-128">Esto indica a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> debería usar el extremo de detección de UDP estándar para enviar y recibir mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="5351a-128">This tells [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8.  <span data-ttu-id="5351a-129">En la línea siguiente, llame al método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> y especifique una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que contenga el contrato de servicios que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="5351a-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="5351a-130">En este caso, especifique `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="5351a-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="5351a-131">Después de la llamada a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, compruebe si hay por lo menos un servicio coincidente y devuelva la clase <xref:System.ServiceModel.EndpointAddress> del primer servicio coincidente.</span><span class="sxs-lookup"><span data-stu-id="5351a-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="5351a-132">De lo contrario, devuelva `null`.</span><span class="sxs-lookup"><span data-stu-id="5351a-132">Otherwise return `null`.</span></span>  
  
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
  
10. <span data-ttu-id="5351a-133">Agregue un método estático llamado `InvokeCalculatorService` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="5351a-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="5351a-134">Este método utiliza la dirección del extremo devuelta de `FindCalculatorServiceAddress` para llamar al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="5351a-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="5351a-135">Dentro del método `InvokeCalculatorService`, cree una instancia de la clase `CalculatorServiceClient`.</span><span class="sxs-lookup"><span data-stu-id="5351a-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="5351a-136">Esta clase se define mediante la [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5351a-136">This class is defined by the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="5351a-137">Se ha generado mediante Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="5351a-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="5351a-138">En la línea siguiente, establezca la dirección del extremo del cliente en la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="5351a-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="5351a-139">Inmediatamente después del código del paso anterior, llame a los métodos expuestos por el servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="5351a-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
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
  
14. <span data-ttu-id="5351a-140">Agregue el código al método `Main()` de la clase `Program` para llamar a `FindCalculatorServiceAddress`.</span><span class="sxs-lookup"><span data-stu-id="5351a-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="5351a-141">En la línea siguiente, llame a `InvokeCalculatorService()` y pase la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="5351a-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="5351a-142">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5351a-142">To test the application</span></span>  
  
1.  <span data-ttu-id="5351a-143">Abra un símbolo del sistema elevado y ejecute Service.exe.</span><span class="sxs-lookup"><span data-stu-id="5351a-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2.  <span data-ttu-id="5351a-144">Abra un símbolo del sistema y ejecute Discoveryclientapp.exe.</span><span class="sxs-lookup"><span data-stu-id="5351a-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3.  <span data-ttu-id="5351a-145">El resultado de service.exe debería ser el siguiente.</span><span class="sxs-lookup"><span data-stu-id="5351a-145">The output from service.exe should look like the following output.</span></span>  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  <span data-ttu-id="5351a-146">El resultado de Discoveryclientapp.exe debería ser el siguiente.</span><span class="sxs-lookup"><span data-stu-id="5351a-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="5351a-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5351a-147">Example</span></span>  
 <span data-ttu-id="5351a-148">A continuación, se muestra una lista completa del código de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5351a-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="5351a-149">Dado que este código se basa en el [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo, se muestran solo los archivos que se cambian.</span><span class="sxs-lookup"><span data-stu-id="5351a-149">Because this code is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5351a-150">el ejemplo de autohospedaje, consulte [instrucciones de instalación](http://go.microsoft.com/fwlink/?LinkId=145522).</span><span class="sxs-lookup"><span data-stu-id="5351a-150"> the Self-Host sample, see [Setup Instructions](http://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
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

## <a name="see-also"></a><span data-ttu-id="5351a-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="5351a-151">See Also</span></span>  
 [<span data-ttu-id="5351a-152">Información general sobre la detección WCF</span><span class="sxs-lookup"><span data-stu-id="5351a-152">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="5351a-153">Modelo de objetos de detección WCF</span><span class="sxs-lookup"><span data-stu-id="5351a-153">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
