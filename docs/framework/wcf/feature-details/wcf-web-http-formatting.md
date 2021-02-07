---
description: 'Más información acerca de: formato de Web HTTP de WCF'
title: Formato HTTP Web de WCF
ms.date: 03/30/2017
ms.assetid: e2414896-5463-41cd-b0a6-026a713eac2c
ms.openlocfilehash: 715c28635f097cb9f1a773aa3afb7a12faa9478c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752605"
---
# <a name="wcf-web-http-formatting"></a><span data-ttu-id="c789e-103">Formato HTTP Web de WCF</span><span class="sxs-lookup"><span data-stu-id="c789e-103">WCF Web HTTP formatting</span></span>

<span data-ttu-id="c789e-104">El modelo de programación web HTTP de WCF permite determinar dinámicamente el mejor formato para que una operación de servicio devuelva su respuesta.</span><span class="sxs-lookup"><span data-stu-id="c789e-104">The WCF Web HTTP programming model allows you to dynamically determine the best format for a service operation to return its response in.</span></span> <span data-ttu-id="c789e-105">Dos métodos para determinar un formato adecuado se admiten: automático y explícito.</span><span class="sxs-lookup"><span data-stu-id="c789e-105">Two methods for determining an appropriate format are supported: automatic and explicit.</span></span>  
  
## <a name="automatic-formatting"></a><span data-ttu-id="c789e-106">Formato automático</span><span class="sxs-lookup"><span data-stu-id="c789e-106">Automatic formatting</span></span>  

 <span data-ttu-id="c789e-107">Cuando se habilita, el formato automático elige el mejor formato en el que devolver la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c789e-107">When enabled, automatic formatting chooses the best format in which to return the response.</span></span> <span data-ttu-id="c789e-108">Determina el mejor formato comprobando lo siguiente, en el orden indicado:</span><span class="sxs-lookup"><span data-stu-id="c789e-108">It determines the best format by checking the following, in order:</span></span>  
  
1. <span data-ttu-id="c789e-109">Los tipos de medios en el encabezado Accept del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c789e-109">The media types in the request message’s Accept header.</span></span>  
  
2. <span data-ttu-id="c789e-110">El tipo de contenido del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c789e-110">The content-type of the request message.</span></span>  
  
3. <span data-ttu-id="c789e-111">La configuración de formato predeterminado en la operación.</span><span class="sxs-lookup"><span data-stu-id="c789e-111">The default format setting in the operation.</span></span>  
  
4. <span data-ttu-id="c789e-112">La configuración de formato predeterminado en WebHttpBehavior.</span><span class="sxs-lookup"><span data-stu-id="c789e-112">The default format setting in the WebHttpBehavior.</span></span>  
  
 <span data-ttu-id="c789e-113">Si el mensaje de solicitud contiene un encabezado Accept, la infraestructura Windows Communication Foundation (WCF) busca un tipo que admita.</span><span class="sxs-lookup"><span data-stu-id="c789e-113">If the request message contains an Accept header the Windows Communication Foundation (WCF) infrastructure searches for a type that it supports.</span></span> <span data-ttu-id="c789e-114">Si el encabezado `Accept` especifica prioridades para sus tipos de medios, éstas se respetan.</span><span class="sxs-lookup"><span data-stu-id="c789e-114">If the `Accept` header specifies priorities for its media types, they are honored.</span></span> <span data-ttu-id="c789e-115">Si no se encuentra ningún formato adecuado en el encabezado `Accept`, se utiliza el tipo de contenido del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c789e-115">If no suitable format is found in the `Accept` header, the content-type of the request message is used.</span></span> <span data-ttu-id="c789e-116">Si no se especifica ningún tipo de contenido adecuado, se utiliza la configuración de formato predeterminado para la operación.</span><span class="sxs-lookup"><span data-stu-id="c789e-116">If no suitable content-type is specified, the default format setting for the operation is used.</span></span> <span data-ttu-id="c789e-117">El formato predeterminado se establece con el parámetro `ResponseFormat` de los atributos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c789e-117">The default format is set with the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes.</span></span> <span data-ttu-id="c789e-118">Si no se especifica un formato predeterminado en la operación, se utiliza el valor de propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="c789e-118">If no default format is specified on the operation, the value of the <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A> property is used.</span></span> <span data-ttu-id="c789e-119">El formato automático se basa en la propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="c789e-119">Automatic formatting relies on the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property.</span></span> <span data-ttu-id="c789e-120">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="c789e-120">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="c789e-121">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c789e-121">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="c789e-122">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c789e-122">Automatic format selection can be enabled programmatically or through configuration.</span></span> <span data-ttu-id="c789e-123">En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automática en código.</span><span class="sxs-lookup"><span data-stu-id="c789e-123">The following example shows how to enable automatic format selection in code.</span></span>  
  
