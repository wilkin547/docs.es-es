---
title: "Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="be433-104">Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly</span><span class="sxs-lookup"><span data-stu-id="be433-104">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="be433-105">El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como el código abierto [Polly](https://github.com/App-vNext/Polly) biblioteca.</span><span class="sxs-lookup"><span data-stu-id="be433-105">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="be433-106">Polly es una biblioteca de .NET que proporciona capacidades de control de errores transitorios y resistencia.</span><span class="sxs-lookup"><span data-stu-id="be433-106">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="be433-107">Puede implementar esas capacidades fácilmente mediante la aplicación de directivas de Polly como reintento, disyuntor, aislamiento de cierre, tiempo de espera y de respaldo.</span><span class="sxs-lookup"><span data-stu-id="be433-107">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="be433-108">Polly tiene como destino .NET 4.x y el estándar de .NET versión 1.0 (que es compatible con .NET Core).</span><span class="sxs-lookup"><span data-stu-id="be433-108">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="be433-109">La directiva de reintentos en Polly es el enfoque usado en eShopOnContainers al implementar los reintentos HTTP.</span><span class="sxs-lookup"><span data-stu-id="be433-109">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="be433-110">Puede implementar una interfaz, por lo que puede insertar funcionalidad HttpClient estándar o una versión resistente de HttpClient mediante Polly, dependiendo de la configuración de directiva de reintento que desea usar.</span><span class="sxs-lookup"><span data-stu-id="be433-110">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="be433-111">En el ejemplo siguiente se muestra la interfaz implementada en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="be433-111">The following example shows the interface implemented in eShopOnContainers.</span></span>

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

<span data-ttu-id="be433-112">Puede usar la implementación estándar si no desea usar un mecanismo resistente a errores, como cuando se está desarrollando o probando enfoques más sencillos.</span><span class="sxs-lookup"><span data-stu-id="be433-112">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="be433-113">El código siguiente muestra el estándar HttpClient permitir las solicitudes de implementación con tokens de autenticación como un caso opcional.</span><span class="sxs-lookup"><span data-stu-id="be433-113">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

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

<span data-ttu-id="be433-114">La implementación interesante es codificar la clase de otro, de forma similar, pero usa Polly para implementar los mecanismos resistentes que desea usar, en el ejemplo siguiente, vuelve a intentar con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="be433-114">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

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

<span data-ttu-id="be433-115">Con Polly, se define una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error.</span><span class="sxs-lookup"><span data-stu-id="be433-115">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="be433-116">En este caso, la directiva está configurada, de forma que intentará el número de veces especificado al registrar los tipos en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="be433-116">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="be433-117">Debido a la configuración de retroceso exponencial, siempre que el código detecta una excepción HttpRequest, volver a intentar la solicitud Http después de esperar un período de tiempo que aumenta exponencialmente dependiendo de cómo se configuró la directiva.</span><span class="sxs-lookup"><span data-stu-id="be433-117">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="be433-118">El método en importancia es HttpInvoker, que es lo que hace que las solicitudes HTTP a través de esta clase de utilidad.</span><span class="sxs-lookup"><span data-stu-id="be433-118">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="be433-119">Que método internamente ejecuta la solicitud HTTP con \_policyWrapper.ExecuteAsync, que tiene en cuenta la directiva de reintentos.</span><span class="sxs-lookup"><span data-stu-id="be433-119">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="be433-120">En eShopOnContainers especificar directivas de Polly al registrar los tipos en el contenedor de IoC, como se muestra en el siguiente código de la [aplicación web MVC en el startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) clase.</span><span class="sxs-lookup"><span data-stu-id="be433-120">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

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

<span data-ttu-id="be433-121">Tenga en cuenta que los objetos IHttpClient se crean instancias como singleton en lugar de como transitorio para que las conexiones TCP se usen de forma eficaz por el servicio y [un problema con sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) no se producirá.</span><span class="sxs-lookup"><span data-stu-id="be433-121">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="be433-122">Pero es importante sobre la resistencia es aplicar la directiva de Polly WaitAndRetryAsync en ResilientHttpClientFactory en el método CreateResilientHttpClient, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="be433-122">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

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
<span data-ttu-id="be433-123">[Anterior] (implement-custom-http-call-retries-exponential-backoff.md) [siguiente] (implemente circuito-separador pattern.md)</span><span class="sxs-lookup"><span data-stu-id="be433-123">[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)</span></span>
