---
title: Eventos de dominio, diseño e implementación
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga una vista detallada de los eventos de dominio, un concepto clave para establecer la comunicación entre agregados.
ms.date: 10/08/2018
ms.openlocfilehash: 0cc2072408e110d94b47bd47a9c337a604d4c1a3
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271781"
---
# <a name="domain-events-design-and-implementation"></a>Eventos de dominio: diseño e implementación

Uso de eventos de dominio para implementar explícitamente los efectos secundarios de los cambios en el dominio. En otras palabras y con la terminología de DDD, usar eventos de dominio para implementar explícitamente los efectos secundarios entre varios agregados. Opcionalmente, para una mejor escalabilidad y un menor impacto en los bloqueos de base de datos, use la coherencia final entre agregados dentro del mismo dominio.

## <a name="what-is-a-domain-event"></a>¿Qué es un evento de dominio?

Un evento es algo que ha sucedido en el pasado. Un evento de dominio es algo que ha sucedido en el dominio que quiere que otras partes del mismo dominio (en curso) tengan en cuenta. Normalmente las partes notificadas reaccionan de alguna manera a los eventos.

Una ventaja importante de los eventos de dominio es que los efectos secundarios se pueden expresar explícitamente.

Por ejemplo, si simplemente usa Entity Framework y debe haber una reacción a algún evento, probablemente codificaría cualquier cosa que necesite cerca de lo que desencadena el evento. Por tanto, la regla se acopla, implícitamente, en el código, y tendrá que mirar el código para, con suerte, descubrir que la regla se implementa allí.

Por otro lado, el uso de los eventos de dominio hace el concepto explícito, porque hay un `DomainEvent` y al menos un `DomainEventHandler` implicados.

Por ejemplo, en la aplicación eShopOnContainers, cuando se crea un pedido, el usuario se convierte en un comprador, por tanto se genera un `OrderStartedDomainEvent` y se controla en el `ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler`, por lo que el concepto subyacente es evidente.

En resumen, los eventos de dominio le ayudan a expresar explícitamente las reglas de dominio, en función del lenguaje ubicuo proporcionado por los expertos de dominio. Además, los eventos de dominio permiten una mejor separación de cuestiones entre clases dentro del mismo dominio.

Es importante asegurarse de que, al igual que en una transacción de base de datos, o todas las operaciones relacionadas con un evento de dominio finalizan correctamente o ninguna lo hace.

Los eventos de dominio son similares a los eventos de estilo de mensajería, con una diferencia importante. Con la mensajería real, las colas de mensajes, los agentes de mensajes o un bus de servicio con AMQP, un mensaje siempre se envía de forma asincrónica y se comunica entre procesos y equipos. Esto es útil para integrar varios contextos delimitados, microservicios o incluso otras aplicaciones. Pero con los eventos de dominio, le interesa generar un evento desde la operación de dominio que se está ejecutando actualmente, pero que los efectos secundarios se produzcan dentro del mismo dominio.

Los eventos de dominio y sus efectos secundarios (las acciones iniciadas después que se administren mediante controladores de eventos) se deben producir casi de inmediato, por lo general en el proceso y dentro del mismo dominio. Por tanto, los eventos de dominio pueden ser sincrónicos o asincrónicos. Pero los eventos de integración siempre deben ser asincrónicos.

## <a name="domain-events-versus-integration-events"></a>Eventos de dominio frente a eventos de integración

Semánticamente, los eventos de dominio y los de integración son lo mismo: notificaciones sobre algo que acaba de ocurrir. Pero su implementación debe ser diferente. Los eventos de dominio son simplemente mensajes insertados en un distribuidor de eventos de dominio, que se puede implementar como un mediador en memoria basado en un contenedor de IoC o cualquier otro método.

Por otro lado, el propósito de los eventos de integración es propagar las transacciones confirmadas y actualizaciones a subsistemas adicionales, con independencia de que sean otros microservicios, contextos delimitados o incluso aplicaciones externas. Por tanto, solo se deben producir si la entidad se conserva correctamente, de otra forma será como si toda la operación nunca se hubiera producido.

Como se ha mencionado anteriormente, los eventos de integración se deben basar en la comunicación asincrónica entre varios microservicios (otros contextos delimitados) o incluso sistemas o aplicaciones externos.

