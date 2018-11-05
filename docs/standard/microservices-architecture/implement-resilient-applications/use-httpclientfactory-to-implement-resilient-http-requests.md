---
title: Uso de HttpClientFactory para implementar solicitudes HTTP resistentes
description: HttpClientFactory es una fábrica bien fundamentada, disponible desde .NET Core 2.1, para crear instancias de `HttpClient` con el fin de usarlas en las aplicaciones.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: f2be3daf1b04613fa8afc1d17cbcbca2d338e062
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347934"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Uso de HttpClientFactory para implementar solicitudes HTTP resistentes

`HttpClientFactory` es una fábrica bien fundamentada, disponible desde .NET Core 2.1, para crear instancias de `HttpClient` con el fin de usarlas en las aplicaciones. 

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Problemas con la clase HttpClient original disponible en .NET Core

La clase [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) original y bien conocida se puede usar fácilmente pero, en algunos casos, muchos desarrolladores no la usan de forma correcta. 

Como primer problema, aunque esta clase es descartable, usarla con la instrucción `using` no es la mejor opción porque incluso cuando se descarta el objeto `HttpClient`, el socket subyacente no se libera de forma inmediata y puede causar un problema grave denominado "agotamiento de socket". Para obtener más información sobre este problema, vea la entrada de blog [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Está usando HttpClient mal y eso desestabiliza el software).

