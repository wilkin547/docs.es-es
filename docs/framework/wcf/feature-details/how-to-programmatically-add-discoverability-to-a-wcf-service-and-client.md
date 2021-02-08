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
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a>Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF

En este tema se explica cómo hacer que un servicio de Windows Communication Foundation (WCF) sea reconocible. Se basa en el ejemplo de [host propio](../samples/self-host.md) .  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>Para configurar el ejemplo de servicio de host automático existente repara para la detección  
  
1. Abra la solución Self-Host en Visual Studio 2012. El ejemplo se encuentra en el directorio TechnologySamples\Basic\Service\Hosting\SelfHost.  
  
2. Agregue una referencia a `System.ServiceModel.Discovery.dll` al proyecto de servicio. Es posible que vea un mensaje de error que indica "System. ServiceModel.Discovery.dll o una de sus dependencias requiere una versión posterior del .NET Framework que la especificada en el proyecto... " Si ve este mensaje, haga clic con el botón derecho en el proyecto en el Explorador de soluciones y elija **propiedades**. En la ventana **propiedades del proyecto** , asegúrese de que la versión de **.NET Framework de destino** sea [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .  
  
3. Abra el archivo Service.cs y agregue la siguiente instrucción `using`.  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. En el método `Main()`, dentro de la instrucción `using`, agregue una instancia <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> al host de servicio.  
  
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
  
     La clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> especifica que el servicio al que se aplica es reconocible.  
  
5. Agregue <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al host de servicio justo después del código que agrega <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Este código especifica que los mensajes de detección se deberían enviar al extremo de detección de UDP estándar.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>Para crear una aplicación cliente que usa la detección para llamar al servicio  
  
1. Agregue a la solución una aplicación de consola nueva denominada `DiscoveryClientApp`.  
  
2. Agregue una referencia a `System.ServiceModel.dll` y `System.ServiceModel.Discovery.dll`.  
  
3. Copie los archivos GeneratedClient.cs y App.config del proyecto de cliente existente en el nuevo proyecto DiscoveryClientApp. Para ello, haga clic con el botón derecho en los archivos del **Explorador de soluciones**, seleccione **copiar** y, a continuación, seleccione el proyecto **DiscoveryClientApp** , haga clic con el botón derecho y seleccione **pegar**.  
  
4. Abra Program.cs.  
  
5. Agregue las siguientes instrucciones `using`.  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. Agregue un método estático llamado `FindCalculatorServiceAddress()` a la clase `Program`.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Este método usa la detección para buscar el servicio `CalculatorService`.  
  
7. Dentro del método `FindCalculatorServiceAddress`, cree una instancia <xref:System.ServiceModel.Discovery.DiscoveryClient> nueva, pasando <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al constructor.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     Esto indica a WCF que la <xref:System.ServiceModel.Discovery.DiscoveryClient> clase debe usar el extremo de detección de UDP estándar para enviar y recibir mensajes de detección.  
  
8. En la línea siguiente, llame al método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> y especifique una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que contenga el contrato de servicios que desea buscar. En este caso, especifique `ICalculator`.  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. Después de la llamada a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, compruebe si hay por lo menos un servicio coincidente y devuelva la clase <xref:System.ServiceModel.EndpointAddress> del primer servicio coincidente. De lo contrario, devuelva `null`.  
  
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
  
10. Agregue un método estático llamado `InvokeCalculatorService` a la clase `Program`.  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     Este método utiliza la dirección del extremo devuelta de `FindCalculatorServiceAddress` para llamar al servicio de calculadora.  
  
11. Dentro del método `InvokeCalculatorService`, cree una instancia de la clase `CalculatorServiceClient`. Esta clase se define mediante el ejemplo [de host propio](../samples/self-host.md) . Se ha generado mediante Svcutil.exe.  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. En la línea siguiente, establezca la dirección del extremo del cliente en la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. Inmediatamente después del código del paso anterior, llame a los métodos expuestos por el servicio de calculadora.  
  
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
  
14. Agregue el código al método `Main()` de la clase `Program` para llamar a `FindCalculatorServiceAddress`.  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. En la línea siguiente, llame a `InvokeCalculatorService()` y pase la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1. Abra un símbolo del sistema elevado y ejecute Service.exe.  
  
2. Abra un símbolo del sistema y ejecute Discoveryclientapp.exe.  
  
3. El resultado de service.exe debería ser el siguiente.  
  
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
  
4. El resultado de Discoveryclientapp.exe debería ser el siguiente.  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Ejemplo  

 A continuación, se muestra una lista completa del código de este ejemplo. Dado que este código se basa en el ejemplo de [host propio](../samples/self-host.md) , solo se muestran los archivos que se han modificado. Para obtener más información sobre el ejemplo de Self-Host, vea [instrucciones de configuración](../samples/set-up-instructions.md).  
  
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

## <a name="see-also"></a>Vea también

- [Información general de Detección de WCF](wcf-discovery-overview.md)
- [Modelo de objetos de Detección de WCF](wcf-discovery-object-model.md)
