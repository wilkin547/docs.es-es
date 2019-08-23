---
title: Servicio AJAX sin configuración
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 24f07193b955e2b4877ac2e9302a7be0cd879676
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913344"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="ce90d-102">Servicio AJAX sin configuración</span><span class="sxs-lookup"><span data-stu-id="ce90d-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="ce90d-103">En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript y XML (AJAX) ASP.NET asincrónico básico (un servicio al que se puede tener acceso mediante código JavaScript desde un cliente del explorador Web) sin utilizar ninguna configuración. Configuración.</span><span class="sxs-lookup"><span data-stu-id="ce90d-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="ce90d-104">El servicio utiliza la sintaxis especial en el archivo .svc para habilitar automáticamente un punto de conexión de AJAX.</span><span class="sxs-lookup"><span data-stu-id="ce90d-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="ce90d-105">La compatibilidad de Ajax en WCF está optimizada para su uso con `ScriptManager` ASP.NET AJAX a través del control.</span><span class="sxs-lookup"><span data-stu-id="ce90d-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="ce90d-106">Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="ce90d-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce90d-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ce90d-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ce90d-108">Este ejemplo se compila en el servicio AJAX mediante HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="ce90d-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="ce90d-109">Tal y como se describe en el ejemplo de <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> [servicio Ajax básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , se usa para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce90d-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="ce90d-110">La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> agrega automáticamente la clase <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio.</span><span class="sxs-lookup"><span data-stu-id="ce90d-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="ce90d-111">Si no se necesita realizar ningún cambio de configuración en el extremo, la sección `<system.ServiceModel>` se puede quitar totalmente del archivo Web.config del servicio.</span><span class="sxs-lookup"><span data-stu-id="ce90d-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="ce90d-112">El archivo Web.config contiene parte de la configuración de ASP.NET, que la usa el archivo ConfigFreeClientPage.aspx.</span><span class="sxs-lookup"><span data-stu-id="ce90d-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="ce90d-113">Si este no es el caso, se podría quitar el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="ce90d-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce90d-114">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ce90d-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ce90d-115">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ce90d-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ce90d-116">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ce90d-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ce90d-117">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ce90d-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ce90d-118">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce90d-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ce90d-119">Asegúrese de que realiza las instrucciones de configuración en [un procedimiento de instalación único para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ce90d-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ce90d-120">Compile la solución ConfigFreeAjaxService. sln tal y como se describe en [Building the Windows Communication Foundation samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ce90d-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ce90d-121">Vaya a `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (no abra ConfigFreeClientPage. aspx en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="ce90d-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce90d-122">Al ejecutar este ejemplo, asegúrese de que la Autenticación anónima y la Autenticación de Windows no están habilitadas simultáneamente para la carpeta ServiceModelSamples en IIS.</span><span class="sxs-lookup"><span data-stu-id="ce90d-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="ce90d-123">Si es así, deshabilite la Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ce90d-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="ce90d-124">Una vez ha ejecutado el ejemplo, habilite la Autenticación de Windows y ejecute "iisreset".</span><span class="sxs-lookup"><span data-stu-id="ce90d-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce90d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce90d-125">See also</span></span>

- [<span data-ttu-id="ce90d-126">Servicio AJAX básico</span><span class="sxs-lookup"><span data-stu-id="ce90d-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