Por tanto, `HttpClient` está diseñado para que se cree una instancia una vez y se reutilice durante la vida de una aplicación. Crear una instancia de una clase `HttpClient` para cada solicitud agotará el número de sockets disponibles bajo cargas pesadas. Ese problema generará errores `SocketException`. Los enfoques posibles para solucionar ese problema se basan en la creación del objeto `HttpClient` como singleton o estático, como se explica en este [artículo de Microsoft sobre el uso de HttpClient](https://docs.microsoft.com/dotnet/csharp/tutorials/console-webapiclient). 

Pero hay un segundo problema con `HttpClient` que puede aparecer cuando se usa como objeto singleton o estático. En este caso, un `HttpClient` singleton o estático no respeta los cambios de DNS, como se explica en este [problema en el repositorio de .NET Core de GitHub](https://github.com/dotnet/corefx/issues/11224). 

Para resolver esos problemas mencionados y facilitar la administración de las instancias de `HttpClient`, .NET Core 2.1 ofrece un nuevo `HttpClientFactory` que también se puede usar para implementar llamadas HTTP resistentes si se le integra Polly.   

## <a name="what-is-httpclientfactory"></a>Qué es HttpClientFactory

`HttpClientFactory` está diseñado para:

- Proporcionar una ubicación central para denominar y configurar instancias lógicas de HttpClient. Por ejemplo, puede configurar un cliente (Agente de servicio) preconfigurado para acceder a un microservicio concreto.
- Codifique el concepto de software intermedio de salida a través de controladores de delegación en `HttpClient` e implemente software intermedio basado en Polly para aprovechar las directivas de resistencia de Polly.
- `HttpClient` ya posee el concepto de controladores de delegación, que se pueden vincular entre sí para las solicitudes HTTP salientes. Los clientes HTTP se registran en la fábrica y, además, se puede usar un controlador de Polly que permite utilizar directivas de Polly para el reintento, interruptores, etc.
- Administre la duración de HttpClientMessageHandlers para evitar los problemas mencionados y los que se puedan producir al administrar las duraciones de `HttpClient` usted mismo. 

## <a name="multiple-ways-to-use-httpclientfactory"></a>Varias formas de usar HttpClientFactory

Hay varias formas de usar `HttpClientFactory` en la aplicación:

- Usar `HttpClientFactory` directamente.
- Usar clientes con nombre.
- Usar clientes con tipo.
- Usar clientes generados.

Por brevedad, en esta guía se muestra la manera más estructurada de usar `HttpClientFactory`, que consiste en utilizar Clientes con tipo (el modelo de agente de servicio), pero todas las opciones se documentan y se enumeran actualmente en este [artículo sobre el uso de HttpClientFactory ](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Cómo usar clientes con tipo con HttpClientFactory

En el diagrama siguiente se muestra cómo se usan los clientes con tipo con HttpClientFactory.

![Diagrama con un controlador de MVC en el que se usa un ClientService insertado, que internamente usa un HttpClient configurado por HttpClientFactory y las directivas de Polly](./media/image3.5.png)

**Figura 10-4**. Uso de `HttpClientFactory` con clases de cliente con tipo.

En primer lugar, configure `HttpClientFactory` en la aplicación. Agregue una referencia al paquete `Microsoft.Extensions.Http` que incluye el método de extensión `AddHttpClient()` para `IServiceCollection`. Este método de extensión registra el `DefaultHttpClientFactory` que se va a usar como singleton para la interfaz `IHttpClientFactory`. Define una configuración transitoria para `HttpMessageHandlerBuilder`. Este controlador de mensajes (el objeto `HttpMessageHandler`), tomado de un grupo, lo usa el `HttpClient` devuelto desde la fábrica.

En el código siguiente, puede ver cómo se puede `AddHttpClient()` utilizar para registrar clientes con tipo (agentes de servicio) que necesitan usar `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Al agregar las clases de cliente con tipo mediante AddHttpClient(), siempre que se use el objeto `HttpClient` que se va a insertar en la clase a través de su constructor, ese objeto `HttpClient` usará toda la configuración y directivas proporcionadas. En las secciones siguientes, se verán esas directivas, como los reintentos o los interruptores de Polly.

### <a name="httpclient-lifetimes"></a>Duraciones de HttpClient

Cada vez que se obtiene un objeto `HttpClient` de IHttpClientFactory, se devuelve una nueva instancia de `HttpClient`. Habrá un HttpMessageHandler** por cada cliente con nombre o tipo. `IHttpClientFactory` agrupará las instancias de HttpMessageHandler creadas por la fábrica para reducir el consumo de recursos. Se puede reutilizar una instancia de HttpMessageHandler del grupo al crear una instancia de `HttpClient` si su duración aún no ha expirado.

La agrupación de controladores es conveniente porque cada controlador suele administrar sus propias conexiones HTTP subyacentes. Crear más controladores de lo necesario puede provocar retrasos en la conexión. Además, algunos controladores dejan las conexiones abiertas de forma indefinida, lo que puede ser un obstáculo a la hora de reaccionar ante los cambios de DNS.

Los objetos HttpMessageHandler del grupo tienen una duración que es el período de tiempo que se puede reutilizar una instancia de HttpMessageHandler en el grupo. El valor predeterminado es de dos minutos, pero se puede invalidar por cada cliente con nombre o tipo. Para invalidarlo, se llama a SetHandlerLifetime() en la interfaz IHttpClientBuilder que se devuelve al crear al cliente, como se muestra en el código siguiente.

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

Cada cliente con tipo o nombre puede tener configurado su propio valor de duración de controlador. Establecer la duración en InfiniteTimeSpan para deshabilitar la expiración del controlador.

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

Por último, una vez implementadas las clases de tipo y después de registrarlas con AddHttpClient(), se pueden usar en cualquier lugar donde haya servicios insertados mediante la inserción de dependencias, por ejemplo en cualquier código de Razor Pages o cualquier controlador de una aplicación web MVC, como en el código siguiente de eShopOnContainers.

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

-   **Uso de HttpClientFactory en .NET Core 2.1**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)


-   **Repositorio de HttpClientFactory en GitHub**

    [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)



>[!div class="step-by-step"]
[Anterior] (explore-custom-http-call-retries-exponential-backoff.md) [Siguiente] (implement-http-call-retries-exponential-backoff-polly.md)
