---
description: 'Más información sobre: Cómo: utilizar un moniker de servicio con contratos WSDL'
title: Procedimiento para usar un moniker de servicio con contratos WSDL
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 70a8ef0258cd8490d8e14b6a80e8de0248fa0ae2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734378"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a><span data-ttu-id="a8829-103">Procedimiento para usar un moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="a8829-103">How to: Use a Service Moniker with WSDL Contracts</span></span>

<span data-ttu-id="a8829-104">Hay situaciones en las que usted querrá tener un cliente de Interoperabilidad COM completamente autónomo.</span><span class="sxs-lookup"><span data-stu-id="a8829-104">There are situations when you may want to have a completely self-contained COM Interop client.</span></span> <span data-ttu-id="a8829-105">Puede que el servicio que quiere llamar no exponga un extremo MEX y puede que la DLL cliente de WCF no se registre para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="a8829-105">The service you want to call may not expose a MEX endpoint, and the WCF client DLL may not be registered for COM interop.</span></span> <span data-ttu-id="a8829-106">En estos casos, puede crear un archivo WSDL que describe el servicio y lo pasa en el moniker del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a8829-106">In these cases, you can create a WSDL file that describes the service and pass it into the WCF service moniker.</span></span> <span data-ttu-id="a8829-107">Este tema describe cómo llamar al ejemplo de WCF Introducción utilizando un moniker WSDL de WCF.</span><span class="sxs-lookup"><span data-stu-id="a8829-107">This topic describes how to call the Getting Started WCF sample using a WCF WSDL moniker.</span></span>  
  
### <a name="using-the-wsdl-service-moniker"></a><span data-ttu-id="a8829-108">Utilizar el moniker de servicio WSDL</span><span class="sxs-lookup"><span data-stu-id="a8829-108">Using the WSDL service moniker</span></span>  
  
1. <span data-ttu-id="a8829-109">Abra y compile la solución de ejemplo GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="a8829-109">Open and build the GettingStarted sample solution.</span></span>  
  
2. <span data-ttu-id="a8829-110">Abra Internet Explorer y vaya a `http://localhost/ServiceModelSamples/Service.svc` para asegurarse de que el servicio está funcionando.</span><span class="sxs-lookup"><span data-stu-id="a8829-110">Open Internet Explorer and browse to `http://localhost/ServiceModelSamples/Service.svc` to make sure that the service is working.</span></span>  
  
3. <span data-ttu-id="a8829-111">En el archivo Service.cs, agregue el atributo siguiente en la clase CalculatorService:</span><span class="sxs-lookup"><span data-stu-id="a8829-111">In the Service.cs file, add the following attribute on the CalculatorService class:</span></span>  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. <span data-ttu-id="a8829-112">Agregue un espacio de nombres de enlace al servicio App.config:</span><span class="sxs-lookup"><span data-stu-id="a8829-112">Add a binding namespace to the service App.config:</span></span>  

5. <span data-ttu-id="a8829-113">Cree un archivo WSDL para que lo lea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8829-113">Create a WSDL file for the application to read.</span></span> <span data-ttu-id="a8829-114">Dado que los espacios de nombres se agregaron en los pasos 3 y 4, puede usar IE para consultar la descripción completa del WSDL del servicio examinando `http://localhost/ServiceModelSamples/Service.svc?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="a8829-114">Because the namespaces were added in steps 3 and 4, you can use IE to query for the entire WSDL description of the service by browsing to `http://localhost/ServiceModelSamples/Service.svc?wsdl`.</span></span> <span data-ttu-id="a8829-115">Puede guardar a continuación el archivo desde Internet Explorer como serviceWSDL.xml.</span><span class="sxs-lookup"><span data-stu-id="a8829-115">You can then save the file from Internet Explorer as serviceWSDL.xml.</span></span> <span data-ttu-id="a8829-116">Si no especifica los espacios de nombres en los pasos 3 y 4, el documento WSDL devuelto de la consulta a la dirección URL anterior no será el WSDL completo.</span><span class="sxs-lookup"><span data-stu-id="a8829-116">If you do not specify the namespaces in steps 3 and 4, the WSDL document returned from querying the above URL will not be the complete WSDL.</span></span> <span data-ttu-id="a8829-117">El documento WSDL devuelto incluirá varias instrucciones de importación que importan otros documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="a8829-117">The WSDL document returned will include several import statements that import other WSDL documents.</span></span> <span data-ttu-id="a8829-118">Tendrá que pasar por cada instrucción de importación y crear el documento WSDL completo, combinando el WSDL devuelto desde el servicio con el WSDL importado.</span><span class="sxs-lookup"><span data-stu-id="a8829-118">You will have to go through each import statement and build the complete WSDL document, combining the WSDL returned from the service with the WSDL imported.</span></span>  
  
6. <span data-ttu-id="a8829-119">Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar.</span><span class="sxs-lookup"><span data-stu-id="a8829-119">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="a8829-120">Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:</span><span class="sxs-lookup"><span data-stu-id="a8829-120">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    > Si el moniker es incorrecto o si el servicio no está disponible la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."  <span data-ttu-id="a8829-122">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="a8829-122">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
7. <span data-ttu-id="a8829-123">Ejecutar aplicación de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8829-123">Run the Visual Basic application.</span></span> <span data-ttu-id="a8829-124">Se mostrará un cuadro de mensaje con los resultados de llamar a Subtract (145, 76.54).</span><span class="sxs-lookup"><span data-stu-id="a8829-124">A message box will be displayed with the results of calling Subtract(145, 76.54).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8829-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8829-125">See also</span></span>

- [<span data-ttu-id="a8829-126">Introducción</span><span class="sxs-lookup"><span data-stu-id="a8829-126">Getting Started</span></span>](../samples/getting-started-sample.md)
- [<span data-ttu-id="a8829-127">Integración con la información general de las aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="a8829-127">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)