Por tanto, la interfaz de bus de eventos necesita una infraestructura que permita la comunicación entre procesos y distribuida entre servicios potencialmente remotos. Se pueden basar en un bus de servicio comercial, colas, una base de datos compartida que se use como un buzón o cualquier otro sistema de mensajería distribuido e, idealmente, basado en inserciones.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Eventos de dominio como método preferido para desencadenar efectos secundarios entre varios agregados dentro del mismo dominio

Si la ejecución de un comando relacionado con una instancia de agregado requiere reglas de dominio adicionales para ejecutarse en uno o varios agregados adicionales, debe diseñar e implementar esos efectos secundarios para que se desencadenen mediante eventos de dominio. Como se muestra en la figura 7-14 y como uno de los casos de uso más importantes, se debe usar un evento de dominio para propagar los cambios de estado entre varios agregados dentro del mismo modelo de dominio.

![Diagrama que muestra un evento de dominio que controla los datos a un agregado Buyer.](./media/domain-events-design-implementation/domain-model-ordering-microservice.png)

**Figura 7-14**. Eventos de dominio para exigir la coherencia entre varios agregados dentro del mismo dominio

En la figura 7-14 se muestra cómo consiguen los eventos de dominio la coherencia entre los agregados. Cuando el usuario inicia un pedido, el agregado Order envía un evento de dominio `OrderStarted`. El agregado Buyer controla el evento de dominio OrderStarted para crear un objeto Buyer en el microservicio de pedidos, según la información de usuario original del microservicio de identidades (con la información proporcionada en el comando CreateOrder).

Como alternativa, puede hacer que la raíz agregada se suscriba a los eventos generados por los miembros de sus agregados (las entidades secundarias). Por ejemplo, cada entidad secundaria OrderItem puede generar un evento cuando el precio del artículo sea mayor que una cantidad específica, o bien cuando la cantidad del elemento de producto sea demasiado alta. Después, la raíz agregada puede recibir esos eventos y realizar un cálculo o una agregación global.

Es importante comprender que este tipo de comunicación basada en eventos no se implementa de forma directa dentro de los agregados; tendrá que implementar controladores de eventos de dominio.

El control de los eventos de dominio es una cuestión de la aplicación. El nivel de modelo de dominio solo debe centrarse en la lógica del dominio, en lo que un experto de dominio debería entender, no en la infraestructura de la aplicación como controladores y acciones de persistencia de efectos secundarios mediante repositorios. Por tanto, el nivel de aplicación es donde los controladores de eventos de dominio deberían desencadenar acciones cuando se produzca un evento de dominio.

Los eventos de dominio también se pueden usar para desencadenar cualquier número de acciones de la aplicación y, lo que es más importante, deben ser abiertos para aumentar ese número en el futuro de forma desacoplada. Por ejemplo, al iniciar el pedido, es posible que le interese publicar un evento de dominio para propagar esa información a otros agregados o incluso para generar acciones de la aplicación como notificaciones.

El punto clave es el número abierto de acciones que se van a ejecutar cuando se produce un evento de dominio. Con el tiempo, las acciones y reglas en el dominio y la aplicación aumentarán. La complejidad o el número de acciones de efectos secundarios aumentará cuando ocurra algo, pero si el código se acoplara con "adherencia" (es decir, la creación de objetos específicos con `new`), cada vez que necesitara agregar una acción nueva también tendría que cambiar el código funcional y probado.

