---
title: Uso de HttpClientFactory para implementar solicitudes HTTP resistentes
description: Aprenda a utilizar HttpClientFactory, disponible desde .NET Core 2.1, para crear instancias de `HttpClient`, lo que le facilita su uso en sus aplicaciones.
ms.date: 08/08/2019
ms.openlocfilehash: 1a6d65509d669166e73ad907b506bae7fa26536d
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900325"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="e7bcb-103">Uso de HttpClientFactory para implementar solicitudes HTTP resistentes</span><span class="sxs-lookup"><span data-stu-id="e7bcb-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="e7bcb-104">`HttpClientFactory` es una fábrica bien fundamentada, disponible desde .NET Core 2.1, para crear instancias de <xref:System.Net.Http.HttpClient> con el fin de usarlas en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="e7bcb-105">Problemas con la clase HttpClient original disponible en .NET Core</span><span class="sxs-lookup"><span data-stu-id="e7bcb-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="e7bcb-106">La clase <xref:System.Net.Http.HttpClient> original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de manera correcta.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="e7bcb-107">Como primer problema, aunque esta clase es descartable, usarla con la instrucción `using` no es la mejor opción porque incluso cuando se descarta el objeto `HttpClient`, el socket subyacente no se libera de forma inmediata y puede causar un problema grave denominado "agotamiento de socket".</span><span class="sxs-lookup"><span data-stu-id="e7bcb-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="e7bcb-108">Para obtener más información sobre este problema, vea la entrada de blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Está usando HttpClient mal y eso desestabiliza el software).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="e7bcb-109">Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="e7bcb-110">Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="e7bcb-111">Ese problema generará errores `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="e7bcb-112">Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="e7bcb-113">Pero hay un segundo problema con `HttpClient` que puede aparecer cuando se usa como objeto singleton o estático.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="e7bcb-114">En este caso, un `HttpClient` singleton o estático no respeta los cambios de DNS, tal como se explica en este [problema](https://github.com/dotnet/corefx/issues/11224) en el repositorio dotnet/corefx de GitHub.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="e7bcb-115">Para resolver esos problemas mencionados y facilitar la administración de las instancias de `HttpClient`, .NET Core 2.1 ofrece un nuevo `HttpClientFactory` que también se puede usar para implementar llamadas HTTP resistentes si se le integra Polly.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="e7bcb-116">[Polly](http://www.thepollyproject.org/) es una biblioteca de control de errores transitorios que ayuda a los desarrolladores a agregar resistencia a sus aplicaciones mediante el uso de directivas predefinidas de manera fluida y segura para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="e7bcb-117">Qué es HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7bcb-117">What is HttpClientFactory</span></span>

<span data-ttu-id="e7bcb-118">`HttpClientFactory` está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="e7bcb-119">Proporcionar una ubicación central para denominar y configurar instancias lógicas de `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="e7bcb-120">Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="e7bcb-121">Codifique el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="e7bcb-122">`HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="e7bcb-123">Los clientes HTTP se registran en la fábrica y se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="e7bcb-124">Administre la duración de `HttpClientMessageHandlers` para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="e7bcb-125">`HttpClientFactory` está estrechamente ligado a la implementación de la inserción de dependencias (DI) en el paquete de NuGet `Microsoft.Extensions.DependencyInjection`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-125">`HttpClientFactory` is tightly tied to the dependency injection (DI) implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="e7bcb-126">Para más información sobre el uso de otros contenedores de inserción de dependencias, consulte esta [conversación de GitHub](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-126">For more information about using other dependency injection containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="e7bcb-127">Varias formas de usar HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7bcb-127">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="e7bcb-128">Hay varias formas de usar `HttpClientFactory` en la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-128">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="e7bcb-129">Usar `HttpClientFactory` directamente.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-129">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="e7bcb-130">Usar clientes con nombre.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-130">Use Named Clients</span></span>
- <span data-ttu-id="e7bcb-131">Usar clientes con tipo.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-131">Use Typed Clients</span></span>
- <span data-ttu-id="e7bcb-132">Usar clientes generados.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-132">Use Generated Clients</span></span>

<span data-ttu-id="e7bcb-133">En pro de la brevedad, esta guía muestra la manera más estructurada para usar `HttpClientFactory`, que consiste en usar clientes con tipo (el patrón de agente de servicio).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-133">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="e7bcb-134">Sin embargo, todas las opciones están documentadas y actualmente se muestra en este [artículo que trata sobre el uso de HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-134">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="e7bcb-135">Cómo usar clientes con tipo con HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="e7bcb-135">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="e7bcb-136">Así pues, ¿qué es un "Cliente con tipo"?</span><span class="sxs-lookup"><span data-stu-id="e7bcb-136">So, what's a "Typed Client"?</span></span> <span data-ttu-id="e7bcb-137">Se trata sencillamente de un cliente `HttpClient` configurado por `DefaultHttpClientFactory` tras la inserción.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-137">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="e7bcb-138">En el diagrama siguiente se muestra cómo se usan los clientes con tipo con `HttpClientFactory`:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-138">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Diagrama que muestra cómo se usan los clientes con tipo con HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="e7bcb-140">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-140">**Figure 8-4**.</span></span> <span data-ttu-id="e7bcb-141">Uso de HttpClientFactory con clases de cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="e7bcb-142">En la imagen anterior, un servicio ClientService (usado por un controlador o código de cliente) utiliza un cliente `HttpClient` creado por la fábrica `IHttpClientFactory` registrada.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-142">In the above image, a ClientService (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="e7bcb-143">Este generador asigna a `HttpClient` un `HttpMessageHandler` de un grupo que administra.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-143">This factory assigns the `HttpClient` an `HttpMessageHandler` from a pool it manages.</span></span> <span data-ttu-id="e7bcb-144">El cliente `HttpClient` se puede configurar con las directivas de Polly al registrar la fábrica `IHttpClientFactory` en el contenedor de DI con el método de extensión `AddHttpClient`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-144">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method `AddHttpClient`.</span></span>

<span data-ttu-id="e7bcb-145">Para configurar la estructura anterior, agregue `HttpClientFactory` a la aplicación mediante la instalación del paquete de NuGet `Microsoft.Extensions.Http`, que incluye el método de extensión `AddHttpClient()` para `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-145">To configure the above structure, add `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="e7bcb-146">Este método de extensión registra el `DefaultHttpClientFactory` que se va a usar como singleton para la interfaz `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-146">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="e7bcb-147">Define una configuración transitoria para `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-147">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="e7bcb-148">Este controlador de mensajes (el objeto `HttpMessageHandler`), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-148">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="e7bcb-149">En el código siguiente, puede ver cómo se puede `AddHttpClient()` utilizar para registrar clientes con tipo (agentes de servicio) que necesitan usar `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-149">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="e7bcb-150">Al registrar los servicios de cliente como se muestra en el código anterior, `DefaultClientFactory` crea un `HttpClient` estándar para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-150">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="e7bcb-151">También puede agregar una configuración específica de instancia en el registro para, por ejemplo, configurar la dirección base y agregar algunas directivas de resistencia, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-151">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="e7bcb-152">Solo para el ejemplo, puede ver una de las directivas anteriores en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-152">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="e7bcb-153">Puede encontrar más detalles sobre el uso de Polly en el [artículo siguiente](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-153">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="e7bcb-154">Duraciones de HttpClient</span><span class="sxs-lookup"><span data-stu-id="e7bcb-154">HttpClient lifetimes</span></span>

<span data-ttu-id="e7bcb-155">Cada vez que se obtiene un objeto `HttpClient` de `IHttpClientFactory`, se devuelve una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-155">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="e7bcb-156">Pero cada cliente `HttpClient` usa un controlador `HttpMessageHandler` que `IHttpClientFactory` agrupa y vuelve a usar para reducir el consumo de recursos, siempre y cuando la vigencia de `HttpMessageHandler`no haya expirado.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-156">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="e7bcb-157">La agrupación de controladores es conveniente porque cada controlador suele administrar sus propias conexiones HTTP subyacentes. Crear más controladores de lo necesario puede provocar retrasos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-157">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="e7bcb-158">Además, algunos controladores dejan las conexiones abiertas de forma indefinida, lo que puede ser un obstáculo a la hora de reaccionar ante los cambios de DNS.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-158">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="e7bcb-159">Los objetos `HttpMessageHandler` del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de `HttpMessageHandler` en el grupo.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-159">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="e7bcb-160">El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-160">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="e7bcb-161">Para ello, llame a `SetHandlerLifetime()` en el `IHttpClientBuilder` que se devuelve cuando se crea el cliente, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-161">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="e7bcb-162">Cada cliente con tipo puede tener configurado su propio valor de duración de controlador.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-162">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="e7bcb-163">Establezca la duración en `InfiniteTimeSpan` para deshabilitar la expiración del controlador.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-163">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="e7bcb-164">Implementar las clases de cliente con tipo que usan el HttpClient insertado y configurado</span><span class="sxs-lookup"><span data-stu-id="e7bcb-164">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="e7bcb-165">Como paso anterior, debe tener las clases de cliente con tipo definidas, como las del código de ejemplo (por ejemplo, "BasketService", "CatalogService", "OrderingService", etc.). Un cliente con tipo es una clase que acepta un objeto `HttpClient` (insertado a través de su constructor) y lo usa para llamar a algún servicio remoto de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-165">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="e7bcb-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-166">For example:</span></span>

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

<span data-ttu-id="e7bcb-167">El cliente con tipo (CatalogService en el ejemplo) se activa mediante la inserción de dependencias, lo que significa que puede aceptar cualquier servicio registrado en su constructor, además de HttpClient.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-167">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="e7bcb-168">Un cliente con tipo es, de hecho, un objeto transitorio, lo que significa que se crea una instancia cada vez que se necesita una y que recibirá una instancia de `HttpClient` nueva cada vez se construya.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-168">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="e7bcb-169">Pero los objetos HttpMessageHandler del grupo son los que reutilizan varias solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-169">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="e7bcb-170">Usar las clases de cliente con tipo</span><span class="sxs-lookup"><span data-stu-id="e7bcb-170">Use your Typed Client classes</span></span>

<span data-ttu-id="e7bcb-171">Por último, una vez que las clases con tipo se implementan y se registran con `AddHttpClient()`, se pueden usar en cualquier lugar donde haya servicios insertados mediante la inserción de dependencias,</span><span class="sxs-lookup"><span data-stu-id="e7bcb-171">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="e7bcb-172">por ejemplo, en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-172">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="e7bcb-173">Hasta el momento, el código que se ha mostrado solo realiza solicitudes HTTP convencionales, pero la "magia" aparecerá en las secciones siguientes donde, con tan solo agregar directivas y controladores de delegación a los clientes con tipo registrados, todas las solicitudes HTTP que `HttpClient` va a realizar se comportarán teniendo en cuenta las directivas de resistencia como los reintentos con retroceso exponencial, los interruptores o cualquier otro controlador de delegación personalizado para implementar características de seguridad adicionales, como el uso de tokens de autenticación, o bien cualquier otra característica personalizada.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-173">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7bcb-174">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e7bcb-174">Additional resources</span></span>

- <span data-ttu-id="e7bcb-175">**Uso de HttpClientFactory en .NET Core**</span><span class="sxs-lookup"><span data-stu-id="e7bcb-175">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="e7bcb-176">**Código fuente de HttpClientFactory en el repositorio de GitHub `dotnet/extensions`**</span><span class="sxs-lookup"><span data-stu-id="e7bcb-176">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="e7bcb-177">**Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**</span><span class="sxs-lookup"><span data-stu-id="e7bcb-177">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="e7bcb-178">**Uso de HttpClientFactory sin inserción de dependencias (problema de GitHub)**</span><span class="sxs-lookup"><span data-stu-id="e7bcb-178">**Using HttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="e7bcb-179">[Anterior](explore-custom-http-call-retries-exponential-backoff.md)
>[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="e7bcb-179">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
