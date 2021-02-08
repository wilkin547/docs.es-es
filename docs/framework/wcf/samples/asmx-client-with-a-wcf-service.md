---
description: 'Más información acerca de: cliente ASMX con un servicio WCF'
title: Cliente ASMX con un servicio WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: b9f561f6651c591556f821478c4c4bfd7d7da23d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778924"
---
# <a name="asmx-client-with-a-wcf-service"></a><span data-ttu-id="e4020-103">Cliente ASMX con un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="e4020-103">ASMX Client with a WCF Service</span></span>

<span data-ttu-id="e4020-104">Este ejemplo muestra cómo crear un servicio mediante Windows Communication Foundation (WCF) y, a continuación, obtener acceso al servicio desde un cliente que no sea de WCF, como un cliente ASMX.</span><span class="sxs-lookup"><span data-stu-id="e4020-104">This sample demonstrates how to create a service using Windows Communication Foundation (WCF) and then access the service from a non-WCF client, such as an ASMX client.</span></span>

> [!NOTE]
> <span data-ttu-id="e4020-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="e4020-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="e4020-106">Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e4020-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="e4020-107">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="e4020-107">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="e4020-108">La interfaz `ICalculator`, que expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`) define el contrato.</span><span class="sxs-lookup"><span data-stu-id="e4020-108">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="e4020-109">El cliente ASMX realiza solicitudes sincrónicas a una operación matemática y el servicio responde con el resultado.</span><span class="sxs-lookup"><span data-stu-id="e4020-109">The ASMX client makes synchronous requests to a math operation and the service replies with the result.</span></span>

<span data-ttu-id="e4020-110">El servicio implementa un contrato `ICalculator` tal y como se define en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4020-110">The service implements an `ICalculator` contract as defined in the following code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
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

<span data-ttu-id="e4020-111"><xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer> asignan los tipos CLR a una representación XML.</span><span class="sxs-lookup"><span data-stu-id="e4020-111">The <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Xml.Serialization.XmlSerializer> map CLR types to an XML representation.</span></span> <span data-ttu-id="e4020-112"><xref:System.Runtime.Serialization.DataContractSerializer> interpreta algunas representaciones XML de manera diferente a XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="e4020-112">The <xref:System.Runtime.Serialization.DataContractSerializer> interprets some XML representations differently than XmlSerializer.</span></span> <span data-ttu-id="e4020-113">Los generadores de proxy que no son de WCF, como Wsdl.exe, generan una interfaz más utilizable cuando se usa XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="e4020-113">Non-WCF proxy generators, such as Wsdl.exe, generate a more usable interface when the XmlSerializer is being used.</span></span> <span data-ttu-id="e4020-114"><xref:System.ServiceModel.XmlSerializerFormatAttribute>Se aplica a la `ICalculator` interfaz para asegurarse de que se utiliza XmlSerializer para asignar tipos CLR a XML.</span><span class="sxs-lookup"><span data-stu-id="e4020-114">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is applied to the `ICalculator` interface, to ensure that the XmlSerializer is used for mapping CLR types to XML.</span></span> <span data-ttu-id="e4020-115">La implementación del servicio calcula y devuelve el resultado adecuado.</span><span class="sxs-lookup"><span data-stu-id="e4020-115">The service implementation calculates and returns the appropriate result.</span></span>

<span data-ttu-id="e4020-116">El servicio expone un extremo único para comunicarse con el servicio, que se define utilizando el archivo de configuración (Web.config).</span><span class="sxs-lookup"><span data-stu-id="e4020-116">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="e4020-117">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="e4020-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="e4020-118">El servicio expone el extremo en la dirección base proporcionada por el host de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e4020-118">The service exposes the endpoint at the base address provided by the Internet Information Services (IIS) host.</span></span> <span data-ttu-id="e4020-119">El atributo `binding` está definido en basicHttpBinding, que proporciona las comunicaciones HTTP usando SOAP 1.1, que es conforme a WS-I BasicProfile 1.1, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4020-119">The `binding` attribute is set to basicHttpBinding that provides HTTP communications using SOAP 1.1, which is compliant with WS-I BasicProfile 1.1 as shown in the following sample configuration.</span></span>

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

<span data-ttu-id="e4020-120">El cliente ASMX se comunica con el servicio WCF mediante un proxy con tipo generado por la utilidad de lenguaje de descripción de servicios web (WSDL) (Wsdl.exe).</span><span class="sxs-lookup"><span data-stu-id="e4020-120">The ASMX client communicates with the WCF service using a typed proxy that is generated by the Web Services Description Language (WSDL) utility (Wsdl.exe).</span></span> <span data-ttu-id="e4020-121">El proxy con tipo se encuentra en el archivo generatedClient.cs.</span><span class="sxs-lookup"><span data-stu-id="e4020-121">The typed proxy is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="e4020-122">La utilidad WSDL recupera los metadatos para el servicio especificado y genera un proxy con tipo para que un cliente lo utilice para comunicarse.</span><span class="sxs-lookup"><span data-stu-id="e4020-122">The WSDL utility retrieves metadata for the specified service and generates a typed proxy for use by a client to communicate.</span></span> <span data-ttu-id="e4020-123">De forma predeterminada, el marco no expone ningún metadato.</span><span class="sxs-lookup"><span data-stu-id="e4020-123">By default, the framework does not expose any metadata.</span></span> <span data-ttu-id="e4020-124">Para exponer los metadatos necesarios para generar el proxy, debe agregar [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) y establecer su `httpGetEnabled` atributo en `True` tal y como se muestra en la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4020-124">To expose the metadata required to generate the proxy, you must add a [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) and set its `httpGetEnabled` attribute to `True` as shown in the following configuration.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="e4020-125">Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.</span><span class="sxs-lookup"><span data-stu-id="e4020-125">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

<span data-ttu-id="e4020-126">Al utilizar el proxy con tipo generado, el cliente puede tener acceso a un punto de conexión de servicio determinado configurando la dirección adecuada.</span><span class="sxs-lookup"><span data-stu-id="e4020-126">By using the generated typed proxy, the client can access a given service endpoint by configuring the appropriate address.</span></span> <span data-ttu-id="e4020-127">El cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que comunicarse.</span><span class="sxs-lookup"><span data-stu-id="e4020-127">The client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span>

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

<span data-ttu-id="e4020-128">La implementación del cliente construye una instancia del proxy con tipo para comenzar la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="e4020-128">The client implementation constructs an instance of the typed proxy to begin communicating with the service.</span></span>

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
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

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="e4020-129">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4020-129">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e4020-130">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="e4020-130">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e4020-131">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4020-131">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e4020-132">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4020-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e4020-133">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4020-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="e4020-134">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4020-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e4020-135">Para obtener más información sobre cómo pasar y devolver tipos de datos complejos, consulte [enlace de datos en un cliente de Windows Forms](data-binding-in-a-windows-forms-client.md), [enlace de datos en un cliente Windows Presentation Foundation](data-binding-in-a-wpf-client.md)y [enlace de datos en un cliente de ASP.net](data-binding-in-an-aspnet-client.md)</span><span class="sxs-lookup"><span data-stu-id="e4020-135">For more information about passing and returning complex data types see: [Data Binding in a Windows Forms Client](data-binding-in-a-windows-forms-client.md), [Data Binding in a Windows Presentation Foundation Client](data-binding-in-a-wpf-client.md), and [Data Binding in an ASP.NET Client](data-binding-in-an-aspnet-client.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4020-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e4020-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e4020-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e4020-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e4020-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e4020-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e4020-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e4020-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
