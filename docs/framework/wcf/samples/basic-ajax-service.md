---
title: Servicio AJAX básico
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 0bb8a2b28ea87cb0c22126540f6cdab604ca5120
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805985"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="ddc91-102">Servicio AJAX básico</span><span class="sxs-lookup"><span data-stu-id="ddc91-102">Basic AJAX Service</span></span>
<span data-ttu-id="ddc91-103">Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio básico de ASP.NET Asynchronous JavaScript y XML (AJAX) (es decir, un servicio que se puede tener acceso mediante código JavaScript de un cliente del explorador Web).</span><span class="sxs-lookup"><span data-stu-id="ddc91-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="ddc91-104">El servicio utiliza el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para asegurarse de que el servicio responde a las solicitudes HTTP GET y de que está configurado para utilizar el formato de datos de Notación de objeto de JavaScript (JSON) para las respuestas.</span><span class="sxs-lookup"><span data-stu-id="ddc91-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="ddc91-105">Compatibilidad con AJAX de WCF está optimizado para su uso con ASP.NET AJAX a través del `ScriptManager` control.</span><span class="sxs-lookup"><span data-stu-id="ddc91-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="ddc91-106">Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea el [muestra AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="ddc91-106">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddc91-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ddc91-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ddc91-108">En el código siguiente, el atributo <xref:System.ServiceModel.Web.WebGetAttribute> se aplica a la operación `Add` para asegurarse de que el servicio responde a las solicitudes HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="ddc91-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="ddc91-109">El código usa GET por simplicidad (puede construir una solicitud HTTP GET desde cualquier explorador web).</span><span class="sxs-lookup"><span data-stu-id="ddc91-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="ddc91-110">También puede utilizar GET para habilitar el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="ddc91-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="ddc91-111">HTTP POST es el valor predeterminado en la ausencia del atributo `WebGetAttribute`.</span><span class="sxs-lookup"><span data-stu-id="ddc91-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 <span data-ttu-id="ddc91-112">El archivo .svc de ejemplo utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, que agrega un extremo estándar <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio.</span><span class="sxs-lookup"><span data-stu-id="ddc91-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="ddc91-113">El punto de conexión se configura en una dirección vacía relativa al archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="ddc91-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="ddc91-114">Esto significa que la dirección del servicio es http://localhost/ServiceModelSamples/service.svc, sin ningún sufijo adicional que no sea el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="ddc91-114">This means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <span data-ttu-id="ddc91-115"><xref:System.ServiceModel.Description.WebScriptEndpoint> se preconfigura de modo que el servicio esté accesible desde una página de cliente AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ddc91-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="ddc91-116">La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el extremo.</span><span class="sxs-lookup"><span data-stu-id="ddc91-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="ddc91-117">Se puede quitar si no se necesita ningún cambio adicional.</span><span class="sxs-lookup"><span data-stu-id="ddc91-117">It can be removed if no extra changes are required.</span></span>  
  
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
  
 <span data-ttu-id="ddc91-118"><xref:System.ServiceModel.Description.WebScriptEndpoint> establece el formato de datos predeterminado para el servicio en JSON en lugar de XML.</span><span class="sxs-lookup"><span data-stu-id="ddc91-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="ddc91-119">Para invocar el servicio, vaya a http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 después de completar el conjunto de seguridad y se muestra más adelante en este tema de pasos de compilación.</span><span class="sxs-lookup"><span data-stu-id="ddc91-119">To invoke the service, navigate to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="ddc91-120">El uso de una solicitud HTTP GET habilita esta funcionalidad de la prueba.</span><span class="sxs-lookup"><span data-stu-id="ddc91-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="ddc91-121">La página web del cliente SimpleAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación en la página.</span><span class="sxs-lookup"><span data-stu-id="ddc91-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="ddc91-122">El control `ScriptManager` se utiliza para hacer que un proxy al servicio sea accesible a través de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ddc91-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 <span data-ttu-id="ddc91-123">Se crean instancias del proxy local y las operaciones se invocan utilizando el siguiente código de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ddc91-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 <span data-ttu-id="ddc91-124">Si la llamada del servicio es correcta, el código invoca el controlador `onSuccess` y el resultado de la operación se muestra en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ddc91-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  <span data-ttu-id="ddc91-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ddc91-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ddc91-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ddc91-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ddc91-127">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ddc91-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ddc91-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ddc91-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="ddc91-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc91-129">See Also</span></span>
