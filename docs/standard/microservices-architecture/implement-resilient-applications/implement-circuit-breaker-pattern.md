---
title: "Implementar el patrón de disyuntor"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar el patrón de disyuntor"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementar el patrón de disyuntor

Tal y como se indicó anteriormente, debe controlar los errores que pueden tardar una cantidad variable de tiempo de recuperación, como podría ocurrir al intentar conectarse a un recurso o servicio remoto. Control de este tipo de error puede mejorar la estabilidad y la resistencia de una aplicación.

En un entorno distribuido, llamadas a servicios y recursos remotos pueden producir errores debido a errores transitorios, como conexiones de red lentas y tiempos de espera, o si se va recursos lenta o no están disponibles temporalmente. Estos errores suelen corrigen por sí mismos después de unos minutos y una aplicación de nube sólidas debe estar preparada para controlarlos mediante el uso de una estrategia como en el patrón de reintento.

Sin embargo, también puede haber situaciones donde los errores son debido a eventos imprevistos que pueden tardar mucho más tiempo en corregir. Estos errores pueden abarcar gravedad de una pérdida parcial de conectividad para el error completo de un servicio. En estas situaciones, podría ser sentido para una aplicación para continuamente volver a intentar una operación que no es probable que lleve a cabo correctamente. En su lugar, se debe codificar la aplicación para que acepte que ha fallado la operación y controlar los errores en consecuencia.

El patrón de disyuntor tiene un propósito diferente que el patrón de reintento. El patrón de reintento permite a una aplicación volver a intentar una operación de la expectativa de que finalmente se realizará correctamente la operación. El patrón de disyuntor impide que una aplicación realiza una operación que es probable que un error. Una aplicación puede combinar estos dos modelos mediante el patrón de reintento para invocar una operación a través de un disyuntor. Sin embargo, la lógica de reintento debe ser sensible a las excepciones devueltas por el disyuntor, y deben abandonar reintentos si el disyuntor indica que un error no es transitorio.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementar un patrón de disyuntor con Polly

Como al implementar reintentos, el enfoque recomendado para los disyuntores consiste en aprovechar las ventajas de eficacia comprobadas de bibliotecas de .NET como Polly.

La aplicación eShopOnContainers utiliza la directiva de disyuntor de Polly al implementar los reintentos HTTP. De hecho, la aplicación aplica a las dos directivas a la clase de utilidad ResilientHttpClient. Siempre que se use un objeto de tipo ResilientHttpClient para las solicitudes HTTP (desde eShopOnContainers), que va a aplicar esas directivas de ambos, pero puede agregar directivas adicionales, demasiado.

El único que se agrega a continuación al código utilizado para los reintentos de llamada HTTP es el código que agrega la directiva de disyuntor a la lista de directivas que se va a usar, tal como se muestra al final del código siguiente:

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

El código agrega una directiva para el contenedor de HTTP. Que la directiva define un disyuntor que se abre cuando el código detecta el número especificado de excepciones consecutivos (excepciones en una fila), como pasa en el parámetro exceptionsAllowedBeforeBreaking (5 en este caso). Una vez abierto el circuito, las solicitudes HTTP no funcionan, pero se produce una excepción.

Los disyuntores también debe utilizarse para redirigir las solicitudes a una infraestructura de reserva si es posible que tenga problemas en un recurso concreto que se implementa en un entorno diferente de la aplicación cliente o servicio que realiza la llamada HTTP. De este modo, si se produce una interrupción en el centro de datos que afecta solo la microservicios de back-end, pero no las aplicaciones de cliente, las aplicaciones cliente pueden redirigir a los servicios de reserva. Polly está planeando una directiva nueva para automatizar esta tarea, [directiva de conmutación por error](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) escenario.

Por supuesto, todas esas características están en los casos donde está administrando la conmutación por error desde dentro del código. NET, en lugar de tener que administran automáticamente para Azure, con transparencia de ubicación.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Uso de la clase de utilidad ResilientHttpClient desde eShopOnContainers

Utilice la clase de utilidad ResilientHttpClient de forma similar a cómo utilizar la clase .NET HttpClient. En el ejemplo siguiente de la aplicación web MVC de eShopOnContainers (la clase de agente OrderingService utilizada por OrderController), el objeto ResilientHttpClient se aplica a través del parámetro httpClient del constructor. A continuación, el objeto se usa para realizar solicitudes HTTP.

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

Cada vez que la \_se utiliza el objeto de miembro apiClient, usa internamente la clase contenedora con Polly policiesؙ: la directiva de reintentos, la directiva de disyuntor y cualquier otra directiva que desea aplicar de la colección de directivas de Polly.

## <a name="testing-retries-in-eshoponcontainers"></a>Probar los reintentos en eShopOnContainers

Cada vez que inicia la solución eShopOnContainers en un host Docker, debe iniciar varios contenedores. Algunos de los contenedores son más lentos iniciar e inicializar, al igual que el contenedor de SQL Server. Esto es especialmente cierto en la primera vez que implemente la aplicación eShopOnContainers en Docker, porque es necesario configurar las imágenes y la base de datos. El hecho de que algunos contenedores de inician con una velocidad superior otros pueden provocar el resto de los servicios inicialmente iniciar excepciones de HTTP, incluso si configura las dependencias entre los contenedores en la redacción docker nivel, como se explica en las secciones anteriores. Los docker-crear dependencias entre los contenedores son simplemente en el nivel de proceso. Se puede iniciar el proceso de punto de entrada del contenedor, pero SQL Server podrían no estar preparado para las consultas. El resultado puede ser una cascada de errores y la aplicación puede obtener una excepción al intentar utilizar dicho contenedor determinado.

