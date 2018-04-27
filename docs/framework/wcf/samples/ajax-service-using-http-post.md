---
title: Servicio AJAX mediante HTTP POST
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1446fadeb249d91f0eb3e65b1155f00090441a5a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="891fa-102">Servicio AJAX mediante HTTP POST</span><span class="sxs-lookup"><span data-stu-id="891fa-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="891fa-103">Este ejemplo muestra cómo utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para crear un servicio JavaScript asincrónico [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y XML (AJAX) que utiliza HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="891fa-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="891fa-104">Un servicio AJAX es un servicio al que puede tener acceso utilizando el código JavaScript básico desde un cliente del explorador web.</span><span class="sxs-lookup"><span data-stu-id="891fa-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="891fa-105">En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo; la única diferencia entre las dos muestras es el uso de HTTP POST en lugar de HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="891fa-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="891fa-106">La compatibilidad de AJAX en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se optimiza para su uso con ASP.NET AJAX a través del control `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="891fa-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="891fa-107">Para obtener un ejemplo del uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, vea el [muestra Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="891fa-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="891fa-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="891fa-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="891fa-109">El servicio en el ejemplo siguiente es un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin el código específico de AJAX.</span><span class="sxs-lookup"><span data-stu-id="891fa-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="891fa-110">Si el <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica el atributo en una operación, o la <xref:System.ServiceModel.Web.WebGetAttribute> no se aplica el atributo, se utiliza el verbo HTTP predeterminado ("POST").</span><span class="sxs-lookup"><span data-stu-id="891fa-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="891fa-111">Las solicitudes POST son más difíciles de construir que las solicitudes GET, aunque no estén almacenadas en la memoria caché. Use las solicitudes POST para todas las operaciones en las que no sea adecuado almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="891fa-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="891fa-112">Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.</span><span class="sxs-lookup"><span data-stu-id="891fa-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="891fa-113">A diferencia de las solicitudes GET, no se pueden invocar los servicios POST desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="891fa-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="891fa-114">Por ejemplo, navegar a http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 da como resultado un error, porque el servicio POST espera el `n1` y `n2` parámetros para ser enviados en el cuerpo del mensaje, en el formato JSON y no en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="891fa-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="891fa-115">La página web del cliente PostAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación de la página.</span><span class="sxs-lookup"><span data-stu-id="891fa-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="891fa-116">El servicio responde de la misma manera que en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo, con la solicitud GET.</span><span class="sxs-lookup"><span data-stu-id="891fa-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="891fa-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="891fa-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="891fa-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="891fa-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="891fa-119">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="891fa-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="891fa-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="891fa-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="891fa-121">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="891fa-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="891fa-122">Asegúrese de que lleva a cabo las instrucciones de configuración [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="891fa-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="891fa-123">Compile la solución PostAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="891fa-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="891fa-124">Vaya a http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (no abra PostAjaxClientPage.aspx en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="891fa-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891fa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="891fa-125">See Also</span></span>
