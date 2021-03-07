---
title: El bloque de creación de invocación del servicio DAPR
description: Una descripción del bloque de creación de invocación de servicio, sus características, ventajas y cómo aplicarla
author: amolenk
ms.date: 02/07/2021
ms.openlocfilehash: 2b64aa1e9b079a3fefe120e687cd6d395981c633
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401842"
---
# <a name="the-dapr-service-invocation-building-block"></a>El bloque de creación de invocación del servicio DAPR

En un sistema distribuido, un servicio a menudo necesita comunicarse con otro para completar una operación empresarial. El [bloque de creación de invocación del servicio DAPR](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) puede ayudar a simplificar la comunicación entre los servicios.

## <a name="what-it-solves"></a>Qué resuelve

Es posible que las llamadas entre los servicios de una aplicación distribuida parezcan sencillas, pero hay muchos desafíos. Por ejemplo:

- Dónde se encuentran los otros servicios.
- Cómo llamar a un servicio de forma segura, dada la dirección del servicio.
- Cómo controlar los reintentos cuando se producen [errores transitorios](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) de corta duración.

Por último, a medida que las aplicaciones distribuidas componen muchos servicios diferentes, la captura de información en los gráficos de llamadas de servicio es fundamental para diagnosticar los problemas de producción.

El bloque de creación de invocación de servicio soluciona estos desafíos mediante el uso de un sidecar de DAPR como un [proxy inverso](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) para su servicio.

## <a name="how-it-works"></a>Funcionamiento

Comencemos con un ejemplo. Considere dos servicios, "servicio A" y "servicio B". El servicio a necesita llamar a la `catalog/items` API en el servicio B. Aunque el servicio A podría tomar una dependencia del servicio B y realizar una llamada directa a él, el servicio A invoca la API de invocación del servicio en el sidecar de DAPR. En la figura 6-1 se muestra la operación.

![Cómo funciona la invocación del servicio DAPR](./media/service-invocation/service-invocation-flow.png)

**Figura 6-1**. Cómo funciona la invocación del servicio DAPR.

Tenga en cuenta los pasos de la ilustración anterior:

1. El servicio A realiza una llamada al `catalog/items` punto de conexión en el servicio B mediante la invocación de la API de invocación del servicio en el servicio a sidecar.

    > [!NOTE]
    > El sidecar usa un mecanismo de resolución de nombres conectable para resolver la dirección del servicio B. En el modo autohospedado, DAPR usa [MDN](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) para encontrarlo. Cuando se ejecuta en modo Kubernetes, el servicio DNS de Kubernetes determina la dirección.  

1. El servicio un sidecar reenvía la solicitud al sidecar del servicio B.

1. El sidecar del servicio B realiza la `catalog/items` solicitud real contra la API del servicio b.

1. El servicio B ejecuta la solicitud y devuelve una respuesta a su sidecar.

1. El servicio B sidecar reenvía la respuesta al servicio a sidecar.

1. El servicio A sidecar devuelve la respuesta al servicio a.

Dado que las llamadas fluyen a través de sidecar, DAPR puede inyectar algunos comportamientos de corte transversal útiles:

- Reintentar llamadas automáticamente en caso de error.
- Realizar llamadas entre servicios seguros con autenticación mutua (mTLS), incluida la sustitución automática de certificados.
- Controlar qué operaciones pueden realizar los clientes mediante directivas de control de acceso.
- Capture los seguimientos y las métricas de todas las llamadas entre servicios para proporcionar información y diagnósticos.

Cualquier aplicación puede invocar un sidecar de DAPR mediante la API de **invocación** nativa integrada en DAPR. Se puede llamar a la API con HTTP o gRPC. Use la siguiente dirección URL para llamar a la API HTTP:

``` http
http://localhost:<dapr-port>/v1.0/invoke/<application-id>/method/<method-name>
```

- `<dapr-port>` el puerto HTTP en el que escucha DAPR.
- `<application-id>` IDENTIFICADOR de la aplicación del servicio que se va a llamar.
- `<method-name>` nombre del método que se va a invocar en el servicio remoto.