También puede ver este tipo de error en el inicio cuando la aplicación se implementa en la nube. En ese caso, orchestrators podría ser mover contenedores de un nodo o la máquina virtual a otra (que es, a partir de las nuevas instancias) cuando el número de contenedores de equilibrio en todos los nodos del clúster.

La manera eShopOnContainers soluciona este problema es mediante el patrón de reintento que se mostrados anteriormente. También es ¿por qué, al comienzo de la solución, podría obtener seguimientos del registro o advertencias similar al siguiente:

> "**Reintento 1 implementa con RetryPolicy de Polly**, debido a que: System.Net.Http.HttpRequestException: se produjo un error al enviar la solicitud. ---&gt;System.Net.Http.CurlException: No se pudo conectar al servidor\\n en System.Net.Http.CurlHandler.ThrowIfCURLEError (error CURLcode)\\n en \[... \].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Probar el disyuntor en eShopOnContainers

Hay varias maneras de poder abrir el circuito y probarlo con eShopOnContainers.

Una opción consiste en reducir el número permitido de reintentos en 1 en la directiva de disyuntor y volver a implementar la solución completa en Docker. Con un reintento único, hay una gran probabilidad de que una solicitud HTTP se producirá un error durante la implementación, el disyuntor se abrirá y se produce un error.

Otra opción es usar middleware personalizado que se implementa en la ordenación microservicio. Cuando se habilita este middleware, detecta todas las solicitudes HTTP y devuelve el código de estado 500. Puede habilitar el middleware realizando una solicitud GET al error del URI, similar al siguiente:

-   GET/error

Esta solicitud devuelve el estado actual del middleware de. Si está habilitado el software intermedio, la solicitud devuelve el código de estado 500. Si se deshabilita el software intermedio, no hay ninguna respuesta.

-   GET/errores? habilitar

Esta solicitud habilita el middleware.

-   GET/errores? deshabilitar

Esta solicitud deshabilita el middleware.

Por ejemplo, una vez que se ejecuta la aplicación, puede habilitar el middleware realizando una solicitud usando el siguiente URI en cualquier explorador. Tenga en cuenta que la ordenación microservicio utiliza el puerto 5102.

http://localhost:5102 / errores? habilitar

A continuación, puede comprobar el estado usando el URI [http://localhost:5102 / errores](http://localhost:5100/failing), tal y como se muestra en la figura 10-4.

![](./media/image4.png)

**Figura 10-4**. Simular un error con middleware ASP.NET

En este momento, la ordenación responde de microservicio con código de estado 500 cada vez que se llama a invocarlo.

Una vez que se está ejecutando el software intermedio, puede intentar realizar un pedido de la aplicación web MVC. Debido al error de las solicitudes, se abrirá el circuito.

En el ejemplo siguiente, puede ver que la aplicación web MVC tiene una instrucción catch bloquear en la lógica para realizar un pedido. Si el código detecta una excepción de circuito abierto, muestra al usuario un mensaje descriptivo que les indica que esperar.

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

Este es un resumen. La directiva de reintentos prueba varias veces para que la solicitud HTTP y obtiene errores HTTP. Cuando el número de intentos alcanza el número máximo establecido para la directiva de disyuntor (en este caso, 5), la aplicación produce una BrokenCircuitException. El resultado es un mensaje descriptivo, como se muestra en la figura 10-5.

![](./media/image5.png)

**Figura 5-10**. Disyuntor devolviendo un error en la interfaz de usuario

Puede implementar una lógica diferente para cuando se abra el circuito. O bien puede intentar una solicitud HTTP con un microservicio de back-end diferente si hay un centro de datos de reserva o el sistema back-end redundante.

Por último, otra posibilidad de que el CircuitBreakerPolicy es usar aíslan (lo que obliga a abrir y mantiene abierto el circuito) y restablecimiento (que se cierra nuevo). Puede utilizarse para crear un punto de conexión HTTP de utilidad que invoca a aislar y restablecimiento directamente en la directiva. Este tipo de extremo HTTP también podría usarse, protegida adecuadamente, en el entorno de producción para aislar temporalmente un sistema de nivel inferior, como cuando desee actualizarlo. O bien, podría viaje el circuito manualmente para proteger un sistema de nivel inferior que sospecha que se produzca un error.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Agregar una estrategia de vibración a la directiva de reintentos

Una directiva de reintentos regular puede afectar a su sistema en los casos de escalabilidad y alta simultaneidad y en elevada contención. Para superar los picos de reintentos similar procedentes de muchos clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva de algoritmo de reintento. Esto puede mejorar el rendimiento general del sistema to-end mediante la adición de aleatoriedad al retroceso exponencial. Esto se extiende los picos cuando surgen problemas. Cuando usas Polly, código para implementar la vibración podría ser similar al ejemplo siguiente:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Recursos adicionales

-   **Vuelva a intentar patrón**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Resistencia de conexión** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (resistencia de .NET y la biblioteca de control de errores transitorios) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Patrón de disyuntor**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Saavedra. Vibración: Hacer cosas mejor con aleatoriedad** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Anterior] (implement-http-call-retries-exponential-backoff-polly.md) [siguiente] (aplicación-monitor-health.md)
