---
title: Ejemplo de introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: 12568b2bb86257ed7075f2dc83b8077714a1318e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347040"
---
# <a name="getting-started-sample"></a><span data-ttu-id="fda23-102">Ejemplo de introducción</span><span class="sxs-lookup"><span data-stu-id="fda23-102">Getting Started Sample</span></span>

<span data-ttu-id="fda23-103">En el ejemplo Introducción se muestra cómo implementar un servicio típico y un cliente típico mediante Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fda23-103">The Getting Started sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="fda23-104">Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.</span><span class="sxs-lookup"><span data-stu-id="fda23-104">This sample is the basis for all other basic technology samples.</span></span>

> [!NOTE]
> <span data-ttu-id="fda23-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="fda23-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fda23-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="fda23-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fda23-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fda23-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="fda23-108">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fda23-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fda23-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="fda23-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

<span data-ttu-id="fda23-110">El servicio describe las operaciones que realiza en un contrato de servicios que expone públicamente como metadatos.</span><span class="sxs-lookup"><span data-stu-id="fda23-110">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="fda23-111">El servicio también contiene el código para implementar las operaciones.</span><span class="sxs-lookup"><span data-stu-id="fda23-111">The service also contains the code to implement the operations.</span></span>

<span data-ttu-id="fda23-112">El cliente contiene una definición del contrato de servicios y una clase de proxy para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="fda23-112">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="fda23-113">El código proxy se genera a partir de los metadatos del servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fda23-113">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

