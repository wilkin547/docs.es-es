---
title: Cómo elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 0f7a221d1fd14b4a978683f008858e35cbd2df19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184757"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a><span data-ttu-id="6f8ff-102">Cómo elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6f8ff-102">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>

<span data-ttu-id="6f8ff-103">Windows Communication Foundation (WCF) permite crear un servicio que expone un extremo habilitado para ASP.NET AJAX que se puede llamar desde JavaScript en un sitio Web cliente.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="6f8ff-104">Los procedimientos básicos para crear estos servicios se describen en [Cómo: Usar la configuración para agregar un ASP.NET punto](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) de conexión de AJAX y Cómo: agregar un ASP.NET punto de conexión de AJAX [sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="6f8ff-104">The basic procedures for building such services is discussed in [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) and [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
 <span data-ttu-id="6f8ff-105">AJAX de ASP.NET admite operaciones que utilizan verbos HTTP POST y HTTP GET, donde HTTP POST es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-105">ASP.NET AJAX supports operations that use the HTTP POST and HTTP GET verbs, with HTTP POST being the default.</span></span> <span data-ttu-id="6f8ff-106">Si crea una operación que no tiene efectos secundarios y devuelve datos que raramente o nunca cambian, utilice HTTP GET en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-106">When creating an operation that has no side effects and returns data that rarely or never changes, use HTTP GET instead.</span></span> <span data-ttu-id="6f8ff-107">Los resultados de operaciones GET pueden almacenarse en memoria caché, lo que significa que varias llamadas a la misma operación solo pueden producir una solicitud a su servicio.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-107">Results of GET operations can be cached, which means that multiple calls to the same operation may result in only one request to your service.</span></span> <span data-ttu-id="6f8ff-108">WCF no realiza el almacenamiento en caché, pero puede tener lugar en cualquier nivel (en el explorador de un usuario, en un servidor proxy y otros niveles.) El almacenamiento en caché es ventajoso si desea aumentar el rendimiento del servicio, pero puede no ser aceptable si los datos cambian con frecuencia o si la operación realiza alguna acción.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-108">The caching is not done by WCF but can take place at any level (in a user's browser, on a proxy server, and other levels.) Caching is advantageous if you want to increase service performance, but may not be acceptable if data changes frequently or if the operation performs some action.</span></span>  
  
 <span data-ttu-id="6f8ff-109">Por ejemplo, si está diseñando un servicio para administrar la biblioteca de música de un usuario, una operación que busca al artista basándose en el título del álbum, se beneficia del uso de GET, pero una operación que agrega un álbum a la colección personal del usuario debe utilizar POST.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-109">For example, if you are designing service to manage a user's music library, an operation that looks up the artist based on an album's title benefits from using GET, but an operation that adds an album to the user's personal collection must use POST.</span></span>  
  
 <span data-ttu-id="6f8ff-110">Para controlar la duración de la caché, utilice el tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-110">To control the lifetime of the cache, use the <xref:System.ServiceModel.Web.OutgoingWebResponseContext> type.</span></span> <span data-ttu-id="6f8ff-111">Por ejemplo, al diseñar un servicio que devuelve los boletines de previsión meteorológica actualizados cada hora, utilizaría GET pero limitar la duración del almacenamiento en caché a una hora o menos para evitar que los usuarios del servicio tengan acceso a datos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-111">For example, when designing a service that returns weather forecasts updated hourly, you would use GET but limit the cache duration to an hour or less to prevent the users of the service from accessing stale data.</span></span>  
  
 <span data-ttu-id="6f8ff-112">Al utilizar los servicios en una página AJAX de ASP.NET que utiliza el control del administrador de scripts, no hay diferencia si la operación usa GET o POST, el mecanismo del administrador de scripts se asegurara de que se emita el tipo de petición correcto.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-112">When using services from an ASP.NET AJAX page that use the Script Manager control, it makes no difference whether the operation uses GET or POST - the script manager mechanism ensures that the correct request type is issued.</span></span>  
  
 <span data-ttu-id="6f8ff-113">Las operaciones GET y HTTP utilizan cualquier parámetro de entrada admitido por operaciones POST, incluso los datos complejos como los tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-113">HTTP GET operations use any input parameters supported by POST operations, including complex data contract types.</span></span> <span data-ttu-id="6f8ff-114">Sin embargo, en la mayoría de los casos se recomienda evitar demasiados parámetros o parámetros que son demasiado complejos en operaciones GET, porque se reduce la eficacia de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-114">However, in most cases it is recommended to avoid too many parameters or parameters that are too complex in GET operations because it reduces caching efficiency.</span></span>  
  
 <span data-ttu-id="6f8ff-115">En este tema se muestra cómo elegir entre GET y POST agregando atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> a las operaciones pertinentes en el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-115">This topic demonstrates how to select between GET and POST by adding the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to the relevant operations in the service contract.</span></span> <span data-ttu-id="6f8ff-116">Los otros pasos (para implementar, configurar y hospedar el servicio) que son necesarios para ejecutar el servicio son similares a los utilizados por cualquier servicio ASP.NET AJAX en WCF.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-116">The other steps (to implement, configure and host the service) that are required to get the service running are similar to those used by any ASP.NET AJAX service in WCF.</span></span>  
  
 <span data-ttu-id="6f8ff-117">Una operación marcada con <xref:System.ServiceModel.Web.WebGetAttribute> siempre usa una solicitud GET.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-117">An operation marked with the <xref:System.ServiceModel.Web.WebGetAttribute> always uses a GET request.</span></span> <span data-ttu-id="6f8ff-118">Una operación marcada con <xref:System.ServiceModel.Web.WebInvokeAttribute> o no marcada con ninguno de los dos atributos, usa una solicitud POST.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-118">An operation marked with the <xref:System.ServiceModel.Web.WebInvokeAttribute>, or not marked with any of the two attributes, uses a POST request.</span></span> <span data-ttu-id="6f8ff-119"><xref:System.ServiceModel.Web.WebInvokeAttribute> permite el uso de otros verbos HTTP, distintos de GET y POST (como PUT y DELETE) mediante la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-119">The <xref:System.ServiceModel.Web.WebInvokeAttribute> allows the use of other HTTP verbs, other than GET and POST (such as PUT and DELETE) through the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span> <span data-ttu-id="6f8ff-120">AJAX de ASP.NET no admite, sin embargo, estos verbos.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-120">However, these verbs are not supported by ASP.NET AJAX.</span></span> <span data-ttu-id="6f8ff-121">Si piensa utilizar el servicio desde páginas ASP.NET utilizando el control del administrador de scripts, no utilice la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-121">If you intend to use the service from ASP.NET pages using the Script Manager control, do not use the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span>  
  
 <span data-ttu-id="6f8ff-122">Para obtener un ejemplo de trabajo de cambio a GET, vea el ejemplo [de servicio AJAX básico.](../../../../docs/framework/wcf/samples/basic-ajax-service.md)</span><span class="sxs-lookup"><span data-stu-id="6f8ff-122">For a working example of switching to GET, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="6f8ff-123">Para obtener un ejemplo que usa POST, vea el [ejemplo AJAX Service Using HTTP POST.](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)</span><span class="sxs-lookup"><span data-stu-id="6f8ff-123">For a sample that uses POST, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a><span data-ttu-id="6f8ff-124">Creación de un servicio WCF que responda a solicitudes HTTP GET o HTTP POST</span><span class="sxs-lookup"><span data-stu-id="6f8ff-124">To create a WCF service that responds to HTTP GET or HTTP POST requests</span></span>
  
1. <span data-ttu-id="6f8ff-125">Defina un contrato de servicio WCF <xref:System.ServiceModel.ServiceContractAttribute> básico con una interfaz marcada con el atributo.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-125">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="6f8ff-126">Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-126">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="6f8ff-127">Agregue el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para estipular que una operación debería responder a las solicitudes HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-127">Add the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to stipulate that an operation should respond to HTTP GET requests.</span></span> <span data-ttu-id="6f8ff-128">También puede agregar el atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> para especificar explícitamente HTTP POST o no especificar un atributo, que tiene como valor predeterminado HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-128">You can also add the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute to explicitly specify HTTP POST, or not specify an attribute, which defaults to HTTP POST.</span></span>
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="6f8ff-129">Implemente el contrato de servicios `IMusicService` con un `MusicService`.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-129">Implement the `IMusicService` service contract with a `MusicService`.</span></span>
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. <span data-ttu-id="6f8ff-130">Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-130">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="6f8ff-131">Edite este archivo agregando la información de directiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-131">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="6f8ff-132">Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva ServiceHost para configurar automáticamente un ASP.NET extremo AJAX.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-132">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a><span data-ttu-id="6f8ff-133">Realización de llamadas al servicio</span><span class="sxs-lookup"><span data-stu-id="6f8ff-133">To call the service</span></span>  
  
1. <span data-ttu-id="6f8ff-134">Puede probar las operaciones GET de su servicio sin código de cliente, utilizando el examinador.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-134">You can test your service's GET operations without any client code, by using the browser.</span></span> <span data-ttu-id="6f8ff-135">Por ejemplo, si el servicio `http://example.com/service.svc` está configurado `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` en la dirección, al escribir en la barra de direcciones del explorador se invoca el servicio y se muestra la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-135">For example, if your service is configured at the `http://example.com/service.svc` address, then typing `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` into the browser address bar invokes the service and causes the response to be downloaded or displayed.</span></span>
  
2. <span data-ttu-id="6f8ff-136">Puede utilizar los servicios con operaciones GET de la misma manera que cualquier otro servicio de AJAX de ASP.NET: escribiendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6f8ff-136">You can use services with GET operations in the same way as any other ASP.NET AJAX services - by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="6f8ff-137">Para obtener un ejemplo, vea el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span><span class="sxs-lookup"><span data-stu-id="6f8ff-137">For an example, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f8ff-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f8ff-138">See also</span></span>

- [<span data-ttu-id="6f8ff-139">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6f8ff-139">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="6f8ff-140">Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="6f8ff-140">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
