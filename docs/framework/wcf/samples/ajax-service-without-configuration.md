---
title: Servicio AJAX sin configuración
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 2ea5c61ea3f0f8adcce6dc14be11a8b098c7ca0f
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332928"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="8f409-102">Servicio AJAX sin configuración</span><span class="sxs-lookup"><span data-stu-id="8f409-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="8f409-103">Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio básico de ASP.NET Asynchronous JavaScript y XML (AJAX) (es decir, un servicio que puede tener acceso mediante código JavaScript de un cliente del explorador Web) sin utilizar ninguna configuración Configuración.</span><span class="sxs-lookup"><span data-stu-id="8f409-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="8f409-104">El servicio utiliza la sintaxis especial en el archivo .svc para habilitar automáticamente un punto de conexión de AJAX.</span><span class="sxs-lookup"><span data-stu-id="8f409-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="8f409-105">Compatibilidad con AJAX en WCF está optimizado para su uso con AJAX de ASP.NET a través de la `ScriptManager` control.</span><span class="sxs-lookup"><span data-stu-id="8f409-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="8f409-106">Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea el [muestras de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="8f409-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f409-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8f409-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8f409-108">Este ejemplo se compila en el servicio AJAX mediante HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="8f409-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="8f409-109">Como se describe en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se usa para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8f409-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="8f409-110">La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> agrega automáticamente la clase <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio.</span><span class="sxs-lookup"><span data-stu-id="8f409-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="8f409-111">Si no se necesita realizar ningún cambio de configuración en el extremo, la sección `<system.ServiceModel>` se puede quitar totalmente del archivo Web.config del servicio.</span><span class="sxs-lookup"><span data-stu-id="8f409-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="8f409-112">El archivo Web.config contiene parte de la configuración de ASP.NET, que la usa el archivo ConfigFreeClientPage.aspx.</span><span class="sxs-lookup"><span data-stu-id="8f409-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="8f409-113">Si este no es el caso, se podría quitar el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="8f409-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f409-114">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8f409-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8f409-115">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8f409-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8f409-116">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8f409-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8f409-117">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8f409-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8f409-118">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f409-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8f409-119">Asegúrese de realizar las instrucciones de instalación de [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8f409-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8f409-120">Compile la solución configfreeajaxservice.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8f409-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8f409-121">Vaya a `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (no abra ConfigFreeClientPage.aspx en el explorador desde dentro del directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="8f409-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f409-122">Al ejecutar este ejemplo, asegúrese de que la Autenticación anónima y la Autenticación de Windows no están habilitadas simultáneamente para la carpeta ServiceModelSamples en IIS.</span><span class="sxs-lookup"><span data-stu-id="8f409-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="8f409-123">Si es así, deshabilite la Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="8f409-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="8f409-124">Una vez ha ejecutado el ejemplo, habilite la Autenticación de Windows y ejecute "iisreset".</span><span class="sxs-lookup"><span data-stu-id="8f409-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f409-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f409-125">See also</span></span>
- [<span data-ttu-id="8f409-126">Servicio AJAX básico</span><span class="sxs-lookup"><span data-stu-id="8f409-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
