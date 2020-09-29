---
title: Uso de IHttpClientFactory para implementar solicitudes HTTP resistentes
description: Aprenda a utilizar IHttpClientFactory, disponible a partir de .NET Core 2.1, para crear instancias de `HttpClient`, lo que le facilita su uso en sus aplicaciones.
ms.date: 08/31/2020
ms.openlocfilehash: ae093ef960b2540bf4916bf72ad3bec51fa33ebe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152577"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="9a8cc-103">Uso de IHttpClientFactory para implementar solicitudes HTTP resistentes</span><span class="sxs-lookup"><span data-stu-id="9a8cc-103">Use IHttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="9a8cc-104"><xref:System.Net.Http.IHttpClientFactory> es un contrato implementado por `DefaultHttpClientFactory`, una fábrica bien fundamentada disponible desde .NET Core 2.1 para crear instancias de <xref:System.Net.Http.HttpClient> con el fin de usarlas en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-104"><xref:System.Net.Http.IHttpClientFactory> is a contract implemented by `DefaultHttpClientFactory`, an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="9a8cc-105">Problemas con la clase HttpClient original disponible en .NET Core</span><span class="sxs-lookup"><span data-stu-id="9a8cc-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="9a8cc-106">La clase <xref:System.Net.Http.HttpClient> original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de manera correcta.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="9a8cc-107">Aunque esta clase implementa `IDisposable`, no se aconseja declarar y crear instancias de ella en una instrucción `using` porque, cuando el objeto `HttpClient` se desecha, el socket subyacente no se libera inmediatamente, lo que puede conducir a un problema de _agotamiento del socket_.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-107">Though this class implements `IDisposable`, declaring and instantiating it within a `using` statement is not preferred because when the `HttpClient` object gets disposed of, the underlying socket is not immediately released, which can lead to a _socket exhaustion_ problem.</span></span> <span data-ttu-id="9a8cc-108">Para obtener más información sobre este problema, vea la entrada de blog [Está usando HttpClient mal y eso desestabiliza el software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-108">For more information about this issue, see the blog post [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span></span>

<span data-ttu-id="9a8cc-109">Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="9a8cc-110">Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="9a8cc-111">Ese problema generará errores `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="9a8cc-112">Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span> <span data-ttu-id="9a8cc-113">Puede tratarse de una buena solución para las aplicaciones de consola de corta duración o elementos similares que se ejecutan varias veces al día.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-113">This can be a good solution for short-lived console apps or similar, that run a few times a day.</span></span>

<span data-ttu-id="9a8cc-114">Otra incidencia a la que los desarrolladores deben hacer frente es cuando se usa una instancia compartida de `HttpClient` en procesos de larga duración.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-114">Another issue that developers run into is when using a shared instance of `HttpClient` in long-running processes.</span></span> <span data-ttu-id="9a8cc-115">En una situación en la que se crean instancias del HttpClient como un singleton o un objeto estático, los cambios de DNS no se pueden controlar, tal y como se describe en esta [incidencia](https://github.com/dotnet/runtime/issues/18348) del repositorio de GitHub sobre dotnet/runtime.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-115">In a situation where the HttpClient is instantiated as a singleton or a static object, it fails to handle the DNS changes as described in this [issue](https://github.com/dotnet/runtime/issues/18348) of the dotnet/runtime GitHub repository.</span></span>

<span data-ttu-id="9a8cc-116">Realmente el problema no está en `HttpClient`, sino en el [constructor predeterminado de HttpClient](/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), ya que crea una instancia concreta de <xref:System.Net.Http.HttpMessageHandler>, que es la que plantea los problemas de *agotamiento de sockets* y los cambios de DNS mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-116">However, the issue isn't really with `HttpClient` per se, but with the [default constructor for HttpClient](/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), because it creates a new concrete instance of <xref:System.Net.Http.HttpMessageHandler>, which is the one that has *sockets exhaustion* and DNS changes issues mentioned above.</span></span>

<span data-ttu-id="9a8cc-117">Para solucionar estos problemas y hacer que las instancias de `HttpClient` se puedan administrar, .NET Core 2.1 ha incorporado la interfaz <xref:System.Net.Http.IHttpClientFactory>, que se puede usar para configurar y crear instancias de `HttpClient` en una aplicación a través de la inserción de dependencias (DI).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-117">To address the issues mentioned above and to make `HttpClient` instances manageable, .NET Core 2.1 introduced the <xref:System.Net.Http.IHttpClientFactory> interface which can be used to configure and create `HttpClient` instances in an app through Dependency Injection (DI).</span></span> <span data-ttu-id="9a8cc-118">También proporciona extensiones para el middleware basado en Polly a fin de aprovechar los controladores de delegación en HttpClient.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-118">It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span></span>

<span data-ttu-id="9a8cc-119">[Polly](http://www.thepollyproject.org/) es una biblioteca de control de errores transitorios que ayuda a los desarrolladores a agregar resistencia a sus aplicaciones mediante el uso de directivas predefinidas de manera fluida y segura para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-119">[Polly](http://www.thepollyproject.org/) is a transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="benefits-of-using-ihttpclientfactory"></a><span data-ttu-id="9a8cc-120">Ventajas de usar IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="9a8cc-120">Benefits of using IHttpClientFactory</span></span>

<span data-ttu-id="9a8cc-121">La implementación actual de <xref:System.Net.Http.IHttpClientFactory>, que también implementa <xref:System.Net.Http.IHttpMessageHandlerFactory>, reporta las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-121">The current implementation of <xref:System.Net.Http.IHttpClientFactory>, that also implements <xref:System.Net.Http.IHttpMessageHandlerFactory>, offers the following benefits:</span></span>

- <span data-ttu-id="9a8cc-122">Proporciona una ubicación central para denominar y configurar instancias lógicas de `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-122">Provides a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="9a8cc-123">Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-123">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="9a8cc-124">Codifica el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-124">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly's policies for resiliency.</span></span>
- <span data-ttu-id="9a8cc-125">`HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-125">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="9a8cc-126">Los clientes HTTP se pueden registrar en la fábrica y se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-126">You can register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="9a8cc-127">Administre la duración de <xref:System.Net.Http.HttpMessageHandler> para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-127">Manage the lifetime of <xref:System.Net.Http.HttpMessageHandler> to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!TIP]
> <span data-ttu-id="9a8cc-128">Las instancias de `HttpClient` insertadas mediante DI se pueden eliminar de forma segura, porque el elemento `HttpMessageHandler` asociado lo administra la fábrica.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-128">The `HttpClient` instances injected by DI, can be disposed of safely, because the associated `HttpMessageHandler` is managed by the factory.</span></span> <span data-ttu-id="9a8cc-129">En realidad, las instancias de `HttpClient` insertadas están *dentro del ámbito*, desde el punto de vista de DI.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-129">As a matter of fact, injected `HttpClient` instances are *Scoped* from a DI perspective.</span></span>

> [!NOTE]
> <span data-ttu-id="9a8cc-130">La implementación de `IHttpClientFactory` (`DefaultHttpClientFactory`) está estrechamente ligada a la implementación de la inserción de dependencias (DI) en el paquete de NuGet `Microsoft.Extensions.DependencyInjection`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-130">The implementation of `IHttpClientFactory` (`DefaultHttpClientFactory`) is tightly tied to the DI implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="9a8cc-131">Para obtener más información sobre cómo usar otros contenedores de inserción de dependencias, vea esta [conversación de GitHub](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-131">For more information about using other DI containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-ihttpclientfactory"></a><span data-ttu-id="9a8cc-132">Varias formas de usar IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="9a8cc-132">Multiple ways to use IHttpClientFactory</span></span>

<span data-ttu-id="9a8cc-133">Hay varias formas de usar `IHttpClientFactory` en la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-133">There are several ways that you can use `IHttpClientFactory` in your application:</span></span>

- <span data-ttu-id="9a8cc-134">Uso básico</span><span class="sxs-lookup"><span data-stu-id="9a8cc-134">Basic usage</span></span>
- <span data-ttu-id="9a8cc-135">Usar clientes con nombre.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-135">Use Named Clients</span></span>
- <span data-ttu-id="9a8cc-136">Usar clientes con tipo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-136">Use Typed Clients</span></span>
- <span data-ttu-id="9a8cc-137">Usar clientes generados.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-137">Use Generated Clients</span></span>

<span data-ttu-id="9a8cc-138">En pro de la brevedad, esta guía muestra la manera más estructurada para usar `IHttpClientFactory`, que consiste en usar clientes con tipo (el patrón de agente de servicio).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-138">For the sake of brevity, this guidance shows the most structured way to use `IHttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="9a8cc-139">Pero todas las opciones están documentadas e incluidas actualmente en este [artículo que trata sobre el uso de HttpClientFactory`IHttpClientFactory`](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-139">However, all options are documented and are currently listed in this [article covering the `IHttpClientFactory` usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a><span data-ttu-id="9a8cc-140">Cómo usar clientes con tipo con IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="9a8cc-140">How to use Typed Clients with IHttpClientFactory</span></span>

<span data-ttu-id="9a8cc-141">Así pues, ¿qué es un "Cliente con tipo"?</span><span class="sxs-lookup"><span data-stu-id="9a8cc-141">So, what's a "Typed Client"?</span></span> <span data-ttu-id="9a8cc-142">Es solo un elemento `HttpClient` que está preconfigurado para un uso específico.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-142">It's just an `HttpClient` that's pre-configured for some specific use.</span></span> <span data-ttu-id="9a8cc-143">Esta configuración puede incluir valores específicos como un servidor base, encabezados HTTP o tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-143">This configuration can include specific values such as the base server, HTTP headers or time outs.</span></span>

<span data-ttu-id="9a8cc-144">En el diagrama siguiente se muestra cómo se usan los clientes con tipo con `IHttpClientFactory`:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-144">The following diagram shows how Typed Clients are used with `IHttpClientFactory`:</span></span>

![Diagrama que muestra cómo se usan los clientes con tipo con IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="9a8cc-146">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-146">**Figure 8-4**.</span></span> <span data-ttu-id="9a8cc-147">Uso de `IHttpClientFactory` con clases de cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-147">Using `IHttpClientFactory` with Typed Client classes.</span></span>

<span data-ttu-id="9a8cc-148">En la imagen anterior, un servicio `ClientService` (usado por un controlador o código de cliente) utiliza un cliente `HttpClient` creado por la fábrica `IHttpClientFactory` registrada.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-148">In the above image, a `ClientService` (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="9a8cc-149">Este generador asigna a `HttpClient` un elemento `HttpMessageHandler` desde un grupo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-149">This factory assigns an `HttpMessageHandler` from a pool to the `HttpClient`.</span></span> <span data-ttu-id="9a8cc-150">El cliente `HttpClient` se puede configurar con las directivas de Polly al registrar la fábrica `IHttpClientFactory` en el contenedor de DI con el método de extensión <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-150">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.</span></span>

<span data-ttu-id="9a8cc-151">Para configurar la estructura anterior, agregue <xref:System.Net.Http.IHttpClientFactory> a la aplicación mediante la instalación del paquete de NuGet `Microsoft.Extensions.Http`, que incluye el método de extensión <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> para <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-151">To configure the above structure, add <xref:System.Net.Http.IHttpClientFactory> in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> extension method for <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="9a8cc-152">Este método de extensión registra la clase interna `DefaultHttpClientFactory` que se va a usar como singleton en la interfaz `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-152">This extension method registers the internal `DefaultHttpClientFactory` class to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="9a8cc-153">Define una configuración transitoria para <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-153">It defines a transient configuration for the <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span></span> <span data-ttu-id="9a8cc-154">Este controlador de mensajes (el objeto <xref:System.Net.Http.HttpMessageHandler>), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-154">This message handler (<xref:System.Net.Http.HttpMessageHandler> object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="9a8cc-155">En el código siguiente, puede ver cómo se puede `AddHttpClient()` utilizar para registrar clientes con tipo (agentes de servicio) que necesitan usar `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-155">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="9a8cc-156">Al registrar los servicios de cliente como se muestra en el código anterior, `DefaultClientFactory` crea un `HttpClient` estándar para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-156">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="9a8cc-157">También puede agregar una configuración específica de instancia en el registro para, por ejemplo, configurar la dirección base y agregar algunas directivas de resistencia, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-157">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="9a8cc-158">Solo para el ejemplo, puede ver una de las directivas anteriores en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-158">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="9a8cc-159">Puede encontrar más detalles sobre el uso de Polly en el [artículo siguiente](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="9a8cc-159">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="9a8cc-160">Duraciones de HttpClient</span><span class="sxs-lookup"><span data-stu-id="9a8cc-160">HttpClient lifetimes</span></span>

<span data-ttu-id="9a8cc-161">Cada vez que se obtiene un objeto `HttpClient` de `IHttpClientFactory`, se devuelve una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-161">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="9a8cc-162">Pero cada cliente `HttpClient` usa un controlador `HttpMessageHandler` que `IHttpClientFactory` agrupa y vuelve a usar para reducir el consumo de recursos, siempre y cuando la vigencia de `HttpMessageHandler`no haya expirado.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-162">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="9a8cc-163">La agrupación de controladores es conveniente porque cada controlador suele administrar sus propias conexiones HTTP subyacentes. Crear más controladores de lo necesario puede provocar retrasos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-163">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="9a8cc-164">Además, algunos controladores dejan las conexiones abiertas de forma indefinida, lo que puede ser un obstáculo a la hora de reaccionar ante los cambios de DNS.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-164">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="9a8cc-165">Los objetos `HttpMessageHandler` del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de `HttpMessageHandler` en el grupo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-165">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="9a8cc-166">El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-166">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="9a8cc-167">Para ello, llame a `SetHandlerLifetime()` en el <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> que se devuelve cuando se crea el cliente, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-167">To override it, call `SetHandlerLifetime()` on the <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="9a8cc-168">Cada cliente con tipo puede tener configurado su propio valor de duración de controlador.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-168">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="9a8cc-169">Establezca la duración en `InfiniteTimeSpan` para deshabilitar la expiración del controlador.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-169">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="9a8cc-170">Implementar las clases de cliente con tipo que usan el HttpClient insertado y configurado</span><span class="sxs-lookup"><span data-stu-id="9a8cc-170">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="9a8cc-171">Como paso anterior, debe tener las clases de cliente con tipo definidas, como las del código de ejemplo (por ejemplo, "BasketService", "CatalogService", "OrderingService", etc.). Un cliente con tipo es una clase que acepta un objeto `HttpClient` (insertado a través de su constructor) y lo usa para llamar a algún servicio remoto de HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-171">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like 'BasketService', 'CatalogService', 'OrderingService', etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="9a8cc-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-172">For example:</span></span>

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

<span data-ttu-id="9a8cc-173">El cliente con tipo (`CatalogService` en el ejemplo) se activa mediante DI (inserción de dependencias), lo que significa que puede aceptar cualquier servicio registrado en su constructor, además de `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-173">The Typed Client (`CatalogService` in the example) is activated by DI (Dependency Injection), that means it can accept any registered service in its constructor, in addition to `HttpClient`.</span></span>

<span data-ttu-id="9a8cc-174">Un cliente con tipo es realmente un objeto transitorio, lo que significa que, cada vez que se necesita uno, se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-174">A Typed Client is effectively a transient object, that means a new instance is created each time one is needed.</span></span> <span data-ttu-id="9a8cc-175">Recibe una nueva instancia de `HttpClient` cada vez que se construye.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-175">It receives a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="9a8cc-176">Pero los objetos `HttpMessageHandler` del grupo son los objetos que varias instancias de `HttpClient` reutilizan.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-176">However, the `HttpMessageHandler` objects in the pool are the objects that are reused by multiple `HttpClient` instances.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="9a8cc-177">Usar las clases de cliente con tipo</span><span class="sxs-lookup"><span data-stu-id="9a8cc-177">Use your Typed Client classes</span></span>

<span data-ttu-id="9a8cc-178">Por último, una vez que haya implementado las clases con tipo, puede registrarlas y configurarlas con `AddHttpClient()`.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-178">Finally, once you have your typed classes implemented, you can have them registered and configured with `AddHttpClient()`.</span></span> <span data-ttu-id="9a8cc-179">Después, puede usarlas dondequiera que los servicios se inserten mediante DI.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-179">After that you can use them wherever have services injected by DI.</span></span> <span data-ttu-id="9a8cc-180">por ejemplo, en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-180">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="9a8cc-181">Hasta ahora, el fragmento de código anterior solo ha mostrado el ejemplo de realizar solicitudes HTTP normales.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-181">Up to this point, the above code snippet has only shown the example of performing regular HTTP requests.</span></span> <span data-ttu-id="9a8cc-182">Pero la "magia" viene en las secciones siguientes, donde se muestra cómo todas las solicitudes HTTP que realiza `HttpClient` pueden tener directivas resistentes como, por ejemplo, reintentos con retroceso exponencial, disyuntores, características de seguridad que usan tokens de autenticación o incluso cualquier otra característica personalizada.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-182">But the 'magic' comes in the following sections where it shows how all the HTTP requests made by `HttpClient`, can have resilient policies such as retries with exponential backoff, circuit breakers, security features using auth tokens, or even any other custom feature.</span></span> <span data-ttu-id="9a8cc-183">Y todo esto se puede hacer simplemente agregando directivas y delegando controladores a los clientes con tipo registrados.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-183">And all of these can be done just by adding policies and delegating handlers to your registered Typed Clients.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a8cc-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9a8cc-184">Additional resources</span></span>

- <span data-ttu-id="9a8cc-185">**Uso de HttpClientFactory en .NET Core**</span><span class="sxs-lookup"><span data-stu-id="9a8cc-185">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="9a8cc-186">**Código fuente de HttpClientFactory en el repositorio de GitHub `dotnet/extensions`**</span><span class="sxs-lookup"><span data-stu-id="9a8cc-186">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="9a8cc-187">**Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**</span><span class="sxs-lookup"><span data-stu-id="9a8cc-187">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="9a8cc-188">**Uso de IHttpClientFactory sin inserción de dependencias (problema de GitHub)**</span><span class="sxs-lookup"><span data-stu-id="9a8cc-188">**Using IHttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="9a8cc-189">[Anterior](implement-resilient-entity-framework-core-sql-connections.md)
>[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="9a8cc-189">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
