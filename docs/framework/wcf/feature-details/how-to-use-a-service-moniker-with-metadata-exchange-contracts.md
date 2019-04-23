---
title: Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 367cbd4a2bfbde3d4ab0a74eeeaf5d5f5662ec27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319838"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="87c9f-102">Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="87c9f-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="87c9f-103">Después de desarrollar algunos servicios de WCF nueva, puede decidir que desea llamar a estos servicios desde un script o una aplicación de Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="87c9f-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="87c9f-104">Un método sería generar un ensamblado de cliente WCF, registrar el ensamblado con COM, instale al ensamblado en la GAC y, a continuación, hacer referencia a los tipos COM desde código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87c9f-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="87c9f-105">Cuando se distribuye la aplicación, tendrá que distribuir también el ensamblado de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="87c9f-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="87c9f-106">El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC.</span><span class="sxs-lookup"><span data-stu-id="87c9f-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="87c9f-107">Interoperabilidad de COM de WCF también permite realizar las mismas llamadas de servicio sin tener que depender de un ensamblado de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="87c9f-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="87c9f-108">El moniker WCF le permite llamar a cualquier servicio WCF en cualquier lenguaje compatible con COM (Visual Basic, VBScript, Visual Basic para aplicaciones (VBA) etc.) mediante la especificación de un extremo de intercambio (Mex) identificador URI que utiliza el moniker de servicio para extraer el tipo de metadatos información sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="87c9f-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="87c9f-109">Este tema describe cómo llamar al ejemplo de WCF Introducción utilizando un moniker WCF que especifica un punto de conexión Mex.</span><span class="sxs-lookup"><span data-stu-id="87c9f-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87c9f-110">Realmente nunca se crean instancias de los tipos definidos por el ensamblado de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="87c9f-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="87c9f-111">El ensamblado solo se utiliza para los metadatos.</span><span class="sxs-lookup"><span data-stu-id="87c9f-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="87c9f-112">Utilizar el moniker de servicio con una dirección de Mex</span><span class="sxs-lookup"><span data-stu-id="87c9f-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="87c9f-113">Compile el ejemplo de introducción y utilice Internet Explorer para ir a su dirección URL (http://localhost/ServiceModelSamples/Service.svc) para asegurarse de que el servicio está funcionando.</span><span class="sxs-lookup"><span data-stu-id="87c9f-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="87c9f-114">Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="87c9f-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="87c9f-115">Ejecute la aplicación Visual Basic o script.</span><span class="sxs-lookup"><span data-stu-id="87c9f-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87c9f-116">El servicio al que está llamando debe exponer un extremo de Mex para que el moniker pueda leer los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="87c9f-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="87c9f-117">Para obtener más información, vea [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="87c9f-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87c9f-118">Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."</span><span class="sxs-lookup"><span data-stu-id="87c9f-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="87c9f-119">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="87c9f-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c9f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="87c9f-120">See also</span></span>

- [<span data-ttu-id="87c9f-121">Cómo: Utilice el Moniker de servicio de Windows Communication Foundation sin registrarse</span><span class="sxs-lookup"><span data-stu-id="87c9f-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="87c9f-122">Cómo: Utilizar un Moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="87c9f-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
