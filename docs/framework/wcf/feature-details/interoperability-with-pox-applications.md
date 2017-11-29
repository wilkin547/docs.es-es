---
title: Interoperabilidad con aplicaciones POX
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6dbdd72dce196ea58550cff956a7b0e6fe0b1a73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="9f585-102">Interoperabilidad con aplicaciones POX</span><span class="sxs-lookup"><span data-stu-id="9f585-102">Interoperability with POX Applications</span></span>
<span data-ttu-id="9f585-103">"Plain Old XML" aplicaciones (POX) se comunican mediante el intercambio de mensajes HTTP sin formato que contienen solo datos de aplicación de XML que no se encuentran dentro de un sobre SOAP.</span><span class="sxs-lookup"><span data-stu-id="9f585-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="9f585-104"> puede proporcionar servicios y clientes que usan mensajes POX.</span><span class="sxs-lookup"><span data-stu-id="9f585-104"> can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="9f585-105">En el servicio, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar para implementar servicios que exponen extremos a clientes como exploradores web y lenguajes de script que envían y reciben mensajes POX.</span><span class="sxs-lookup"><span data-stu-id="9f585-105">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="9f585-106">En el cliente, el modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar para implementar clientes que se comuniquen con servicios basados en POX.</span><span class="sxs-lookup"><span data-stu-id="9f585-106">On the client, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f585-107">Este documento se redactó inicialmente para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="9f585-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]<span data-ttu-id="9f585-108"> 3.5 integra compatibilidad para trabajar con aplicaciones POX.</span><span class="sxs-lookup"><span data-stu-id="9f585-108"> 3.5 has built-in support for working with POX applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f585-109">vea [modelo de programación de Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span><span class="sxs-lookup"><span data-stu-id="9f585-109"> see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span></span>  
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="9f585-110">Programación POX con WCF</span><span class="sxs-lookup"><span data-stu-id="9f585-110">POX Programming with WCF</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9f585-111">servicios que se comunican a través de HTTP mediante el uso de mensajes POX un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9f585-111"> services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
```xml  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="9f585-112">Este enlace personalizado contiene dos elementos:</span><span class="sxs-lookup"><span data-stu-id="9f585-112">This custom binding contains two elements:</span></span>  
  
-   <span data-ttu-id="9f585-113">El [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) y</span><span class="sxs-lookup"><span data-stu-id="9f585-113">The [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) and</span></span>  
  
-   <span data-ttu-id="9f585-114">El [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="9f585-114">The [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
 <span data-ttu-id="9f585-115">El codificador de mensajes de texto de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar se configura especialmente para utilizar el valor <xref:System.ServiceModel.Channels.MessageVersion.None%2A>, que le permite procesar cargas útiles de mensajes XML que no llegan ajustadas dentro de una envoltura SOAP.</span><span class="sxs-lookup"><span data-stu-id="9f585-115">The standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>  
  
 <span data-ttu-id="9f585-116">Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se comunican sobre HTTP mediante mensajes POX utilizan un enlace similar (mostrado en el código imperativo siguiente).</span><span class="sxs-lookup"><span data-stu-id="9f585-116">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>  
  
```  
private static Binding CreatePoxBinding()  
{  
    TextMessageEncodingBindingElement encoder =   
    new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );  
    HttpTransportBindingElement transport = new HttpTransportBindingElement();  
    transport.ManualAddressing = true;  
    return new CustomBinding( new BindingElement[] { encoder, transport } );  
}   
```  
  
 <span data-ttu-id="9f585-117">Dado que los clientes POX deben especificar explícitamente los URI a los que envían los mensajes, normalmente deben configurar <xref:System.ServiceModel.Channels.HttpTransportBindingElement> como un modo de direccionamiento manual estableciendo la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> en `true` en el elemento.</span><span class="sxs-lookup"><span data-stu-id="9f585-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="9f585-118">Esto permite direccionar los mensajes explícitamente mediante código de aplicación y no es necesario para crear un nuevo <xref:System.ServiceModel.ChannelFactory> cada vez que una aplicación envía un mensaje a un URI HTTP diferente.</span><span class="sxs-lookup"><span data-stu-id="9f585-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>  
  
 <span data-ttu-id="9f585-119">Dado que los mensajes POX no utilizan encabezados SOAP para llevar información protocolar importante, los clientes y servicios POX a menudo deben manipular partes de la solicitud HTTP subyacente utilizada para enviar o recibir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="9f585-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="9f585-120">La información protocolar específica de HTTP, como los encabezados HTTP y los códigos de estado aparecen en el modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a través de dos clases:</span><span class="sxs-lookup"><span data-stu-id="9f585-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model through two classes:</span></span>  
  
-   <span data-ttu-id="9f585-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, que contiene información sobre la solicitud HTTP, como el método HTTP y los encabezados de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9f585-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>  
  
-   <span data-ttu-id="9f585-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, que contiene información sobre la respuesta HTTP, como el código de estado HTTP y la descripción del estado, así como cualquier encabezado de respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f585-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>  
  
 <span data-ttu-id="9f585-123">El ejemplo de código siguiente muestra cómo crear un mensaje de solicitud HTTP GET que se dirija a http://localhost:8100/customers.</span><span class="sxs-lookup"><span data-stu-id="9f585-123">The following code example shows how to create an HTTP GET request message that is addressed to http://localhost:8100/customers.</span></span>  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = "http://localhost:8100/customers";  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = "GET";  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 <span data-ttu-id="9f585-124">Primero, se crea un <xref:System.ServiceModel.Channels.Message> de solicitud vacío llamando a <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="9f585-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="9f585-125">El parámetro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> se utiliza para indicar que no se requiere una envoltura SOAP y el parámetro <xref:System.String.Empty> se pasa como la Acción.</span><span class="sxs-lookup"><span data-stu-id="9f585-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="9f585-126">El mensaje de solicitud se direcciona a continuación estableciendo el encabezad <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> en el URI deseado.</span><span class="sxs-lookup"><span data-stu-id="9f585-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="9f585-127">Luego, se crea una <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> se establece en el método de verbo HTTP GET y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> se establece en `true` para indicar que no se deberían enviar datos en el cuerpo del mensaje de la solicitud HTTP de salida.</span><span class="sxs-lookup"><span data-stu-id="9f585-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="9f585-128">Finalmente, la propiedad de solicitud se agrega así a la colección <xref:System.ServiceModel.Channels.Message.Properties%2A> del mensaje de solicitud para que pueda influenciar en la forma en la que el Transporte HTTP envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9f585-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="9f585-129">El mensaje está listo para su envío sobre una instancia adecuada de <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="9f585-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>  
  
 <span data-ttu-id="9f585-130">Se pueden utilizar técnicas similares en el servicio para extraer la <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> de un mensaje entrante y construir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="9f585-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
