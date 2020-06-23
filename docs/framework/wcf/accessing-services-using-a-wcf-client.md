---
title: Acceso a los servicios mediante un cliente WCF
description: Obtenga información acerca de cómo crear un proxy de cliente de WCF para el servicio WCF. Una aplicación cliente utiliza el proxy de cliente para comunicarse con el servicio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 25446a89a0b5657d32d77e2d0d57f58f36bed71b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245549"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="70e2c-104">Acceso a los servicios mediante un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="70e2c-104">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="70e2c-105">Después de crear un servicio, el siguiente paso es crear un proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="70e2c-105">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="70e2c-106">Una aplicación cliente utiliza el proxy de cliente de WCF para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-106">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="70e2c-107">Las aplicaciones cliente suelen importar los metadatos de un servicio para generar el código de cliente de WCF que se puede usar para invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-107">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="70e2c-108">Los pasos básicos para crear un cliente WCF son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="70e2c-108">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="70e2c-109">Compilar el código del servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-109">Compile the service code.</span></span>

2. <span data-ttu-id="70e2c-110">Genere el proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="70e2c-110">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="70e2c-111">Cree una instancia del proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="70e2c-111">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="70e2c-112">El proxy de cliente de WCF se puede generar manualmente mediante la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil.exe) para obtener más información, vea [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="70e2c-112">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="70e2c-113">También se puede generar el proxy de cliente de WCF en Visual Studio mediante la característica **Agregar referencia de servicio** .</span><span class="sxs-lookup"><span data-stu-id="70e2c-113">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="70e2c-114">Para generar el proxy de cliente de WCF usando cualquier método, el servicio debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="70e2c-114">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="70e2c-115">Si el servicio se autohospeda, debe ejecutar el host.</span><span class="sxs-lookup"><span data-stu-id="70e2c-115">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="70e2c-116">Si el servicio se hospeda en IIS/WAS no necesita hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="70e2c-116">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="70e2c-117">Herramienta de utilidad de metadatos ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70e2c-117">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="70e2c-118">La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) es una herramienta de línea de comandos para generar código a partir de metadatos.</span><span class="sxs-lookup"><span data-stu-id="70e2c-118">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="70e2c-119">A continuación se muestra un ejemplo del uso de un comando básico Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="70e2c-119">The following use is an example of a basic Svcutil.exe command.</span></span>

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="70e2c-120">Como alternativa, puede usar Svcutil.exe con archivos de Lenguaje de descripción de servicios Web (WSDL) y de lenguaje de definición de esquemas XML (XSD) en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="70e2c-120">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="70e2c-121">El resultado es un archivo de código que contiene el código de cliente de WCF que la aplicación cliente puede usar para invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-121">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="70e2c-122">También puede usar la herramienta para generar archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="70e2c-122">You can also use the tool to generate configuration files.</span></span>

```console
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="70e2c-123">Si se proporciona solo uno nombre de archivo, ése será el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="70e2c-123">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="70e2c-124">Si se proporcionan dos nombres de archivo, entonces el primer archivo es un archivo de configuración de entrada cuyo contenido está combinado con la configuración generada y que se escribe en el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="70e2c-124">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="70e2c-125">Para obtener más información acerca de la configuración, consulte [configuración de enlaces para servicios](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="70e2c-125">For more information about configuration, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70e2c-126">Las solicitudes de metadatos que no son seguras plantean ciertos riesgos, al igual que cualquier solicitud de una red no segura: si no está seguro de que el punto de conexión con el que se está comunicando es el que dice ser, es posible que la información que recupere sean metadatos de un servicio malintencionado.</span><span class="sxs-lookup"><span data-stu-id="70e2c-126">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="70e2c-127">Agregar referencia de servicio en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="70e2c-127">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="70e2c-128">Con el servicio en ejecución, haga clic con el botón secundario en el proyecto que contendrá el proxy de cliente de WCF y seleccione **Agregar**  >  **referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="70e2c-128">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="70e2c-129">En el **cuadro de diálogo Agregar referencia de servicio**, escriba la dirección URL del servicio al que desea llamar y haga clic en el botón **ir** .</span><span class="sxs-lookup"><span data-stu-id="70e2c-129">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="70e2c-130">El cuadro de diálogo mostrará una lista de servicios disponibles en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="70e2c-130">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="70e2c-131">Haga doble clic en el servicio para ver los contratos y las operaciones disponibles, especifique un espacio de nombres para el código generado y haga clic en el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="70e2c-131">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="70e2c-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70e2c-132">Example</span></span>
 <span data-ttu-id="70e2c-133">El ejemplo de código siguiente muestra un contrato de servicio creado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-133">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="70e2c-134">La herramienta de utilidad de metadatos de ServiceModel y **Agregar referencia de servicio** en Visual Studio generan la siguiente clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="70e2c-134">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="70e2c-135">La clase adquiere de la clase <xref:System.ServiceModel.ClientBase%601> genérica e implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="70e2c-135">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="70e2c-136">La herramienta también genera la interfaz (no se muestra aquí) `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="70e2c-136">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="70e2c-137">Uso del cliente WCF</span><span class="sxs-lookup"><span data-stu-id="70e2c-137">Using the WCF Client</span></span>
 <span data-ttu-id="70e2c-138">Para usar el cliente de WCF, cree una instancia del cliente de WCF y, a continuación, llame a sus métodos, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="70e2c-138">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="70e2c-139">Depuración de las excepciones iniciadas por un cliente</span><span class="sxs-lookup"><span data-stu-id="70e2c-139">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="70e2c-140">Muchas de las excepciones producidas por un cliente de WCF se producen debido a una excepción en el servicio.</span><span class="sxs-lookup"><span data-stu-id="70e2c-140">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="70e2c-141">A continuación se indican algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="70e2c-141">Some examples of this are:</span></span>

- <span data-ttu-id="70e2c-142"><xref:System.Net.Sockets.SocketException>: el host remoto forzó el cierre de la conexión existente.</span><span class="sxs-lookup"><span data-stu-id="70e2c-142"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

- <span data-ttu-id="70e2c-143"><xref:System.ServiceModel.CommunicationException>: la conexión ha terminado de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="70e2c-143"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

- <span data-ttu-id="70e2c-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: se anuló la conexión de socket.</span><span class="sxs-lookup"><span data-stu-id="70e2c-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="70e2c-145">La causa puede ser un error en el procesamiento del mensaje, que se superó el tiempo de espera de recepción en el host remoto, o bien un problema de recursos de red subyacente.</span><span class="sxs-lookup"><span data-stu-id="70e2c-145">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="70e2c-146">Cuando se producen estos tipos de excepciones, la mejor manera de resolver el problema es activar el seguimiento en el lado del servicio y determinar qué excepción se produjo allí.</span><span class="sxs-lookup"><span data-stu-id="70e2c-146">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="70e2c-147">Para obtener más información sobre el seguimiento, vea [seguimiento](./diagnostics/tracing/index.md) y [uso del seguimiento para solucionar problemas de la aplicación](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="70e2c-147">For more information about tracing, see [Tracing](./diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70e2c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="70e2c-148">See also</span></span>

- [<span data-ttu-id="70e2c-149">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="70e2c-149">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="70e2c-150">Procedimiento para obtener acceso a los servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="70e2c-150">How to: Access Services with a Duplex Contract</span></span>](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="70e2c-151">Procedimiento para llamar a operaciones de servicio de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="70e2c-151">How to: Call Service Operations Asynchronously</span></span>](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="70e2c-152">Procedimiento para obtener acceso a los servicios con contratos unidireccionales y de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="70e2c-152">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="70e2c-153">Procedimiento para obtener acceso a un servicio WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="70e2c-153">How to: Access a WSE 3.0 Service</span></span>](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="70e2c-154">Comprender códigos de cliente generado</span><span class="sxs-lookup"><span data-stu-id="70e2c-154">Understanding Generated Client Code</span></span>](./feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="70e2c-155">Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="70e2c-155">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="70e2c-156">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="70e2c-156">Specifying Client Run-Time Behavior</span></span>](specifying-client-run-time-behavior.md)
- [<span data-ttu-id="70e2c-157">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="70e2c-157">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
