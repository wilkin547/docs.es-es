---
title: Implementación del patrón de interruptor
description: Aprenda a implementar el patrón de interruptor como un sistema complementario en los reintentos HTTP.
ms.date: 03/03/2020
ms.openlocfilehash: bebe0b4a622db928175f78f8d3e303d3d7adf170
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988890"
---
# <a name="implement-the-circuit-breaker-pattern"></a>Implementación del patrón de interruptor

Tal y como se indicó anteriormente, debe controlar los errores que pueden comportar un tiempo variable de recuperación, como puede suceder al intentar conectarse a un recurso o servicio remoto. Controlar este tipo de error puede mejorar la estabilidad y la resistencia de una aplicación.

En un entorno distribuido, las llamadas a servicios y recursos remotos pueden producir errores causados por errores transitorios, como tiempos de espera y conexiones de red lentas, o si los recursos responden de forma lenta o no están disponibles temporalmente. Estos errores suelen corregirse solos pasado un tiempo, y una aplicación en la nube sólida debería estar preparada para controlarlos mediante el uso de una estrategia como el "Patrón de reintento".

Pero también puede haber situaciones en que los errores se deban a eventos imprevistos que pueden tardar mucho más tiempo en corregirse. La gravedad de estos errores puede ir desde una pérdida parcial de conectividad hasta el fallo total del servicio. En estas situaciones, no tiene sentido que una aplicación reintente continuamente una operación que es probable que no se lleve a cabo correctamente.

Lo que debe hacer la aplicación es codificarse para aceptar que la operación ha fallado y controlar el error en consecuencia.

El uso de los reintentos HTTP de forma descuidada podría crear ataques por denegación de servicio ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) dentro de su propio software. Cuando se produce un error en un microservicio o se ejecuta lentamente, es posible que varios clientes reintenten solicitudes con error de forma repetida. Eso genera un riesgo peligroso de que el tráfico destinado al servicio con errores aumente de manera exponencial.

Por tanto, se necesita algún tipo de barrera de defensa para que se detengan las solicitudes excesivas cuando ya no tiene sentido seguir intentándolo. Esa barrera de defensa es precisamente el interruptor.

El patrón de interruptor tiene una finalidad distinta a la del "patrón de reintento". El "patrón de reintento" permite que una aplicación reintente una operación con la expectativa de que finalmente se realice correctamente. El patrón de interruptor impide que una aplicación realice una operación que es probable que falle. Una aplicación puede combinar estos dos patrones. Pero la lógica de reintento debe ser sensible a las excepciones devueltas por el interruptor, y debe dejar de intentar repetir la operación si el interruptor indica que un error no es transitorio.

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a>Implementación de un patrón de interruptor con `IHttpClientFactory` y Polly

Como sucede al implementar los reintentos, el enfoque recomendado para los interruptores es aprovechar las bibliotecas .NET de eficacia probada como Polly y su integración nativa con `IHttpClientFactory`.

Agregar una directiva de interruptor a la canalización de software intermedio saliente de `IHttpClientFactory` es tan sencillo como agregar un único fragmento de código incremental a lo que ya tiene cuando se usa `IHttpClientFactory`.

En este caso, lo único que se agrega al código que se usa para los reintentos de llamada HTTP es el código en el que se agrega la directiva de interruptor a la lista de directivas que se van a usar, como se muestra en el código incremental siguiente, parte del método ConfigureServices().

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

El método `AddPolicyHandler()` es el que agrega las directivas a los objetos `HttpClient` que se van a usar. En este caso, se agrega una directiva de Polly para un interruptor.

Para tener un enfoque más modular, la directiva de interruptor se define en un método independiente denominado `GetCircuitBreakerPolicy()`, como se muestra en el código siguiente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

