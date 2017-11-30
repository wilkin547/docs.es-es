---
title: "Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed6ce9b87a5e2d8945a57110c02cce8024439f14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="4dc32-102">Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="4dc32-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="4dc32-103">Después de desarrollar algunos servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nuevos, puede decidir que quiere poder llamar a estos servicios desde un script o una aplicación de Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="4dc32-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="4dc32-104">Un método sería generar un ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], registre el ensamblado con COM, instale el ensamblado en la GAC y, a continuación, haga referencia a los tipos COM de su código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4dc32-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="4dc32-105">Al distribuir la aplicación, tendrá que distribuir también el ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc32-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="4dc32-106">El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC.</span><span class="sxs-lookup"><span data-stu-id="4dc32-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="4dc32-107">Interoperabilidad COM [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también le permite realizar las mismas llamadas de servicio sin confiar en un ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc32-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="4dc32-108">El moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite llamar a cualquier servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde cualquier lenguaje COM compatible (Visual Basic, VBScript, Visual Basic para Aplicaciones (VBA), etc.) especificando un extremo URI de intercambio de metadatos (Mex) que el moniker de servicio utiliza para extraer información de tipo sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="4dc32-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="4dc32-109">En este tema se describe cómo llamar al ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de la Introducción mediante un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifica un extremo de Mex.</span><span class="sxs-lookup"><span data-stu-id="4dc32-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dc32-110">No se crean instancias realmente de los tipos definidos por el ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc32-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="4dc32-111">El ensamblado solo se utiliza para los metadatos.</span><span class="sxs-lookup"><span data-stu-id="4dc32-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="4dc32-112">Utilizar el moniker de servicio con una dirección de Mex</span><span class="sxs-lookup"><span data-stu-id="4dc32-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="4dc32-113">Compile el ejemplo de Introducción y utilice Internet Explorer para ir a su dirección URL (http://localhost/ServiceModelSamples/Service.svc) con el fin de asegurarse que el servicio está funcionando.</span><span class="sxs-lookup"><span data-stu-id="4dc32-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="4dc32-114">Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4dc32-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="4dc32-115">Ejecute la aplicación Visual Basic o script.</span><span class="sxs-lookup"><span data-stu-id="4dc32-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4dc32-116">El servicio al que está llamando debe exponer un punto de conexión de Mex para que el moniker pueda leer los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="4dc32-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="4dc32-117">Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4dc32-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4dc32-118">Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."</span><span class="sxs-lookup"><span data-stu-id="4dc32-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="4dc32-119">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="4dc32-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc32-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dc32-120">See Also</span></span>  
 [<span data-ttu-id="4dc32-121">Cómo: utilizar el Moniker de servicio de Windows Communication Foundation sin registro</span><span class="sxs-lookup"><span data-stu-id="4dc32-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="4dc32-122">Cómo: utilizar un Moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="4dc32-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