En el ejemplo siguiente, se realiza una llamada a *rizo* en el `catalog/items` punto de conexión "Get" de `Service B` :

```console
curl http://localhost:3500/v1.0/invoke/serviceb/method/catalog/items
```

> [!NOTE]
> Las API de DAPR habilitan cualquier pila de aplicaciones que admita HTTP o gRPC para usar los bloques de creación de DAPR. Por lo tanto, el bloque de creación de invocación del servicio puede actuar como un puente entre los protocolos. Los servicios pueden comunicarse entre sí mediante HTTP, gRPC o una combinación de ambos.

En la sección siguiente, aprenderá a usar el SDK de .NET para simplificar las llamadas de invocación de servicio.

## <a name="use-the-dapr-net-sdk"></a>Uso del SDK de .NET para DAPR

El [SDK de .net](https://github.com/dapr/dotnet-sdk) para DAPR proporciona a los desarrolladores de .net una forma intuitiva y específica del lenguaje de interactuar con DAPR. El SDK ofrece a los desarrolladores tres maneras de realizar llamadas de invocación del servicio remoto:

1. Invocar servicios HTTP mediante HttpClient
1. Invocar servicios HTTP mediante DaprClient
1. Invocar servicios gRPC mediante DaprClient

### <a name="invoke-http-services-using-httpclient"></a>Invocar servicios HTTP mediante HttpClient

La mejor manera de llamar a un punto de conexión HTTP es usar la integración enriquecida de DAPR con `HttpClient` . En el ejemplo siguiente se envía un pedido llamando al `submit` método de la `orderservice` aplicación:

```csharp
var httpClient = DaprClient.CreateHttpClient();
await httpClient.PostAsJsonAsync("http://orderservice/submit", order);
```

En el ejemplo, `DaprClient.CreateHttpClient` devuelve una `HttpClient` instancia de que se usa para realizar la invocación del servicio DAPR. El devuelto `HttpClient` utiliza un controlador de mensajes DAPR especial que reescribe los URI de las solicitudes salientes. El nombre de host se interpreta como el identificador de la aplicación del servicio al que se va a llamar. La solicitud reescrita que se está llamando realmente es:

```http
http://127.0.0.1:3500/v1/invoke/orderservice/method/submit
```

En este ejemplo se usa el valor predeterminado para el punto de conexión HTTP DAPR, que es `http://127.0.0.1:<dapr-http-port>/` . El valor de `dapr-http-port` se toma de la `DAPR_HTTP_PORT` variable de entorno. Si no se establece, se usa el número de puerto predeterminado `3500` .

Como alternativa, puede configurar un punto de conexión personalizado en la llamada a `DaprClient.CreateHttpClient` :

```csharp
var httpClient = DaprClient.CreateHttpClient(daprEndpoint = "localhost:4000");
```

También puede establecer directamente la dirección base especificando el identificador de la aplicación. Esto hace posible el uso de URI relativos al realizar una llamada:

```csharp
var httpClient = DaprClient.CreateHttpClient("orderservice");
await httpClient.PostAsJsonAsync("/submit");
```

El `HttpClient` objeto está pensado para tener una duración prolongada. Una sola `HttpClient` instancia se puede reutilizar durante la vigencia de la aplicación. En el escenario siguiente se muestra cómo una `OrderServiceClient` clase vuelve a usar una instancia de DAPR `HttpClient` :  

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddSingleton<IOrderServiceClient, OrderServiceClient>(
        _ => new OrderServiceClient(DaprClient.CreateInvokeHttpClient("orderservice")));
}
```

En el fragmento de código anterior, `OrderServiceClient` se registra como singleton con el sistema de inserción de dependencias ASP.net Core. Un generador de implementación crea una nueva `HttpClient` instancia de mediante una llamada a `DaprClient.CreateInvokeHttpClient` . A continuación, usa el recién creado `HttpClient` para crear instancias del `OrderServiceClient` objeto. Al registrar `OrderServiceClient` como singleton, se volverá a usar durante la vigencia de la aplicación.

El `OrderServiceClient` propio no tiene código específico de DAPR. Aunque la invocación del servicio DAPR se usa en el capó, puede tratar el HttpClient de DAPR como cualquier otro HttpClient:

```csharp
public class OrderServiceClient : IOrderServiceClient
{
    private readonly HttpClient _httpClient;

