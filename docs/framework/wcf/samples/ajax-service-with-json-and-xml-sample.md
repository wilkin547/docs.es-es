---
description: Más información sobre el ejemplo de servicio AJAX con JSON y XML
title: Servicio AJAX con ejemplo JSON y XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: e47f6cbd7e4659488325e158e5594ca94322c520
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779067"
---
# <a name="ajax-service-with-json-and-xml-sample"></a><span data-ttu-id="10346-103">Servicio AJAX con ejemplo JSON y XML</span><span class="sxs-lookup"><span data-stu-id="10346-103">AJAX Service with JSON and XML Sample</span></span>

<span data-ttu-id="10346-104">En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio asincrónico de JavaScript y XML (AJAX) que devuelve datos de notación de objetos JavaScript (JSON) o XML.</span><span class="sxs-lookup"><span data-stu-id="10346-104">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an Asynchronous JavaScript and XML (AJAX) service that returns either JavaScript Object Notation (JSON) or XML data.</span></span> <span data-ttu-id="10346-105">Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web.</span><span class="sxs-lookup"><span data-stu-id="10346-105">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="10346-106">Este ejemplo se basa en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="10346-106">This sample builds on the [Basic AJAX Service](basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="10346-107">A diferencia de la otra muestra AJAX, este ejemplo no utiliza AJAX de ASP.NET ni el control <xref:System.Web.UI.ScriptManager>.</span><span class="sxs-lookup"><span data-stu-id="10346-107">Unlike the other AJAX samples, this sample does not use ASP.NET AJAX and the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="10346-108">Con algunas configuraciones adicionales, se puede tener acceso a los servicios AJAX de WCF desde cualquier página HTML a través de JavaScript y este escenario se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="10346-108">With some additional configuration, WCF AJAX services can be accessed from any HTML page through JavaScript, and this scenario is shown here.</span></span> <span data-ttu-id="10346-109">Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte [ejemplos de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="10346-109">For an example of using WCF with ASP.NET AJAX, see [AJAX Samples](ajax.md).</span></span>

<span data-ttu-id="10346-110">Este ejemplo muestra cómo intercambiar el tipo de respuesta de una operación entre JSON y XML.</span><span class="sxs-lookup"><span data-stu-id="10346-110">This sample shows how to switch the response type of an operation between JSON and XML.</span></span> <span data-ttu-id="10346-111">Esta funcionalidad está disponible sin tener en cuenta si el servicio se configura para el acceso mediante AJAX de ASP.NET o una página de cliente de HTML/JavaScript.</span><span class="sxs-lookup"><span data-stu-id="10346-111">This functionality is available regardless of whether the service is configured to be accessed by ASP.NET AJAX or by an HTML/JavaScript client page.</span></span>

> [!NOTE]
> <span data-ttu-id="10346-112">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="10346-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="10346-113">Para habilitar el uso de los clientes de AJAX de ASP.NET, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (no <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) en el archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="10346-113">To enable the use of non-ASP.NET AJAX clients, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (not <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in the .svc file.</span></span> <span data-ttu-id="10346-114"><xref:System.ServiceModel.Activation.WebServiceHostFactory> agrega un extremo <xref:System.ServiceModel.Description.WebHttpEndpoint> estándar al servicio.</span><span class="sxs-lookup"><span data-stu-id="10346-114"><xref:System.ServiceModel.Activation.WebServiceHostFactory> adds a <xref:System.ServiceModel.Description.WebHttpEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="10346-115">El punto de conexión se configura en una dirección vacía relativa al archivo. SVC; Esto significa que la dirección del servicio es `http://localhost/ServiceModelSamples/service.svc` , sin sufijos adicionales que no sean el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="10346-115">The endpoint is configured at an empty address relative to the .svc file; this means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>`

<span data-ttu-id="10346-116">La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="10346-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="10346-117">Se puede quitar si no se necesita ningún cambio adicional.</span><span class="sxs-lookup"><span data-stu-id="10346-117">It can be removed if no extra changes are needed.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <!-- Use this element to configure the endpoint -->
      <standardEndpoint name="" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="10346-118">El formato de datos predeterminado para <xref:System.ServiceModel.Description.WebHttpEndpoint> es XML, mientras que el formato de datos predeterminado para <xref:System.ServiceModel.Description.WebScriptEndpoint> es JSON.</span><span class="sxs-lookup"><span data-stu-id="10346-118">The default data format for <xref:System.ServiceModel.Description.WebHttpEndpoint> is XML, while the default data format for <xref:System.ServiceModel.Description.WebScriptEndpoint> is JSON.</span></span> <span data-ttu-id="10346-119">Para obtener más información, consulte [crear servicios WCF Ajax sin ASP.net](../feature-details/creating-wcf-ajax-services-without-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="10346-119">For more information, see [Creating WCF AJAX Services without ASP.NET](../feature-details/creating-wcf-ajax-services-without-aspnet.md).</span></span>

<span data-ttu-id="10346-120">El servicio en el ejemplo siguiente es un servicio WCF estándar con dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="10346-120">The service in the following sample is a standard WCF service with two operations.</span></span> <span data-ttu-id="10346-121">Ambas operaciones requieren el estilo de cuerpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> en <xref:System.ServiceModel.Web.WebGetAttribute> o los atributos <xref:System.ServiceModel.Web.WebInvokeAttribute>, que es concreto al comportamiento `webHttp` y no están afectados por el cambio de formato de JSON/XML.</span><span class="sxs-lookup"><span data-stu-id="10346-121">Both operations require the <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> body style on the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes, which is specific to the `webHttp` behavior and has no bearing on the JSON/XML data format switch.</span></span>

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathXml(double n1, double n2);
```

<span data-ttu-id="10346-122">El formato de respuesta para la operación se especifica como XML, que es la configuración predeterminada para el [\<webHttp>](../../configure-apps/file-schema/wcf/webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="10346-122">The response format for the operation is specified as XML, which is the default setting for the [\<webHttp>](../../configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="10346-123">No obstante, es conveniente especificar de forma explícita al formato de respuesta.</span><span class="sxs-lookup"><span data-stu-id="10346-123">However, it is good practice explicitly specify the response format.</span></span>

<span data-ttu-id="10346-124">La otra operación utiliza el atributo `WebInvokeAttribute` y explícitamente especifica JSON en lugar de XML para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="10346-124">The other operation uses the `WebInvokeAttribute` attribute and explicitly specifies JSON instead of XML for the response.</span></span>

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathJson(double n1, double n2);
```

<span data-ttu-id="10346-125">Tenga en cuenta que, en ambos casos, las operaciones devuelven un tipo complejo, `MathResult` , que es un tipo de contrato de datos de WCF estándar.</span><span class="sxs-lookup"><span data-stu-id="10346-125">Note that in both cases the operations return a complex type, `MathResult`, which is a standard WCF data contract type.</span></span>

<span data-ttu-id="10346-126">La página web del cliente XmlAjaxClientPage.htm contiene código JavaScript que invoca una de las dos operaciones anteriores cuando el usuario hace clic en los botones **realizar cálculo (devolver JSON)** o **realizar cálculo (devolver XML)** de la página.</span><span class="sxs-lookup"><span data-stu-id="10346-126">The client Web page XmlAjaxClientPage.htm contains JavaScript code that invokes one of the preceding two operations when the user clicks the **Perform calculation (return JSON)** or **Perform calculation (return XML)** buttons on the page.</span></span> <span data-ttu-id="10346-127">El código para invocar el servicio construye un cuerpo de JSON y lo envía utilizando HTTP POST, de manera similar al ejemplo.</span><span class="sxs-lookup"><span data-stu-id="10346-127">The code to invoke the service constructs a JSON body and sends it using HTTP POST.</span></span> <span data-ttu-id="10346-128">La solicitud se crea manualmente en JavaScript, a diferencia del ejemplo de [servicio Ajax básico](basic-ajax-service.md) y de los otros ejemplos que usan ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="10346-128">The request is created manually in JavaScript, unlike the [Basic AJAX Service](basic-ajax-service.md) sample and the other samples using ASP.NET AJAX.</span></span>

```csharp
// Create HTTP request
var xmlHttp;
// Request instantiation code omitted…
// Result handler code omitted…

// Build the operation URL
var url = "service.svc/ajaxEndpoint/";
url = url + operation;

// Build the body of the JSON message
var body = '{"n1":';
body = body + document.getElementById("num1").value + ',"n2":';
body = body + document.getElementById("num2").value + '}';

// Send the HTTP request
xmlHttp.open("POST", url, true);
xmlHttp.setRequestHeader("Content-type", "application/json");
xmlHttp.send(body);
```

<span data-ttu-id="10346-129">Cuando el servicio responde, la respuesta se muestra sin más procesamientos en un cuadro de texto en la página.</span><span class="sxs-lookup"><span data-stu-id="10346-129">When the service responds, the response is displayed without any further processing in a textbox on the page.</span></span> <span data-ttu-id="10346-130">Esto se implementa a efectos de demostración para permitir que poder observar directamente los formatos de datos de JSON y XML utilizados.</span><span class="sxs-lookup"><span data-stu-id="10346-130">This is implemented for demonstration purposes to allow you to directly observe the XML and JSON data formats used.</span></span>

```javascript
// Create result handler
xmlHttp.onreadystatechange=function(){
     if(xmlHttp.readyState == 4){
          document.getElementById("result").value = xmlHttp.responseText;
     }
}
```

> [!IMPORTANT]
> <span data-ttu-id="10346-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="10346-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="10346-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="10346-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="10346-133">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="10346-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10346-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="10346-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="10346-135">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="10346-135">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="10346-136">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="10346-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="10346-137">Compile la solución Postajaxservice. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="10346-137">Build the solution XmlAjaxService.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="10346-138">Vaya a `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (no abra XmlAjaxClientPage.htm en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="10346-138">Navigate to `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (do not open XmlAjaxClientPage.htm in the browser from the project directory).</span></span>

## <a name="see-also"></a><span data-ttu-id="10346-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="10346-139">See also</span></span>

- [<span data-ttu-id="10346-140">Servicio AJAX mediante HTTP POST</span><span class="sxs-lookup"><span data-stu-id="10346-140">AJAX Service Using HTTP POST</span></span>](ajax-service-using-http-post.md)
