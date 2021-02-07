---
description: 'Más información sobre: Stand-Alone ejemplo de fuente de diagnósticos'
title: Ejemplo de fuente de diagnósticos independientes
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 98fd65a44f9f6f0183b879627bd8eb444152a8ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668869"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Ejemplo de fuente de diagnósticos independientes

Este ejemplo muestra cómo crear una fuente RSS/Atom para la distribución con Windows Communication Foundation (WCF). Se trata de un programa básico de "Hola mundo" que muestra los conceptos básicos del modelo de objetos y cómo configurarlo en un servicio Windows Communication Foundation (WCF).  
  
 WCF modela las fuentes de distribución como operaciones de servicio que devuelven un tipo de datos Especial, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> . Las instancias de <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> pueden serializar una fuente en los formatos RSS 2.0 y Atom 1.0. El código de ejemplo siguiente muestra el contrato utilizado.  
  
```csharp  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 La `GetProcesses` operación se anota con el <xref:System.ServiceModel.Web.WebGetAttribute> atributo que le permite controlar cómo WCF envía las solicitudes HTTP GET a las operaciones de servicio y especifica el formato de los mensajes enviados.  
  
 Al igual que cualquier servicio WCF, las fuentes de distribución pueden hospedarse automáticamente en cualquier aplicación administrada. Los servicios de distribución requieren un enlace específico (<xref:System.ServiceModel.WebHttpBinding>) y un comportamiento del extremo específico (<xref:System.ServiceModel.Description.WebHttpBehavior>) para funcionar correctamente. La nueva clase <xref:System.ServiceModel.Web.WebServiceHost> proporciona un API apropiado para crear estos puntos de conexión sin una configuración específica.  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 También puede utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> desde un archivo .svc hospedado en IIS para proporcionar funcionalidad equivalente (esta técnica no está demostrada en este código de ejemplo).  
  
```xml
<% @ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 Dado que este servicio recibe las solicitudes que utilizan el HTTP GET estándar, puede utilizar cualquier cliente que reconozca RSS o Atom para tener acceso al servicio. Por ejemplo, puede ver la salida de este servicio navegando a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` en un explorador compatible con RSS.
  
 También puede usar el [modo en que el modelo de objetos de sindicación de WCF se asigna a Atom y RSS](../feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) para leer datos sindicados y procesarlos mediante código imperativo.  
  
```csharp
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",
    new XmlReaderSettings()
    {
        //MaxCharactersInDocument can be used to control the maximum amount of data
        //read from the reader and helps prevent OutOfMemoryException
        MaxCharactersInDocument = 1024 * 64
    } );

SyndicationFeed feed = SyndicationFeed.Load(reader);

foreach (SyndicationItem i in feed.Items)
{
    XmlSyndicationContent content = i.Content as XmlSyndicationContent;
    ProcessData pd = content.ReadContent<ProcessData>();

    Console.WriteLine(i.Title.Text);
    Console.WriteLine(pd.ToString());
}
```
  
## <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo
  
1. Asegúrese de que tiene el permiso de registro de dirección correcto para HTTP y HTTPS en el equipo, tal como se explica en el procedimiento de configuración de la [instalación de una sola vez para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compile la solución.

3. Ejecución de la aplicación de consola.

4. Mientras se ejecuta la aplicación de consola, vaya a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` use un explorador compatible con RSS.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](../feature-details/wcf-web-http-programming-model.md)
- [Sindicación en WCF](../feature-details/wcf-syndication.md)
