---
title: Uso de HttpClientFactory para implementar solicitudes HTTP resistentes
description: Aprenda a utilizar HttpClientFactory, disponible desde .NET Core 2.1, para crear instancias de `HttpClient`, lo que le facilita su uso en sus aplicaciones.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 73faa847dae2f844784ae5d85ce905b7e1e64cd0
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479820"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="6cf55-103">Uso de HttpClientFactory para implementar solicitudes HTTP resistentes</span><span class="sxs-lookup"><span data-stu-id="6cf55-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="6cf55-104">`HttpClientFactory` es una fábrica bien fundamentada, disponible desde .NET Core 2.1, para crear instancias de <xref:System.Net.Http.HttpClient> con el fin de usarlas en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6cf55-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="6cf55-105">Problemas con la clase HttpClient original disponible en .NET Core</span><span class="sxs-lookup"><span data-stu-id="6cf55-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="6cf55-106">La clase [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="6cf55-106">The original and well-known [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span> 

<span data-ttu-id="6cf55-107">Como primer problema, aunque esta clase es descartable, usarla con la instrucción `using` no es la mejor opción porque incluso cuando se descarta el objeto `HttpClient`, el socket subyacente no se libera de forma inmediata y puede causar un problema grave denominado "agotamiento de socket".</span><span class="sxs-lookup"><span data-stu-id="6cf55-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="6cf55-108">Para obtener más información sobre este problema, vea la entrada de blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Está usando HttpClient mal y eso desestabiliza el software).</span><span class="sxs-lookup"><span data-stu-id="6cf55-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="6cf55-109">Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6cf55-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="6cf55-110">Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas.</span><span class="sxs-lookup"><span data-stu-id="6cf55-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="6cf55-111">Ese problema generará errores `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="6cf55-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="6cf55-112">Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](/dotnet/csharp/tutorials/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="6cf55-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="6cf55-113">Pero hay un segundo problema con `HttpClient` que puede aparecer cuando se usa como objeto singleton o estático.</span><span class="sxs-lookup"><span data-stu-id="6cf55-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="6cf55-114">En este caso, un `HttpClient` singleton o estático no respeta los cambios de DNS, como se explica en este [problema en el repositorio de .NET Core de GitHub](https://github.com/dotnet/corefx/issues/11224).</span><span class="sxs-lookup"><span data-stu-id="6cf55-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="6cf55-115">Para resolver esos problemas mencionados y facilitar la administración de las instancias de `HttpClient`, .NET Core 2.1 ofrece un nuevo `HttpClientFactory` que también se puede usar para implementar llamadas HTTP resistentes si se le integra Polly.</span><span class="sxs-lookup"><span data-stu-id="6cf55-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="6cf55-116">Qué es HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="6cf55-116">What is HttpClientFactory</span></span>

<span data-ttu-id="6cf55-117">`HttpClientFactory` está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="6cf55-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="6cf55-118">Proporcionar una ubicación central para denominar y configurar instancias lógicas de HttpClient.</span><span class="sxs-lookup"><span data-stu-id="6cf55-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="6cf55-119">Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.</span><span class="sxs-lookup"><span data-stu-id="6cf55-119">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="6cf55-120">Codifique el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.</span><span class="sxs-lookup"><span data-stu-id="6cf55-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="6cf55-121">`HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes.</span><span class="sxs-lookup"><span data-stu-id="6cf55-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="6cf55-122">Los clientes HTTP se registran en la fábrica y, además, se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.</span><span class="sxs-lookup"><span data-stu-id="6cf55-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="6cf55-123">Administre la duración de HttpClientMessageHandlers para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo.</span><span class="sxs-lookup"><span data-stu-id="6cf55-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="6cf55-124">Varias formas de usar HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="6cf55-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="6cf55-125">Hay varias formas de usar `HttpClientFactory` en la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6cf55-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="6cf55-126">Usar `HttpClientFactory` directamente.</span><span class="sxs-lookup"><span data-stu-id="6cf55-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="6cf55-127">Usar clientes con nombre.</span><span class="sxs-lookup"><span data-stu-id="6cf55-127">Use Named Clients</span></span>
- <span data-ttu-id="6cf55-128">Usar clientes con tipo.</span><span class="sxs-lookup"><span data-stu-id="6cf55-128">Use Typed Clients</span></span>
- <span data-ttu-id="6cf55-129">Usar clientes generados.</span><span class="sxs-lookup"><span data-stu-id="6cf55-129">Use Generated Clients</span></span>

<span data-ttu-id="6cf55-130">Por brevedad, en esta guía se muestra la manera más estructurada de usar `HttpClientFactory`, que consiste en utilizar Clientes con tipo (el modelo de agente de servicio), pero todas las opciones se documentan y se enumeran actualmente en este [artículo sobre el uso de HttpClientFactory](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="6cf55-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that's to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="6cf55-131">Cómo usar clientes con tipo con HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="6cf55-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="6cf55-132">Así pues, ¿qué es un "Cliente con tipo"?</span><span class="sxs-lookup"><span data-stu-id="6cf55-132">So, what's a "Typed Client"?</span></span> <span data-ttu-id="6cf55-133">Se trata sencillamente de un cliente `HttpClient` configurado por `DefaultHttpClientFactory` tras la inserción.</span><span class="sxs-lookup"><span data-stu-id="6cf55-133">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="6cf55-134">En el diagrama siguiente se muestra cómo se usan los clientes con tipo con `HttpClientFactory`:</span><span class="sxs-lookup"><span data-stu-id="6cf55-134">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Un servicio ClientService (usado por un controlador o código de cliente) utiliza un cliente HttpClient creado por la fábrica IHttpClientFactory registrada.](./media/image3.5.png)

<span data-ttu-id="6cf55-138">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="6cf55-138">**Figure 8-4**.</span></span> <span data-ttu-id="6cf55-139">Uso de HttpClientFactory con clases de cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="6cf55-139">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="6cf55-140">Primero, configure `HttpClientFactory` en su aplicación, agregando una referencia al paquete `Microsoft.Extensions.Http` que incluye el método de extensión `AddHttpClient()` para `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="6cf55-140">First, setup `HttpClientFactory` in your application, adding a reference to the `Microsoft.Extensions.Http` package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="6cf55-141">Este método de extensión registra el `DefaultHttpClientFactory` que se va a usar como singleton para la interfaz `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="6cf55-141">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="6cf55-142">Define una configuración transitoria para `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="6cf55-142">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="6cf55-143">Este controlador de mensajes (el objeto `HttpMessageHandler`), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.</span><span class="sxs-lookup"><span data-stu-id="6cf55-143">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="6cf55-144">En el código siguiente, puede ver cómo se puede `AddHttpClient()` utilizar para registrar clientes con tipo (agentes de servicio) que necesitan usar `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="6cf55-144">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="6cf55-145">Al registrarse los servicios cliente como se muestra en el código anterior, la fábrica `DefaultClientFactory` crea un cliente `HttpClient` configurado específicamente para cada servicio, como explicaremos en el párrafo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6cf55-145">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create an `HttpClient` configured specifically for each service, as we'll explain in the next paragraph.</span></span>

<span data-ttu-id="6cf55-146">Solo registrando su clase de servicio cliente con `AddHttpClient()`, el objeto `HttpClient` que se insertará en su clase usará la configuración y las directivas proporcionadas tras el registro.</span><span class="sxs-lookup"><span data-stu-id="6cf55-146">Just by registering your client service class with `AddHttpClient()`, the `HttpClient` object that will be injected into your class will use the configuration and policies provided upon registration.</span></span> <span data-ttu-id="6cf55-147">En las secciones siguientes, se verán esas directivas, como los reintentos o los interruptores de Polly.</span><span class="sxs-lookup"><span data-stu-id="6cf55-147">In the next sections, you'll see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="6cf55-148">Duraciones de HttpClient</span><span class="sxs-lookup"><span data-stu-id="6cf55-148">HttpClient lifetimes</span></span>

<span data-ttu-id="6cf55-149">Cada vez que se obtiene un objeto `HttpClient` de `IHttpClientFactory`, se devuelve una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="6cf55-149">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="6cf55-150">Pero cada cliente `HttpClient` usa un controlador `HttpMessageHandler` que `IHttpClientFactory` agrupa y vuelve a usar para reducir el consumo de recursos, siempre y cuando la vigencia de `HttpMessageHandler`no haya expirado.</span><span class="sxs-lookup"><span data-stu-id="6cf55-150">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="6cf55-151">La agrupación de controladores es conveniente porque cada controlador suele administrar sus propias conexiones HTTP subyacentes. Crear más controladores de lo necesario puede provocar retrasos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="6cf55-151">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="6cf55-152">Además, algunos controladores dejan las conexiones abiertas de forma indefinida, lo que puede ser un obstáculo a la hora de reaccionar ante los cambios de DNS.</span><span class="sxs-lookup"><span data-stu-id="6cf55-152">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="6cf55-153">Los objetos `HttpMessageHandler` del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de `HttpMessageHandler` en el grupo.</span><span class="sxs-lookup"><span data-stu-id="6cf55-153">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="6cf55-154">El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="6cf55-154">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="6cf55-155">Para ello, llame a `SetHandlerLifetime()` en el `IHttpClientBuilder` que se devuelve cuando se crea el cliente, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="6cf55-155">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="6cf55-156">Cada cliente con tipo puede tener configurado su propio valor de duración de controlador.</span><span class="sxs-lookup"><span data-stu-id="6cf55-156">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="6cf55-157">Establezca la duración en `InfiniteTimeSpan` para deshabilitar la expiración del controlador.</span><span class="sxs-lookup"><span data-stu-id="6cf55-157">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="6cf55-158">Implementar las clases de cliente con tipo que usan el HttpClient insertado y configurado</span><span class="sxs-lookup"><span data-stu-id="6cf55-158">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="6cf55-159">Como paso anterior, debe tener las clases de cliente con tipo definidas, como las del código de ejemplo (por ejemplo, "BasketService", "CatalogService", "OrderingService", etc.). Un cliente con tipo es una clase que acepta un objeto `HttpClient` (insertado a través de su constructor) y lo usa para llamar a algún servicio remoto de HTTP.</span><span class="sxs-lookup"><span data-stu-id="6cf55-159">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="6cf55-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6cf55-160">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take, 
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl, 
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="6cf55-161">El cliente con tipo (CatalogService en el ejemplo) se activa mediante la inserción de dependencias, lo que significa que puede aceptar cualquier servicio registrado en su constructor, además de HttpClient.</span><span class="sxs-lookup"><span data-stu-id="6cf55-161">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="6cf55-162">Un cliente con tipo es, de hecho, un objeto transitorio, lo que significa que se crea una instancia cada vez que se necesita una y que recibirá una instancia de `HttpClient` nueva cada vez se construya.</span><span class="sxs-lookup"><span data-stu-id="6cf55-162">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="6cf55-163">Pero los objetos HttpMessageHandler del grupo son los que reutilizan varias solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="6cf55-163">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="6cf55-164">Usar las clases de cliente con tipo</span><span class="sxs-lookup"><span data-stu-id="6cf55-164">Use your Typed Client classes</span></span>

<span data-ttu-id="6cf55-165">Por último, una vez implementadas las clases de tipo y después de registrarlas con AddHttpClient(), se pueden usar en cualquier lugar donde haya servicios insertados mediante la inserción de dependencias, por ejemplo en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="6cf55-165">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) => 
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied, 
                                               int? TypesFilterApplied, 
                                               int? page, 
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0, 
                                                            itemsPage, 
                                                            BrandFilterApplied, 
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="6cf55-166">Hasta el momento, el código que se ha mostrado solo realiza solicitudes HTTP convencionales, pero la "magia" aparecerá en las secciones siguientes donde, con tan solo agregar directivas y controladores de delegación a los clientes con tipo registrados, todas las solicitudes HTTP que `HttpClient` va a realizar se comportarán teniendo en cuenta las directivas de resistencia como los reintentos con retroceso exponencial, los interruptores o cualquier otro controlador de delegación personalizado para implementar características de seguridad adicionales, como el uso de tokens de autenticación, o bien cualquier otra característica personalizada.</span><span class="sxs-lookup"><span data-stu-id="6cf55-166">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="6cf55-167">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6cf55-167">Additional resources</span></span>

- <span data-ttu-id="6cf55-168">**Uso de HttpClientFactory en .NET Core**\\</span><span class="sxs-lookup"><span data-stu-id="6cf55-168">**Using HttpClientFactory in .NET Core**\\</span></span>
  [*https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)

- <span data-ttu-id="6cf55-169">**Repositorio de HttpClientFactory en GitHub**\\</span><span class="sxs-lookup"><span data-stu-id="6cf55-169">**HttpClientFactory GitHub repo**\\</span></span>
  [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)

>[!div class="step-by-step"]
><span data-ttu-id="6cf55-170">[Anterior](explore-custom-http-call-retries-exponential-backoff.md)
>[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="6cf55-170">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>