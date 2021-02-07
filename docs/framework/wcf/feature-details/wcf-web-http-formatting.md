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
# <a name="wcf-web-http-formatting"></a>Formato HTTP Web de WCF

El modelo de programación web HTTP de WCF permite determinar dinámicamente el mejor formato para que una operación de servicio devuelva su respuesta. Dos métodos para determinar un formato adecuado se admiten: automático y explícito.  
  
## <a name="automatic-formatting"></a>Formato automático  

 Cuando se habilita, el formato automático elige el mejor formato en el que devolver la respuesta. Determina el mejor formato comprobando lo siguiente, en el orden indicado:  
  
1. Los tipos de medios en el encabezado Accept del mensaje de solicitud.  
  
2. El tipo de contenido del mensaje de solicitud.  
  
3. La configuración de formato predeterminado en la operación.  
  
4. La configuración de formato predeterminado en WebHttpBehavior.  
  
 Si el mensaje de solicitud contiene un encabezado Accept, la infraestructura Windows Communication Foundation (WCF) busca un tipo que admita. Si el encabezado `Accept` especifica prioridades para sus tipos de medios, éstas se respetan. Si no se encuentra ningún formato adecuado en el encabezado `Accept`, se utiliza el tipo de contenido del mensaje de solicitud. Si no se especifica ningún tipo de contenido adecuado, se utiliza la configuración de formato predeterminado para la operación. El formato predeterminado se establece con el parámetro `ResponseFormat` de los atributos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>. Si no se especifica un formato predeterminado en la operación, se utiliza el valor de propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>. El formato automático se basa en la propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>. Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar. La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores. La selección de formato automática puede habilitarse mediante programación o a través de la configuración. En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automática en código.  
  
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
  
 El formato automático también puede habilitarse a través de la configuración. Puede establecer la propiedad <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> directamente en <xref:System.ServiceModel.Description.WebHttpBehavior> o mediante <xref:System.ServiceModel.Description.WebHttpEndpoint>. En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automático en <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
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
  
 En el siguiente ejemplo, se muestra cómo habilitar la selección de formato automático mediante <xref:System.ServiceModel.Description.WebHttpEndpoint>.  
  
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
  
## <a name="explicit-formatting"></a>Formato explícito  

 Como su nombre indica, en el formato explícito, el desarrollador determina el mejor formato que se debe utilizar dentro del código de operación. Si el formato mejor es XML o JSON, el desarrollador de software establece la propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> en los campos <xref:System.ServiceModel.Web.WebMessageFormat.Xml> o <xref:System.ServiceModel.Web.WebMessageFormat.Json>. Si no se establece explícitamente la propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>, se usa el formato predeterminado de la operación.  
  
 En el siguiente ejemplo, se comprueba el parámetro de cadena de consulta de formato para buscar el formato que se debe utilizar. Si se ha especificado, establece el formato de la operación mediante <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.  
  
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
  
 Si necesita soportar formatos distintos de XML o JSON, defina la operación para que tenga un tipo de devolución de <xref:System.ServiceModel.Channels.Message>. Dentro del código de operación, determine el formato adecuado que se debe utilizar y, a continuación, cree un objeto <xref:System.ServiceModel.Channels.Message> mediante uno de los siguientes métodos:  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 Cada uno de estos métodos toma contenido y crea un mensaje con el formato adecuado. El método `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` se puede utilizarse para obtener una lista de formatos preferidos por el cliente ordenados por preferencia, de mayor a menor. El siguiente ejemplo muestra cómo utilizar `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` para determinar el formato que se debe utilizar y, a continuación, utiliza el método de creación de respuesta adecuado para crear el mensaje de respuesta.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
- [UriTemplate y UriTemplateTable](uritemplate-and-uritemplatetable.md)
- [Información general del modelo de programación web HTTP de WCF](wcf-web-http-programming-model-overview.md)
- [Modelo de objetos de programación web HTTP de WCF](wcf-web-http-programming-object-model.md)
