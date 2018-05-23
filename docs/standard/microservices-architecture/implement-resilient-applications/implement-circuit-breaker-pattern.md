---
title: Implementación del patrón de interruptor
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementación del patrón de interruptor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: dea94d8eda3341cca5e3aaf6b3c8369c27381135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementación del patrón de interruptor

Tal y como se indicó anteriormente, debe controlar los errores que pueden comportar un tiempo variable de recuperación, como puede suceder al intentar conectarse a un recurso o servicio remoto. Controlar este tipo de error puede mejorar la estabilidad y la resistencia de una aplicación.

En un entorno distribuido, las llamadas a servicios y recursos remotos pueden producir errores causados por errores transitorios, como tiempos de espera y conexiones de red lentas, o si los recursos van lentos o no están disponibles temporalmente. Estos errores suelen corregirse solos pasados unos minutos y hay que tener una aplicación sólida en la nube preparada para controlarlos mediante el uso de una estrategia como el patrón de reintento.

Pero también puede haber situaciones en que los errores se deban a eventos imprevistos que pueden tardar mucho más tiempo en corregirse. La gravedad de estos errores puede ir desde una pérdida parcial de conectividad hasta el fallo total del servicio. En estas situaciones, no tiene sentido que una aplicación reintente continuamente una operación que es probable que no se lleve a cabo correctamente. Lo que debe hacer la aplicación es codificarse para aceptar que la operación ha fallado y controlar el error en consecuencia.

El patrón de interruptor tiene una finalidad distinta a la del patrón de reintento. El patrón de reintento permite que una aplicación reintente una operación con la expectativa de que finalmente se realice correctamente. El patrón de interruptor impide que una aplicación realice una operación que es probable que falle. Una aplicación puede combinar estos dos patrones utilizando el patrón de reintento para invocar una operación mediante un interruptor. Pero la lógica de reintento debe ser sensible a las excepciones devueltas por el interruptor y debe dejar de intentar llevar a cabo la operación si el interruptor indica que un error no es transitorio.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementación de un patrón de interruptor con Polly

Al implementar los reintentos, en el caso de los interruptores se recomienda aprovechar bibliotecas .NET de eficacia probada, como Polly.

La aplicación eShopOnContainers utiliza la directiva de interruptor de Polly al implementar los reintentos de HTTP. De hecho, la aplicación aplica las dos directivas a la clase de utilidad ResilientHttpClient. Siempre que use un objeto del tipo ResilientHttpClient para las solicitudes HTTP (desde eShopOnContainers), va a aplicar esas dos directivas, aunque también puede agregar directivas adicionales.

En este caso, lo único que se agrega al código utilizado para los reintentos de llamada HTTP es el código en el que debe agregar la directiva de interruptor a la lista de directivas que se van a utilizar, como se muestra al final del código siguiente:

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

El código agrega una directiva al contenedor de HTTP. Esa directiva define un interruptor que se abre cuando el código detecta el número especificado de excepciones consecutivas (excepciones seguidas), como sucede en el parámetro exceptionsAllowedBeforeBreaking (5 en este caso). Una vez abierto el circuito, las solicitudes HTTP no funcionan, pero se produce una excepción.

Los interruptores también deben utilizarse para redirigir las solicitudes a una infraestructura de reserva siempre que tenga problemas en un recurso concreto que se implemente en un entorno distinto al de la aplicación o del servicio del cliente que realiza la llamada HTTP. De este modo, si se produce una interrupción en el centro de datos que afecta solo a los microservicios de back-end, pero no a las aplicaciones cliente, estas aplicaciones pueden redirigir a los servicios de reserva. Polly está creando una directiva nueva para automatizar este escenario de [directiva de conmutación por error](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).

Todas estas características sirven para los casos en que administre la conmutación por error desde el código .NET, y no cuando Azure los administra automáticamente por usted, con la transparencia de ubicación.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Uso de la clase de utilidad ResilientHttpClient desde eShopOnContainers

La clase de utilidad ResilientHttpClient se utiliza de forma similar a cómo se utiliza la clase .NET HttpClient. En el ejemplo siguiente de la aplicación web MVC de eShopOnContainers (la clase de agente OrderingService utilizada por OrderController), el objeto ResilientHttpClient se aplica mediante el parámetro httpClient del constructor. A continuación, el objeto se usa para realizar solicitudes HTTP.

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

Cada vez que se usa el objeto de miembro \_apiClient, este emplea internamente la clase contenedora con las directivas de Polly: la directiva de reintentos, la directiva de interruptor y cualquier otra directiva de Polly que quiera aplicar.

## <a name="testing-retries-in-eshoponcontainers"></a>Pruebas de los reintentos en eShopOnContainers

Cada vez que inicie la solución eShopOnContainers en un host Docker, debe iniciar varios contenedores. Algunos de los contenedores tardan más en iniciarse e inicializarse, como el contenedor de SQL Server. Esto sucede especialmente la primera vez que implementa la aplicación eShopOnContainers en Docker, porque las imágenes y la base de datos se tienen que configurar. El hecho de que algunos contenedores se inicien más lentamente que otros puede provocar que el resto de servicios lancen inicialmente excepciones HTTP, aunque configure las dependencias entre contenedores en el nivel de Docker Compose, como se ha explicado en las secciones anteriores. Las dependencias de Docker Compose entre contenedores solo se dan en el nivel de proceso. El proceso de punto de entrada del contenedor se puede iniciar, pero podría ser que SQL Server no estuviera listo para las consultas. El resultado puede ser una cascada de errores y la aplicación puede obtener una excepción al intentar utilizar dicho contenedor.

