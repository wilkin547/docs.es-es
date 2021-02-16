---
title: Uso de IHttpClientFactory para implementar solicitudes HTTP resistentes
description: Aprenda a utilizar IHttpClientFactory, disponible a partir de .NET Core 2.1, para crear instancias de `HttpClient`, lo que le facilita su uso en sus aplicaciones.
ms.date: 01/13/2021
ms.openlocfilehash: fc5da088b1ed7573532dff101aff03d39a02a6f4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429317"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a>Uso de IHttpClientFactory para implementar solicitudes HTTP resistentes

<xref:System.Net.Http.IHttpClientFactory> es un contrato implementado por `DefaultHttpClientFactory`, una fábrica bien fundamentada disponible desde .NET Core 2.1 para crear instancias de <xref:System.Net.Http.HttpClient> con el fin de usarlas en las aplicaciones.

## <a name="issues-with-the-original-httpclient-class-available-in-net"></a>Problemas con la clase HttpClient original disponible en .NET

La clase <xref:System.Net.Http.HttpClient> original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de manera correcta.

Aunque esta clase implementa `IDisposable`, no se aconseja declarar y crear instancias de ella en una instrucción `using` porque, cuando el objeto `HttpClient` se desecha, el socket subyacente no se libera inmediatamente, lo que puede conducir a un problema de _agotamiento del socket_. Para obtener más información sobre este problema, vea la entrada de blog [Está usando HttpClient mal y eso desestabiliza el software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación. Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas. Ese problema generará errores `SocketException`. Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](../../../csharp/tutorials/console-webapiclient.md). Puede tratarse de una buena solución para las aplicaciones de consola de corta duración o elementos similares que se ejecutan varias veces al día.

