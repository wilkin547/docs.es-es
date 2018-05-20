---
title: Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 66ac57fc824e01f96d6584ab86bb95ba1b0174a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly

El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como la biblioteca de código abierto [Polly](https://github.com/App-vNext/Polly).

Polly es una biblioteca de .NET que proporciona capacidades de resistencia y control de errores transitorios. Puede implementar esas capacidades fácilmente mediante la aplicación de directivas de Polly como reintento, disyuntor, aislamiento de cierre, tiempo de espera y respaldo. Polly tiene como destino .NET 4.x y .NET Standard versión 1.0 (que es compatible con .NET Core).

La directiva de reintentos en Polly es el enfoque usado en eShopOnContainers al implementar los reintentos HTTP. Puede implementar una interfaz, por lo que puede insertar la función HttpClient estándar o una versión resistente de HttpClient mediante Polly, según la configuración de la directiva de reintento que quiera usar.

En el ejemplo siguiente se muestra la interfaz implementada en eShopOnContainers.

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

Puede usar la implementación estándar si no quiere usar un mecanismo resistente, como cuando desarrolla o prueba enfoques más sencillos. El código siguiente muestra la implementación de HttpClient estándar en que se permiten las solicitudes con tokens de autenticación como un caso opcional.

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

La implementación interesante es codificar otra clase similar, pero usar Polly para implementar los mecanismos resistentes que quiere usar (en el ejemplo siguiente, reintentos con retroceso exponencial).

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

Con Polly, define una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error. En este caso, la directiva está configurada, de forma que intentará el número de veces especificado al registrar los tipos en el contenedor de IoC. Debido a la configuración de retroceso exponencial, siempre que el código detecta una excepción HttpRequest, vuelve a intentar la solicitud Http después de esperar un período de tiempo que aumenta exponencialmente según cómo se haya configurado la directiva.

El método importante es HttpInvoker, que es lo que emite las solicitudes HTTP a través de esta clase de utilidad. Ese método ejecuta internamente la solicitud HTTP con \_policyWrapper.ExecuteAsync, que tiene en cuenta la directiva de reintentos.

En eShopOnContainers puede especificar directivas de Polly al registrar los tipos en el contenedor de IoC, como se muestra en el siguiente código de la clase [aplicación web MVC en startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).

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

Tenga en cuenta que las instancias de los objetos IHttpClient se crean como singleton en lugar de como transitorias, de modo que el servicio usará las conexiones TCP de forma eficaz y no se producirá [ningún problema con los sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Pero lo importante sobre la resistencia es que aplica la directiva de Polly WaitAndRetryAsync en ResilientHttpClientFactory en el método CreateResilientHttpClient, tal como se muestra en el código siguiente:

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
[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)
