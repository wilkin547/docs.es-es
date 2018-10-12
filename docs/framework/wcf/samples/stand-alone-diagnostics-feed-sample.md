---
title: Ejemplo de fuente de diagnósticos independientes
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 6def1d02ed46675d98db115f77ac36bb9f9401de
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123558"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Ejemplo de fuente de diagnósticos independientes
Este ejemplo muestra cómo crear una fuente de distribución con Windows Communication Foundation (WCF) de RSS/Atom. Es un programa básico "Hola mundo" que muestra los aspectos básicos del modelo de objetos y cómo configurarlo en un servicio de Windows Communication Foundation (WCF).  
  
 WCF modela las fuentes de distribución como operaciones de servicio que devuelven un tipo de datos especiales <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Las instancias de <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> pueden serializar una fuente en los formatos RSS 2.0 y Atom 1.0. El código de ejemplo siguiente muestra el contrato utilizado.  
  
```  
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
  
 El `GetProcesses` operación se anota con el <xref:System.ServiceModel.Web.WebGetAttribute> solicita el atributo que le permite controlar cómo WCF envía HTTP GET para las operaciones del servicio y especificar el formato de los mensajes enviados.  
  
 Al igual que cualquier servicio WCF, las fuentes de distribución pueden ser alojada en cualquier aplicación administrada por el usuario. Los servicios de distribución requieren un enlace específico (<xref:System.ServiceModel.WebHttpBinding>) y un comportamiento del punto de conexión específico (<xref:System.ServiceModel.Description.WebHttpBehavior>) para funcionar correctamente. La nueva clase <xref:System.ServiceModel.Web.WebServiceHost> proporciona un API apropiado para crear estos extremos sin una configuración específica.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 También puede utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> desde un archivo .svc hospedado en IIS para proporcionar funcionalidad equivalente (esta técnica no está demostrada en este código de ejemplo).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Dado que este servicio recibe las solicitudes que utilizan el HTTP GET estándar, puede utilizar cualquier cliente que reconozca RSS o Atom para tener acceso al servicio. Por ejemplo, puede ver el resultado de este servicio yendo a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` en un explorador que reconozca RSS.
  
 También puede usar el [cómo the WCF Syndication objeto modelo se asigna a Atom y RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) para leer datos distribuidos y procesarlos mediante código imperativo.  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que tiene el permiso de registro de dirección derecha para HTTP y HTTPS en el equipo como se explica en el conjunto de instrucciones en [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución.  
  
3.  Ejecute la aplicación de consola.  
  
4.  Mientras se ejecuta la aplicación de consola, vaya a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` mediante un explorador que reconozca RSS.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>Vea también  
 [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Redifusión en WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