Este cambio podría provocar nuevos errores y este enfoque también va en contra del [principio abierto/cerrado](https://en.wikipedia.org/wiki/Open/closed_principle) de [SOLID](https://en.wikipedia.org/wiki/SOLID). No solo eso, la clase original que orquestaba las operaciones no dejaría de crecer, algo contrario al [Principio de responsabilidad única (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).

Por otro lado, si usa eventos de dominio, puede crear una implementación específica y desacoplada mediante la separación de las responsabilidades de esta manera:

1. Envíe un comando (por ejemplo, CreateOrder).
2. Reciba el comando en un controlador de comandos.
   - Ejecute la transacción de un solo agregado.
   - (Opcional) Genere eventos de dominio para los efectos secundarios (por ejemplo, OrderStartedDomainEvent).
3. Controle los eventos de dominio (en el proceso actual) que van a ejecutar un número abierto de efectos secundarios en varios agregados o acciones de la aplicación. Por ejemplo:
   - Compruebe o cree el comprador y el método de pago.
   - Cree y envíe un evento de integración relacionado al bus de eventos para propagar los estados entre los microservicios o desencadenar acciones externas como enviar un correo electrónico al comprador.
   - Controle otros efectos secundarios.

Como se muestra en la figura 7-15, empezando desde el mismo evento de dominio, puede controlar varias acciones relacionadas con otros agregados en el dominio o acciones de la aplicación adicionales que tenga que realizar entre los microservicios conectados con eventos de integración y el bus de eventos.

![Diagrama que muestra un evento de dominio que pasa datos a varios controladores de eventos.](./media/domain-events-design-implementation/aggregate-domain-event-handlers.png)

**Figura 7-15**. Control de varias acciones por dominio

Puede haber varios controladores para el mismo evento de dominio en el nivel de aplicación, un controlador puede resolver la coherencia entre agregados y otro controlador puede publicar un evento de integración, por lo que otros microservicios pueden hacer algo con él. Normalmente los controladores de eventos se encuentran en el nivel de aplicación, porque los objetos de infraestructura como los repositorios o una API de aplicación se usarán para el comportamiento del microservicio. En ese sentido, los controladores de eventos son similares a los controladores de comandos, por lo que ambos forman parte del nivel de aplicación. La diferencia más importante es que un comando solo se debe procesar una vez. Un evento de dominio se podría procesar cero o *n* veces, porque lo pueden recibir varios receptores o controladores de eventos con un propósito diferente para cada controlador.

Tener un número abierto de controladores de eventos de dominio permite agregar tantas reglas de dominio como sea necesario sin que el código actual se vea afectado. Por ejemplo, la implementación de la siguiente regla de negocio podría ser tan fácil como agregar algunos controladores de eventos (o incluso solo uno):

> Cuando la cantidad total adquirida por un cliente en el almacén, en cualquier número de pedidos, supera los 6000 dólares, se aplica un 10 % de descuento a cada pedido nuevo y se notifica ese descuento para futuros pedidos a los clientes con un correo electrónico.

## <a name="implement-domain-events"></a>Implementación de eventos de dominio

En C#, un evento de dominio es simplemente una estructura o clase que almacena datos, como un DTO, con toda la información relacionada con lo que ha sucedido en el dominio, como se muestra en el ejemplo siguiente:

```csharp
public class OrderStartedDomainEvent : INotification
{
    public string UserId { get; }
    public int CardTypeId { get; }
    public string CardNumber { get; }
    public string CardSecurityNumber { get; }
    public string CardHolderName { get; }
    public DateTime CardExpiration { get; }
    public Order Order { get; }

    public OrderStartedDomainEvent(Order order,
                                   int cardTypeId, string cardNumber,
                                   string cardSecurityNumber, string cardHolderName,
                                   DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

Esto es básicamente una clase que contiene todos los datos relacionados con el evento OrderStarted.

En cuanto al lenguaje ubicuo del dominio, como un evento es algo que tuvo lugar en el pasado, el nombre de clase del evento se debe representar como un verbo en pasado, como OrderStartedDomainEvent u OrderShippedDomainEvent. Esta es la forma de implementar el evento de dominio en el microservicio de pedidos en eShopOnContainers.

Como se indicó anteriormente, una característica importante de los eventos es que, como un evento es algo que se produjo en el pasado, no debe cambiar. Por tanto, debe ser una clase inmutable. En el código anterior se puede ver que las propiedades son de solo lectura. No hay ninguna manera de actualizar el objeto, solo se pueden establecer valores al crearlo.

Es importante destacar aquí que si los eventos de dominio tuvieran que administrarse de forma asincrónica, mediante una cola que necesitase serializar y deserializar los objetos de eventos, las propiedades tendrían que ser "conjunto privado" en lugar de solo lectura, por lo que el deserializador podría asignar los valores tras quitar de la cola. Esto no es un problema en el microservicio Ordering, ya que el evento de dominio pub/sub se implementa sincrónicamente con MediatR.

### <a name="raise-domain-events"></a>Generación de eventos de dominio

La siguiente pregunta es cómo generar un evento de dominio para que llegue a sus controladores de eventos relacionados. Se pueden usar varios enfoques.

Originalmente, Udi Dahan propuso el uso de una clase estática para administrar y generar los eventos (por ejemplo, en algunas publicaciones relacionadas, como [Domain Events – Take 2](https://udidahan.com/2008/08/25/domain-events-take-2/) [Eventos de dominio: Toma 2]). Esto podría incluir una clase estática denominada DomainEvents que generaría los eventos de dominio inmediatamente cuando se llama, con una sintaxis similar a `DomainEvents.Raise(Event myEvent)`. Jimmy Bogard escribió una entrada de blog [[Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/) (Reforzar el dominio: eventos de dominio)] que recomienda un enfoque similar.

Pero cuando la clase de eventos de dominio es estática, también lo envía a los controladores inmediatamente. Esto dificulta las pruebas y la depuración, dado que los controladores de eventos con la lógica de efectos secundarios se ejecutan inmediatamente después de que se genera el evento. Durante las pruebas y la depuración, le interesa centrarse únicamente en lo que sucede en las clases agregadas actuales; no le interesa que repentinamente se le redirija a otros controladores de eventos para los efectos secundarios relacionados con otros agregados o la lógica de la aplicación. Es el motivo de que otros métodos hayan evolucionado, como se explica en la sección siguiente.

#### <a name="the-deferred-approach-to-raise-and-dispatch-events"></a>El enfoque diferido para generar y enviar eventos

En lugar de enviar a un controlador de eventos de dominio de forma inmediata, un método más adecuado consiste en agregar los eventos de dominio a una colección y, después, enviarlos *justo antes* o *justo* *después* de confirmar la transacción (como ocurre con SaveChanges en EF). (Este enfoque lo describió Jimmy Bogard en esta publicación [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/) [Un patrón de eventos de dominio mejor]).

Decidir si enviar los eventos de dominio justo antes o justo después de confirmar la transacción es importante, ya que determina si se van a incluir los efectos secundarios como parte de la misma transacción o en transacciones diferentes. En este último caso, debe controlar la coherencia final entre varios agregados. Este tema se analiza en la sección siguiente.

El enfoque diferido es el que se usa en eShopOnContainers. En primer lugar, se agregan los eventos que tienen lugar en las entidades a una colección o lista de eventos por entidad. Esa lista debe formar parte del objeto de entidad, o incluso mejor, de la clase de entidad base, como se muestra en el ejemplo siguiente de la clase base Entity:

```csharp
public abstract class Entity
{
     //...
     private List<INotification> _domainEvents;
     public List<INotification> DomainEvents => _domainEvents;

     public void AddDomainEvent(INotification eventItem)
     {
         _domainEvents = _domainEvents ?? new List<INotification>();
         _domainEvents.Add(eventItem);
     }

     public void RemoveDomainEvent(INotification eventItem)
     {
         _domainEvents?.Remove(eventItem);
     }
     //... Additional code
}
```

Cuando quiera generar un evento, simplemente agréguelo a la colección de eventos desde el código en cualquier método de la entidad raíz agregada.

En el código siguiente, parte de la [raíz agregada Order de eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs), se muestra un ejemplo:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
                                                          cardTypeId, cardNumber,
                                                          cardSecurityNumber,
                                                          cardHolderName,
                                                          cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Tenga en cuenta que lo único que hace el método AddDomainEvent es agregar un evento a la lista. Todavía no se distribuye ningún evento, ni tampoco se invoca ningún controlador de eventos.

Lo que realmente le interesa es enviar los eventos después, cuando la transacción se confirme en la base de datos. Si usa Entity Framework Core, eso significa hacerlo en el método SaveChanges del DbContext de EF, como en el código siguiente:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<bool> SaveEntitiesAsync(CancellationToken cancellationToken = default(CancellationToken))
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.
        await _mediator.DispatchDomainEventsAsync(this);

        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be committed
        var result = await base.SaveChangesAsync();
    }
}
```

Con este código, los eventos de entidad se envían a sus controladores de eventos correspondientes.

El resultado general es que se separa la generación de un evento de dominio (una sencilla adición a una lista en memoria) de su envío a un controlador de eventos. Además, en función del tipo de distribuidor que se use, los eventos se podrían enviar de forma sincrónica o asincrónica.

Tenga en cuenta que aquí los límites transaccionales tienen una importancia especial. Si la unidad de trabajo y la transacción pueden abarcar más de un agregado (como ocurre cuando se usa EF Core y una base de datos relacional), esto puede funcionar bien. Pero si la transacción no puede abarcar agregados, como cuando se usa una base de datos NoSQL como Azure CosmosDB, se deben implementar pasos adicionales para lograr la coherencia. Este es otro motivo por el que la omisión de persistencia no es universal; depende del sistema de almacenamiento que se use.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Transacción única entre agregados frente a coherencia final entre agregados

La pregunta de si se debe realizar una única transacción entre agregados en lugar de depender de la coherencia final entre esos agregados es controvertida. Muchos autores de DDD, como Eric Evans y Vaughn Vernon, promueven la regla "una transacción = un agregado" y argumentan, por tanto, la coherencia final entre agregados. Por ejemplo, en su libro *Domain-Driven Design* (Diseño controlado por eventos), Eric Evans afirma lo siguiente:

> No se espera que las reglas que abarcan agregados estén actualizadas en todo momento. A través del procesamiento de eventos, el procesamiento por lotes u otros mecanismos de actualización, se pueden resolver otras dependencias dentro de un periodo determinado. (página 128)

Vaughn Vernon afirma lo siguiente en [Effective Aggregate Design. Part II: Making Aggregates Work Together](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf) (Diseño eficaz de agregados - Parte II: hacer que los agregados funcionen de forma conjunta):

> Por tanto, si la ejecución de un comando en una instancia del agregado requiere que se ejecuten reglas de negocio adicionales en uno o varios agregados, use la coherencia final \[...\] Hay una forma práctica de admitir la coherencia final en un modelo de DDD. Un método de agregado publica un evento de dominio que con el tiempo se entrega a uno o varios suscriptores asincrónicos.

Esta lógica se basa en la adopción de transacciones específicas en lugar de transacciones distribuidas entre varios agregados o entidades. La idea es que, en el segundo caso, el número de bloqueos de base de datos será relevante en aplicaciones a gran escala con necesidades de alta escalabilidad. Asumir el hecho de que las aplicaciones de alta escalabilidad no necesitan coherencia transaccional entre varios agregados ayudará a aceptar el concepto de la coherencia final. A menudo los cambios atómicos no son necesarios por parte de la empresa y, en cualquier caso, es la responsabilidad de los expertos de dominio indicar si determinadas operaciones necesitan transacciones atómicas o no. Si una operación siempre necesita una transacción atómica entre varios agregados, podría preguntarse si el agregado debe ser mayor o no se ha diseñado correctamente.

Pero otros desarrolladores y arquitectos como Jimmy Bogard se conforman con una sola transacción que abarque varios agregados, pero solo cuando esos agregados adicionales estén relacionados con efectos secundarios para el mismo comando original. Por ejemplo, en [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard afirma lo siguiente:

> Normalmente, me interesa que los efectos secundarios de un evento de dominio se produzcan en la misma transacción lógica, pero no necesariamente en el mismo ámbito de generación del evento de dominio \[...\] Justo antes de que se confirme la transacción, los eventos se envían a sus correspondientes controladores.

Si los eventos de dominio se envían justo *antes* de confirmar la transacción original, es porque interesa que los efectos secundarios de esos eventos se incluyan en la misma transacción. Por ejemplo, si se produce un error en el método SaveChanges de DbContext de EF, la transacción revertirá todos los cambios, incluido el resultado de cualquier operación de efecto secundario implementada por los controladores de eventos de dominio relacionados. Esto se debe a que el ámbito de la duración de DbContext se define de forma predeterminada como "en ámbito". Por tanto, el objeto DbContext se comparte entre varios objetos de repositorio de los que se crean instancias en el mismo ámbito o gráfico de objetos. Esto coincide con el ámbito de HttpRequest al desarrollar aplicaciones de API web o MVC.

En realidad, ambos enfoques (única transacción atómica y coherencia final) pueden ser correctos. Realmente depende de los requisitos empresariales o de dominio, y de lo que los expertos de dominio digan. También depende de la capacidad de escalabilidad que deba tener el servicio (las transacciones más granulares tienen un impacto menor en relación con los bloqueos de base de datos). Y depende de la inversión que esté dispuesto a realizar en el código, puesto que la coherencia final requiere un código más complejo con el fin de detectar posibles incoherencias entre los agregados y la necesidad de implementar acciones de compensación. Tenga en cuenta que si confirma los cambios en el agregado original y después, cuando los eventos se distribuyan, si se produce un problema y los controladores de eventos no pueden confirmar sus efectos secundarios, tendrá incoherencias entre los agregados.

Una manera de permitir acciones de compensación sería almacenar los eventos de dominio en tablas de base de datos adicionales para que puedan formar parte de la transacción original. Después, podría tener un proceso por lotes que detectara las incoherencias y ejecutara acciones de compensación comparando la lista de eventos con el estado actual de los agregados. Las acciones de compensación forman parte de un tema complejo que requerirá un análisis profundo por su parte, incluido su análisis con los usuarios empresariales y expertos de dominio.

En cualquier caso, puede elegir el enfoque que necesite. Pero el enfoque diferido inicial (generar los eventos antes de la confirmación y usar una sola transacción) es el más sencillo cuando se usa EF Core y una base de datos relacional. Es más fácil de implementar y resulta válido en muchos casos empresariales. También es el enfoque que se usa en el microservicio de pedidos de eShopOnContainers.

¿Pero cómo se envían realmente los eventos a sus correspondientes controladores de eventos? ¿Qué es el objeto `_mediator` que ve en el ejemplo anterior? Tiene que ver con las técnicas y los artefactos que se usan para la asignación entre eventos y sus controladores de eventos.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>El distribuidor de eventos de dominio: asignación de eventos a controladores de eventos

Una vez que se puedan enviar o publicar los eventos, se necesita algún tipo de artefacto que publique el evento, para que todos los controladores relacionados puedan obtenerlo y procesar efectos secundarios en función de ese evento.

Un enfoque es un sistema de mensajería real o incluso un bus de eventos, posiblemente basado en un bus de servicio en lugar de en eventos en memoria. Pero para el primer caso, la mensajería real sería excesiva para el procesamiento de eventos de dominio, ya que solo es necesario procesar los eventos dentro del mismo proceso (es decir, dentro del mismo nivel de dominio y aplicación).

Otra manera de asignar eventos a varios controladores de eventos consiste en usar el registro de tipos en un contenedor de IoC para poder inferir de forma dinámica a dónde enviar los eventos. En otras palabras, debe saber qué controladores de eventos tienen que obtener un evento específico. En la figura 7-16 se muestra un enfoque simplificado para esto.

![Diagrama que muestra un distribuidor de eventos de dominio que envía eventos a los controladores adecuados.](./media/domain-events-design-implementation/domain-event-dispatcher.png)

**Figura 7-16**. Distribuidor de eventos de dominio con IoC

Puede crear usted mismo todos los artefactos para implementar este enfoque. Pero también puede usar bibliotecas disponibles como [MediatR](https://github.com/jbogard/MediatR), que interiormente usa el contenedor de IoC. Por tanto, puede usar directamente las interfaces predefinidas y los métodos de publicación y distribución del objeto de mediador.

En el código, primero debe registrar los tipos de controlador de eventos en el contenedor de IoC, como se muestra en el ejemplo siguiente del [microservicio de pedidos de eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs):

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement IAsyncNotificationHandler<>)
        // in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
                                       .GetTypeInfo().Assembly)
                                         .AsClosedTypesOf(typeof(IAsyncNotificationHandler<>));
        // Other registrations ...
    }
}
```

En primer lugar, el código identifica el ensamblado que contiene los controladores de eventos de dominio localizando el ensamblado que contiene cualquiera de los controladores (mediante typeof(ValidateOrAddBuyerAggregateWhenXxxx), pero podría haber elegido cualquier otro controlador de eventos para buscar el ensamblado). Como todos los controladores de eventos implementan la interfaz IAsyncNotificationHandler, el código solo busca esos tipos y registra todos los controladores de eventos.

### <a name="how-to-subscribe-to-domain-events"></a>Cómo suscribirse a eventos de dominio

Cuando se usa MediatR, todos los controladores de eventos deben usar un tipo de evento que se proporciona en el parámetro genérico de la interfaz INotificationHandler, como se puede ver en el código siguiente:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

En función de la relación entre el evento y el controlador de eventos, que se puede considerar la suscripción, el artefacto de MediatR puede detectar todos los controladores de eventos para cada evento y desencadenar cada uno de ellos.

### <a name="how-to-handle-domain-events"></a>Cómo controlar eventos de dominio

Por último, el controlador de eventos normalmente implementa código de nivel de aplicación en el que se usan repositorios de infraestructura para obtener los agregados adicionales necesarios y para ejecutar la lógica del dominio de efectos secundarios. En el siguiente [código de controlador de eventos de dominio de eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs), se muestra un ejemplo de implementación.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
                   : INotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;

    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // ...Parameter validations...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ? orderStartedEvent.CardTypeId : 1;
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;

        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }

        buyer.VerifyOrAddPaymentMethod(cardTypeId,
                                       $"Payment Method on {DateTime.UtcNow}",
                                       orderStartedEvent.CardNumber,
                                       orderStartedEvent.CardSecurityNumber,
                                       orderStartedEvent.CardHolderName,
                                       orderStartedEvent.CardExpiration,
                                       orderStartedEvent.Order.Id);

        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer)
                                                                      : _buyerRepository.Add(buyer);

        await _buyerRepository.UnitOfWork
                .SaveEntitiesAsync();

        // Logging code using buyerUpdated info, etc.
    }
}
```

