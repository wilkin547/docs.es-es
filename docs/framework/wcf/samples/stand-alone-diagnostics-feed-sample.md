---
title: Ejemplo de fuente de diagnósticos independientes
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: b4c3613656e0aec42c0d3f5cd7cde0af6540a69a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268253"
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="3a1a3-102">Ejemplo de fuente de diagnósticos independientes</span><span class="sxs-lookup"><span data-stu-id="3a1a3-102">Stand-Alone Diagnostics Feed Sample</span></span>

<span data-ttu-id="3a1a3-103">Este ejemplo muestra cómo crear una fuente RSS/Atom para la distribución con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3a1a3-103">This sample demonstrates how to create an RSS/Atom feed for syndication with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="3a1a3-104">Se trata de un programa básico de "Hola mundo" que muestra los conceptos básicos del modelo de objetos y cómo configurarlo en un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3a1a3-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="3a1a3-105">WCF modela las fuentes de distribución como operaciones de servicio que devuelven un tipo de datos Especial, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> .</span><span class="sxs-lookup"><span data-stu-id="3a1a3-105">WCF models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="3a1a3-106">Las instancias de <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> pueden serializar una fuente en los formatos RSS 2.0 y Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="3a1a3-107">El código de ejemplo siguiente muestra el contrato utilizado.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-107">The following sample code shows the contract used.</span></span>  
  
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
  
 <span data-ttu-id="3a1a3-108">La `GetProcesses` operación se anota con el <xref:System.ServiceModel.Web.WebGetAttribute> atributo que le permite controlar cómo WCF envía las solicitudes HTTP GET a las operaciones de servicio y especifica el formato de los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how WCF dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="3a1a3-109">Al igual que cualquier servicio WCF, las fuentes de distribución pueden hospedarse automáticamente en cualquier aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-109">Like any WCF service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="3a1a3-110">Los servicios de distribución requieren un enlace específico (<xref:System.ServiceModel.WebHttpBinding>) y un comportamiento del extremo específico (<xref:System.ServiceModel.Description.WebHttpBehavior>) para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="3a1a3-111">La nueva clase <xref:System.ServiceModel.Web.WebServiceHost> proporciona un API apropiado para crear estos puntos de conexión sin una configuración específica.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="3a1a3-112">También puede utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> desde un archivo .svc hospedado en IIS para proporcionar funcionalidad equivalente (esta técnica no está demostrada en este código de ejemplo).</span><span class="sxs-lookup"><span data-stu-id="3a1a3-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```xml
<% @ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 <span data-ttu-id="3a1a3-113">Dado que este servicio recibe las solicitudes que utilizan el HTTP GET estándar, puede utilizar cualquier cliente que reconozca RSS o Atom para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="3a1a3-114">Por ejemplo, puede ver la salida de este servicio navegando a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` en un explorador compatible con RSS.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-114">For example, you can view the output of this service by navigating to `http://localhost:8000/diagnostics/feed/?format=atom` or `http://localhost:8000/diagnostics/feed/?format=rss` in an RSS-aware browser.</span></span>
  
 <span data-ttu-id="3a1a3-115">También puede usar el [modo en que el modelo de objetos de sindicación de WCF se asigna a Atom y RSS](../feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) para leer datos sindicados y procesarlos mediante código imperativo.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
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
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="3a1a3-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a1a3-116">Set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="3a1a3-117">Asegúrese de que tiene el permiso de registro de dirección correcto para HTTP y HTTPS en el equipo, tal como se explica en el procedimiento de configuración de la [instalación de una sola vez para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a1a3-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3a1a3-118">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-118">Build the solution.</span></span>

3. <span data-ttu-id="3a1a3-119">Ejecución de la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-119">Run the console application.</span></span>

4. <span data-ttu-id="3a1a3-120">Mientras se ejecuta la aplicación de consola, vaya a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` use un explorador compatible con RSS.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-120">While the console application is running, navigate to `http://localhost:8000/diagnostics/feed/?format=atom` or `http://localhost:8000/diagnostics/feed/?format=rss` using an RSS-aware browser.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a1a3-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3a1a3-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3a1a3-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3a1a3-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="3a1a3-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a><span data-ttu-id="3a1a3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a1a3-125">See also</span></span>

- [<span data-ttu-id="3a1a3-126">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="3a1a3-126">WCF Web HTTP Programming Model</span></span>](../feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="3a1a3-127">Sindicación en WCF</span><span class="sxs-lookup"><span data-stu-id="3a1a3-127">WCF Syndication</span></span>](../feature-details/wcf-syndication.md)