En el ejemplo de código anterior, la directiva de interruptor se configura para que interrumpa o abra el circuito cuando se hayan producido cinco fallos consecutivos al reintentar las solicitudes HTTP. Cuando esto ocurre, el circuito se interrumpirá durante 30 segundos. En ese período, las llamadas no se podrán realizar debido al interruptor del circuito.  La directiva interpreta automáticamente las [excepciones relevantes y los códigos de estado HTTP](/aspnet/core/fundamentals/http-requests#handle-transient-faults) como errores.  

Los interruptores también se deben usar para redirigir las solicitudes a una infraestructura de reserva siempre que haya tenido problemas en un recurso concreto implementado en otro entorno que no sea el de la aplicación cliente o del servicio que realiza la llamada HTTP. De este modo, si se produce una interrupción en el centro de datos que afecta solo a los microservicios de back-end, pero no a las aplicaciones cliente, estas aplicaciones pueden redirigir a los servicios de reserva. Polly está creando una directiva nueva para automatizar este escenario de [directiva de conmutación por error](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).

Todas estas características sirven para los casos en los que se administra la conmutación por error desde el código .NET, y no cuando Azure lo hace de forma automática, con la transparencia de ubicación.

Desde un punto de vista del uso, al utilizar HttpClient no hay necesidad de agregar nada nuevo aquí porque el código es el mismo que cuando se usa `HttpClient` con `IHttpClientFactory`, como se mostró en las secciones anteriores.

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a>Prueba de reintentos HTTP e interruptores en eShopOnContainers

Cada vez que inicie la solución eShopOnContainers en un host Docker, debe iniciar varios contenedores. Algunos de los contenedores tardan más en iniciarse e inicializarse, como el contenedor de SQL Server. Esto sucede especialmente la primera vez que implementa la aplicación eShopOnContainers en Docker, porque las imágenes y la base de datos se tienen que configurar. El hecho de que algunos contenedores se inicien más lentamente que otros puede provocar que el resto de servicios lancen inicialmente excepciones HTTP, aunque configure las dependencias entre contenedores en el nivel de Docker Compose, como se ha explicado en las secciones anteriores. Las dependencias de Docker Compose entre contenedores solo se dan en el nivel de proceso. El proceso de punto de entrada del contenedor se puede iniciar, pero podría ser que SQL Server no estuviera listo para las consultas. El resultado puede ser una cascada de errores y la aplicación puede obtener una excepción al intentar utilizar dicho contenedor.

Este tipo de error también puede darse en el inicio, cuando la aplicación se está implementando en la nube. En ese caso, podría ser que los orquestadores movieran los contenedores de un nodo o máquina virtual a otro (iniciando así nuevas instancias) al repartir equitativamente los contenedores entre los nodos de clúster.

La forma en que estos problemas se solucionan al iniciar todos los contenedores en "eShopOnContainers" es mediante el patrón de reintento mostrado anteriormente.

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a>Prueba del interruptor en eShopOnContainers

Hay varias formas de interrumpir y abrir el circuito, y probarlo con eShopOnContainers.

Una opción es reducir el número permitido de reintentos a 1 en la directiva del interruptor y volver a implementar la solución completa en Docker. Con un solo reintento, hay una gran probabilidad de que una solicitud HTTP falle durante la implementación, el interruptor se abra y se produzca un error.

Otra opción consiste en usar middleware personalizado que se implemente en el microservicio **Basket**. Al habilitar este middleware, detecta todas las solicitudes HTTP y devuelve el código de estado 500. Para habilitar el middleware, envíe una solicitud GET al URI que falla, de forma similar a esta:

- `GET http://localhost:5103/failing`\
  Esta solicitud devuelve el estado actual del middleware. Si el middleware está habilitado, la solicitud devuelve el código de estado 500. Si el middleware está deshabilitado, no se emite ninguna respuesta.

- `GET http://localhost:5103/failing?enable`\
  Esta solicitud habilita el middleware.

- `GET http://localhost:5103/failing?disable`\
  Esta solicitud deshabilita el middleware.

Por ejemplo, cuando la aplicación se está ejecutando, puede habilitar el middleware realizando una solicitud con el siguiente URI en cualquier explorador. Tenga en cuenta que el microservicio de ordenación utiliza el puerto 5103.

`http://localhost:5103/failing?enable`

Después, puede comprobar el estado mediante el URI `http://localhost:5103/failing`, como se muestra en la Figura 8-5.

![Captura de pantalla de la comprobación del estado de una simulación de middleware con errores.](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

**Figura 8-5**. Comprobación del estado del middleware ASP.NET "con errores": en este caso, deshabilitado.

En este punto, el microservicio de la cesta responde con el código de estado 500 siempre que su llamada lo invoque.

Cuando se esté ejecutando el middleware, puede intentar realizar un pedido desde la aplicación web MVC. Como se produce un error en las solicitudes, el circuito se abre.

En el ejemplo siguiente, la aplicación web MVC presenta un bloque catch en la lógica para realizar un pedido.  Si el código detecta una excepción de circuito abierto, muestra un mensaje descriptivo al usuario en que se le indica que espere.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
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

Aquí tiene un resumen. La directiva de reintentos intenta realizar la solicitud HTTP varias veces y obtiene errores HTTP. Cuando el número de reintentos alcanza el número máximo establecido para la directiva del interruptor (en este caso, 5), la aplicación genera una excepción BrokenCircuitException. El resultado es un mensaje descriptivo, como el que se muestra en la Figura 8-6.

![Captura de pantalla de la aplicación web MVC con el error de servicio de cesta no operativo.](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

**Figura 8-6**. Interruptor que devuelve un error en la interfaz de usuario

Puede implementar otra lógica que indique cuándo se debe abrir o interrumpir el circuito. También puede probar una solicitud HTTP en un microservicio de back-end distinto si se dispone de un centro de datos de reserva o un sistema back-end redundante.

Por último, otra posibilidad para `CircuitBreakerPolicy` consiste en usar `Isolate` (que fuerza y mantiene la apertura del circuito) y `Reset` (que lo cierra de nuevo). Estas características se pueden utilizar para crear un punto de conexión HTTP de utilidad que invoque Aislar y Restablecer directamente en la directiva.  Este tipo de punto de conexión HTTP, protegido adecuadamente, también se puede usar en el entorno de producción para aislar temporalmente un sistema de nivel inferior, como cuando quiere actualizarlo. También puede activar el circuito manualmente para proteger un sistema de nivel inferior que le parezca que está fallando.

## <a name="additional-resources"></a>Recursos adicionales

- **Circuit Breaker pattern (Patrón de interruptor)** \
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
>[Anterior](implement-http-call-retries-exponential-backoff-polly.md)
>[Siguiente](monitor-app-health.md)
