---
title: Servicio AJAX con ejemplo JSON y XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 17b0fd362ac84c7fbc0c9e88fb3d318966356bc6
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836198"
---
# <a name="ajax-service-with-json-and-xml-sample"></a><span data-ttu-id="9d3d1-102">Servicio AJAX con ejemplo JSON y XML</span><span class="sxs-lookup"><span data-stu-id="9d3d1-102">AJAX Service with JSON and XML Sample</span></span>
<span data-ttu-id="9d3d1-103">Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript asincrónico y XML (AJAX) que devuelve datos JavaScript Object Notation (JSON) o XML.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an Asynchronous JavaScript and XML (AJAX) service that returns either JavaScript Object Notation (JSON) or XML data.</span></span> <span data-ttu-id="9d3d1-104">Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="9d3d1-105">En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="9d3d1-106">A diferencia de la otra muestra AJAX, este ejemplo no utiliza AJAX de ASP.NET ni el control <xref:System.Web.UI.ScriptManager>.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-106">Unlike the other AJAX samples, this sample does not use ASP.NET AJAX and the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="9d3d1-107">Con alguna configuración adicional, servicios de AJAX de WCF se pueden acceder desde cualquier página HTML a través de JavaScript y este escenario se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-107">With some additional configuration, WCF AJAX services can be accessed from any HTML page through JavaScript, and this scenario is shown here.</span></span> <span data-ttu-id="9d3d1-108">Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea [muestras de AJAX](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="9d3d1-108">For an example of using WCF with ASP.NET AJAX, see [AJAX Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>
  
 <span data-ttu-id="9d3d1-109">Este ejemplo muestra cómo intercambiar el tipo de respuesta de una operación entre JSON y XML.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-109">This sample shows how to switch the response type of an operation between JSON and XML.</span></span> <span data-ttu-id="9d3d1-110">Esta funcionalidad está disponible sin tener en cuenta si el servicio se configura para el acceso mediante AJAX de ASP.NET o una página de cliente de HTML/JavaScript.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-110">This functionality is available regardless of whether the service is configured to be accessed by ASP.NET AJAX or by an HTML/JavaScript client page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d3d1-111">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>
  
<span data-ttu-id="9d3d1-112">Para habilitar el uso de los clientes de AJAX de ASP.NET, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (no <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) en el archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-112">To enable the use of non-ASP.NET AJAX clients, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (not <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in the .svc file.</span></span> <span data-ttu-id="9d3d1-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> agrega un extremo <xref:System.ServiceModel.Description.WebHttpEndpoint> estándar al servicio.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> adds a <xref:System.ServiceModel.Description.WebHttpEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="9d3d1-114">El extremo se configura en una dirección vacía relativa al archivo .svc; Esto significa que la dirección del servicio es `http://localhost/ServiceModelSamples/service.svc`, sin ningún sufijo adicional que no sea el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-114">The endpoint is configured at an empty address relative to the .svc file; this means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>  
  
```svc
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 <span data-ttu-id="9d3d1-115">La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-115">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="9d3d1-116">Se puede quitar si no se necesita ningún cambio adicional.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-116">It can be removed if no extra changes are needed.</span></span>  
  
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
  
 <span data-ttu-id="9d3d1-117">Para dar formato a los datos predeterminados <xref:System.ServiceModel.Description.WebHttpEndpoint> es XML, mientras que el formato de datos predeterminado para <xref:System.ServiceModel.Description.WebScriptEndpoint> es JSON.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-117">The default data format for <xref:System.ServiceModel.Description.WebHttpEndpoint> is XML, while the default data format for <xref:System.ServiceModel.Description.WebScriptEndpoint> is JSON.</span></span> <span data-ttu-id="9d3d1-118">Para obtener más información, consulte [crear los servicios AJAX WCF sin ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="9d3d1-118">For more information, see [Creating WCF AJAX Services without ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span></span>  
  
 <span data-ttu-id="9d3d1-119">El servicio en el ejemplo siguiente es un servicio WCF estándar con dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-119">The service in the following sample is a standard WCF service with two operations.</span></span> <span data-ttu-id="9d3d1-120">Ambas operaciones requieren el estilo de cuerpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> en <xref:System.ServiceModel.Web.WebGetAttribute> o los atributos <xref:System.ServiceModel.Web.WebInvokeAttribute>, que es concreto al comportamiento `webHttp` y no están afectados por el cambio de formato de JSON/XML.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-120">Both operations require the <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> body style on the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes, which is specific to the `webHttp` behavior and has no bearing on the JSON/XML data format switch.</span></span>  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 <span data-ttu-id="9d3d1-121">Se especifica el formato de la operación de respuesta como XML, que es el valor predeterminado para el [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-121">The response format for the operation is specified as XML, which is the default setting for the [\<webHttp>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="9d3d1-122">No obstante, es conveniente especificar de forma explícita al formato de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-122">However, it is good practice explicitly specify the response format.</span></span>  
  
 <span data-ttu-id="9d3d1-123">La otra operación utiliza el atributo `WebInvokeAttribute` y explícitamente especifica JSON en lugar de XML para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-123">The other operation uses the `WebInvokeAttribute` attribute and explicitly specifies JSON instead of XML for the response.</span></span>  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 <span data-ttu-id="9d3d1-124">Tenga en cuenta que en ambos casos las operaciones devuelven un tipo complejo, `MathResult`, que es un tipo de contrato de datos WCF estándar.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-124">Note that in both cases the operations return a complex type, `MathResult`, which is a standard WCF data contract type.</span></span>  
  
 <span data-ttu-id="9d3d1-125">La página Web cliente XmlAjaxClientPage.htm contiene código JavaScript que invoca una de las dos operaciones anteriores cuando el usuario hace clic en el **realizar cálculo (devuelve JSON)** o **realizar cálculo (devuelve XML)**  botones en la página.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-125">The client Web page XmlAjaxClientPage.htm contains JavaScript code that invokes one of the preceding two operations when the user clicks the **Perform calculation (return JSON)** or **Perform calculation (return XML)** buttons on the page.</span></span> <span data-ttu-id="9d3d1-126">El código para invocar el servicio construye un cuerpo de JSON y lo envía utilizando HTTP POST, de manera similar al ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-126">The code to invoke the service constructs a JSON body and sends it using HTTP POST.</span></span> <span data-ttu-id="9d3d1-127">La solicitud se crea manualmente en JavaScript, a diferencia de la [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo y los otros ejemplos utilizando AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-127">The request is created manually in JavaScript, unlike the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample and the other samples using ASP.NET AJAX.</span></span>  

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

 <span data-ttu-id="9d3d1-128">Cuando el servicio responde, la respuesta se muestra sin más procesamientos en un cuadro de texto en la página.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-128">When the service responds, the response is displayed without any further processing in a textbox on the page.</span></span> <span data-ttu-id="9d3d1-129">Esto se implementa a efectos de demostración para permitir que poder observar directamente los formatos de datos de JSON y XML utilizados.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-129">This is implemented for demonstration purposes to allow you to directly observe the XML and JSON data formats used.</span></span>  

```javascript
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```

> [!IMPORTANT]
>  <span data-ttu-id="9d3d1-130">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9d3d1-131">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9d3d1-132">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9d3d1-133">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9d3d1-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9d3d1-134">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d3d1-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9d3d1-135">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9d3d1-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9d3d1-136">Compile la solución Postajaxservice.sln tal como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9d3d1-136">Build the solution XmlAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9d3d1-137">Vaya a `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (no abra Xmlajaxclientpage.aspx en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="9d3d1-137">Navigate to `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (do not open XmlAjaxClientPage.htm in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3d1-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3d1-138">See Also</span></span>  
 [<span data-ttu-id="9d3d1-139">Servicio AJAX mediante HTTP POST</span><span class="sxs-lookup"><span data-stu-id="9d3d1-139">AJAX Service Using HTTP POST</span></span>](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
