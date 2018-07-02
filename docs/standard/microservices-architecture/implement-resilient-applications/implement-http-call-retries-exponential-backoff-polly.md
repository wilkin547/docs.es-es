---
title: Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: cce1392bb381859e7cad89c9f2518113241ae724
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106936"
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="de2d3-103">Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly</span><span class="sxs-lookup"><span data-stu-id="de2d3-103">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="de2d3-104">El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como la biblioteca de código abierto [Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="de2d3-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="de2d3-105">Polly es una biblioteca de .NET que proporciona capacidades de resistencia y control de errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="de2d3-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="de2d3-106">Puede implementar esas capacidades fácilmente mediante la aplicación de directivas de Polly como reintento, disyuntor, aislamiento de cierre, tiempo de espera y respaldo.</span><span class="sxs-lookup"><span data-stu-id="de2d3-106">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="de2d3-107">Polly tiene como destino .NET 4.x y .NET Standard versión 1.0 (que es compatible con .NET Core).</span><span class="sxs-lookup"><span data-stu-id="de2d3-107">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="de2d3-108">La directiva de reintentos en Polly es el enfoque usado en eShopOnContainers al implementar los reintentos HTTP.</span><span class="sxs-lookup"><span data-stu-id="de2d3-108">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="de2d3-109">Puede implementar una interfaz, por lo que puede insertar la función HttpClient estándar o una versión resistente de HttpClient mediante Polly, según la configuración de la directiva de reintento que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="de2d3-109">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="de2d3-110">En el ejemplo siguiente se muestra la interfaz implementada en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="de2d3-110">The following example shows the interface implemented in eShopOnContainers.</span></span>

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

<span data-ttu-id="de2d3-111">Puede usar la implementación estándar si no quiere usar un mecanismo resistente, como cuando desarrolla o prueba enfoques más sencillos.</span><span class="sxs-lookup"><span data-stu-id="de2d3-111">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="de2d3-112">El código siguiente muestra la implementación de HttpClient estándar en que se permiten las solicitudes con tokens de autenticación como un caso opcional.</span><span class="sxs-lookup"><span data-stu-id="de2d3-112">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

<span data-ttu-id="de2d3-113">La implementación interesante es codificar otra clase similar, pero usar Polly para implementar los mecanismos resistentes que quiere usar (en el ejemplo siguiente, reintentos con retroceso exponencial).</span><span class="sxs-lookup"><span data-stu-id="de2d3-113">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

<span data-ttu-id="de2d3-114">Con Polly, define una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error.</span><span class="sxs-lookup"><span data-stu-id="de2d3-114">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="de2d3-115">En este caso, la directiva está configurada, de forma que intentará el número de veces especificado al registrar los tipos en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="de2d3-115">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="de2d3-116">Debido a la configuración de retroceso exponencial, siempre que el código detecta una excepción HttpRequest, vuelve a intentar la solicitud Http después de esperar un período de tiempo que aumenta exponencialmente según cómo se haya configurado la directiva.</span><span class="sxs-lookup"><span data-stu-id="de2d3-116">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="de2d3-117">El método importante es HttpInvoker, que es lo que emite las solicitudes HTTP a través de esta clase de utilidad.</span><span class="sxs-lookup"><span data-stu-id="de2d3-117">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="de2d3-118">Ese método ejecuta internamente la solicitud HTTP con \_policyWrapper.ExecuteAsync, que tiene en cuenta la directiva de reintentos.</span><span class="sxs-lookup"><span data-stu-id="de2d3-118">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="de2d3-119">En eShopOnContainers puede especificar directivas de Polly al registrar los tipos en el contenedor de IoC, como se muestra en el siguiente código de la clase [aplicación web MVC en startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).</span><span class="sxs-lookup"><span data-stu-id="de2d3-119">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

<span data-ttu-id="de2d3-120">Tenga en cuenta que las instancias de los objetos IHttpClient se crean como singleton en lugar de como transitorias, de modo que el servicio usará las conexiones TCP de forma eficaz y no se producirá [ningún problema con los sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="de2d3-120">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="de2d3-121">Pero lo importante sobre la resistencia es que aplica la directiva de Polly WaitAndRetryAsync en ResilientHttpClientFactory en el método CreateResilientHttpClient, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="de2d3-121">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
<span data-ttu-id="de2d3-122">[Anterior](implement-custom-http-call-retries-exponential-backoff.md)
[Siguiente](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="de2d3-122">[Previous](implement-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