<span data-ttu-id="fda23-114">En Windows Vista, el servicio se hospeda en el servicio de activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="fda23-114">On Windows Vista, the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="fda23-115">En [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y Windows Server 2003, se hospeda en Internet Information Services (IIS) y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fda23-115">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and Windows Server 2003, it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="fda23-116">Hospedar un servicio en IIS o WAS permite activar el servicio automáticamente cuando se tiene acceso por primera vez.</span><span class="sxs-lookup"><span data-stu-id="fda23-116">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>

> [!NOTE]
> <span data-ttu-id="fda23-117">Si prefiere empezar a trabajar con un ejemplo que hospeda el servicio en una aplicación de consola en lugar de en IIS, consulte el ejemplo de [host propio](../../../../docs/framework/wcf/samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="fda23-117">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>

<span data-ttu-id="fda23-118">El servicio y cliente especifican los detalles de acceso en valores de archivo de configuración, los cuales proporciona la flexibilidad en el momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="fda23-118">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="fda23-119">Esto incluye una definición de punto de conexión que especifica una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="fda23-119">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="fda23-120">El enlace especifica el transporte y los detalles de seguridad sobre cómo se tiene acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="fda23-120">The binding specifies transport and security details for how the service is to be accessed.</span></span>

<span data-ttu-id="fda23-121">El servicio configura un comportamiento de tiempo de ejecución para publicar sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="fda23-121">The service configures a run-time behavior to publish its metadata.</span></span>

<span data-ttu-id="fda23-122">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="fda23-122">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="fda23-123">La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato.</span><span class="sxs-lookup"><span data-stu-id="fda23-123">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="fda23-124">El cliente realiza solicitudes a una operación matemática concreta y el servicio responde con el resultado.</span><span class="sxs-lookup"><span data-stu-id="fda23-124">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="fda23-125">El servicio implementa un contrato `ICalculator` que se define en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="fda23-125">The service implements an `ICalculator` contract that is defined in the following code.</span></span>

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
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

<span data-ttu-id="fda23-126">La implementación del servicio calcula y devuelve el resultado adecuado, tal y como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="fda23-126">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="fda23-127">El servicio expone un punto de conexión para comunicarse con el servicio, que se define utilizando un archivo de configuración (Web.config), como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fda23-127">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

<span data-ttu-id="fda23-128">El servicio expone el punto de conexión en la dirección base proporcionada por el host IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="fda23-128">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="fda23-129">El enlace se configura con un <xref:System.ServiceModel.WSHttpBinding>estándar, que proporciona comunicación del HTTP y protocolos estándar del servicio Web para direccionar y seguridad.</span><span class="sxs-lookup"><span data-stu-id="fda23-129">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="fda23-130">El contrato es el `ICalculator` implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="fda23-130">The contract is the `ICalculator` implemented by the service.</span></span>

<span data-ttu-id="fda23-131">Tal y como se ha configurado, se puede tener acceso al servicio en `http://localhost/servicemodelsamples/service.svc` un cliente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="fda23-131">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="fda23-132">Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="fda23-132">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>

<span data-ttu-id="fda23-133">El marco no expone ningún metadato de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fda23-133">The framework does not expose metadata by default.</span></span> <span data-ttu-id="fda23-134">Como tal, el servicio activa el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y expone un punto de conexión de intercambio de metadatos (MEX) en `http://localhost/servicemodelsamples/service.svc/mex`.</span><span class="sxs-lookup"><span data-stu-id="fda23-134">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="fda23-135">La siguiente configuración lo muestra.</span><span class="sxs-lookup"><span data-stu-id="fda23-135">The following configuration demonstrates this.</span></span>

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

<span data-ttu-id="fda23-136">El cliente se comunica utilizando un tipo de contrato determinado mediante una clase de cliente generada por la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fda23-136">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="fda23-137">Este cliente generado se encuentra en el archivo generatedClient.cs o generatedClient.vb.</span><span class="sxs-lookup"><span data-stu-id="fda23-137">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="fda23-138">Esta utilidad recupera los metadatos para un servicio determinado y genera un cliente para el uso por la aplicación del cliente para comunicarse, utilizando un tipo de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="fda23-138">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="fda23-139">El servicio hospedado debe estar disponible para generar el código de cliente, porque el servicio se utiliza para recuperar los metadatos actualizados.</span><span class="sxs-lookup"><span data-stu-id="fda23-139">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>

 <span data-ttu-id="fda23-140">Ejecute el comando siguiente desde un símbolo del sistema SDK en el directorio cliente para generar el proxy especificado:</span><span class="sxs-lookup"><span data-stu-id="fda23-140">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

<span data-ttu-id="fda23-141">Para generar el cliente en el tipo Visual Basic el siguiente símbolo del sistema de SDK:</span><span class="sxs-lookup"><span data-stu-id="fda23-141">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

<span data-ttu-id="fda23-142">Al utilizar el cliente generado, el cliente puede tener acceso a un punto de conexión de servicio determinado configurando la dirección adecuada y el enlace.</span><span class="sxs-lookup"><span data-stu-id="fda23-142">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="fda23-143">Como el servicio, el cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="fda23-143">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="fda23-144">La configuración del extremo del cliente está compuesta por una dirección absoluta para el extremo del servicio, el enlace y el contrato, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fda23-144">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

<span data-ttu-id="fda23-145">La implementación del cliente crea instancias de cliente y utiliza la interfaz especificada para empezar a comunicarse con el servicio, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fda23-145">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

<span data-ttu-id="fda23-146">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="fda23-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="fda23-147">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="fda23-147">Press ENTER in the client window to shut down the client.</span></span>

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

<span data-ttu-id="fda23-148">El ejemplo de la Introducción muestra la manera estándar de crear un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="fda23-148">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="fda23-149">La otra compilación [básica](../../../../docs/framework/wcf/samples/basic-sample.md) sobre este ejemplo para mostrar características específicas del producto.</span><span class="sxs-lookup"><span data-stu-id="fda23-149">The other [Basic](../../../../docs/framework/wcf/samples/basic-sample.md) build on this sample to demonstrate specific product features.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fda23-150">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fda23-150">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="fda23-151">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fda23-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="fda23-152">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fda23-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="fda23-153">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fda23-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fda23-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="fda23-154">See also</span></span>

- [<span data-ttu-id="fda23-155">Cómo hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="fda23-155">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="fda23-156">Cómo: hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="fda23-156">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
