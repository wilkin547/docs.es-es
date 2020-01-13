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
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Uso de HttpClientFactory para implementar solicitudes HTTP resistentes

`HttpClientFactory` es una fábrica bien fundamentada, disponible desde .NET Core 2.1, para crear instancias de <xref:System.Net.Http.HttpClient> con el fin de usarlas en las aplicaciones.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemas con la clase HttpClient original disponible en .NET Core

La clase <xref:System.Net.Http.HttpClient> original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de manera correcta.

Como primer problema, aunque esta clase es descartable, usarla con la instrucción `using` no es la mejor opción porque incluso cuando se descarta el objeto `HttpClient`, el socket subyacente no se libera de forma inmediata y puede causar un problema grave denominado "agotamiento de socket". Para obtener más información sobre este problema, vea la entrada de blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Está usando HttpClient mal y eso desestabiliza el software).

Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación. Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas. Ese problema generará errores `SocketException`. Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](../../../csharp/tutorials/console-webapiclient.md).

Pero hay un segundo problema con `HttpClient` que puede aparecer cuando se usa como objeto singleton o estático. En este caso, un `HttpClient` singleton o estático no respeta los cambios de DNS, tal como se explica en este [problema](https://github.com/dotnet/corefx/issues/11224) en el repositorio dotnet/corefx de GitHub.

Para resolver esos problemas mencionados y facilitar la administración de las instancias de `HttpClient`, .NET Core 2.1 ofrece un nuevo `HttpClientFactory` que también se puede usar para implementar llamadas HTTP resistentes si se le integra Polly.

[Polly](http://www.thepollyproject.org/) es una biblioteca de control de errores transitorios que ayuda a los desarrolladores a agregar resistencia a sus aplicaciones mediante el uso de directivas predefinidas de manera fluida y segura para subprocesos.

## <a name="what-is-httpclientfactory"></a>Qué es HttpClientFactory

`HttpClientFactory` está diseñado para:

- Proporcionar una ubicación central para denominar y configurar instancias lógicas de `HttpClient`. Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.
- Codifique el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.
- `HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes. Los clientes HTTP se registran en la fábrica y se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.
- Administre la duración de `HttpClientMessageHandlers` para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo.

> [!NOTE]
> `HttpClientFactory` está estrechamente ligado a la implementación de la inserción de dependencias (DI) en el paquete de NuGet `Microsoft.Extensions.DependencyInjection`. Para más información sobre el uso de otros contenedores de inserción de dependencias, consulte esta [conversación de GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-httpclientfactory"></a>Varias formas de usar HttpClientFactory

Hay varias formas de usar `HttpClientFactory` en la aplicación:

- Usar `HttpClientFactory` directamente.
- Usar clientes con nombre.
- Usar clientes con tipo.
- Usar clientes generados.

En pro de la brevedad, esta guía muestra la manera más estructurada para usar `HttpClientFactory`, que consiste en usar clientes con tipo (el patrón de agente de servicio). Sin embargo, todas las opciones están documentadas y actualmente se muestra en este [artículo que trata sobre el uso de HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Cómo usar clientes con tipo con HttpClientFactory

Así pues, ¿qué es un "Cliente con tipo"? Se trata sencillamente de un cliente `HttpClient` configurado por `DefaultHttpClientFactory` tras la inserción.

En el diagrama siguiente se muestra cómo se usan los clientes con tipo con `HttpClientFactory`:

![Diagrama que muestra cómo se usan los clientes con tipo con HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Figura 8-4**. Uso de HttpClientFactory con clases de cliente con tipo.

En la imagen anterior, un servicio ClientService (usado por un controlador o código de cliente) utiliza un cliente `HttpClient` creado por la fábrica `IHttpClientFactory` registrada. Este generador asigna a `HttpClient` un `HttpMessageHandler` de un grupo que administra. El cliente `HttpClient` se puede configurar con las directivas de Polly al registrar la fábrica `IHttpClientFactory` en el contenedor de DI con el método de extensión `AddHttpClient`.

Para configurar la estructura anterior, agregue `HttpClientFactory` a la aplicación mediante la instalación del paquete de NuGet `Microsoft.Extensions.Http`, que incluye el método de extensión `AddHttpClient()` para `IServiceCollection`. Este método de extensión registra el `DefaultHttpClientFactory` que se va a usar como singleton para la interfaz `IHttpClientFactory`. Define una configuración transitoria para `HttpMessageHandlerBuilder`. Este controlador de mensajes (el objeto `HttpMessageHandler`), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.

En el código siguiente, puede ver cómo se puede `AddHttpClient()` utilizar para registrar clientes con tipo (agentes de servicio) que necesitan usar `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Al registrar los servicios de cliente como se muestra en el código anterior, `DefaultClientFactory` crea un `HttpClient` estándar para cada servicio.

También puede agregar una configuración específica de instancia en el registro para, por ejemplo, configurar la dirección base y agregar algunas directivas de resistencia, como se muestra en el código siguiente:

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Solo para el ejemplo, puede ver una de las directivas anteriores en el código siguiente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

Puede encontrar más detalles sobre el uso de Polly en el [artículo siguiente](implement-http-call-retries-exponential-backoff-polly.md).

### <a name="httpclient-lifetimes"></a>Duraciones de HttpClient

Cada vez que se obtiene un objeto `HttpClient` de `IHttpClientFactory`, se devuelve una nueva instancia. Pero cada cliente `HttpClient` usa un controlador `HttpMessageHandler` que `IHttpClientFactory` agrupa y vuelve a usar para reducir el consumo de recursos, siempre y cuando la vigencia de `HttpMessageHandler`no haya expirado.

La agrupación de controladores es conveniente porque cada controlador suele administrar sus propias conexiones HTTP subyacentes. Crear más controladores de lo necesario puede provocar retrasos en la conexión. Además, algunos controladores dejan las conexiones abiertas de forma indefinida, lo que puede ser un obstáculo a la hora de reaccionar ante los cambios de DNS.

Los objetos `HttpMessageHandler` del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de `HttpMessageHandler` en el grupo. El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con tipo. Para ello, llame a `SetHandlerLifetime()` en el `IHttpClientBuilder` que se devuelve cuando se crea el cliente, como se muestra en el siguiente código:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Cada cliente con tipo puede tener configurado su propio valor de duración de controlador. Establezca la duración en `InfiniteTimeSpan` para deshabilitar la expiración del controlador.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Implementar las clases de cliente con tipo que usan el HttpClient insertado y configurado

Como paso anterior, debe tener las clases de cliente con tipo definidas, como las del código de ejemplo (por ejemplo, "BasketService", "CatalogService", "OrderingService", etc.). Un cliente con tipo es una clase que acepta un objeto `HttpClient` (insertado a través de su constructor) y lo usa para llamar a algún servicio remoto de HTTP. Por ejemplo:

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

El cliente con tipo (CatalogService en el ejemplo) se activa mediante la inserción de dependencias, lo que significa que puede aceptar cualquier servicio registrado en su constructor, además de HttpClient.

Un cliente con tipo es, de hecho, un objeto transitorio, lo que significa que se crea una instancia cada vez que se necesita una y que recibirá una instancia de `HttpClient` nueva cada vez se construya. Pero los objetos HttpMessageHandler del grupo son los que reutilizan varias solicitudes HTTP.

### <a name="use-your-typed-client-classes"></a>Usar las clases de cliente con tipo

Por último, una vez que las clases con tipo se implementan y se registran con `AddHttpClient()`, se pueden usar en cualquier lugar donde haya servicios insertados mediante la inserción de dependencias, por ejemplo, en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers:

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

Hasta el momento, el código que se ha mostrado solo realiza solicitudes HTTP convencionales, pero la "magia" aparecerá en las secciones siguientes donde, con tan solo agregar directivas y controladores de delegación a los clientes con tipo registrados, todas las solicitudes HTTP que `HttpClient` va a realizar se comportarán teniendo en cuenta las directivas de resistencia como los reintentos con retroceso exponencial, los interruptores o cualquier otro controlador de delegación personalizado para implementar características de seguridad adicionales, como el uso de tokens de autenticación, o bien cualquier otra característica personalizada.

## <a name="additional-resources"></a>Recursos adicionales

- **Uso de HttpClientFactory en .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **Código fuente de HttpClientFactory en el repositorio de GitHub `dotnet/extensions`**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**  
  <http://www.thepollyproject.org/>
  
- **Uso de HttpClientFactory sin inserción de dependencias (problema de GitHub)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Anterior](explore-custom-http-call-retries-exponential-backoff.md)
>[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)
