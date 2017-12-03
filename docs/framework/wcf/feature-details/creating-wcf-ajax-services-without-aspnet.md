---
title: "Creación de servicios AJAX WCF sin ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4ff3e41608c9b879bd64e004fcae5e87599e0b4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="7bf8c-102">Creación de servicios AJAX WCF sin ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7bf8c-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="7bf8c-103">Se puede tener acceso a los servicios AJAX de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] desde cualquier página web con JavaScript habilitado, sin necesidad de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="7bf8c-104">En este tema se describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf8c-104">This topic describes how to create such a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="7bf8c-105">Para obtener instrucciones sobre el uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, vea [crear servicios de WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="7bf8c-105">For instructions on using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="7bf8c-106">Para crear un servicio AJAX  de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] existen tres partes:</span><span class="sxs-lookup"><span data-stu-id="7bf8c-106">There are three parts to a creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX service:</span></span>  
  
-   <span data-ttu-id="7bf8c-107">Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
-   <span data-ttu-id="7bf8c-108">Creación de un contrato de servicios compatible con AJAX.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-108">Creating an AJAX-compatible service contract.</span></span>  
  
-   <span data-ttu-id="7bf8c-109">Acceso a servicios de AJAX de WCF.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="7bf8c-110">Creación de un extremo de AJAX</span><span class="sxs-lookup"><span data-stu-id="7bf8c-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="7bf8c-111">La manera más simple de habilitar la compatibilidad de AJAX en un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste en utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> en el archivo .svc asociado al servicio, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-111">The most basic way to enable AJAX support in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="7bf8c-112">Por otra parte, también puede utilizar la configuración para agregar un extremo de AJAX.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="7bf8c-113">Utilice el <xref:System.ServiceModel.WebHttpBinding> en el extremo de servicio y configure ese extremo con <xref:System.ServiceModel.Description.WebHttpBehavior>, tal y como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="7bf8c-114">Para obtener un ejemplo, vea el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7bf8c-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="7bf8c-115">Creación de un contrato de servicios compatible con AJAX</span><span class="sxs-lookup"><span data-stu-id="7bf8c-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="7bf8c-116">De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="7bf8c-117">Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del punto de conexión seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="7bf8c-118">Esta operación es accesible mediante una solicitud HTTP POST a `http://serviceaddress/endpointaddress/GetCities` y devolver un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="7bf8c-119">Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="7bf8c-120">Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7bf8c-121">el [modelo de programación de Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) tema.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-121"> the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="7bf8c-122">El formato de datos de JSON se utiliza a menudo en los servicios de AJAX.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="7bf8c-123">Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) en <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="7bf8c-124">El [de serialización JSON independiente](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) tema muestra cómo integradas .NET datos y tipos de contrato tipos asignación a JSON.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="7bf8c-125">Normalmente, las solicitudes y respuestas de JSON constan de un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="7bf8c-126">En la operación `GetCities` anterior, la solicitud se parece a la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```  
"na"  
```  
  
 <span data-ttu-id="7bf8c-127">La respuesta a esa solicitud se parece a la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-127">The response to that request resembles the following statement.</span></span>  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="7bf8c-128">Si la operación toma un parámetro adicional, el estilo de la solicitud debe ser ajustado para ajustar ambos parámetros en un objeto JSON único.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="7bf8c-129">A continuación se muestra un ejemplo de este mensaje JSON de estilo.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="7bf8c-130">El siguiente contrato acepta este mensaje.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-130">The following contract accepts this message.</span></span>  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="7bf8c-131">Acceso a servicios de AJAX</span><span class="sxs-lookup"><span data-stu-id="7bf8c-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="7bf8c-132">Los extremos de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre aceptan solicitudes JSON y XML.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-132">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="7bf8c-133">Las solicitudes HTTP POST con un tipo de contenido de "application/json" se tratan como JSON y aquellas cuyo tipo de contenido que indique XML (por ejemplo, "text/xml") se tratan como XML.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="7bf8c-134">Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="7bf8c-135">Depende del usuario decidir cómo crear la solicitud HTTP en el extremo.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="7bf8c-136">Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bf8c-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="7bf8c-137">Para obtener un ejemplo de creación de una solicitud de JavaScript, consulte el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7bf8c-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
