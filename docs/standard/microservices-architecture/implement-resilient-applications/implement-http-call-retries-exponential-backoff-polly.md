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
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly

El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como el código abierto [Polly](https://github.com/App-vNext/Polly) biblioteca.

Polly es una biblioteca de .NET que proporciona capacidades de control de errores transitorios y resistencia. Puede implementar esas capacidades fácilmente mediante la aplicación de directivas de Polly como reintento, disyuntor, aislamiento de cierre, tiempo de espera y de respaldo. Polly tiene como destino .NET 4.x y el estándar de .NET versión 1.0 (que es compatible con .NET Core).

La directiva de reintentos en Polly es el enfoque usado en eShopOnContainers al implementar los reintentos HTTP. Puede implementar una interfaz, por lo que puede insertar funcionalidad HttpClient estándar o una versión resistente de HttpClient mediante Polly, dependiendo de la configuración de directiva de reintento que desea usar.

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

Puede usar la implementación estándar si no desea usar un mecanismo resistente a errores, como cuando se está desarrollando o probando enfoques más sencillos. El código siguiente muestra el estándar HttpClient permitir las solicitudes de implementación con tokens de autenticación como un caso opcional.

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

La implementación interesante es codificar la clase de otro, de forma similar, pero usa Polly para implementar los mecanismos resistentes que desea usar, en el ejemplo siguiente, vuelve a intentar con retroceso exponencial.

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

Con Polly, se define una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error. En este caso, la directiva está configurada, de forma que intentará el número de veces especificado al registrar los tipos en el contenedor de IoC. Debido a la configuración de retroceso exponencial, siempre que el código detecta una excepción HttpRequest, volver a intentar la solicitud Http después de esperar un período de tiempo que aumenta exponencialmente dependiendo de cómo se configuró la directiva.

El método en importancia es HttpInvoker, que es lo que hace que las solicitudes HTTP a través de esta clase de utilidad. Que método internamente ejecuta la solicitud HTTP con \_policyWrapper.ExecuteAsync, que tiene en cuenta la directiva de reintentos.

En eShopOnContainers especificar directivas de Polly al registrar los tipos en el contenedor de IoC, como se muestra en el siguiente código de la [aplicación web MVC en el startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) clase.

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

Tenga en cuenta que los objetos IHttpClient se crean instancias como singleton en lugar de como transitorio para que las conexiones TCP se usen de forma eficaz por el servicio y [un problema con sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) no se producirá.

Pero es importante sobre la resistencia es aplicar la directiva de Polly WaitAndRetryAsync en ResilientHttpClientFactory en el método CreateResilientHttpClient, tal como se muestra en el código siguiente:

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
[Anterior] (implement-custom-http-call-retries-exponential-backoff.md) [siguiente] (implemente circuito-separador pattern.md)