El código anterior de controlador de eventos de dominio se considera código de nivel de aplicación porque usa repositorios de infraestructura, como se explica en la sección siguiente sobre el nivel de persistencia de infraestructura. Los controladores de eventos también pueden usar otros componentes de infraestructura.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Los eventos de dominio pueden generar eventos de integración para publicarse fuera de los límites del microservicio

Por último, es importante mencionar que en ocasiones es posible que le interese propagar los eventos a través de varios microservicios. Dicha propagación es un evento de integración y se podría publicar a través de un bus de eventos desde cualquier controlador de eventos de dominio específico.

## <a name="conclusions-on-domain-events"></a>Conclusiones sobre los eventos de dominio

Como se mencionó, los eventos de dominio se usan para implementar explícitamente los efectos secundarios de los cambios en el dominio. Para usar la terminología de DDD, los eventos de dominio se usan para implementar explícitamente los efectos secundarios a través de uno o varios agregados. Además, para una mejor escalabilidad y un menor impacto en los bloqueos de base de datos, la coherencia final se usa entre agregados dentro del mismo dominio.

La aplicación de referencia usa [MediatR](https://github.com/jbogard/MediatR) para propagar los eventos de dominio sincrónicamente entre agregados, dentro de una única transacción. No obstante, también puede usar una implementación de AMQP como [RabbitMQ](https://www.rabbitmq.com/) o [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) para propagar los eventos de dominio de forma asincrónica con la coherencia eventual. Pero, como se mencionó anteriormente, hay que tener en cuenta la necesidad de acciones compensatorias en caso de que se produzcan errores.

## <a name="additional-resources"></a>Recursos adicionales

- **Greg Young. ¿Qué es un evento de dominio?** \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf#page=25>

- **Jan Stenberg. Eventos de dominio y coherencia definitiva** \
  <https://www.infoq.com/news/2015/09/domain-events-consistency>

- **Jimmy Bogard. A better domain events pattern** (Un mejor patrón de eventos de dominio) \
  <https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/>

- **Vaughn Vernon. Effective Aggregate Design Part II: Making Aggregates Work Together** (Vaughn Vernon. Diseño eficaz de agregados - Parte II: hacer que los agregados funcionen de forma conjunta) \
  [https://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

- **Jimmy Bogard. Strengthening your domain: Domain Events** (Jimmy Bogard. Reforzar el dominio: eventos de dominio) \
  <https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>

- **Tony Truong. Domain Events Pattern Example** (Ejemplo de patrón de eventos de dominio) \
  <https://www.tonytruong.net/domain-events-pattern-example/>

- **Udi Dahan. How to create fully encapsulated Domain Models** (Cómo crear modelos de dominio totalmente encapsulados) \
  <https://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

- **Udi Dahan. Domain Events – Take 2** (Eventos de dominio: parte 2) \
  <https://udidahan.com/2008/08/25/domain-events-take-2/>

- **Udi Dahan. Domain Events – Salvation** (Eventos de dominio: salvación) \
  <https://udidahan.com/2009/06/14/domain-events-salvation/>

- **Jan Kronquist. Don't publish Domain Events, return them!** (No publique eventos de dominio, devuélvalos) \
  <https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/>

- **Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures** (Eventos de integración en DDD y arquitecturas de microservicios) \
  <https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/>

>[!div class="step-by-step"]
>[Anterior](client-side-validation.md)
>[Siguiente](infrastructure-persistence-layer-design.md)