Este tipo de error también puede darse en el inicio, cuando la aplicación se está implementando en la nube. En ese caso, podría ser que los orquestadores movieran los contenedores de un nodo o máquina virtual a otro (iniciando así nuevas instancias) al repartir equitativamente los contenedores entre los nodos de clúster.

La forma que tiene eShopOnContainers de solucionar este problema es utilizar el patrón de reintento que hemos mostrado anteriormente. Este es también el motivo por el cual, al iniciar la solución, puede ser que reciba seguimientos del registro o advertencias como las siguientes:

> "**Reintento 1 implementado con RetryPolicy de Polly**, en que: System.Net.Http.HttpRequestException: error al enviar la solicitud. ---&gt; System.Net.Http.CurlException: no se pudo conectar al servidor\\n en System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n en \[...\].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Prueba del interruptor en eShopOnContainers

Hay varias formas de abrir el circuito y probarlo con eShopOnContainers.

Una opción es reducir el número permitido de reintentos a 1 en la directiva del interruptor y volver a implementar la solución completa en Docker. Con un solo reintento, hay una gran probabilidad de que una solicitud HTTP falle durante la implementación, el interruptor se abra y se produzca un error.

Otra opción consiste en usar un middleware personalizado que se implemente en el microservicio `Basket`. Al habilitar este middleware, detecta todas las solicitudes HTTP y devuelve el código de estado 500. Para habilitar el middleware, envíe una solicitud GET al URI que falla, de forma similar a esta:

-   GET /failing

Esta solicitud devuelve el estado actual del middleware. Si el middleware está habilitado, la solicitud devuelve el código de estado 500. Si el middleware está deshabilitado, no se emite ninguna respuesta.

-   GET /failing?enable

Esta solicitud habilita el middleware.

-   GET /failing?disable

Esta solicitud deshabilita el middleware.

Por ejemplo, cuando la aplicación se está ejecutando, puede habilitar el middleware realizando una solicitud con el siguiente URI en cualquier explorador. Tenga en cuenta que el microservicio de ordenación utiliza el puerto 5103.

http://localhost:5103/failing?enable

Luego, puede comprobar el estado usando el URI [http://localhost:5103/failing](http://localhost:5103/failing), como se muestra en la Figura 10-4.

![](./media/image4.png)

**Figura 10-4**. Comprobación del estado del middleware ASP.NET "Error": en este caso, deshabilitado 

En este punto, el microservicio de la cesta responde con el código de estado 500 siempre que su llamada lo invoque.

Cuando se esté ejecutando el middleware, puede intentar realizar un pedido desde la aplicación web MVC. Como el error falla, el circuito se abre.

En el ejemplo siguiente, la aplicación web MVC presenta un bloque catch en la lógica para realizar un pedido. Si el código detecta una excepción de circuito abierto, muestra un mensaje descriptivo al usuario en que se le indica que espere.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

Aquí tiene un resumen. La directiva de reintentos intenta realizar la solicitud HTTP varias veces y obtiene errores HTTP. Cuando el número de intentos alcanza el número máximo establecido para la directiva del interruptor (en este caso, 5), la aplicación emite la excepción BrokenCircuitException. El resultado es un mensaje descriptivo, como el que se muestra en la Figura 10-5.

![](./media/image5.png)

**Figura 10-5**. Interruptor que devuelve un error en la interfaz de usuario

Puede implementar una lógica que indique cuándo se debe abrir el circuito. También puede probar una solicitud HTTP en un microservicio de back-end distinto si se dispone de un centro de datos de reserva o un sistema back-end redundante.

Por último, otra posibilidad de CircuitBreakerPolicy es utilizar Aislar (que fuerza y mantiene la apertura del circuito) y Restablecer (que lo cierra de nuevo). Estas características se pueden utilizar para crear un punto de conexión HTTP de utilidad que invoque Aislar y Restablecer directamente en la directiva. Este tipo de punto de conexión HTTP, protegido adecuadamente, también se puede usar en el entorno de producción para aislar temporalmente un sistema de nivel inferior, como cuando quiere actualizarlo. También puede activar el circuito manualmente para proteger un sistema de nivel inferior que le parezca que está fallando.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Agregar una estrategia de vibración a la directiva de reintentos

Una directiva de reintentos normal puede afectar a su sistema en casos de escalabilidad y simultaneidad altas y de gran contención. Para gestionar los picos de reintentos similares procedentes de diferentes clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva o algoritmo de reintento. Esto puede mejorar el rendimiento general del sistema de un extremo a otro añadiendo aleatoriedad al retroceso exponencial. De esta forma, cuando surgen problemas, los picos se reparten. Al utilizar Polly, el código para implementar la vibración puede parecerse a este ejemplo:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Recursos adicionales

-   **Retry pattern (Patrón de reintento)**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Connection Resiliency** (Entity Framework Core) (Resistencia de conexión [Entity Framework Core])[*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia .NET])[*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Circuit Breaker pattern (Patrón de interruptor)**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. Jitter: Making Things Better With Randomness** (Vibración: hacer mejor las cosas gracias a la aleatoriedad) https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Anterior] (implement-http-call-retries-exponential-backoff-polly.md) [Siguiente] (monitor-app-health.md)
