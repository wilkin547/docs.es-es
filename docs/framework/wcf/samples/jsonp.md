---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 6b5b42285539c2334bccaa04e1ba179d2cf0046c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183571"
---
# <a name="jsonp"></a><span data-ttu-id="1bf9b-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="1bf9b-102">JSONP</span></span>
<span data-ttu-id="1bf9b-103">En este ejemplo se muestra cómo admitir JSON con relleno (JSONP) en los servicios REST de WCF.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="1bf9b-104">JSONP es una convención usada para invocar scripts entre dominios generando las etiquetas de scripts en el documento actual.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="1bf9b-105">El resultado se devuelve en una función de devolución de llamada especificada.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="1bf9b-106">JSONP se basa en la `<script src="http://..." >` idea de que etiquetas como pueden evaluar scripts de cualquier dominio y el script recuperado por esas etiquetas se evalúa dentro de un ámbito en el que otras funciones ya pueden estar definidas.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1bf9b-107">Muestra</span><span class="sxs-lookup"><span data-stu-id="1bf9b-107">Demonstrates</span></span>
 <span data-ttu-id="1bf9b-108">Scripting a través de dominios con JSONP.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-108">Cross-domain scripting with JSONP.</span></span>

## <a name="discussion"></a><span data-ttu-id="1bf9b-109">Discusión</span><span class="sxs-lookup"><span data-stu-id="1bf9b-109">Discussion</span></span>
 <span data-ttu-id="1bf9b-110">El ejemplo incluye una página web que agrega dinámicamente un bloque de script una vez representada la página en el explorador.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="1bf9b-111">Este bloque de script llama a un servicio REST de WCF que tiene una sola operación: `GetCustomer`.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="1bf9b-112">El servicio REST de WCF devuelve el nombre y la dirección de un cliente ajustados en un nombre de función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="1bf9b-113">Cuando el servicio REST de WCF responde, se invoca la función de devolución de llamada en la página web con los datos del cliente y la función muestra los datos en la página web.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="1bf9b-114">El control ScriptManager de ASP.NET AJAX administra automáticamente la inyección de la etiqueta de script y la ejecución de la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="1bf9b-115">El patrón de uso es igual que el de todos los servidores proxy AJAX de ASP.NET, aunque incorpora una línea para habilitar JSONP, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="1bf9b-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 <span data-ttu-id="1bf9b-116">La página web puede llamar al servicio REST de WCF porque el servicio usa el objeto <xref:System.ServiceModel.Description.WebScriptEndpoint> con `crossDomainScriptAccessEnabled` establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="1bf9b-117">Ambas configuraciones se realizan en el archivo \<Web.config en el elemento system.serviceModel>.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 <span data-ttu-id="1bf9b-118">El ScriptManager administra la interacción con el servicio y oculta la complejidad de la implementación manual del acceso JSONP.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="1bf9b-119">Cuando `crossDomainScriptAccessEnabled` se `true` establece en y el formato de respuesta para una operación es JSON, la infraestructura WCF inspecciona el URI de la solicitud de un parámetro de cadena de consulta de devolución de llamada y ajusta la respuesta JSON con el valor del parámetro de cadena de consulta de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="1bf9b-120">En el ejemplo, la página web llama al servicio REST de WCF con el siguiente URI.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 <span data-ttu-id="1bf9b-121">Dado que el parámetro de cadena de una consulta de devolución de llamada tiene el valor `JsonPCallback`, el servicio WCF devuelve una respuesta JSONP que se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 <span data-ttu-id="1bf9b-122">Esta respuesta JSONP incluye los datos del cliente con formato JSON, ajustados con el nombre de la función de devolución de llamada que la página web solicitó.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="1bf9b-123">El ScriptManager ejecutará esta devolución de llamada utilizando una etiqueta de script para lograr la solicitud a través de los dominios y, a continuación, pasará el resultado al controlador onSuccess que se pasó a la operación GetCustomer del proxy AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>

 <span data-ttu-id="1bf9b-124">El ejemplo consta de dos ASP.NET aplicaciones web: una contiene solo un servicio WCF y otra contiene la página web .aspx, que llama al servicio.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="1bf9b-125">Al ejecutar la solución, Visual Studio 2012 hospedará los dos sitios web en puertos diferentes, lo que crea un entorno donde el servicio y el cliente viven en dominios diferentes.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-125">When running the solution, Visual Studio 2012 will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bf9b-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1bf9b-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1bf9b-128">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1bf9b-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1bf9b-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="1bf9b-130">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bf9b-130">To run the sample</span></span>  
  
1. <span data-ttu-id="1bf9b-131">Abra la solución para obtener el ejemplo de JSONP.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-131">Open the solution for the JSONP Sample.</span></span>  
  
2. <span data-ttu-id="1bf9b-132">Presione F5 `http://localhost:26648/JSONPClientPage.aspx` para iniciar en el navegador.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3. <span data-ttu-id="1bf9b-133">Tenga en cuenta que después de cargar la página, las entradas de texto para "Nombre" y "Dirección" se rellenan con valores.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="1bf9b-134">Estos valores se proporcionaron desde una llamada al servicio WCF después de que el explorador terminó de representar la página.</span><span class="sxs-lookup"><span data-stu-id="1bf9b-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>