```csharp
// This code assumes the service name is MyService and the service contract is IMyContract
Uri baseAddress = new Uri("http://localhost:8000");  
  
WebServiceHost host = new WebServiceHost(typeof(MyService), baseAddress)  
try  
{  
   ServiceEndpoint sep = host.AddServiceEndpoint(typeof(IMyContract), new WebHttpBinding(), "");  
   // Check it see if the WebHttpBehavior already exists  
   WebHttpBehavior whb = sep.Behaviors.Find<WebHttpBehavior>();  
  
   if (whb != null)  
   {  
      whb.AutomaticFormatSelectionEnabled = true;  
   }  
   else  
   {  
      WebHttpBehavior webBehavior = new WebHttpBehavior();  
      webBehavior.AutomaticFormatSelectionEnabled = true;  
      sep.Behaviors.Add(webBehavior);  
   }  
         // Open host to start listening for messages  
   host.Open();
  
  // ...  
}  
  catch(CommunicationException ex)  
  {  
     Console.WriteLine("An exception occurred: " + ex.Message());  
  }  
```  
  
 <span data-ttu-id="c789e-124">El formato automático también puede habilitarse a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c789e-124">Automatic formatting can also be enabled through configuration.</span></span> <span data-ttu-id="c789e-125">Puede establecer la propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> directamente en <xref:System.ServiceModel.Description.WebHttpBehavior> o mediante <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="c789e-125">You can set the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property directly on the <xref:System.ServiceModel.Description.WebHttpBehavior> or using the <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span> <span data-ttu-id="c789e-126">En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automático en <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="c789e-126">The following example shows how to enable the automatic format selection on the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <endpointBehaviors>  
      <behavior>  
        <webHttp automaticFormatSelectionEnabled="true" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
      <standardEndpoint name="" helpEnabled="true" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c789e-127">En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automático mediante <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="c789e-127">The following example shows how to enable automatic format selection using <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
      <webHttpEndpoint>  
        <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
        <standardEndpoint name="" helpEnabled="true" automaticFormatSelectionEnabled="true"  />  
      </webHttpEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```  
  
## <a name="explicit-formatting"></a><span data-ttu-id="c789e-128">Formato explícito</span><span class="sxs-lookup"><span data-stu-id="c789e-128">Explicit formatting</span></span>  

 <span data-ttu-id="c789e-129">Como su nombre indica, en el formato explícito, el desarrollador determina el mejor formato que se debe utilizar dentro del código de operación.</span><span class="sxs-lookup"><span data-stu-id="c789e-129">As the name implies, in explicit formatting the developer determines the best format to use within the operation code.</span></span> <span data-ttu-id="c789e-130">Si el formato mejor es XML o JSON, el desarrollador de software establece la propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> en los campos <xref:System.ServiceModel.Web.WebMessageFormat.Xml> o <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="c789e-130">If the best format is XML or JSON the developer sets <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> to either <xref:System.ServiceModel.Web.WebMessageFormat.Xml> or <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="c789e-131">Si no se establece explícitamente la propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>, se usa el formato predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="c789e-131">If the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property is not explicitly set, then the operation’s default format is used.</span></span>  
  
 <span data-ttu-id="c789e-132">En el siguiente ejemplo, se comprueba el parámetro de cadena de consulta de formato para buscar el formato que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="c789e-132">The following example checks the format query string parameter for a format to use.</span></span> <span data-ttu-id="c789e-133">Si se ha especificado, establece el formato de la operación mediante <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span><span class="sxs-lookup"><span data-stu-id="c789e-133">If it has been specified, it sets the operation’s format using <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span></span>  
  
```csharp
public class Service : IService  
{  
    [WebGet]  
     public string EchoWithGet(string s)  
    {  
        // if a format query string parameter has been specified, set the response format to that. If no such
        // query string parameter exists the Accept header will be used
        string formatQueryStringValue = WebOperationContext.Current.IncomingRequest.UriTemplateMatch.QueryParameters["format"];  
        if (!string.IsNullOrEmpty(formatQueryStringValue))  
        {  
            if (formatQueryStringValue.Equals("xml", System.StringComparison.OrdinalIgnoreCase))  
            {
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Xml;
            }
            else if (formatQueryStringValue.Equals("json", System.StringComparison.OrdinalIgnoreCase))  
            {  
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Json;  
            }  
            else  
            {  
                throw new WebFaultException<string>($"Unsupported format '{formatQueryStringValue}'",   HttpStatusCode.BadRequest);
            }  
        }  
        return "You said " + s;  
    }  
```  
  
 <span data-ttu-id="c789e-134">Si necesita soportar formatos distintos de XML o JSON, defina la operación para que tenga un tipo de devolución de <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="c789e-134">If you need to support formats other than XML or JSON, define your operation to have a return type of <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="c789e-135">Dentro del código de operación, determine el formato adecuado que se debe utilizar y, a continuación, cree un objeto <xref:System.ServiceModel.Channels.Message> mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="c789e-135">Within the operation code, determine the appropriate format to use and then create a <xref:System.ServiceModel.Channels.Message> object using one of the following methods:</span></span>  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 <span data-ttu-id="c789e-136">Cada uno de estos métodos toma contenido y crea un mensaje con el formato adecuado.</span><span class="sxs-lookup"><span data-stu-id="c789e-136">Each of these methods takes content and creates a message with the appropriate format.</span></span> <span data-ttu-id="c789e-137">El método `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` se puede utilizarse para obtener una lista de formatos preferidos por el cliente ordenados por preferencia, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="c789e-137">The `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` method can be used to get a list of formats preferred by the client in order of decreasing preference.</span></span> <span data-ttu-id="c789e-138">El siguiente ejemplo muestra cómo utilizar `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` para determinar el formato que se debe utilizar y, a continuación, utiliza el método de creación de respuesta adecuado para crear el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c789e-138">The following example shows how to use `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` to determine the format to use and then uses the appropriate create response method to create the response message.</span></span>  
  
```csharp
public class Service : IService  
{  
    public Message EchoListWithGet(string list)  
    {  
        List<string> returnList = new List<string>(list.Split(new char[] { ',' }, StringSplitOptions.RemoveEmptyEntries));  
        IList<ContentType> acceptHeaderElements = WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements();  
        for (int x = 0; x < acceptHeaderElements.Count; x++)  
        {  
            string normalizedMediaType = acceptHeaderElements[x].MediaType.ToLowerInvariant();  
            switch (normalizedMediaType)  
            {  
                case "image/jpeg": return CreateJpegResponse(returnList);  
                case "application/xhtml+xml": return CreateXhtmlResponse(returnList);  
                case "application/atom+xml": return CreateAtom10Response(returnList);  
                case "application/xml": return CreateXmlResponse(returnList);  
                case "application/json": return CreateJsonResponse(returnList);  
          }  
    }  
  
    // Default response format is XML  
    return CreateXmlResponse(returnList);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c789e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c789e-139">See also</span></span>

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [<span data-ttu-id="c789e-140">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="c789e-140">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="c789e-141">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c789e-141">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="c789e-142">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="c789e-142">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="c789e-143">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="c789e-143">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
