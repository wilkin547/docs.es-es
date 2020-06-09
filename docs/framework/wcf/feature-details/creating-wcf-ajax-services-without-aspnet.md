---
title: Creación de servicios AJAX WCF sin ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: b5f0f730f90227dcccc7e5ebf533d80a28f6e6eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599300"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="142d8-102">Creación de servicios AJAX WCF sin ASP.NET</span><span class="sxs-lookup"><span data-stu-id="142d8-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="142d8-103">Se puede tener acceso a los servicios AJAX de Windows Communication Foundation (WCF) desde cualquier página web habilitada para JavaScript, sin necesidad de ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="142d8-103">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="142d8-104">En este tema se describe cómo crear un servicio WCF de este tipo.</span><span class="sxs-lookup"><span data-stu-id="142d8-104">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="142d8-105">Para obtener instrucciones sobre el uso de WCF con ASP.NET AJAX, consulte [creación de servicios WCF para ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="142d8-105">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="142d8-106">Hay tres partes en la creación de un servicio WCF AJAX:</span><span class="sxs-lookup"><span data-stu-id="142d8-106">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="142d8-107">Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="142d8-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="142d8-108">Creación de un contrato de servicios compatible con AJAX.</span><span class="sxs-lookup"><span data-stu-id="142d8-108">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="142d8-109">Acceso a servicios de AJAX de WCF.</span><span class="sxs-lookup"><span data-stu-id="142d8-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="142d8-110">Creación de un extremo de AJAX</span><span class="sxs-lookup"><span data-stu-id="142d8-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="142d8-111">La forma más básica de habilitar la compatibilidad de AJAX en un servicio WCF es usar el <xref:System.ServiceModel.Activation.WebServiceHostFactory> en el archivo. SVC asociado al servicio, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="142d8-111">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```text
<%ServiceHost
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="142d8-112">Por otra parte, también puede utilizar la configuración para agregar un punto de conexión de AJAX.</span><span class="sxs-lookup"><span data-stu-id="142d8-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="142d8-113">Utilice el <xref:System.ServiceModel.WebHttpBinding> en el punto de conexión de servicio y configure ese punto de conexión con <xref:System.ServiceModel.Description.WebHttpBehavior>, tal y como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="142d8-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="142d8-114">Para obtener un ejemplo práctico, vea el [servicio AJAX con JSON y XML](../samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="142d8-114">For a working example, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="142d8-115">Creación de un contrato de servicios compatible con AJAX</span><span class="sxs-lookup"><span data-stu-id="142d8-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="142d8-116">De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML.</span><span class="sxs-lookup"><span data-stu-id="142d8-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="142d8-117">Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del punto de conexión seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="142d8-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="142d8-118">Se puede tener acceso a esta operación mediante una solicitud HTTP POST a `http://serviceaddress/endpointaddress/GetCities` y devolver un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="142d8-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="142d8-119">Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="142d8-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="142d8-120">Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas.</span><span class="sxs-lookup"><span data-stu-id="142d8-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="142d8-121">Para obtener más información, vea el tema sobre el [modelo de programación web http de WCF](wcf-web-http-programming-model.md) .</span><span class="sxs-lookup"><span data-stu-id="142d8-121">For more information, see the [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="142d8-122">El formato de datos de JSON se utiliza a menudo en los servicios de AJAX.</span><span class="sxs-lookup"><span data-stu-id="142d8-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="142d8-123">Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) en <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="142d8-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="142d8-124">En el tema de [serialización de JSON independiente](stand-alone-json-serialization.md) se muestra cómo se asignan los tipos y tipos de contrato de datos de .net integrados a JSON.</span><span class="sxs-lookup"><span data-stu-id="142d8-124">The [Stand-Alone JSON Serialization](stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="142d8-125">Normalmente, las solicitudes y respuestas de JSON constan de un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="142d8-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="142d8-126">En la operación `GetCities` anterior, la solicitud se parece a la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="142d8-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```json
"na"  
```  
  
 <span data-ttu-id="142d8-127">La respuesta a esa solicitud se parece a la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="142d8-127">The response to that request resembles the following statement.</span></span>  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="142d8-128">Si la operación toma un parámetro adicional, el estilo de la solicitud debe ser ajustado para ajustar ambos parámetros en un objeto JSON único.</span><span class="sxs-lookup"><span data-stu-id="142d8-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="142d8-129">A continuación se muestra un ejemplo de este mensaje JSON de estilo.</span><span class="sxs-lookup"><span data-stu-id="142d8-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="142d8-130">El siguiente contrato acepta este mensaje.</span><span class="sxs-lookup"><span data-stu-id="142d8-130">The following contract accepts this message.</span></span>  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="142d8-131">Acceso a servicios de AJAX</span><span class="sxs-lookup"><span data-stu-id="142d8-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="142d8-132">Los puntos de conexión de AJAX de WCF siempre aceptan solicitudes JSON y XML.</span><span class="sxs-lookup"><span data-stu-id="142d8-132">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="142d8-133">Las solicitudes HTTP POST con un tipo de contenido de "Application/JSON" se tratan como JSON y las que tienen el tipo de contenido que indica XML (por ejemplo, "text/xml") se tratan como XML.</span><span class="sxs-lookup"><span data-stu-id="142d8-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="142d8-134">Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.</span><span class="sxs-lookup"><span data-stu-id="142d8-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="142d8-135">Depende del usuario decidir cómo crear la solicitud HTTP en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="142d8-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="142d8-136">Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="142d8-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="142d8-137">Para obtener un ejemplo de cómo crear una solicitud desde JavaScript, vea el [servicio AJAX con JSON y XML](../samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="142d8-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>
