---
title: Ejemplo básico
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 5d0470fefff86ee3a88fa290be5f349c38ca8276
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716078"
---
# <a name="basic-sample"></a>Ejemplo básico

En este ejemplo se muestra cómo hacer que un servicio se pueda detectar y cómo buscar y llamar a un servicio detectable. Este ejemplo se compone de dos proyectos: servicio y cliente.

> [!NOTE]
> En él se implementa la detección en el código.  Para obtener un ejemplo que implementa la detección en la configuración, vea [Configuration (configuración](../../../../docs/framework/wcf/samples/configuration-sample.md)).

## <a name="service"></a>Servicio

Se trata de la implementación de un servicio de calculadora sencillo. El código relacionado con la detección se puede encontrar en `Main` donde un objeto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> se agrega al host del servicio y un objeto <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> se agrega como se muestra en el siguiente código.

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

## <a name="client"></a>Client

El cliente usa un objeto <xref:System.ServiceModel.Discovery.DynamicEndpoint> para localizar el servicio. El <xref:System.ServiceModel.Discovery.DynamicEndpoint>, un extremo estándar, resuelve el extremo del servicio cuando se abre el cliente. En este caso, el <xref:System.ServiceModel.Discovery.DynamicEndpoint> busca el servicio según el contrato de servicio. El <xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la búsqueda a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> de forma predeterminada. Cuando localiza un punto de conexión de servicio, el cliente se conecta a ese servicio a través del enlace especificado.

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

El cliente define un método denominado `InvokeCalculatorService` que utiliza la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios. <xref:System.ServiceModel.Discovery.DynamicEndpoint> hereda de <xref:System.ServiceModel.Description.ServiceEndpoint>, de modo que se pueda pasar al método `InvokeCalculatorService`. A continuación, el ejemplo utiliza <xref:System.ServiceModel.Discovery.DynamicEndpoint> para crear una instancia de `CalculatorServiceClient` y llama a diversas operaciones del servicio de calculadora.

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

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Para obtener más información, consulte [configuración de http y https](https://go.microsoft.com/fwlink/?LinkId=70353). Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas. Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Con Visual Studio 2012, abra Basic. sln y compile el ejemplo.

3. Ejecute la aplicación service.exe.

4. Después de que se inicie el servicio, ejecute la aplicación client.exe.

5. Observe que el cliente pudo encontrar el servicio sin conocer su dirección.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
