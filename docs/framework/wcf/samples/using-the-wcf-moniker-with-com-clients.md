---
title: Uso del moniker de WCF con clientes COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: faaf8e80402ddaef85dcf8d7bfe9b1da202227c9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715285"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a><span data-ttu-id="9e32b-102">Uso del moniker de WCF con clientes COM</span><span class="sxs-lookup"><span data-stu-id="9e32b-102">Using the WCF Moniker with COM Clients</span></span>
<span data-ttu-id="9e32b-103">Este ejemplo muestra cómo utilizar el moniker de servicio de Windows Communication Foundation (WCF) para integrar los servicios web en entornos de desarrollo basados en COM, como Microsoft Office Visual Basic para Aplicaciones (Office VBA) o Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="9e32b-103">This sample demonstrates how to use the Windows Communication Foundation (WCF) service moniker to integrate Web services into COM-based development environments, such as Microsoft Office Visual Basic for Applications (Office VBA) or Visual Basic 6.0.</span></span> <span data-ttu-id="9e32b-104">El ejemplo está compuesto por un cliente de Windows Script Host (.vbs), una biblioteca de cliente auxiliar (.dll) y una biblioteca de servicios (.dll) hospedados en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="9e32b-104">This sample consists of a Windows Script Host client (.vbs), a supporting client library (.dll), and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="9e32b-105">El servicio es un servicio de calculadora y el cliente COM llama operaciones matemáticas: Sumar, Restar, Multiplicar y Dividir, en el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-105">The service is a calculator service and the COM client calls math operations—Add, Subtract, Multiply, and Divide—on the service.</span></span> <span data-ttu-id="9e32b-106">La actividad Client está visible en las ventanas de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e32b-106">Client activity is visible in the message box windows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e32b-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9e32b-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9e32b-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9e32b-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9e32b-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9e32b-109">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="9e32b-110">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e32b-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e32b-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-111">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 <span data-ttu-id="9e32b-112">El servicio implementa un contrato `ICalculator` definido como se muestra en el ejemplo de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e32b-112">The service implements an `ICalculator` contract defined as shown in the following code example.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="9e32b-113">El ejemplo muestra los tres enfoques alternativos para utilizar el moniker:</span><span class="sxs-lookup"><span data-stu-id="9e32b-113">The sample demonstrates the three alternative approaches for using the moniker:</span></span>  
  
- <span data-ttu-id="9e32b-114">Contrato con tipo: el contrato se registra como un tipo visible COM en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-114">Typed contract – The contract is registered as a COM visible type on the client computer.</span></span>  
  
