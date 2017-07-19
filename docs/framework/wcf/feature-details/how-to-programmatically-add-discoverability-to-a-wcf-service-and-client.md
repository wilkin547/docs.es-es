---
title: "C&#243;mo: Agregar detectabilidad mediante programaci&#243;n a un cliente y un servicio de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo: Agregar detectabilidad mediante programaci&#243;n a un cliente y un servicio de WCF
En este tema, se explica cómo hacer un que un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sea reconocible. Se basa en el [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo.  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>Para configurar el ejemplo de servicio de host automático existente repara para la detección  
  
1.  Abra la solución de host automático en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]. El ejemplo se encuentra en el directorio TechnologySamples\Basic\Service\Hosting\SelfHost.  
  
2.  Agregue una referencia a `System.ServiceModel.Discovery.dll` al proyecto de servicio. Puede ver un mensaje de error que dice "System. ServiceModel.Discovery.dll, o una de sus dependencias requiere una versión posterior de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que el especificado en el proyecto... " Si ve este mensaje, haga clic en el proyecto en el Explorador de soluciones y elija **propiedades**. En el **propiedades del proyecto** ventana, asegúrese de que el **.NET Framework de destino** es [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
3.  Abra el archivo Service.cs y agregue la siguiente instrucción `using`.  
  
    ```  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  En el `Main()` (método), dentro los `using` instrucción, agregue un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instancia al host de servicio.  
  
    ```  
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
  
     El <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> especifica que el servicio que se aplica es reconocible.  
  
5.  Agregar un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al host de servicio justo después del código que agrega el <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.  
  
    ```  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Este código especifica que los mensajes de detección se deberían enviar al punto de conexión de detección de UDP estándar.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>Para crear una aplicación cliente que usa la detección para llamar al servicio  
  
1.  Agregue a la solución una aplicación de consola nueva denominada `DiscoveryClientApp`.  
  
2.  Agregue una referencia a `System.ServiceModel.dll` y `System.ServiceModel.Discovery.dll`.  
  
3.  Copie los archivos GeneratedClient.cs y App.config del proyecto de cliente existente en el nuevo proyecto DiscoveryClientApp. Para ello, haga clic en los archivos de la **el Explorador de soluciones**, seleccione **copia**y, a continuación, seleccione la **DiscoveryClientApp** del proyecto, haga clic y seleccione **pegar**.  
  
4.  Abra Program.cs.  
  
5.  Agregue las instrucciones `using` siguientes.  
  
    ```  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
  
    ```  
  
6.  Agregue un método estático llamado `FindCalculatorServiceAddress()` a la clase `Program`.  
  
    ```  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Este método usa la detección para buscar el servicio `CalculatorService`.  
  
7.  Dentro de la `FindCalculatorServiceAddress` (método), cree un nuevo <xref:System.ServiceModel.Discovery.DiscoveryClient> instancia pasando un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al constructor.  
  
    ```  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     Esto indica a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que la <xref:System.ServiceModel.Discovery.DiscoveryClient> clase debería usar el extremo de detección UDP estándar para enviar y recibir mensajes de detección.  
  
8.  En la línea siguiente, llame a la <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> método y especificar un <xref:System.ServiceModel.Discovery.FindCriteria> instancia que contiene el contrato de servicio que desea buscar. En este caso, especifique `ICalculator`.  
  
    ```  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. Después de llamar a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, compruebe si hay al menos un servicio coincidente y devuelva la <xref:System.ServiceModel.EndpointAddress> del primer servicio coincidente. De lo contrario, devuelva `null`.  
  
    ```  
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
  
    ```  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     Este método utiliza la dirección del extremo devuelta de `FindCalculatorServiceAddress` para llamar al servicio de calculadora.  
  
11. Dentro del método `InvokeCalculatorService`, cree una instancia de la clase `CalculatorServiceClient`. Esta clase se define mediante la [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo. Se ha generado mediante Svcutil.exe.  
  
    ```  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. En la línea siguiente, establezca la dirección del extremo del cliente en la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.  
  
    ```  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. Inmediatamente después del código del paso anterior, llame a los métodos expuestos por el servicio de calculadora.  
  
    ```  
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
  
    ```  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. En la línea siguiente, llame a `InvokeCalculatorService()` y pase la dirección del extremo devuelta de `FindCalculatorServiceAddress()`.  
  
    ```  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Abra un símbolo del sistema elevado y ejecute Service.exe.  
  
2.  Abra un símbolo del sistema y ejecute Discoveryclientapp.exe.  
  
3.  El resultado de service.exe debería ser el siguiente.  
  
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
  
4.  El resultado de Discoveryclientapp.exe debería ser el siguiente.  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra una lista completa del código de este ejemplo. Dado que este código se basa en el [autohospedaje](http://go.microsoft.com/fwlink/?LinkId=145523) ejemplo, se muestran sólo los archivos que cambian. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]el ejemplo autohospedaje, consulte [instrucciones de configuración](http://go.microsoft.com/fwlink/?LinkId=145522).  
  
```  
  
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
  
```  
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
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la detección WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Modelo de objeto de detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)