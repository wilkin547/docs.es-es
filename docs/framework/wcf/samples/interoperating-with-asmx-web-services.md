---
description: 'Más información sobre: interoperar con servicios web ASMX'
title: Interoperabilidad con servicios web ASMX
ms.date: 03/30/2017
ms.assetid: a7c11f0a-9e68-4f03-a6b1-39cf478d1a89
ms.openlocfilehash: dd21cf74cf4ee49cae5b9bcfa55e099636c84e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726395"
---
# <a name="interoperating-with-asmx-web-services"></a><span data-ttu-id="c17cf-103">Interoperabilidad con servicios web ASMX</span><span class="sxs-lookup"><span data-stu-id="c17cf-103">Interoperating with ASMX Web Services</span></span>

<span data-ttu-id="c17cf-104">Este ejemplo muestra cómo integrar una aplicación cliente de Windows Communication Foundation (WCF) con un servicio Web ASMX existente.</span><span class="sxs-lookup"><span data-stu-id="c17cf-104">This sample demonstrates how to integrate a Windows Communication Foundation (WCF) client application with an existing ASMX Web service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c17cf-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c17cf-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c17cf-106">Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c17cf-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c17cf-107">El servicio es un servicio Web ASMX que implementa un contrato que define un patrón de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="c17cf-107">The service is an ASMX Web Service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="c17cf-108">El servicio expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`).</span><span class="sxs-lookup"><span data-stu-id="c17cf-108">The service exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="c17cf-109">El cliente realiza solicitudes sincrónicas a una operación matemática y el servicio responde con el resultado.</span><span class="sxs-lookup"><span data-stu-id="c17cf-109">The client makes synchronous requests to a math operation and the service replies with the result.</span></span> <span data-ttu-id="c17cf-110">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="c17cf-110">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="c17cf-111">La implementación de servicio Web de ASMX mostrada en el código muestra siguiente calcula y devuelve el resultado adecuado.</span><span class="sxs-lookup"><span data-stu-id="c17cf-111">The ASMX Web service implementation shown in the following sample code calculates and returns the appropriate result.</span></span>  
  
```csharp  
[WebService(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class CalculatorService : System.Web.Services.WebService  
    {  
        [WebMethod]  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
        [WebMethod]  
        public double Subtract(double n1, double n2)  
        {  
            return n1 - n2;  
        }  
        [WebMethod]  
        public double Multiply(double n1, double n2)  
        {  
            return n1 * n2;  
        }  
        [WebMethod]  
        public double Divide(double n1, double n2)  
        {  
            return n1 / n2;  
        }  
    }  
```  
  
 <span data-ttu-id="c17cf-112">Tal y como se ha configurado, se puede tener acceso al servicio en `http://localhost/servicemodelsamples/service.asmx` un cliente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="c17cf-112">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.asmx` by a client on the same machine.</span></span> <span data-ttu-id="c17cf-113">Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="c17cf-113">For clients on remote machines to access the service, a qualified domain name must be specified instead of localhost.</span></span>  
  
 <span data-ttu-id="c17cf-114">La comunicación se realiza a través de un cliente generado por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c17cf-114">Communication is done through a client generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="c17cf-115">El cliente está contenido en el archivo generatedClient.cs.</span><span class="sxs-lookup"><span data-stu-id="c17cf-115">The client is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="c17cf-116">El servicio ASMX debe estar disponible Para compilar el código proxy, porque se utiliza para recuperar los metadatos actualizados.</span><span class="sxs-lookup"><span data-stu-id="c17cf-116">The ASMX service must be available to generate the proxy code, because it is used to retrieve the updated metadata.</span></span> <span data-ttu-id="c17cf-117">Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.</span><span class="sxs-lookup"><span data-stu-id="c17cf-117">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedClient.cs  
```  
  
 <span data-ttu-id="c17cf-118">Utilizando el cliente generado, puede tener acceso a un punto de conexión de servicio configurando la dirección adecuada y el enlace apropiado.</span><span class="sxs-lookup"><span data-stu-id="c17cf-118">By using the generated client, you can access a service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="c17cf-119">Como el servicio, el cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="c17cf-119">Like the service, the client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span> <span data-ttu-id="c17cf-120">La configuración de punto de conexión de cliente está compuesta de un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato, tal y como se muestra en la siguiente configuración de muestra.</span><span class="sxs-lookup"><span data-stu-id="c17cf-120">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
   <endpoint
      address="http://localhost/ServiceModelSamples/service.asmx"
      binding="basicHttpBinding"
      contract="Microsoft.ServiceModel.Samples.CalculatorServiceSoap" />  
</client>  
```  
  
 <span data-ttu-id="c17cf-121">La implementación del cliente crea una instancia del cliente generado.</span><span class="sxs-lookup"><span data-stu-id="c17cf-121">The client implementation constructs an instance of the generated client.</span></span> <span data-ttu-id="c17cf-122">El cliente generado se puede utilizar a continuación para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="c17cf-122">The generated client can then be used to communicate with the service.</span></span>  
  
```csharp  
// Create a client.  
CalculatorServiceSoapClient client = new CalculatorServiceSoapClient();  
  
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
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="c17cf-123">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c17cf-123">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c17cf-124">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c17cf-124">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c17cf-125">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c17cf-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c17cf-126">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c17cf-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c17cf-127">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c17cf-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c17cf-128">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c17cf-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c17cf-129">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c17cf-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c17cf-130">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c17cf-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c17cf-131">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c17cf-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c17cf-132">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c17cf-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\ASMX`  