- <span data-ttu-id="9e32b-115">Contrato de WSDL: el contrato se proporciona en forma de documento WSDL.</span><span class="sxs-lookup"><span data-stu-id="9e32b-115">WSDL contract – The contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="9e32b-116">Contrato de intercambio de metadatos: el contrato se recupera en tiempo de ejecución a partir de un punto de conexión de intercambio de metadatos (MEX).</span><span class="sxs-lookup"><span data-stu-id="9e32b-116">Metadata Exchange contract – The contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="typed-contract"></a><span data-ttu-id="9e32b-117">Contrato con tipo</span><span class="sxs-lookup"><span data-stu-id="9e32b-117">Typed Contract</span></span>  
 <span data-ttu-id="9e32b-118">Para utilizar el moniker con un uso del contrato con tipo, los tipos apropiadamente atribuidos para el contrato de servicios se deben registrar con COM.</span><span class="sxs-lookup"><span data-stu-id="9e32b-118">To use the moniker with a typed contract use, appropriately attributed types for the service contract must be registered with COM.</span></span> <span data-ttu-id="9e32b-119">En primer lugar, se debe generar un cliente mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9e32b-119">First, a client must be generated by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="9e32b-120">Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.</span><span class="sxs-lookup"><span data-stu-id="9e32b-120">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 <span data-ttu-id="9e32b-121">Esta clase debe estar incluida en un proyecto y el proyecto se debería configurar para generar un ensamblado firmado visible en COM al compilarse.</span><span class="sxs-lookup"><span data-stu-id="9e32b-121">This class must be included in a project and the project should be configured to generate a COM-visible, signed assembly when compiled.</span></span> <span data-ttu-id="9e32b-122">El atributo siguiente debería incluirse en el archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="9e32b-122">The following attribute should be included in the AssemblyInfo.cs file.</span></span>  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 <span data-ttu-id="9e32b-123">Después de compilar el proyecto, registre los tipos visibles en COM mediante `regasm`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9e32b-123">After building the project, register the COM-visible types by using `regasm` as shown in the following example.</span></span>  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 <span data-ttu-id="9e32b-124">El ensamblado que se crea se debería agregar a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e32b-124">The assembly that is created should be added to the Global Assembly Cache.</span></span> <span data-ttu-id="9e32b-125">Aunque no estrictamente necesario, esto simplifica el proceso del tiempo de ejecución localizando el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9e32b-125">Though not strictly required, this simplifies the process of the runtime locating the assembly.</span></span> <span data-ttu-id="9e32b-126">El comando siguiente agrega el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e32b-126">The following command adds the assembly to the Global Assembly Cache.</span></span>  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> <span data-ttu-id="9e32b-127">El moniker de servicio requiere solo el registro del tipo y no utiliza el proxy para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-127">The service moniker requires only the type registration and does not use the proxy to communicate with the service.</span></span>  
  
 <span data-ttu-id="9e32b-128">La aplicación cliente ComCalcClient.vbs utiliza la función `GetObject` para construir un proxy para el servicio, utilizando la sintaxis del moniker del servicio para especificar la dirección, enlace y contrato para el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-128">ComCalcClient.vbs client application uses the `GetObject` function to construct a proxy for the service, using the service moniker syntax to specify the address, binding, and contract for the service.</span></span>  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,   
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 <span data-ttu-id="9e32b-129">Los parámetros utilizados por el moniker especifican:</span><span class="sxs-lookup"><span data-stu-id="9e32b-129">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="9e32b-130">La dirección del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-130">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="9e32b-131">El enlace que el cliente debería utilizar para conectar con ese punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e32b-131">The binding that the client should use to connect with that endpoint.</span></span> <span data-ttu-id="9e32b-132">En este caso se utiliza el wsHttpBinding definido por el sistema aunque se pueden definir enlaces personalizados en archivos de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-132">In this case, the system-defined wsHttpBinding is used though custom bindings can be defined in client configuration files.</span></span> <span data-ttu-id="9e32b-133">Para el uso con Windows Scripting Host, el enlace personalizado se define en un archivo Cscript.exe.config en el mismo directorio que Cscript.exe.</span><span class="sxs-lookup"><span data-stu-id="9e32b-133">For use with the Windows Script Host, the custom binding is defined in a Cscript.exe.config file in the same directory as Cscript.exe.</span></span>  
  
- <span data-ttu-id="9e32b-134">El tipo del contrato que se admite en el extremo.</span><span class="sxs-lookup"><span data-stu-id="9e32b-134">The type of the contract that is supported at the endpoint.</span></span> <span data-ttu-id="9e32b-135">Éste es el tipo que se generó y se registró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-135">This is the type that was generated and registered above.</span></span> <span data-ttu-id="9e32b-136">Dado que el script Visual Basic no proporciona un entorno COM fuertemente tipado, se debe especificar un identificador para el contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-136">Because Visual Basic script does not provide a strongly-typed COM environment, an identifier for the contract must be specified.</span></span> <span data-ttu-id="9e32b-137">Este GUID es `interfaceID` de CalcProxy.tlb, que se puede ver utilizando herramientas COM como el Visor de Objetos OLE/COM(OleView.exe).</span><span class="sxs-lookup"><span data-stu-id="9e32b-137">This GUID is the `interfaceID` from CalcProxy.tlb, which can be viewed by using COM tools such as the OLE/COM Object Viewer (OleView.exe).</span></span> <span data-ttu-id="9e32b-138">Para los entornos fuertemente tipados como Office VBA o Visual Basic 6.0, agregar una referencia explícita a la biblioteca de tipos y declarando a continuación el tipo del objeto proxy que se puede utilizar en lugar del parámetro de contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-138">For strongly-typed environments such as Office VBA or Visual Basic 6.0, adding an explicit reference to the type library and then declaring the type of the proxy object can be used in place of the contract parameter.</span></span> <span data-ttu-id="9e32b-139">Esto también proporciona la compatibilidad IntelliSense durante el desarrollo de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-139">This also provides IntelliSense support during client application development.</span></span>  
  
 <span data-ttu-id="9e32b-140">Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e32b-140">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con tipo para comunicarse con un servicio WCF. <span data-ttu-id="9e32b-143">A pesar del uso de COM en la aplicación cliente, la comunicación con el servicio está solo compuesto por las llamadas del Servicio Web.</span><span class="sxs-lookup"><span data-stu-id="9e32b-143">Despite the use of COM in the client application, the communication with the service consists only of Web service calls.</span></span>  
  