    public OrderServiceClient(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public async Task SubmitOrder(Order order)
    {
        var response = await _httpClient.PostAsJsonAsync("submit", order);
        response.EnsureSuccessStatusCode();
    }
}
```

El uso de la clase HttpClient con la invocación del servicio DAPR tiene muchas ventajas:

- HttpClient es una clase conocida que muchos desarrolladores ya usan en su código. El uso de HttpClient para la invocación del servicio DAPR permite a los desarrolladores reutilizar sus conocimientos existentes.
- HttpClient admite escenarios avanzados, como encabezados personalizados, y control total sobre los mensajes de solicitud y respuesta.
- En .NET 5, HttpClient admite la serialización y deserialización automáticas mediante System.Text.Jsen.
- HttpClient se integra con muchos marcos y bibliotecas existentes [, como ajustar,](https://github.com/reactiveui/refit) [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage)y [Polly](https://github.com/App-vNext/Polly).

### <a name="invoke-http-services-using-daprclient"></a>Invocar servicios HTTP mediante DaprClient

Aunque HttpClient es la manera preferida de invocar servicios mediante la semántica de HTTP, también puede usar la `DaprClient.InvokeMethodAsync` familia de métodos. En el ejemplo siguiente se envía un pedido llamando al `submit` método de la `orderservice` aplicación:

``` csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation =
        await daprClient.InvokeMethodAsync<Order, OrderConfirmation>(
            "orderservice", "submit", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

El tercer argumento, un `order` objeto, se serializa internamente (con `System.Text.JsonSerializer` ) y se envía como la carga de la solicitud. El SDK de .NET se encarga de la llamada al sidecar. También deserializa la respuesta a un `OrderConfirmation` objeto. Dado que no se especifica ningún método HTTP, la solicitud se ejecuta como HTTP POST.

En el ejemplo siguiente se muestra cómo puede realizar una solicitud HTTP GET especificando `HttpMethod` :

```csharp
var catalogItems = await daprClient.InvokeMethodAsync<IEnumerable<CatalogItem>>(HttpMethod.Get, "catalogservice", "items");
```

En algunos escenarios, puede que necesite más control sobre el mensaje de solicitud. Por ejemplo, si necesita especificar encabezados de solicitud o si desea utilizar un serializador personalizado para la carga útil. `DaprClient.CreateInvokeMethodRequest` crea un `HttpRequestMessage` . En el ejemplo siguiente se muestra cómo agregar un encabezado de autorización HTTP a un mensaje de solicitud:

```csharp
var request = daprClient.CreateInvokeMethodRequest("orderservice", "submit", order);
request.Headers.Authorization = new AuthenticationHeaderValue("bearer", token);
```

`HttpRequestMessage`Ahora tiene las siguientes propiedades establecidas:

- Dirección URL = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`
- HttpMethod = POST
- Content =  `JsonContent` objeto que contiene la serialización JSON `order`
- Headers. Authorization = "Bearer \<token> "

Una vez que haya configurado la solicitud de la forma que desee, use `DaprClient.InvokeMethodAsync` para enviarla:

```csharp
var orderConfirmation = await daprClient.InvokeMethodAsync<OrderConfirmation>(request);
```

`DaprClient.InvokeMethodAsync` deserializa la respuesta a un `OrderConfirmation` objeto si la solicitud se realiza correctamente. Como alternativa, puede usar `DaprClient.InvokeMethodWithResponseAsync` para obtener acceso completo al subyacente `HttpResponseMessage` :

```csharp
var response = await daprClient.InvokeMethodWithResponseAsync(request);
response.EnsureSuccessStatusCode();

var orderConfirmation = response.Content.ReadFromJsonAsync<OrderConfirmation>();
```

> [!NOTE]
> En el caso de las llamadas de invocación de servicio mediante HTTP, merece la pena considerar el uso de la integración de HttpClient de DAPR presentada en la sección anterior. El uso de HttpClient ofrece ventajas adicionales, como la integración con Marcos y bibliotecas existentes.

### <a name="invoke-grpc-services-using-daprclient"></a>Invocar servicios gRPC mediante DaprClient

DaprClient proporciona una familia de `InvokeMethodGrpcAsync` métodos para llamar a puntos de conexión de gRPC. La principal diferencia con los métodos HTTP es el uso de un serializador protobuf en lugar de JSON. En el ejemplo siguiente se invoca el `submitOrder` método de `orderservice` sobre gRPC.

```csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation = await daprClient.InvokeMethodGrpcAsync<Order, OrderConfirmation>("orderservice", "submitOrder", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

En el ejemplo anterior, DaprClient serializa el objeto especificado `order` mediante [protobuf](https://developers.google.com/protocol-buffers) y usa el resultado como el cuerpo de la solicitud gRPC. Del mismo modo, el cuerpo de la respuesta se protobuf deserializa y se devuelve al autor de la llamada. Protobuf suele proporcionar un mejor rendimiento que las cargas de JSON usadas en la invocación del servicio HTTP.

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

La arquitectura de referencia de microservicios de [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) original de Microsoft usaba una combinación de servicios http/Rest y gRPC. El uso de gRPC se limitó a la comunicación entre un [servicio de agregador](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) y servicios back-end básicos. En la figura 6-2 se muestra la arquitectura:

![llamadas a gRPC y HTTP/REST en eShopOnContainers](./media/service-invocation/eshop-on-containers.png)

**Figura 6-2**. llamadas a gRPC y HTTP/REST en eShopOnContainers.

Tenga en cuenta los pasos de la ilustración anterior:

1. El front-end llama a la [puerta de enlace de API](/azure/architecture/microservices/design/gateway) mediante http/REST.

1. La puerta de enlace de API reenvía las solicitudes [CRUD](https://www.sumologic.com/glossary/crud/) (creación, lectura, actualización y eliminación) sencillas directamente a un servicio back-end básico mediante http/REST.

1. La puerta de enlace de API reenvía las solicitudes complejas que implican llamadas coordinadas a varios servicios de back-end al servicio de agregador de la compra Web.

1. El servicio Aggregator usa gRPC para llamar a los servicios back-end básicos.

En la implementación de eShopOnDapr actualizada recientemente, se agregan DAPR sidecar a los servicios y a la puerta de enlace de API. En la figura 6-3 se muestra la arquitectura actualizada:

![llamadas a gRPC y HTTP/REST con sidecar en eShopOnContainers](./media/service-invocation/eshop-on-dapr.png)

**Figura 6-3**. Arquitectura de eShop actualizada mediante DAPR.

Tenga en cuenta los pasos actualizados de la ilustración anterior:

1. El front-end todavía usa HTTP/REST para llamar a la puerta de enlace de API.

1. La puerta de enlace de API reenvía las solicitudes HTTP a su sidecar de DAPR.

1. La puerta de enlace de API sidecar envía la solicitud al sidecar del servicio back-end o del agregador.

1. El servicio Aggregator usa el SDK de .NET de DAPR para llamar a servicios de back-end a través de su arquitectura de sidecar.

DAPR implementa llamadas entre sidecar con gRPC. Por tanto, incluso si está invocando un servicio remoto con la semántica HTTP/REST, una parte del transporte se sigue implementando mediante gRPC.

La aplicación de referencia eShopOnDapr se beneficia del bloque de creación de invocación del servicio DAPR. Entre las ventajas se incluyen la detección de servicios, la mTLS automática y la observación.

### <a name="forward-http-requests-using-envoy-and-dapr"></a>Reenviar solicitudes HTTP mediante envío y DAPR

Tanto la aplicación de eShop original como la actualizada aprovechan el [proxy de envío](https://www.envoyproxy.io/) como puerta de enlace de API. El envío es un proxy de código abierto y un bus de comunicación que es popular en aplicaciones distribuidas modernas. A partir de Lyft, el envío es propiedad de la [base informática nativa](https://www.cncf.io/)de la nube y la mantiene.

En la implementación de eShopOnContainers original, la puerta de enlace de API de envío reenvió las solicitudes HTTP entrantes directamente al agregador o a los servicios back-end. En el nuevo eShopOnDapr, el proxy de envío reenvía la solicitud a un sidecar de DAPR. El sidecar proporciona invocación de servicio, mTLS y observabilidad.

Los envíos se configuran mediante un archivo de definición de YAML para controlar el comportamiento del proxy. Para permitir que el envío reenvíe las solicitudes HTTP a un contenedor de DAPR sidecar, `dapr` se agrega un clúster a la configuración. La configuración del clúster contiene un host que apunta al puerto HTTP en el que escucha el sidecar de DAPR:

``` yaml
clusters:
- name: dapr
  connect_timeout: 0.25s
  type: strict_dns
  hosts:
  - socket_address:
    address: 127.0.0.1
    port_value: 3500
```

La configuración de rutas de envío se actualiza para reescribir las solicitudes entrantes como llamadas al sidecar DAPR (preste especial atención al `prefix_rewrite` par clave-valor):

``` yaml
- name: "c-short"
  match:
    prefix: "/c/"
  route:
    auto_host_rewrite: true
    prefix_rewrite: "/v1.0/invoke/catalog-api/method/"
    cluster: dapr
```

Considere un escenario en el que el cliente front-end desea recuperar una lista de elementos de catálogo. La API de catálogo proporciona un punto de conexión para obtener los elementos de catálogo:

``` csharp
[Route("api/v1/[controller]")]
[ApiController]
public class CatalogController : ControllerBase
{
    [HttpGet("items")]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery] int pageSize = 10,
        [FromQuery] int pageIndex = 0)
    {
        // ...
    }
```

En primer lugar, el front-end realiza una llamada HTTP directa a la puerta de enlace de API de envío.

```
GET http://<api-gateway>/c/api/v1/catalog/items?pageSize=20
```

El proxy de envío coincide con la ruta, vuelve a escribir la solicitud HTTP y la reenvía a la `invoke` API de su sidecar de DAPR:

```
GET http://127.0.0.1:3500/v1.0/invoke/catalog-api/method/api/v1/catalog/items?pageSize=20
```

El sidecar controla la detección de servicios y enruta la solicitud al servicio de catálogo API sidecar. Por último, el sidecar llama a la API de catálogo para ejecutar la solicitud, capturar los elementos del catálogo y devolver una respuesta:

```
GET http://localhost/api/v1/catalog/items?pageSize=20
```

### <a name="make-aggregated-service-calls-using-the-net-sdk"></a>Realizar llamadas de servicio agregadas mediante el SDK de .NET

La mayoría de las llamadas del front-end de eShop son llamadas CRUD simples. La puerta de enlace de API los reenvía a un único servicio para su procesamiento. Sin embargo, algunos escenarios requieren varios servicios back-end para que funcionen de forma conjunta para completar una solicitud. Para estas llamadas más complejas, eShop usa el servicio de agregador de la compra web para mediar el flujo de trabajo entre varios servicios. En la figura 6-4 se muestra la secuencia de procesamiento de agregar un elemento a la cesta de la compra:

![Diagrama de la secuencia de actualización de la cesta](./media/service-invocation/complex-call.png)

**Figura 6-4**. Actualizar la secuencia de la cesta de la compra.

El servicio de agregación recupera primero los elementos de catálogo de la API de catálogo. Después, valida la disponibilidad y los precios de los elementos. Por último, el servicio agregador guarda la cesta de la compra actualizada llamando a la API basket.

El servicio agregador contiene un `BasketController` que proporciona un punto de conexión para actualizar la cesta de la compra:

``` csharp
[Route("api/v1/[controller]")]
[Authorize]
[ApiController]
public class BasketController : ControllerBase
{
    private readonly ICatalogService _catalog;
    private readonly IBasketService _basket;

    [HttpPost]
    [HttpPut]
    public async Task<ActionResult<BasketData>> UpdateAllBasketAsync(
        [FromBody] UpdateBasketRequest data, [FromHeader] string authorization)
    {
        // Get the item details from the catalog API.
        var catalogItems = await _catalog.GetCatalogItemsAsync(
            data.Items.Select(x => x.ProductId));

        // Check item availability and prices; store results in basket object.
        var basket = CreateValidatedBasket(data, catalogItems);

        // Save the shopping basket.
        await _basket.UpdateAsync(basket, authorization);

        return basket;
    }

    // ...
}
```

El `UpdateAllBasketAsync` método obtiene el encabezado *Authorization* de la solicitud entrante mediante un `FromHeader` atributo. El encabezado *Authorization* contiene el token de acceso que se necesita para llamar a servicios back-end protegidos.

Después de recibir una solicitud para actualizar la cesta, el servicio agregador llama a la API de catálogo para obtener los detalles del elemento. El controlador de cesta utiliza un objeto insertado `ICatalogService` para hacer esa llamada y comunicarse con la API de catálogo. La implementación original de la interfaz usó gRPC para hacer la llamada. La implementación actualizada usa la invocación del servicio DAPR con compatibilidad con HttpClient:

``` csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public Task<IEnumerable<CatalogItem>> GetCatalogItemsAsync(IEnumerable<int> ids)
    {
        var requestUri = $"api/v1/catalog/items?ids={string.Join(",", ids)}";

        return _httpClient.GetFromJsonAsync<IEnumerable<CatalogItem>>(requestUri);
    }

    // ...
}
```

Observe cómo no se requiere ningún código específico de DAPR para realizar la llamada de invocación del servicio. Toda la comunicación se realiza mediante el objeto HttpClient estándar.

El HttpClient de DAPR se inserta en la `CatalogService` clase en el `Startup.ConfigureServices` método:

```csharp
services.AddSingleton<ICatalogService, CatalogService>(
    _ => new CatalogService(DaprClient.CreateInvokeHttpClient("catalog-api")));
```

La otra llamada realizada por el servicio Aggregator es a la API basket. Solo permite solicitudes autorizadas. El token de acceso se pasa en un encabezado de solicitud de *autorización* para asegurarse de que la llamada se realiza correctamente:

``` csharp
public class BasketService : IBasketService
{
    public Task UpdateAsync(BasketData currentBasket, string accessToken)
    {
        var request = new HttpRequestMessage(HttpMethod.Post, "api/v1/basket")
        {
            Content = JsonContent.Create(currentBasket)
        };
        request.Headers.Authorization = new AuthenticationHeaderValue(accessToken);

        var response = await _httpClient.SendAsync(request);
        response.EnsureSuccessStatusCode();
    }

    // ...
}
```

En este ejemplo, solo se usa la funcionalidad HttpClient estándar para llamar al servicio. Esto permite a los desarrolladores que ya están familiarizados con HttpClient reutilicen sus conocimientos existentes. Incluso permite que el código HttpClient existente use la invocación del servicio DAPR sin realizar ningún cambio.

## <a name="summary"></a>Resumen

En este capítulo, ha aprendido sobre el bloque de creación de invocación del servicio. Vio cómo invocar métodos remotos realizando llamadas HTTP directas al sidecar de DAPR y usando el SDK de .NET para DAPR.

El SDK de .NET para DAPR proporciona varias maneras de invocar métodos remotos. La compatibilidad con HttpClient es ideal para los desarrolladores que desean reutilizar los conocimientos existentes y es compatible con muchos marcos y bibliotecas existentes. DaprClient ofrece compatibilidad para usar directamente la API de invocación del servicio DAPR mediante la semántica HTTP o gRPC.

La arquitectura de referencia de eShopOnDapr muestra cómo se moderniza la solución eShopOnContainers original mediante la invocación del servicio DAPR. Agregar DAPR a eShop proporciona ventajas como los reintentos automáticos, el cifrado de mensajes mediante mTLS y una mejor observación.

### <a name="references"></a>Referencias

- [Bloque de creación de invocación del servicio DAPR](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/)

- [Supervisión de aplicaciones nativas distribuidas en la nube](../cloud-native/observability-patterns.md)

> [!div class="step-by-step"]
> [Anterior](state-management.md)
> [Siguiente](publish-subscribe.md)
