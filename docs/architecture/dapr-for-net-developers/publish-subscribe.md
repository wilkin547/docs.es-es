---
title: El bloque DAPR Publish & subscribe Building
description: Una descripción de la publicación DAPR & subscribe Building-Block y cómo aplicarla
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: 11898430d897ec85b7e367fa0e93ca912279784b
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623829"
---
# <a name="the-dapr-publish--subscribe-building-block"></a>El bloque DAPR Publish & subscribe Building

El [patrón de publicación y suscripción](/azure/architecture/patterns/publisher-subscriber) (a menudo denominado "pub/sub") es un patrón de mensajería conocido y ampliamente utilizado. Los arquitectos lo adoptan normalmente en aplicaciones distribuidas. Sin embargo, la infraestructura para implementarla puede ser compleja. A menudo hay diferencias de características sutiles entre distintos productos de mensajería. DAPR ofrece un bloque de creación que simplifica considerablemente la implementación de la funcionalidad de pub/sub.

## <a name="what-it-solves"></a>Qué resuelve

La principal ventaja del patrón Publish-Subscribe es el **acoplamiento flexible**, que a veces se conoce como [desacoplamiento temporal](/azure/architecture/guide/technology-choices/messaging#decoupling). El patrón desacopla los servicios que envían mensajes (los **publicadores**) de los servicios que consumen mensajes (los **suscriptores**). Los publicadores y los suscriptores no se reconocen entre sí: ambos dependen de un agente de **mensajes** centralizado que distribuye los mensajes.

En la figura 7-1 se muestra la arquitectura de alto nivel del patrón pub/sub.

![El patrón pub/sub](./media/publish-subscribe/pub-sub-pattern.png)

**Figura 7-1**. El patrón pub/sub.

En la ilustración anterior, tenga en cuenta los pasos del patrón:

1. Los publicadores envían mensajes al agente de mensajes.
1. Los suscriptores se enlazan a una suscripción en el agente de mensajes.
1. El agente de mensajes reenvía una copia del mensaje a las suscripciones interesadas.
1. Los suscriptores consumen mensajes de sus suscripciones.

La mayoría de los agentes de mensajes encapsulan un mecanismo de puesta en cola que puede conservar los mensajes una vez recibidos. Con él, el agente de mensajes garantiza la **durabilidad** almacenando el mensaje. No es necesario que los suscriptores estén disponibles de inmediato o incluso en línea cuando un publicador envía un mensaje. Una vez disponible, el suscriptor recibe y procesa el mensaje.  DAPR garantiza **una semántica al menos una vez** para la entrega de mensajes. Una vez que se publica un mensaje, se entregará al menos una vez a cualquier suscriptor interesado.

 > Si el servicio solo puede procesar un mensaje una vez, deberá proporcionar una comprobación de [Idempotencia](/azure/architecture/microservices/design/api-design#idempotent-operations) para asegurarse de que el mismo mensaje no se procesa varias veces. Aunque esta lógica se puede codificar, algunos agentes de mensajes, como Azure Service Bus, proporcionan capacidades de mensajería de *detección de duplicados* integrados.

Hay varios productos de agente de mensajes disponibles, tanto comerciales como de código abierto. Cada una tiene ventajas y desventajas. Su trabajo es cumplir los requisitos del sistema con el agente adecuado. Una vez seleccionado, se recomienda desacoplar la aplicación de la fontanería del agente de mensajes. Para lograr esta funcionalidad, ajuste el agente dentro de una *abstracción*. La abstracción encapsula la fontanería del mensaje y expone operaciones genéricas de pub/sub en el código. El código se comunica con la abstracción, no con el agente de mensajes real. A pesar de tomar una decisión acertada, tendrá que escribir y mantener la abstracción y su implementación subyacente. Este enfoque requiere código personalizado que puede ser complejo, repetitivo y propenso a errores.

El bloque DAPR Publish & subscribe Building proporciona la abstracción de mensajería y la implementación. El código personalizado que habría tenido que escribir está precompilado y encapsulado en el bloque de creación de DAPR. Se enlaza a él y se usa. En lugar de escribir el código de la infraestructura de mensajería, usted y su equipo se centran en crear funciones empresariales que agregan valor a sus clientes.

## <a name="how-it-works"></a>Cómo funciona

El bloque DAPR Publish & subscribe Building proporciona un marco de API independiente de la plataforma para enviar y recibir mensajes. Los servicios publican mensajes en un [tema](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions)con nombre. Los servicios se suscriben a un tema para consumir mensajes.

El servicio llama a la API pub/sub en el sidecar de DAPR. A continuación, el sidecar realiza las llamadas a un componente pub/sub de DAPR predefinido que encapsula un producto de agente de mensajes específico. En la figura 7-2 se muestra la pila de mensajería pub/sub de DAPR.

![La pila pub/sub](./media/publish-subscribe/pub-sub-buildingblock.png)

**Figura 7-2**. La pila pub/sub de DAPR.

El bloque DAPR Publish & subscribe Building se puede invocar de muchas maneras.

En el nivel más bajo, cualquier plataforma de programación puede invocar el bloque de creación a través de HTTP o gRPC con la **API nativa de DAPR**. Para publicar un mensaje, realice la siguiente llamada de API:

``` http
http://localhost:<dapr-port>/v1.0/publish/<pub-sub-name>/<topic>
```

Hay varios segmentos de dirección URL específicos de DAPR en la llamada anterior:

- `<dapr-port>` proporciona el número de puerto en el que escucha el sidecar de DAPR.
- `<pub-sub-name>` proporciona el nombre del componente pub/sub de DAPR seleccionado.
- `<topic>` proporciona el nombre del tema en el que se publica el mensaje.

Con la herramienta de línea de comandos de *rizo* para publicar un mensaje, puede probarlo:

``` curl
curl -X POST http://localhost:3500/v1.0/publish/pubsub/newOrder \
  -H "Content-Type: application/json" \
  -d '{ "orderId": "1234", "productId": "5678", "amount": 2 }'
```

Los mensajes se reciben Suscríbase a un tema. En el inicio, el tiempo de ejecución de DAPR llamará a la aplicación en un punto de conexión conocido para identificar y crear las suscripciones necesarias:

``` http
http://localhost:<appPort>/dapr/subscribe
```

- `<appPort>` informa al sidecar de DAPR del puerto en el que escucha la aplicación.

Puede implementar este punto de conexión usted mismo. Sin embargo, DAPR proporciona formas más intuitivas de implementarlo. Abordaremos esta funcionalidad más adelante en este capítulo.

La respuesta de la llamada contiene una lista de temas a los que se suscribirán las aplicaciones. Cada uno incluye un extremo al que llamar cuando el tema recibe un mensaje. A continuación se muestra un ejemplo de una respuesta:

```json
[
  {
    "pubsubname": "pubsub",
    "topic": "newOrder",
    "route": "/orders"
  },
  {
    "pubsubname": "pubsub",
    "topic": "newProduct",
    "route": "/productCatalog/products"
  }
]
```

En la respuesta JSON, puede ver que la aplicación desea suscribirse a los temas `newOrder` y `newProduct` . Registra los puntos `/orders` de conexión y `/productCatalog/products` para cada uno de ellos, respectivamente. En ambas suscripciones, la aplicación se enlaza al componente DAPR denominado `pubsub` .

En la figura 7-3 se presenta el flujo del ejemplo.

![Ejemplo de flujo de pub/sub con DAPR](media/publish-subscribe/pub-sub-flow.png)

**Figura 7-3**. flujo pub/sub con DAPR.

En la ilustración anterior, tenga en cuenta el flujo:

1. El sidecar de DAPR para el servicio B llama al `/dapr/subscribe` extremo del servicio b (el consumidor). El servicio responde con las suscripciones que desea crear.
1. El sidecar de DAPR para el servicio B crea las suscripciones solicitadas en el agente de mensajes.
1. El servicio A publica un mensaje en el `/v1.0/publish/<pub-sub-name>/<topic>` punto de conexión en el servicio DAPR a sidecar.
1. El servicio a sidecar publica el mensaje en el agente de mensajes.
1. El agente de mensajes envía una copia del mensaje al sidecar del servicio B.
1. El sidecar del servicio B llama al punto de conexión correspondiente a la suscripción (en este caso `/orders` ) del servicio b. El servicio responde con un código de Estado HTTP `200 OK` para que el sidecar considere que el mensaje se administra correctamente.

En el ejemplo, el mensaje se trata correctamente. Pero si algo va mal mientras el servicio B controla la solicitud, puede usar la respuesta para especificar lo que debe ocurrir con el mensaje. Cuando devuelve un código de Estado HTTP `404` , se registra un error y se quita el mensaje. Con cualquier otro código de estado que sea `200` o `404` , se registra una advertencia y se vuelve a intentar el mensaje. Como alternativa, el servicio B puede especificar explícitamente lo que debe ocurrir con el mensaje incluyendo una carga de JSON en el cuerpo de la respuesta:

```json
{
  "status": "<status>"
}
```

En la tabla siguiente se muestran los `status` valores disponibles:

| Status           | Acción                                                       |
| ---------------- | ------------------------------------------------------------ |
| CORRECTA          | El mensaje se considera como procesado correctamente y se ha quitado. |
| REINTENTAR            | El mensaje se vuelve a intentar.                                      |
| DROP             | Se registra una advertencia y se quita el mensaje.              |
| Cualquier otro Estado | El mensaje se vuelve a intentar.                                      |

### <a name="competing-consumers"></a>Consumidores de la competencia

Al escalar horizontalmente una aplicación que se suscribe a un tema, debe tratar con los consumidores de la competencia. Solo una instancia de aplicación debe controlar un mensaje enviado al tema. Afortunadamente, DAPR controla ese problema. Cuando varias instancias de un servicio con el mismo identificador de aplicación se suscriben a un tema, DAPR entrega cada mensaje solo a uno de ellos.

### <a name="sdks"></a>SDK

Realizar llamadas HTTP a las API de DAPR nativas requiere mucho tiempo y es abstracto. Las llamadas se diseñan en el nivel de HTTP y deberá controlar los problemas de fontanería, como la serialización y los códigos de respuesta HTTP. Afortunadamente, hay una forma más intuitiva. DAPR proporciona varios SDK específicos del lenguaje para plataformas de desarrollo populares. En el momento de redactar este documento, vaya, Node.js, Python, .NET, Java y JavaScript están disponibles.

## <a name="use-the-dapr-net-sdk"></a>Uso del SDK de .NET para DAPR

Para los desarrolladores de .NET, el [SDK de .net para DAPR](https://www.nuget.org/packages/Dapr.Client) proporciona una manera más productiva de trabajar con DAPR. El SDK expone una `DaprClient` clase a través de la cual puede invocar directamente la funcionalidad de DAPR. Es intuitivo y fácil de usar.

Para publicar un mensaje, `DaprClient` expone un `PublishEventAsync` método.

```csharp
var data = new OrderData
{
  orderId = "123456",
  productId = "67890",
  amount = 2
};

var daprClient = new DaprClientBuilder().Build();

await daprClient.PublishEventAsync<OrderData>("pubsub", "newOrder", data);
```

- El primer argumento `pubsub` es el nombre del componente DAPR que proporciona la implementación del agente de mensajes. Abordaremos los componentes más adelante en este capítulo.
- El segundo argumento `neworder` proporciona el nombre del tema al que se va a enviar el mensaje.
- El tercer argumento es la carga del mensaje.
- Puede especificar el tipo .NET del mensaje utilizando el parámetro de tipo genérico del método.

Para recibir mensajes, debe enlazar un punto de conexión a una suscripción para un tema registrado. La biblioteca de AspNetCore para DAPR hace que sea trivial. Por ejemplo, supongamos que tiene un método de acción ASP.NET WebAPI existente titulado `CreateOrder` :

```csharp
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

 > Debe agregar una referencia al paquete de NuGet [DAPR. AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) en el proyecto para consumir la integración de DAPR ASP.net Core.

Para enlazar este método de acción a un tema, debe decorarlo con el `Topic` atributo:

```csharp
[Topic("pubsub", "newOrder")]
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

Se especifican dos elementos clave con este atributo:

- Componente pub/sub de DAPR de destino (en este caso `pubsub` ).
- Tema al que se va a suscribir (en este caso `newOrder` ).

A continuación, DAPR invoca ese método de acción a medida que recibe mensajes para ese tema.

También necesitará habilitar ASP.NET Core para usar DAPR. El SDK de .NET para DAPR proporciona varios métodos de extensión que se pueden invocar en la `Startup` clase.

En el `ConfigureServices` método, debe agregar el siguiente método de extensión:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddControllers().AddDapr();
}
```

Al anexar el `AddDapr` método de extensión al `AddControllers` método de extensión, se registran los servicios necesarios para integrar DAPR en la canalización de MVC. También registra una `DaprClient` instancia en el contenedor de inserción de dependencias, que se puede insertar en cualquier parte del servicio.

En el `Configure` método, debe agregar los siguientes componentes de middleware para habilitar DAPR:

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // ...
    app.UseCloudEvents();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapSubscribeHandler();
        // ...
    });
}
```

La llamada a `UseCloudEvents` agrega middleware de **CloudEvents** a la canalización de middleware ASP.net Core. Este middleware desencapsulará las solicitudes que usan el formato estructurado CloudEvents, por lo que el método receptor puede leer la carga del evento directamente.

> [CloudEvents](https://cloudevents.io/) es un formato de mensajería normalizado, que proporciona una manera común de describir la información de eventos entre plataformas. DAPR adopta CloudEvents. Para obtener más información sobre CloudEvents, consulte la [especificación de CloudEvents](https://github.com/cloudevents/spec/tree/v1.0).

La llamada a `MapSubscribeHandler` en la configuración de enrutamiento del punto de conexión agregará un punto de conexión de suscripción de DAPR a la aplicación. Este punto de conexión responderá a las solicitudes de `/dapr/subscribe` . Cuando se llama a este punto de conexión, buscará automáticamente todos los métodos de acción de WebAPI decorados con el `Topic` atributo e indicará a DAPR que cree suscripciones para ellos.

## <a name="pubsub-components"></a>Componentes pub/sub

Los [componentes pub/sub](https://github.com/dapr/components-contrib/tree/master/pubsub) de DAPR controlan el transporte real de los mensajes. Hay varios disponibles. Cada encapsula un producto de agente de mensajes específico para implementar la funcionalidad pub/sub. En el momento de escribir este documento, los siguientes componentes pub/sub estaban disponibles:

- Apache Kafka
- Azure Event Hubs
- Azure Service Bus
- SNS/SQS DE AWS
- Pub/sub de GCP
- Hazelcast
- MQTT
- NATS
- Pulsar
- RabbitMQ
- Secuencias de Redis

> [!NOTE]
> La pila en la nube de Azure tiene la funcionalidad de mensajería (Azure Service Bus) y la disponibilidad de streaming de eventos (Azure Event hubs).

Estos componentes los crea la comunidad en un repositorio de componentes que se contrata [en github](https://github.com/dapr/components-contrib/tree/master/pubsub). Le recomendamos que escriba su propio componente DAPR para un agente de mensajes que todavía no se admite.

### <a name="configure-pubsub-components"></a>Configurar componentes pub/sub

Mediante el uso de un archivo de configuración DAPR, puede especificar los componentes pub/sub que se van a usar. Esta configuración contiene varios campos. El `name` campo especifica el componente pub/sub que quiere usar. Al enviar o recibir un mensaje, debe especificar este nombre (como vimos anteriormente en la `PublishEventAsync` firma del método).

A continuación se muestra un ejemplo de un archivo de configuración de DAPR para configurar un componente de agente de mensajes de RabbitMQ:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub-rq
spec:
  type: pubsub.rabbitmq
  version: v1
  metadata:
  - name: host
    value: "amqp://localhost:5672"
  - name: durable
    value: true
```

En este ejemplo, puede ver que puede especificar cualquier configuración específica del agente de mensajes en el `metadata` bloque. En este caso, RabbitMQ se configura para crear colas duraderas. Pero el componente RabbitMQ tiene más opciones de configuración. Cada una de las configuraciones de los componentes tendrá su propio conjunto de campos posibles. Puede leer los campos que están disponibles en la documentación de cada [componente pub/sub](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/).

Junto a la manera programática de suscribirse a un tema desde el código, DAPR pub/sub también proporciona una manera declarativa de suscribirse a un tema. Este enfoque quita la dependencia DAPR del código de la aplicación. Por lo tanto, también permite que una aplicación existente se suscriba a temas sin realizar cambios en el código. En el ejemplo siguiente se muestra un archivo de configuración de DAPR para configurar una suscripción:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Subscription
metadata:
  name: newOrder-subscription
spec:
  pubsubname: pubsub
  topic: newOrder
  route: /orders
scopes:
- ServiceB
- ServiceC
```

Tiene que especificar varios elementos con cada suscripción:

- Nombre del componente pub/sub de DAPR que desea usar (en este caso `pubsub` ).
- Nombre del tema al que se va a suscribir (en este caso `newOrder` ).
- Operación de API que debe llamarse para este tema (en este caso `/orders` ).
- El [ámbito](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) puede especificar qué servicios pueden publicar y suscribirse a un tema.

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

La aplicación [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) adjunta proporciona una arquitectura de referencia de un extremo a otro para crear una aplicación de microservicios que implementa DAPR. eShopOnDapr es una evolución de la aplicación de [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) ampliamente popular, creada hace varios años. Ambas versiones usan el patrón pub/sub para comunicar [eventos de integración](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) entre microservicios. Los eventos de integración incluyen:

- Cuando un usuario desprotege una cesta de la compra.
- Cuando un pago de un pedido se ha realizado correctamente.
- Cuando ha expirado el período de gracia de una compra.

Los eventos de eShopOnContainers se basan en la `IEventBus` interfaz siguiente:

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent integrationEvent);

    void Subscribe<T, THandler>()
        where TEvent : IntegrationEvent
        where THandler : IIntegrationEventHandler<T>;
}
```

Las implementaciones concretas de esta interfaz existen en eShopOnContainers para RabbitMQ y Azure Service Bus. Cada implementación incluía una gran cantidad de código de fontanería personalizado que era complejo de comprender y difícil de mantener.

El eShopOnDapr más reciente simplifica significativamente el comportamiento de pub/sub mediante DAPR. Por ejemplo, la `IEventBus` interfaz se ha reducido a un solo método:

```csharp
public interface IEventBus
{
    Task PublishAsync(IntegrationEvent integrationEvent);
}
```

### <a name="publish-events"></a>Publicación de eventos

En el eShopOnDapr actualizado, una sola `DaprEventBus` implementación puede admitir cualquier agente de mensajes compatible con DAPR. En el siguiente bloque de código se muestra el método de publicación simplificado. Observe cómo el `PublishAsync` método usa el cliente de DAPR para publicar un evento:

```csharp
public class DaprEventBus : IEventBus
{
    private const string PubSubName = "pubsub";

    private readonly DaprClient _daprClient;
    private readonly ILogger<DaprEventBus> _logger;

    public DaprEventBus(DaprClient daprClient, ILogger<DaprEventBus> logger)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task PublishAsync(IntegrationEvent integrationEvent)
    {
        var topicName = integrationEvent.GetType().Name;

        // Dapr uses System.Text.Json which does not support serialization of a
        // polymorphic type hierarchy by default. Using object as the type
        // parameter causes all properties to be serialized.
        await _daprClient.PublishEventAsync<object>(PubSubName, topicName, integrationEvent);
    }
}
```

Como puede ver en el fragmento de código, el nombre del tema se deriva del nombre del tipo de evento. Dado que todos los servicios de eShop usan la `IEventBus` abstracción, DAPR required *no tiene ningún cambio* en el código de la aplicación principal.

> [!IMPORTANT]
> El SDK de DAPR usa `System.Text.Json` para serializar o deserializar los mensajes. Sin embargo, `System.Text.Json` no serializa las propiedades de las clases derivadas de forma predeterminada. En el código de eShop, a veces se declara un evento explícitamente como `IntegrationEvent` , la clase base para los eventos de integración. Esto se hace porque el tipo de evento concreto se determina dinámicamente en tiempo de ejecución en función de la lógica de negocios. Como resultado, el evento se serializa utilizando la información de tipo de la clase base y no la clase derivada. Para forzar `System.Text.Json` la serialización de todas las propiedades de la clase derivada en este caso, el código utiliza `object` como parámetro de tipo genérico. Para obtener más información, vea la [documentación de .net](../../standard/serialization/system-text-json-polymorphism.md).

Con DAPR, el código de infraestructura se ha **simplificado drásticamente**. No es necesario distinguir entre los distintos agentes de mensajes. DAPR proporciona esta abstracción para usted. Y, si es necesario, puede intercambiar fácilmente agentes de mensajes o configurar varios componentes del agente de mensajes.

### <a name="subscribe-to-events"></a>Suscripción a los eventos

La aplicación eShopOnContainers anterior contiene *SubscriptionManagers* para controlar la implementación de la suscripción para cada agente de mensajes. Cada administrador contiene código complejo específico del agente de mensajes para controlar los eventos de suscripción. Para recibir eventos, cada servicio tiene que registrar explícitamente un controlador para cada tipo de evento.

eShopOnDapr simplifica la fontanería de las suscripciones de eventos mediante el uso de bibliotecas de ASP.NET Core de DAPR. Cada evento se controla mediante un método de acción en el controlador. Un `Topic` atributo decora el método de acción con el nombre del tema correspondiente al que suscribirse. A continuación se muestra un fragmento de código tomado de `PaymentService` :

```csharp
[Route("api/v1/[controller]")]
[ApiController]
public class IntegrationEventController : ControllerBase
{
    private const string DAPR_PUBSUB_NAME = "pubsub";

    private readonly IServiceProvider _serviceProvider;

    public IntegrationEventController(IServiceProvider serviceProvider)
    {
        _serviceProvider = serviceProvider;
    }

    [HttpPost("OrderStatusChangedToValidated")]
    [Topic(DAPR_PUBSUB_NAME, "OrderStatusChangedToValidatedIntegrationEvent")]
    public async Task OrderStarted(OrderStatusChangedToValidatedIntegrationEvent integrationEvent)
    {
        var handler = _serviceProvider.GetRequiredService<OrderStatusChangedToValidatedIntegrationEventHandler>();
        await handler.Handle(integrationEvent);
    }
}
```

En el `Topic` atributo, el nombre del tipo .net del evento se usa como el nombre del tema. Para controlar el evento, se invoca un controlador de eventos que ya existía en la base de código eShopOnContainers anterior. En el ejemplo anterior, los mensajes recibidos del `OrderStatusChangedToValidatedIntegrationEvent` tema invocan el `OrderStatusChangedToValidatedIntegrationEventHandler` controlador de eventos existente. Dado que DAPR implementa la fontanería subyacente para las suscripciones y los agentes de mensajes, una gran cantidad de código original quedó obsoleta y se quitó del código base. Gran parte de este código era complejo de entender y difícil de mantener.

### <a name="use-pubsub-components"></a>Uso de componentes pub/sub

En el repositorio de eShopOnDapr, una `deployment` carpeta contiene archivos para implementar la aplicación mediante diferentes modos de implementación: `Docker Compose` y `Kubernetes` . `dapr`Existe una carpeta dentro de cada una de estas carpetas que contiene una `components` carpeta. Esta carpeta contiene un archivo `eshop-pubsub.yaml` que contiene la configuración del componente pub/sub de DAPR que la aplicación usará para el comportamiento de pub/sub. Como vio en los fragmentos de código anteriores, el nombre del componente pub/sub usado es `pubsub` . Este es el contenido del `eshop-pubsub.yaml` archivo en la `deployment/compose/dapr/components` carpeta:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: default
spec:
  type: pubsub.nats
  version: v1
  metadata:
  - name: natsURL
    value: nats://demo.nats.io:4222
```

La configuración anterior especifica el [agente de mensajes de NAT](https://nats.io/) deseado para este ejemplo. Para cambiar los agentes de mensajes, solo tiene que configurar un agente de mensajes diferente, como RabbitMQ o Azure Service Bus y actualizar el archivo YAML. Con DAPR, no se produce ningún cambio en el código de servicio principal al cambiar los agentes de mensajes.

Por último, podría preguntar "¿por qué se necesitarían varios agentes de mensajes en una aplicación?". Muchas veces, un sistema controlará las cargas de trabajo con características diferentes. Un evento se puede producir 10 veces al día, pero se produce otro evento 5.000 veces por segundo. Puede beneficiarse de la creación de particiones del tráfico de mensajería a diferentes agentes de mensajes. Con DAPR, puede agregar varias configuraciones de componente pub/sub, cada una con un nombre diferente.

## <a name="summary"></a>Resumen

El patrón pub/sub le ayuda a desacoplar servicios en una aplicación distribuida. El bloque DAPR Publish & subscribe Building simplifica la implementación de este comportamiento en la aplicación.

A través de DAPR pub/sub, puede publicar mensajes en un *tema* específico. Además, el bloque de creación consultará el servicio para determinar a qué temas se va a suscribir.

Puede usar DAPR pub/sub de forma nativa a través de HTTP o mediante uno de los SDK específicos del lenguaje, como el SDK de .NET para DAPR. El SDK de .NET se integra estrechamente con la plataforma de ASP.NET Core.

Con DAPR, puede conectar un producto de agente de mensajes compatible con su aplicación. Después, puede intercambiar agentes de mensajes sin necesidad de realizar cambios en el código de la aplicación.

> [!div class="step-by-step"]
> [Anterior](service-invocation.md)
> [Siguiente](bindings.md)