## <a name="wsdl-contract"></a><span data-ttu-id="9e32b-144">Contrato WSDL</span><span class="sxs-lookup"><span data-stu-id="9e32b-144">WSDL Contract</span></span>  
 <span data-ttu-id="9e32b-145">No se exigen ningún registro de biblioteca de cliente para utilizar el moniker con un contrato WSDL, pero el contrato WSDL para el servicio se debe recuperar a través de un mecanismo fuera de banda, como utilizar un explorador para tener acceso al punto de conexión WSDL para el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-145">To use the moniker with a WSDL contract, no client library registration is required but the WSDL contract for the service must be retrieved through an out-of-band mechanism such as using a browser to access the WSDL endpoint for the service.</span></span> <span data-ttu-id="9e32b-146">El moniker puede tener acceso entonces a ese contrato en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e32b-146">The moniker can then access that contract at execution time.</span></span>  
  
 <span data-ttu-id="9e32b-147">La aplicación cliente ComCalcClient.vbs utiliza `FileSystemObject` para tener acceso al archivo WSDL guardado localmente y, a continuación, usa de nuevo la función `GetObject` para construir un proxy para el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-147">The ComCalcClient.vbs client application uses the `FileSystemObject` to access the locally saved WSDL file and then again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 <span data-ttu-id="9e32b-148">Los parámetros utilizados por el moniker especifican:</span><span class="sxs-lookup"><span data-stu-id="9e32b-148">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="9e32b-149">La dirección del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-149">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="9e32b-150">El enlace que el cliente debería utilizar para conectarse con ese punto de conexión y el espacio de nombres en el que se define ese enlace.</span><span class="sxs-lookup"><span data-stu-id="9e32b-150">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="9e32b-151">En este caso, se usa `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="9e32b-151">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="9e32b-152">El WSDL que define el contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-152">The WSDL that defines the contract.</span></span> <span data-ttu-id="9e32b-153">En este caso ésta es la cadena leída del archivo serviceWsdl.xml.</span><span class="sxs-lookup"><span data-stu-id="9e32b-153">In this case this is the string that has been read from the serviceWsdl.xml file.</span></span>  
  
- <span data-ttu-id="9e32b-154">El nombre y espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-154">The name and namespace of the contract.</span></span> <span data-ttu-id="9e32b-155">Se requiere esta identificación porque el WSDL puede contener más de un contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-155">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9e32b-156">De forma predeterminada, los servicios WCF generan archivos WSDL independientes para cada espacio de nombres que use.</span><span class="sxs-lookup"><span data-stu-id="9e32b-156">By default, WCF services generate separate WSDL files for each namespace that the use.</span></span> <span data-ttu-id="9e32b-157">Éstos se vinculan con el uso de la construcción de importación de WSDL.</span><span class="sxs-lookup"><span data-stu-id="9e32b-157">These are linked with the use of the WSDL import construct.</span></span> <span data-ttu-id="9e32b-158">Dado que el moniker espera una definición WSDL única, el servicio debe utilizar un espacio de nombres único como se muestra en este ejemplo o los archivos independientes deben estar combinados manualmente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-158">Because the moniker expects a single WSDL definition, the service must either use a single namespace as demonstrated in this sample or the separate files must be manually merged.</span></span>  
  
 <span data-ttu-id="9e32b-159">Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e32b-159">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. <span data-ttu-id="9e32b-161">Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con un contrato WSDL para comunicarse con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="9e32b-161">This demonstrates a COM client making COM calls using the moniker with a WSDL contract to communicate with a WCF service.</span></span>  
  
## <a name="metadata-exchange-contract"></a><span data-ttu-id="9e32b-162">Contrato de Intercambio de Metadatos</span><span class="sxs-lookup"><span data-stu-id="9e32b-162">Metadata Exchange Contract</span></span>  
 <span data-ttu-id="9e32b-163">Para utilizar el moniker con un contrato MEX, como con el contrato WSDL, no se requiere ningún registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-163">To use the moniker with a MEX contract, as with the WSDL contract, no client registration is required.</span></span> <span data-ttu-id="9e32b-164">El contrato para el servicio se recupera en el tiempo de ejecución a través del uso interno de Intercambio de Metadatos.</span><span class="sxs-lookup"><span data-stu-id="9e32b-164">The contract for the service is retrieved at execution time through the internal use of Metadata Exchange.</span></span>  
  
 <span data-ttu-id="9e32b-165">La aplicación cliente ComCalcClient.vbs utiliza de nuevo la función `GetObject` para construir un proxy para el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-165">The ComCalcClient.vbs client application again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 <span data-ttu-id="9e32b-166">Los parámetros utilizados por el moniker especifican:</span><span class="sxs-lookup"><span data-stu-id="9e32b-166">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="9e32b-167">La dirección del punto de conexión de intercambio de metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-167">The address of the service metadata exchange endpoint.</span></span>  
  
- <span data-ttu-id="9e32b-168">La dirección del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-168">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="9e32b-169">El enlace que el cliente debería utilizar para conectarse con ese punto de conexión y el espacio de nombres en el que se define ese enlace.</span><span class="sxs-lookup"><span data-stu-id="9e32b-169">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="9e32b-170">En este caso, se usa `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="9e32b-170">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="9e32b-171">El nombre y espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-171">The name and namespace of the contract.</span></span> <span data-ttu-id="9e32b-172">Se requiere esta identificación porque el WSDL puede contener más de un contrato.</span><span class="sxs-lookup"><span data-stu-id="9e32b-172">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
 <span data-ttu-id="9e32b-173">Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e32b-173">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. <span data-ttu-id="9e32b-175">Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con un contrato MEX para comunicarse con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="9e32b-175">This demonstrates a COM client making COM calls using the moniker with a MEX contract to communicate with a WCF service.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="9e32b-176">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e32b-176">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="9e32b-177">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e32b-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9e32b-178">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e32b-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9e32b-179">En una Símbolo del sistema para desarrolladores para Visual Studio, abra la carpeta \client\bin\, en la carpeta específica del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9e32b-179">From a Developer Command Prompt for Visual Studio, open the \client\bin folder, under the language-specific folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9e32b-180">Si usa [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 o Windows Server 2008 R2, asegúrese de que ejecuta el símbolo del sistema con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9e32b-180">If you are using [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7, or Windows Server 2008 R2, make sure that you run the command prompt with administrator privileges.</span></span>  
  
4. <span data-ttu-id="9e32b-181">Escriba `tlbexp.exe client.dll /out:CalcProxy.tlb` para exportar el archivo DLL a un archivo TLB.</span><span class="sxs-lookup"><span data-stu-id="9e32b-181">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="9e32b-182">Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="9e32b-182">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
5. <span data-ttu-id="9e32b-183">Escriba `regasm.exe /tlb:CalcProxy.tlb client.dll` para registrar los tipos con COM.</span><span class="sxs-lookup"><span data-stu-id="9e32b-183">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="9e32b-184">Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="9e32b-184">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
6. <span data-ttu-id="9e32b-185">Escriba `gacutil.exe /i client.dll` para agregar el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e32b-185">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="9e32b-186">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="9e32b-186">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="9e32b-187">Pruebe que puede tener acceso al servicio mediante un explorador escribiendo la siguiente dirección: `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="9e32b-187">Test that you can access the service using a browser by typing in the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="9e32b-188">Como respuesta se debe mostrar una página de confirmación.</span><span class="sxs-lookup"><span data-stu-id="9e32b-188">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="9e32b-189">Ejecute ComCalcClient.vbs desde \client, en la carpeta específica del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9e32b-189">Run ComCalcClient.vbs from \client, from under the language-specific folder.</span></span> <span data-ttu-id="9e32b-190">La actividad del cliente se muestra en ventanas de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e32b-190">Client activity is displayed in message box windows.</span></span>  
  
3. <span data-ttu-id="9e32b-191">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9e32b-191">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="9e32b-192">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="9e32b-192">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="9e32b-193">En el equipo del servicio, cree un directorio virtual denominado ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="9e32b-193">On the service computer, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="9e32b-194">El script Setupvroot.bat incluido con el ejemplo se puede utilizar para crear el directorio de disco y el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="9e32b-194">The Setupvroot.bat script included with the sample can be used to create the disk directory and virtual directory.</span></span>  
  
2. <span data-ttu-id="9e32b-195">Copie los archivos de programa del servicio del directorio %SystemDrive%\Inetpub\wwwroot\servicemodelsamples al directorio virtual ServiceModelSamples del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-195">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service computer.</span></span> <span data-ttu-id="9e32b-196">Asegúrese de incluir los archivos en el directorio \bin.</span><span class="sxs-lookup"><span data-stu-id="9e32b-196">Be sure to include the files in the \bin directory.</span></span>  
  
3. <span data-ttu-id="9e32b-197">Copie el archivo de script de cliente de la carpeta \client, en la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-197">Copy the client script file from the \client folder, under the language-specific folder, to the client computer.</span></span>  
  
4. <span data-ttu-id="9e32b-198">En el archivo de script, cambie el valor de la dirección de la definición del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="9e32b-198">In the script file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="9e32b-199">Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.</span><span class="sxs-lookup"><span data-stu-id="9e32b-199">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
5. <span data-ttu-id="9e32b-200">Copie el archivo WSDL al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-200">Copy the WSDL file to the client computer.</span></span> <span data-ttu-id="9e32b-201">En el archivo WSDL, serviceWsdl.xml, reemplace cualquier referencia al "host local" con un nombre de dominio completo en la dirección.</span><span class="sxs-lookup"><span data-stu-id="9e32b-201">In the WSDL file, serviceWsdl.xml, replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
6. <span data-ttu-id="9e32b-202">Copie la biblioteca Client.dll de la carpeta \client\bin\, en la carpeta específica del lenguaje, a un directorio en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-202">Copy the Client.dll library from the \client\bin folder, under the language-specific folder, to a directory on the client computer.</span></span>  
  
7. <span data-ttu-id="9e32b-203">Desde un símbolo del sistema, navegue a ese directorio de destino en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9e32b-203">From a command prompt, navigate to that destination directory on the client computer.</span></span> <span data-ttu-id="9e32b-204">Si usa [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], asegúrese de que ejecuta el símbolo del sistema como Administrador.</span><span class="sxs-lookup"><span data-stu-id="9e32b-204">If using [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], make sure to run the command prompt as Administrator.</span></span>  
  
8. <span data-ttu-id="9e32b-205">Escriba `tlbexp.exe client.dll /out:CalcProxy.tlb` para exportar el archivo DLL a un archivo TLB.</span><span class="sxs-lookup"><span data-stu-id="9e32b-205">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="9e32b-206">Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="9e32b-206">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
9. <span data-ttu-id="9e32b-207">Escriba `regasm.exe /tlb:CalcProxy.tlb client.dll` para registrar los tipos con COM.</span><span class="sxs-lookup"><span data-stu-id="9e32b-207">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="9e32b-208">Asegúrese de que la ruta de acceso se ha establecido en la carpeta que contiene `regasm.exe` antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="9e32b-208">Ensure that path has been set to the folder that contains `regasm.exe` before you run the command.</span></span>  
  
10. <span data-ttu-id="9e32b-209">Escriba `gacutil.exe /i client.dll` para agregar el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e32b-209">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="9e32b-210">Asegúrese de que la ruta de acceso se ha establecido en la carpeta que contiene `gacutil.exe` antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="9e32b-210">Ensure that path has been set to the folder that contains `gacutil.exe` before you run the command.</span></span>  
  
11. <span data-ttu-id="9e32b-211">Compruebe que puede tener acceso al servicio desde el equipo cliente utilizando un explorador.</span><span class="sxs-lookup"><span data-stu-id="9e32b-211">Test that you can access the service from the client computer using a browser.</span></span>  
  
12. <span data-ttu-id="9e32b-212">En el equipo cliente, inicie ComCalcClient.vbs.</span><span class="sxs-lookup"><span data-stu-id="9e32b-212">On the client computer, launch ComCalcClient.vbs.</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="9e32b-213">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e32b-213">To clean up after the sample</span></span>  
  
- <span data-ttu-id="9e32b-214">Por razones de seguridad, quite la definición del directorio virtual y los permisos concedidos en los pasos de instalación cuando haya acabado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9e32b-214">For security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
