---
title: "Interoperabilidad con aplicaciones POX | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Interoperabilidad con aplicaciones POX
Las aplicaciones "XML sin formato” \(POX\) se comunican intercambiando mensajes sin formato HTTP que solo contienen los datos de la aplicación XML que no se encuentran dentro de un sobre SOAP.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puede proporcionar servicios y clientes que usan mensajes POX.En el servicio, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar para implementar servicios que exponen extremos a clientes como exploradores web y lenguajes de script que envían y reciben mensajes POX.En el cliente, el modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar para implementar clientes que se comuniquen con servicios basados en POX.  
  
> [!NOTE]
>  Este documento se redactó inicialmente para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5 integra compatibilidad para trabajar con aplicaciones POX.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] vea [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
  
## Programación POX con WCF  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se comunican sobre HTTP mediante mensajes POX utilizan un [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
```  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
  
```  
  
 Este enlace personalizado contiene dos elementos:  
  
-   El [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) y  
  
-   [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
 El codificador de mensajes de texto de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar se configura especialmente para utilizar el valor <xref:System.ServiceModel.Channels.MessageVersion.None%2A>, que le permite procesar cargas útiles de mensajes XML que no llegan ajustadas dentro de una envoltura SOAP.  
  
 Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se comunican sobre HTTP mediante mensajes POX utilizan un enlace similar \(mostrado en el código imperativo siguiente\).  
  
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
  
 Dado que los clientes POX deben especificar explícitamente los URI a los que envían los mensajes, normalmente deben configurar <xref:System.ServiceModel.Channels.HttpTransportBindingElement> como un modo de direccionamiento manual estableciendo la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> en `true` en el elemento.Esto permite direccionar los mensajes explícitamente mediante código de aplicación y no es necesario para crear un nuevo <xref:System.ServiceModel.ChannelFactory> cada vez que una aplicación envía un mensaje a un URI HTTP diferente.  
  
 Dado que los mensajes POX no utilizan encabezados SOAP para llevar información protocolar importante, los clientes y servicios POX a menudo deben manipular partes de la solicitud HTTP subyacente utilizada para enviar o recibir un mensaje.La información protocolar específica de HTTP, como los encabezados HTTP y los códigos de estado aparecen en el modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a través de dos clases:  
  
-   <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, que contiene información sobre la solicitud HTTP, como el método HTTP y los encabezados de la solicitud.  
  
-   <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, que contiene información sobre la respuesta HTTP, como el código de estado HTTP y la descripción del estado, así como cualquier encabezado de respuesta HTTP.  
  
 El ejemplo de código siguiente muestra cómo crear un mensaje de solicitud HTTP GET que se dirija a http:\/\/localhost:8100\/customers.  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = “http://localhost:8100/customers”;  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = “GET”;  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 Primero, se crea un <xref:System.ServiceModel.Channels.Message> de solicitud vacío llamando a <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.El parámetro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> se utiliza para indicar que no se requiere una envoltura SOAP y el parámetro <xref:System.String.Empty> se pasa como la Acción.El mensaje de solicitud se direcciona a continuación estableciendo el encabezad <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> en el URI deseado.Luego, se crea una <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> se establece en el método de verbo HTTP GET y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> se establece en `true` para indicar que no se deberían enviar datos en el cuerpo del mensaje de la solicitud HTTP de salida.Finalmente, la propiedad de solicitud se agrega así a la colección <xref:System.ServiceModel.Channels.Message.Properties%2A> del mensaje de solicitud para que pueda influenciar en la forma en la que el Transporte HTTP envía la solicitud.El mensaje está listo para su envío sobre una instancia adecuada de <xref:System.ServiceModel.Channels.IRequestChannel>.  
  
 Se pueden utilizar técnicas similares en el servicio para extraer la <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> de un mensaje entrante y construir una respuesta.