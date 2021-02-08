---
description: 'Más información acerca de: servicio AJAX mediante HTTP POST'
title: Servicio AJAX mediante HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 4d319d4120310d79af5bda6026a2192d1270943b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779106"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="30f99-103">Servicio AJAX mediante HTTP POST</span><span class="sxs-lookup"><span data-stu-id="30f99-103">AJAX Service Using HTTP POST</span></span>

<span data-ttu-id="30f99-104">En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript asincrónico y XML (AJAX) ASP.NET que utiliza HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="30f99-104">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="30f99-105">Un servicio AJAX es un servicio al que puede tener acceso utilizando el código JavaScript básico desde un cliente del explorador web.</span><span class="sxs-lookup"><span data-stu-id="30f99-105">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="30f99-106">Este ejemplo se basa en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) ; la única diferencia entre los dos ejemplos es el uso de HTTP POST en lugar de HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="30f99-106">This sample builds on the [Basic AJAX Service](basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>

<span data-ttu-id="30f99-107">La compatibilidad de AJAX en Windows Communication Foundation (WCF) se ha optimizado para su uso con ASP.NET AJAX a través del `ScriptManager` control.</span><span class="sxs-lookup"><span data-stu-id="30f99-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="30f99-108">Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="30f99-108">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax-service-using-http-post.md).</span></span>

> [!NOTE]
> <span data-ttu-id="30f99-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="30f99-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="30f99-110">El servicio en el ejemplo siguiente es un servicio WCF sin código específico de AJAX.</span><span class="sxs-lookup"><span data-stu-id="30f99-110">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>

<span data-ttu-id="30f99-111">Si el <xref:System.ServiceModel.Web.WebInvokeAttribute> atributo se aplica en una operación, o <xref:System.ServiceModel.Web.WebGetAttribute> no se aplica el atributo, se utiliza el verbo http predeterminado ("post").</span><span class="sxs-lookup"><span data-stu-id="30f99-111">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="30f99-112">Las solicitudes POST son más difíciles de construir que las solicitudes GET, aunque no estén almacenadas en la memoria caché. Use las solicitudes POST para todas las operaciones en las que no sea adecuado almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="30f99-112">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="30f99-113">Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.</span><span class="sxs-lookup"><span data-stu-id="30f99-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="30f99-114">A diferencia de las solicitudes GET, no se pueden invocar los servicios POST desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="30f99-114">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="30f99-115">Por ejemplo, al navegar a se `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` produce un error, porque el servicio post espera que `n1` `n2` se envíen los parámetros y en el cuerpo del mensaje en formato JSON y no en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="30f99-115">For example, navigating to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body in the JSON format, and not in the URL.</span></span>

<span data-ttu-id="30f99-116">La página web del cliente PostAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación de la página.</span><span class="sxs-lookup"><span data-stu-id="30f99-116">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="30f99-117">El servicio responde de la misma manera que en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) , con la solicitud GET.</span><span class="sxs-lookup"><span data-stu-id="30f99-117">The service responds in the same way as in the [Basic AJAX Service](basic-ajax-service.md) sample, with the GET request.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30f99-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="30f99-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="30f99-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="30f99-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="30f99-120">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="30f99-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="30f99-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="30f99-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="30f99-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="30f99-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="30f99-123">Asegúrese de que realiza el procedimiento de [configuración de una sola vez en las instrucciones de configuración para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30f99-123">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="30f99-124">Compile la solución PostAjaxService. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30f99-124">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="30f99-125">Vaya a `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (no abra PostAjaxClientPage. aspx en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="30f99-125">Navigate to `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>
