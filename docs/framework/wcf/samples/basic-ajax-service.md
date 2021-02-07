---
description: 'Más información acerca de: servicio AJAX básico'
title: Servicio AJAX básico
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 08670c0e87a6f258d29288e2072cd04dd875088a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732727"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="9e9ed-103">Servicio AJAX básico</span><span class="sxs-lookup"><span data-stu-id="9e9ed-103">Basic AJAX Service</span></span>

<span data-ttu-id="9e9ed-104">En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript y XML (AJAX) ASP.NET asincrónico básico (un servicio al que se puede tener acceso mediante código JavaScript desde un cliente del explorador Web).</span><span class="sxs-lookup"><span data-stu-id="9e9ed-104">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="9e9ed-105">El servicio utiliza el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para asegurarse de que el servicio responde a las solicitudes HTTP GET y de que está configurado para utilizar el formato de datos de Notación de objeto de JavaScript (JSON) para las respuestas.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-105">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>

<span data-ttu-id="9e9ed-106">La compatibilidad de AJAX en WCF está optimizada para su uso con ASP.NET AJAX a través del `ScriptManager` control.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="9e9ed-107">Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="9e9ed-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9e9ed-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="9e9ed-109">En el código siguiente, el atributo <xref:System.ServiceModel.Web.WebGetAttribute> se aplica a la operación `Add` para asegurarse de que el servicio responde a las solicitudes HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-109">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="9e9ed-110">El código usa GET por simplicidad (puede construir una solicitud HTTP GET desde cualquier explorador web).</span><span class="sxs-lookup"><span data-stu-id="9e9ed-110">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="9e9ed-111">También puede utilizar GET para habilitar el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-111">You can also use GET to enable caching.</span></span> <span data-ttu-id="9e9ed-112">HTTP POST es el valor predeterminado en la ausencia del atributo `WebGetAttribute`.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-112">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="9e9ed-113">El archivo .svc de ejemplo utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, que agrega un punto de conexión estándar <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-113">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="9e9ed-114">El extremo se configura en una dirección vacía relativa al archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-114">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="9e9ed-115">Esto significa que la dirección del servicio es `http://localhost/ServiceModelSamples/service.svc` , sin sufijos adicionales que no sean el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-115">This means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>

`<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>`

<span data-ttu-id="9e9ed-116"><xref:System.ServiceModel.Description.WebScriptEndpoint> se preconfigura de modo que el servicio esté accesible desde una página de cliente AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-116">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="9e9ed-117">La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-117">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="9e9ed-118">Se puede quitar si no se necesita ningún cambio adicional.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-118">It can be removed if no extra changes are required.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <!-- Use this element to configure the endpoint -->
      <standardEndpoint name=""  />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="9e9ed-119"><xref:System.ServiceModel.Description.WebScriptEndpoint> establece el formato de datos predeterminado para el servicio en JSON en lugar de XML.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-119">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="9e9ed-120">Para invocar el servicio, vaya a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` después de completar los pasos de configuración y compilación que se muestran más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-120">To invoke the service, navigate to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="9e9ed-121">El uso de una solicitud HTTP GET habilita esta funcionalidad de la prueba.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-121">This testing functionality is enabled by the use of a HTTP GET request.</span></span>

<span data-ttu-id="9e9ed-122">La página web del cliente SimpleAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación en la página.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-122">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="9e9ed-123">El control `ScriptManager` se utiliza para hacer que un proxy al servicio sea accesible a través de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-123">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">
    <Services>
        <asp:ServiceReference Path="service.svc" />
    </Services>
</asp:ScriptManager>
```

<span data-ttu-id="9e9ed-124">Se crean instancias del proxy local y las operaciones se invocan utilizando el siguiente código de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-124">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>

```javascript
// Code for extracting arguments n1 and n2 omitted…
// Instantiate a service proxy
var proxy = new SimpleAjaxService.ICalculator();
// Code for selecting operation omitted…
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);
```

<span data-ttu-id="9e9ed-125">Si la llamada del servicio es correcta, el código invoca el controlador `onSuccess` y el resultado de la operación se muestra en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-125">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("result").value = mathResult;
}
```

> [!IMPORTANT]
> <span data-ttu-id="9e9ed-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9e9ed-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9e9ed-128">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e9ed-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9e9ed-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`
