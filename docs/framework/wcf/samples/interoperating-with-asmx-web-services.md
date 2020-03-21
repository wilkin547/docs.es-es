---
title: Interoperabilidad con servicios web ASMX
ms.date: 03/30/2017
ms.assetid: a7c11f0a-9e68-4f03-a6b1-39cf478d1a89
ms.openlocfilehash: b5af8f15d38f730d2243c642d4623c0bc6e1343c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183586"
---
# <a name="interoperating-with-asmx-web-services"></a><span data-ttu-id="6b512-102">Interoperabilidad con servicios web ASMX</span><span class="sxs-lookup"><span data-stu-id="6b512-102">Interoperating with ASMX Web Services</span></span>
<span data-ttu-id="6b512-103">En este ejemplo se muestra cómo integrar una aplicación cliente de Windows Communication Foundation (WCF) con un servicio web ASMX existente.</span><span class="sxs-lookup"><span data-stu-id="6b512-103">This sample demonstrates how to integrate a Windows Communication Foundation (WCF) client application with an existing ASMX Web service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b512-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="6b512-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6b512-105">Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6b512-105">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="6b512-106">El servicio es un servicio Web ASMX que implementa un contrato que define un patrón de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="6b512-106">The service is an ASMX Web Service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="6b512-107">El servicio expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`).</span><span class="sxs-lookup"><span data-stu-id="6b512-107">The service exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="6b512-108">El cliente realiza solicitudes sincrónicas a una operación matemática y el servicio responde con el resultado.</span><span class="sxs-lookup"><span data-stu-id="6b512-108">The client makes synchronous requests to a math operation and the service replies with the result.</span></span> <span data-ttu-id="6b512-109">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="6b512-109">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="6b512-110">La implementación de servicio Web de ASMX mostrada en el código muestra siguiente calcula y devuelve el resultado adecuado.</span><span class="sxs-lookup"><span data-stu-id="6b512-110">The ASMX Web service implementation shown in the following sample code calculates and returns the appropriate result.</span></span>  
  
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
  
 <span data-ttu-id="6b512-111">Según lo configurado, un `http://localhost/servicemodelsamples/service.asmx` cliente en el mismo equipo puede acceder al servicio.</span><span class="sxs-lookup"><span data-stu-id="6b512-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.asmx` by a client on the same machine.</span></span> <span data-ttu-id="6b512-112">Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="6b512-112">For clients on remote machines to access the service, a qualified domain name must be specified instead of localhost.</span></span>  
  
 <span data-ttu-id="6b512-113">La comunicación se realiza a través de un cliente generado por la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)</span><span class="sxs-lookup"><span data-stu-id="6b512-113">Communication is done through a client generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="6b512-114">El cliente está contenido en el archivo generatedClient.cs.</span><span class="sxs-lookup"><span data-stu-id="6b512-114">The client is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="6b512-115">El servicio ASMX debe estar disponible Para compilar el código proxy, porque se utiliza para recuperar los metadatos actualizados.</span><span class="sxs-lookup"><span data-stu-id="6b512-115">The ASMX service must be available to generate the proxy code, because it is used to retrieve the updated metadata.</span></span> <span data-ttu-id="6b512-116">Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.</span><span class="sxs-lookup"><span data-stu-id="6b512-116">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedClient.cs  
```  
  
 <span data-ttu-id="6b512-117">Utilizando el cliente generado, puede tener acceso a un punto de conexión de servicio configurando la dirección adecuada y el enlace apropiado.</span><span class="sxs-lookup"><span data-stu-id="6b512-117">By using the generated client, you can access a service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="6b512-118">Como el servicio, el cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="6b512-118">Like the service, the client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span> <span data-ttu-id="6b512-119">La configuración de punto de conexión de cliente está compuesta de un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato, tal y como se muestra en la siguiente configuración de muestra.</span><span class="sxs-lookup"><span data-stu-id="6b512-119">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
   <endpoint
      address="http://localhost/ServiceModelSamples/service.asmx"
      binding="basicHttpBinding"
      contract="Microsoft.ServiceModel.Samples.CalculatorServiceSoap" />  
</client>  
```  
  
 <span data-ttu-id="6b512-120">La implementación del cliente crea una instancia del cliente generado.</span><span class="sxs-lookup"><span data-stu-id="6b512-120">The client implementation constructs an instance of the generated client.</span></span> <span data-ttu-id="6b512-121">El cliente generado se puede utilizar a continuación para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b512-121">The generated client can then be used to communicate with the service.</span></span>  
  
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
  
 <span data-ttu-id="6b512-122">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="6b512-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6b512-123">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6b512-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6b512-124">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b512-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6b512-125">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="6b512-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6b512-126">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b512-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6b512-127">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="6b512-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b512-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6b512-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6b512-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6b512-129">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6b512-130">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6b512-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b512-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6b512-131">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\ASMX`  
