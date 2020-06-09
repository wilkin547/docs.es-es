---
title: Interoperabilidad con aplicaciones POX
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: 64a6d850a32b14bc60cd43466e04b53a7a39be81
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579272"
---
# <a name="interoperability-with-pox-applications"></a>Interoperabilidad con aplicaciones POX

Las aplicaciones de "XML sin formato" (POX) se comunican mediante el intercambio de mensajes HTTP sin formato que contienen únicamente datos de aplicación XML que no se incluyen en una envoltura SOAP. Windows Communication Foundation (WCF) puede proporcionar servicios y clientes que utilizan mensajes POX. En el servicio, se puede usar WCF para implementar servicios que exponen puntos de conexión a clientes como exploradores Web y lenguajes de scripting que envían y reciben mensajes POX. En el cliente, el modelo de programación de WCF se puede usar para implementar los clientes que se comunican con los servicios basados en POX.  
  
> [!NOTE]
> Este documento se escribió originalmente para el .NET Framework 3,0.  .NET Framework 3,5 tiene compatibilidad integrada para trabajar con aplicaciones POX. Para obtener más información, consulte el [modelo de programación web http de WCF](wcf-web-http-programming-model.md).
  
## <a name="pox-programming-with-wcf"></a>Programación de POX con WCF

Los servicios WCF que se comunican a través de HTTP mediante mensajes POX utilizan un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

Este enlace personalizado contiene dos elementos:

- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md)

El codificador de mensajes de texto WCF estándar está configurado especialmente para utilizar el <xref:System.ServiceModel.Channels.MessageVersion.None%2A> valor, lo que permite procesar cargas de mensajes XML que no llegan en un sobre SOAP.

Los clientes de WCF que se comunican a través de HTTP mediante mensajes POX utilizan un enlace similar (que se muestra en el código imperativo siguiente).

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

Dado que los clientes POX deben especificar explícitamente los URI a los que envían los mensajes, normalmente deben configurar <xref:System.ServiceModel.Channels.HttpTransportBindingElement> como un modo de direccionamiento manual estableciendo la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> en `true` en el elemento. Esto permite direccionar los mensajes explícitamente mediante código de aplicación y no es necesario para crear un nuevo <xref:System.ServiceModel.ChannelFactory> cada vez que una aplicación envía un mensaje a un URI HTTP diferente.

Dado que los mensajes POX no utilizan encabezados SOAP para llevar información protocolar importante, los clientes y servicios POX a menudo deben manipular partes de la solicitud HTTP subyacente utilizada para enviar o recibir un mensaje. La información del protocolo específica de HTTP, como los encabezados HTTP y los códigos de estado, se muestran en el modelo de programación de WCF a través de dos clases:

- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, que contiene información sobre la solicitud HTTP, como el método HTTP y los encabezados de la solicitud.

- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, que contiene información sobre la respuesta HTTP, como el código de estado HTTP y la descripción del estado, así como cualquier encabezado de respuesta HTTP.
  
En el ejemplo de código siguiente se muestra cómo crear un mensaje de solicitud HTTP GET que se dirige a `http://localhost:8100/customers` .

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

Primero, se crea un <xref:System.ServiceModel.Channels.Message> de solicitud vacío llamando a <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>. El parámetro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> se utiliza para indicar que no se requiere una envoltura SOAP y el parámetro <xref:System.String.Empty> se pasa como la Acción. El mensaje de solicitud se direcciona a continuación estableciendo el encabezad <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> en el URI deseado. Luego, se crea una <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> se establece en el método de verbo HTTP GET y el <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> se establece en `true` para indicar que no se deberían enviar datos en el cuerpo del mensaje de la solicitud HTTP de salida. Finalmente, la propiedad de solicitud se agrega así a la colección <xref:System.ServiceModel.Channels.Message.Properties%2A> del mensaje de solicitud para que pueda influenciar en la forma en la que el Transporte HTTP envía la solicitud. El mensaje está listo para su envío sobre una instancia adecuada de <xref:System.ServiceModel.Channels.IRequestChannel>.

Se pueden utilizar técnicas similares en el servicio para extraer la <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> de un mensaje entrante y construir una respuesta.