Otra incidencia a la que los desarrolladores deben hacer frente es cuando se usa una instancia compartida de `HttpClient` en procesos de larga duración. En una situación en la que se crean instancias del HttpClient como un singleton o un objeto estático, los cambios de DNS no se pueden controlar, tal y como se describe en esta [incidencia](https://github.com/dotnet/runtime/issues/18348) del repositorio de GitHub sobre dotnet/runtime.

Realmente el problema no está en `HttpClient`, sino en el [constructor predeterminado de HttpClient](/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), ya que crea una instancia concreta de <xref:System.Net.Http.HttpMessageHandler>, que es la que plantea los problemas de *agotamiento de sockets* y los cambios de DNS mencionados anteriormente.

Para solucionar estos problemas y hacer que las instancias de `HttpClient` se puedan administrar, .NET Core 2.1 ha incorporado la interfaz <xref:System.Net.Http.IHttpClientFactory>, que se puede usar para configurar y crear instancias de `HttpClient` en una aplicación a través de la inserción de dependencias (DI). También proporciona extensiones para el middleware basado en Polly a fin de aprovechar los controladores de delegación en HttpClient.

[Polly](https://thepollyproject.azurewebsites.net/) es una biblioteca de control de errores transitorios que ayuda a los desarrolladores a agregar resistencia a sus aplicaciones mediante el uso de directivas predefinidas de manera fluida y segura para subprocesos.

## <a name="benefits-of-using-ihttpclientfactory"></a>Ventajas de usar IHttpClientFactory

La implementación actual de <xref:System.Net.Http.IHttpClientFactory>, que también implementa <xref:System.Net.Http.IHttpMessageHandlerFactory>, reporta las siguientes ventajas:

- Proporciona una ubicación central para denominar y configurar instancias lógicas de `HttpClient`. Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.
- Codifica el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.
- `HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes. Los clientes HTTP se pueden registrar en la fábrica y se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.
- Administre la duración de <xref:System.Net.Http.HttpMessageHandler> para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo.

> [!TIP]
> Las instancias de `HttpClient` insertadas mediante DI se pueden eliminar de forma segura, porque el elemento `HttpMessageHandler` asociado lo administra la fábrica. En realidad, las instancias de `HttpClient` insertadas están *dentro del ámbito*, desde el punto de vista de DI.

> [!NOTE]
> La implementación de `IHttpClientFactory` (`DefaultHttpClientFactory`) está estrechamente ligada a la implementación de la inserción de dependencias (DI) en el paquete de NuGet `Microsoft.Extensions.DependencyInjection`. Para obtener más información sobre cómo usar otros contenedores de inserción de dependencias, vea esta [conversación de GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-ihttpclientfactory"></a>Varias formas de usar IHttpClientFactory

Hay varias formas de usar `IHttpClientFactory` en la aplicación:

- Uso básico
- Usar clientes con nombre.
- Usar clientes con tipo.
- Usar clientes generados.

En pro de la brevedad, esta guía muestra la manera más estructurada para usar `IHttpClientFactory`, que consiste en usar clientes con tipo (el patrón de agente de servicio). Pero todas las opciones están documentadas e incluidas actualmente en este [artículo que trata sobre el uso de HttpClientFactory`IHttpClientFactory`](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a>Cómo usar clientes con tipo con IHttpClientFactory

Así pues, ¿qué es un "Cliente con tipo"? Es solo un elemento `HttpClient` que está preconfigurado para un uso específico. Esta configuración puede incluir valores específicos como un servidor base, encabezados HTTP o tiempos de espera.

En el diagrama siguiente se muestra cómo se usan los clientes con tipo con `IHttpClientFactory`:

![Diagrama que muestra cómo se usan los clientes con tipo con IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Figura 8-4**. Uso de `IHttpClientFactory` con clases de cliente con tipo.

En la imagen anterior, un servicio `ClientService` (usado por un controlador o código de cliente) utiliza un cliente `HttpClient` creado por la fábrica `IHttpClientFactory` registrada. Este generador asigna a `HttpClient` un elemento `HttpMessageHandler` desde un grupo. El cliente `HttpClient` se puede configurar con las directivas de Polly al registrar la fábrica `IHttpClientFactory` en el contenedor de DI con el método de extensión <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.

Para configurar la estructura anterior, agregue <xref:System.Net.Http.IHttpClientFactory> a la aplicación mediante la instalación del paquete de NuGet `Microsoft.Extensions.Http`, que incluye el método de extensión <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> para <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. Este método de extensión registra la clase interna `DefaultHttpClientFactory` que se va a usar como singleton en la interfaz `IHttpClientFactory`. Define una configuración transitoria para <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>. Este controlador de mensajes (el objeto <xref:System.Net.Http.HttpMessageHandler>), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.

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

Los objetos `HttpMessageHandler` del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de `HttpMessageHandler` en el grupo. El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con tipo. Para ello, llame a `SetHandlerLifetime()` en el <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> que se devuelve cuando se crea el cliente, como se muestra en el siguiente código:

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

El cliente con tipo (`CatalogService` en el ejemplo) se activa mediante DI (inserción de dependencias), lo que significa que puede aceptar cualquier servicio registrado en su constructor, además de `HttpClient`.

Un cliente con tipo es realmente un objeto transitorio, lo que significa que, cada vez que se necesita uno, se crea una instancia. Recibe una nueva instancia de `HttpClient` cada vez que se construye. Pero los objetos `HttpMessageHandler` del grupo son los objetos que varias instancias de `HttpClient` reutilizan.

### <a name="use-your-typed-client-classes"></a>Usar las clases de cliente con tipo

Por último, una vez que haya implementado las clases con tipo, puede registrarlas y configurarlas con `AddHttpClient()`. Después, puede usarlas dondequiera que los servicios se inserten mediante DI. por ejemplo, en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers:

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

Hasta ahora, el fragmento de código anterior solo ha mostrado el ejemplo de realizar solicitudes HTTP normales. Pero la "magia" viene en las secciones siguientes, donde se muestra cómo todas las solicitudes HTTP que realiza `HttpClient` pueden tener directivas resistentes como, por ejemplo, reintentos con retroceso exponencial, disyuntores, características de seguridad que usan tokens de autenticación o incluso cualquier otra característica personalizada. Y todo esto se puede hacer simplemente agregando directivas y delegando controladores a los clientes con tipo registrados.

## <a name="additional-resources"></a>Recursos adicionales

- **Uso de HttpClientFactory en .NET**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **Código fuente de HttpClientFactory en el repositorio de GitHub `dotnet/extensions`**  
  <https://github.com/dotnet/extensions/tree/v3.1.8/src/HttpClientFactory>

- **Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**  
  <https://thepollyproject.azurewebsites.net/>
  
- **Uso de IHttpClientFactory sin inserción de dependencias (problema de GitHub)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Anterior](implement-resilient-entity-framework-core-sql-connections.md)
>[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)
