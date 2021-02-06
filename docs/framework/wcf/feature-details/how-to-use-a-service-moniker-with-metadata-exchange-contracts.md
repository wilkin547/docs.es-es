---
description: 'Más información sobre: Cómo: usar un moniker de servicio con contratos de intercambio de metadatos'
title: Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 220132a10cb637be9e3724232d0ddaf80a13551a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643103"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="4925c-103">Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="4925c-103">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>

<span data-ttu-id="4925c-104">Después de desarrollar algunos servicios WCF nuevos, puede decidir que desea poder llamar a estos servicios desde un script o una aplicación Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="4925c-104">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="4925c-105">Un método sería generar un ensamblado de cliente de WCF, registrar el ensamblado con COM, instalar el ensamblado en la GAC y, a continuación, hacer referencia a los tipos COM desde el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4925c-105">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="4925c-106">Al distribuir la aplicación, tendrá que distribuir también el ensamblado de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="4925c-106">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="4925c-107">El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC.</span><span class="sxs-lookup"><span data-stu-id="4925c-107">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="4925c-108">La interoperabilidad COM de WCF también permite realizar las mismas llamadas de servicio sin depender de un ensamblado de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="4925c-108">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="4925c-109">El moniker de WCF le permite llamar a cualquier servicio de WCF desde cualquier lenguaje compatible con COM (Visual Basic, VBScript, Visual Basic para Aplicaciones (VBA), etc.) especificando un URI de extremo de intercambio de metadatos (MEX) que el moniker de servicio utiliza para extraer información de tipo sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="4925c-109">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="4925c-110">En este tema se describe cómo llamar al ejemplo de Introducción WCF mediante un moniker de WCF que especifica un extremo de Mex.</span><span class="sxs-lookup"><span data-stu-id="4925c-110">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4925c-111">Nunca se crean instancias de los tipos definidos por el ensamblado de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="4925c-111">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="4925c-112">El ensamblado solo se utiliza para los metadatos.</span><span class="sxs-lookup"><span data-stu-id="4925c-112">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="4925c-113">Utilizar el moniker de servicio con una dirección de Mex</span><span class="sxs-lookup"><span data-stu-id="4925c-113">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="4925c-114">Compile el ejemplo Introducción y use Internet Explorer para ir a su dirección URL ( `http://localhost/ServiceModelSamples/Service.svc` ) para asegurarse de que el servicio está funcionando.</span><span class="sxs-lookup"><span data-stu-id="4925c-114">Build the Getting Started sample and use Internet Explorer to browse to its URL (`http://localhost/ServiceModelSamples/Service.svc`) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="4925c-115">Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4925c-115">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="4925c-116">Ejecute la aplicación Visual Basic o script.</span><span class="sxs-lookup"><span data-stu-id="4925c-116">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4925c-117">El servicio al que está llamando debe exponer un extremo de Mex para que el moniker pueda leer los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="4925c-117">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="4925c-118">Para obtener más información, consulte [Cómo: publicar metadatos para un servicio mediante un archivo de configuración](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4925c-118">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4925c-119">Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."</span><span class="sxs-lookup"><span data-stu-id="4925c-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="4925c-120">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="4925c-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4925c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4925c-121">See also</span></span>

- [<span data-ttu-id="4925c-122">Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse</span><span class="sxs-lookup"><span data-stu-id="4925c-122">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="4925c-123">Procedimiento para usar un moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="4925c-123">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)
