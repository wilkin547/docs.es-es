---
title: "Eventos de dominio. Diseño e implementación"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación, diseño y eventos de dominio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a>Eventos de dominio: diseño e implementación

Usar eventos de dominio para implementar explícitamente los efectos secundarios de los cambios de su dominio. En otras palabras y usando terminología DDD, usar eventos de dominio para implementar explícitamente los efectos secundarios a través de varios agregados. Opcionalmente, para una mejor escalabilidad y menos impacto en bloqueos de base de datos, utilice coherencia definitiva entre agregados dentro del mismo dominio.

## <a name="what-is-a-domain-event"></a>¿Qué es un evento de dominio?

Un evento es algo que ha tenido lugar en el pasado. Un evento de dominio es, lógicamente, algo que ha sucedido en un dominio en particular, y algo que desee que otros elementos del mismo dominio (en proceso) para tener en cuenta y potencialmente reaccionar a.

Una ventaja importante de los eventos de dominio es que se puede expresar explícitamente los efectos secundarios después de que hubo un problema en un dominio en lugar de forma implícita. Los efectos deben ser coherentes para cualquier todas las operaciones relacionadas con la tarea de negocio ocurrir de lado, o ninguna de ellas. Además, los eventos de dominio permiten una mejor separación de intereses entre clases dentro del mismo dominio.

Por ejemplo, si simplemente está utilizando solo Entity Framework y las entidades o incluso agregados, si tiene que haber efectos secundarios provocó por un caso de uso, los que se implementará como un concepto implícito en el código de acoplamiento después de que hubo un problema. Sin embargo, si sólo ve ese código, es posible que no sepa si ese código (el efecto secundario) forma parte de la operación principal o si es realmente un efecto secundario. Por otro lado, usar eventos de dominio hace que el concepto explícita y forma parte del lenguaje ubicuo. Por ejemplo, en la aplicación eShopOnContainers, crear un pedido no es prácticamente el orden; las actualizaciones o crea un agregado de comprador según el usuario original, porque el usuario no es un comprador hasta que haya un pedido en su lugar. Si usa eventos de dominio, puede expresar explícitamente esa regla de dominio basada en el lenguaje ubicuo proporcionado por los expertos de dominio.

Eventos de dominio son similares a los eventos de estilo de mensajería, con una diferencia importante. Con mensajería real, message Queue Server, agentes de mensajes o un bus de servicio con AMPQ, un mensaje siempre es enviar de forma asincrónica y comunicar a través de procesos y máquinas. Esto es útil para integrar varios contextos limitado, microservicios o incluso a diferentes aplicaciones. Sin embargo, con los eventos de dominio, que desea generar un evento de la operación de dominio que se está ejecutando actualmente, pero desea que los efectos secundarios que se produzca dentro del mismo dominio.

Los eventos de dominio y sus efectos secundarios (las acciones iniciadas después que se administran mediante controladores de eventos) se deben producir casi de inmediato, por lo general en el proceso y dentro del mismo dominio. Por lo tanto, los eventos de dominio pueden ser sincrónicas o asincrónicas. Eventos de integración, sin embargo, siempre deben ser asincrónicos.

## <a name="domain-events-versus-integration-events"></a>Eventos de dominio frente a eventos de integración

Semánticamente, los eventos de dominio e integración son lo mismo: notificaciones hay algo que se pasó. Sin embargo, su implementación debe ser diferente. Eventos de dominio son simplemente mensajes insertados en un distribuidor de eventos de dominio, que se pueda implementar como un mediador en memoria en función de un contenedor de IoC o cualquier otro método.

Por otro lado, el propósito de eventos de integración es propagar las transacciones confirmadas y actualizaciones con los subsistemas de adicionales, independientemente de si están otros microservicios, contextos limitado o aplicaciones incluso externas. Por lo tanto, debe producir solo si la entidad se almacena correctamente, porque en muchos escenarios si se produce un error, toda la operación eficazmente nunca se produjo.

Además y como se ha mencionado, integración eventos deben basarse en la comunicación asincrónica entre varios microservicios (otros contextos limitado) o incluso externos de sistemas y aplicaciones. Por lo tanto, la interfaz de bus de eventos necesita algunos infraestructura que permite entre procesos y distribuye la comunicación entre servicios potencialmente remoto. Pueden basarse en un bus de servicio comercial, colas, una base de datos compartido utilizado como un buzón o cualquier otro distribuidas y lo ideal es que el sistema de mensajería basado en de inserción.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Eventos de dominio como una manera preferida para desencadenar los efectos secundarios a través de varios agregados dentro del mismo dominio

Si ejecuta un comando relacionada con una instancia del agregado requiere reglas de dominio adicionales para ejecutarse en uno o varios agregados adicionales, debe diseñar e implementar estos efectos secundarios que va a desencadenar eventos de dominio. Tal como se muestra en la figura 9-14 y como uno de los más importantes de casos de uso, debe usarse un evento de dominio para propagar los cambios de estado entre varios agregados dentro del mismo modelo de dominio.

![](./media/image15.png)

**Figura 9-14**. Eventos de dominio para exigir la coherencia entre varios agregados dentro del mismo dominio

En la ilustración, cuando el usuario inicia un pedido, el evento de dominio OrderStarted desencadena la creación de un objeto de comprador en la ordenación microservicio, según la información de usuario original de la identidad de microservicio (con la información proporcionada en el comando CreateOrder). Cuando se crea en primer lugar, se genera el evento de dominio por el agregado de orden.

Como alternativa, puede tener la raíz agregada suscrita para eventos generados por los miembros de sus agregados (las entidades secundarias). Por ejemplo, cada entidad de secundaria OrderItem puede generar un evento cuando el precio del artículo es mayor que una cantidad específica, o cuando la cantidad de elemento de producto es demasiado alta. La raíz agregada, a continuación, puede recibir los eventos y realizar un cálculo global o la agregación.

Es importante comprender que este tipo de comunicación basado en eventos no se implementa directamente dentro de los agregados; debe implementar controladores de eventos de dominio. Controla los eventos de dominio es un problema de aplicación. El nivel de modelo de dominio solo debe centrarse en la lógica del dominio, lo que debería entender un experto de dominio, no la infraestructura de aplicación como controladores y acciones de persistencia de efectos secundarios con repositorios. Por lo tanto, el nivel de capa de aplicación es que debería tener controladores de eventos de dominio desencadenan acciones cuando se produce un evento de dominio.

Eventos de dominio también pueden utilizarse para desencadenar cualquier número de acciones de la aplicación y lo que es más importante, debe estar abierto para aumentar dicho número en el futuro de forma desacoplada. Por ejemplo, cuando se inicia el orden, puede publicar un evento de dominio para propagar la información a otros agregados o incluso para generar las acciones de aplicación como notificaciones.

El punto clave es el número de acciones que se ejecuta cuando se produce un evento de dominio abierto. Finalmente, se incrementan las acciones y reglas en el dominio y la aplicación. La complejidad o el número de acciones de efectos secundarios cuando ocurra algo crecerá, pero si el código se acopla con "adherencia" (es decir, simplemente crear instancias de objetos con la palabra clave nueva en C\#), a continuación, cada vez que necesite agregar una nueva acción deberá Cambie el código original. Esto podría resultar en errores nuevo, porque con cada nuevo requisito necesitará cambiar el flujo de código original. Esto es aplicable en el [principio abierto/cerrado](https://en.wikipedia.org/wiki/Open/closed_principle) de [sólido](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)). No sólo eso, la clase original que se orquestar las operaciones podría crecer y desarrolle, que entra en el [el principio de responsabilidad única (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).

Por otro lado, si usa eventos de dominio, puede crear una implementación específica y desacoplada al separar las responsabilidades de esta manera:

1.  Enviar un comando (por ejemplo, CreateOrder).
2.  Recibe el comando en un controlador de comandos.
    -   Ejecutar las transacciones de un agregado único.
    -   (Opcional) Provocar eventos de dominio para los efectos secundarios (por ejemplo, OrderStartedDomainDvent).
1.  Thast de eventos (dentro del proceso actual) de controlador de dominio ejecutará un número abierto de los efectos secundarios en varios agregados o las acciones de aplicación. Por ejemplo:
    -   Comprobar o crear método de pago y el comprador.
    -   Crear y enviar un evento de integración relacionados para el bus de eventos para propagar los Estados a través de microservicios o desencadenador acciones externas como enviar un correo electrónico al comprador.
    -   Controlar otros efectos secundarios.

Como se muestra en la figura 9-15, desde el mismo evento de dominio, puede controlar varias acciones relacionadas con otros agregados en el dominio o acciones de aplicación adicional que necesite realizar a través de microservicios conectar con eventos de integración y el bus de eventos.

![](./media/image16.png)

**Figura 9-15**. Control de varias acciones por dominio

Los controladores de eventos son normalmente en el nivel de aplicación, porque los utilizará objetos de la infraestructura como repositorios o una API de aplicación para el comportamiento de microservicio. En ese sentido, controladores de eventos son similares a los controladores de comandos, por lo que ambos son parte de la capa de aplicación. La diferencia más importante es que se debe procesar un comando solo una vez. Un evento de dominio podría ser procesado cero o  *n*  el tiempo de espera, porque si puede ser recibido por varios receptores o controladores de eventos con un propósito diferente para cada controlador.

La posibilidad de que un número abierto de controladores de eventos de dominio le permite agregar muchos más reglas de dominio sin afectar a su código actual. Por ejemplo, la implementación de la siguiente regla de negocios que tiene que producirse derecha después de un evento podría ser tan fácil como agregar algunos controladores de eventos (o incluso una sola):

Cuando la cantidad total adquirida por un cliente en el almacén en cualquier número de pedidos, supera 6.000 dólares, un 10% de descuento se aplican a cada nuevo pedido y notificar a los clientes con un correo electrónico sobre ese descuento para futuros pedidos.

## <a name="implementing-domain-events"></a>Implementar los eventos de dominio

En C#, un evento de dominio es simplemente una estructura de almacenamiento de datos o de clase, como un DTO, con toda la información relacionada con lo que pasó en el dominio, tal como se muestra en el ejemplo siguiente:

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

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

En cuanto a lenguaje ubicuo del dominio, puesto que un evento es algo que se produjeron en el pasado, se debe representar el nombre de clase del evento como un verbo en tiempo pasado, como OrderStartedDomainEvent o OrderShippedDomainEvent. Es la forma de implementar el evento de dominio en la ordenación microservicio en eShopOnContainers.

Como hemos señalado, es una característica importante de los eventos que dado que un evento es algo que se produjeron en el pasado, no debería cambiar. Por lo tanto, debe ser una clase inmutable. Puede ver en el código anterior que las propiedades son de solo lectura desde fuera del objeto. La única manera de actualizar el objeto es a través del constructor al crear el objeto de evento.

### <a name="raising-domain-events"></a>Generar eventos de dominio

La siguiente pregunta se muestra cómo generar un evento de dominio para alcanzar sus controladores de eventos relacionados. Puede utilizar varios enfoques.

UDI Dahan propuesta originariamente (por ejemplo, en algunos relacionadas, como blogs, [eventos de dominio, hacer 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) mediante una clase estática para administrar y provocar los eventos. Esto podría incluir una clase estática denominada DomainEvents que se provocan eventos de dominio inmediatamente cuando se llama, con una sintaxis similar DomainEvents.Raise (evento myEvent). Jimmy Bogard escribió una entrada de blog ([reforzar el dominio: dominio eventos](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) que recomienda un enfoque similar.

Sin embargo, cuando la clase de eventos de dominio es estática, también lo envía a controladores inmediatamente. Esto dificulta pruebas y depuración, dado que los controladores de eventos con la lógica de efectos secundarios se ejecutan inmediatamente después de que se genera el evento. Cuando se prueba y depuración, desea centrarse en y solo lo que sucede en las clases agregadas actuales; ¿desea redirigir repentinamente a otros controladores de eventos para los efectos secundarios relacionados con otros agregados o la lógica de la aplicación. Se trata de por qué han evolucionado otros métodos, como se explica en la sección siguiente.

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a>El enfoque para generar y enviar eventos diferido

En lugar de enviar a un controlador de eventos de dominio inmediatamente, un enfoque más adecuado consiste en agregar los eventos de dominio a una colección y, a continuación, para enviar los eventos de dominio *justo antes de* o *derecho*  *una vez* confirmar la transacción (como ocurre con SaveChanges en EF). (Este enfoque descrito por Jimmy Bogard en esta entrada de [un patrón de eventos de dominio mejor](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)

Decidir si enviar los eventos de dominio derecha antes o a la derecha después de confirmar la transacción es importante, ya que determina si se van a incluir los efectos secundarios como parte de la misma transacción o en diferentes transacciones. En este último caso, debe tratar con coherencia definitiva a través de varios agregados. En este tema se describe en la sección siguiente.

El enfoque diferido es qué eShopOnContainers usa. En primer lugar, agregue los eventos que sucede en las entidades en una colección o lista de eventos por entidad. Esa lista debe ser parte del objeto de entidad, o incluso mejor, parte de la clase de entidad base, como se muestra en el ejemplo siguiente:

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

Cuando desea generar un evento, agrega simplemente a la colección de eventos para colocarse dentro de un método de entidad agregado, como se muestra en el código siguiente:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Tenga en cuenta que lo único que está realizando el método AddDomainEvent es agregar un evento a la lista. Se genera ningún evento todavía y no hay ningún controlador de eventos se invoca todavía.

Realmente desea enviar los eventos más adelante cuando se confirma la transacción a la base de datos. Si usa Entity Framework Core, que significa que en el método SaveChanges de sus DbContext EF, como en el código siguiente:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
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
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

Con este código, enviar los eventos de la entidad a sus controladores de eventos correspondientes.

El resultado general es que se separa la generación de un evento de dominio (un sencillo agregar en una lista en la memoria) de enviarlos a un controlador de eventos. Además, dependiendo de qué tipo de distribuidor usa, puede enviar los eventos de forma sincrónica o asincrónica.

Tenga en cuenta que los límites transaccionales surte significativos reproducirán aquí. Si la unidad de trabajo y la transacción puede abarcar más de un agregado (como ocurre cuando se usa una base de datos relacional y los núcleos de EF), esto puede funcionar bien. Pero si la transacción no puede abarcar agregados, como cuando se utiliza una base de datos NoSQL como documentos de Azure, se deben llevar a cabo pasos adicionales para lograr coherencia. Este es otro motivo por qué la omisión de persistencia no es universal; depende del sistema de almacenamiento que utilice.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Transacción única a través de agregados en comparación con coherencia definitiva en agregados

La pregunta de si se debe realizar una única transacción a través de agregados en lugar de depender de coherencia definitiva a través de los agregados es controvertidos. Muchos autores DDD como Eric Evans y Vaughn Vernon promuevan la regla que una transacción = un agregado y argumentan, por tanto, para mantener la coherencia final a través de agregados. Por ejemplo, en su libro *Domain-Driven diseño*, Eric Evans dice lo siguiente:

Cualquier regla que abarca agregados no se espera que estén actualizados en todo momento. A través de procesamiento de eventos, el procesamiento por lotes u otros mecanismos de actualización, se pueden resolver otras dependencias dentro de un determinado momento. (pg. 128)

Vaughn Vernon dice lo siguiente en [diseño agregado efectivo. Parte II: Hacer que agrega trabajo juntos](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

Por lo tanto, si ejecuta un comando en una instancia del agregado requiere que las reglas de negocio adicionales se ejecutan en uno o varios agregados, use coherencia definitiva \[...\] Hay una forma práctica para admitir la coherencia final en un modelo DDD. Un método de agregación publica un evento de dominio que se encuentra en el tiempo de entrega a uno o varios suscriptores asincrónicos.

Esta lógica se basa en la adopción de transacciones específicas en lugar de transacciones distribuidas en varios agregados o entidades. La idea es que en el segundo caso, el número de bloqueos de base de datos será sustancial en aplicaciones a gran escala con necesidades de alta escalabilidad. Adoptan el hecho de que las aplicaciones escalables de alta necesitan no tienen la coherencia transaccional entre varios agregados ayudará a aceptar el concepto de coherencia definitiva. A menudo no son necesarios cambios atómicos por parte de la empresa y en cualquier caso es la responsabilidad de los expertos de dominio para indicar si las operaciones determinadas necesitan que las transacciones atómicas o no. Si una operación siempre necesita una transacción atómica entre varios agregados, podría preguntarse si su agregado debe ser mayor o no se ha diseñado correctamente.

Sin embargo, otros programadores y arquitectos como Jimmy Bogard están conforme con una sola transacción que abarcan varios agregados, pero solo cuando los agregados adicionales están relacionados con efectos secundarios para el mismo comando original. Por ejemplo, en [un patrón de eventos de dominio mejor](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard dice lo siguiente:

Normalmente, desea que los efectos secundarios de un evento de dominio que se produzca en la misma transacción lógica, pero no necesariamente en el mismo ámbito de generar el evento de dominio \[...\] Justo antes de que se confirma la transacción, se envía nuestros eventos a sus correspondientes controladores.

Si envía el derecho de eventos de dominio *antes de* confirmar la transacción original, es porque desea que los efectos secundarios de los eventos que se incluirá en la misma transacción. Por ejemplo, si se produce un error en el método DbContext SaveChanges EF, la transacción revertirá todos los cambios, incluidos el resultado de cualquier operación de efecto secundario implementada por los controladores de eventos de dominio relacionadas. Esto es porque el ámbito de la vida de DbContext es de forma predeterminada que se define como "el ámbito." Por lo tanto, el objeto de DbContext se comparte entre varios objetos de repositorio que se va a crear una instancia en el mismo ámbito o un gráfico de objetos. Esto coincide con el ámbito de HttpRequest al desarrollar aplicaciones MVC o Web API no compatibles.

En realidad, ambos enfoques (única transacción atómica y coherencia definitiva) pueden ser correctas. Realmente depende de los requisitos empresariales o de dominio y lo que los expertos de dominio indican. También depende de cómo escalable necesita el servicio esté (transacciones más granulares tienen un impacto menor en relación con los bloqueos de base de datos). Y depende de cuánto inversión está dispuesto a hacer en el código, puesto que coherencia definitiva requiere un código más complejo con el fin de detectar posibles incoherencias en los agregados y la necesidad de implementar acciones de compensación. Tenga en cuenta que si Confirmar cambios en el agregado original y después, cuando se distribuyen los eventos, hay un problema y los controladores de eventos no pueden confirmar sus efectos secundarios, tendrá las incoherencias entre agregados.

Una manera de permitir acciones de compensación sería almacenar los eventos de dominio en las tablas de base de datos adicional para que puedan ser parte de la transacción original. Después, podría tener un proceso por lotes que detecta incoherencias y ejecutar acciones de compensación comparando la lista de eventos con el estado actual de los agregados. Las acciones de compensación forman parte de un tema complejo que requerirá un análisis profundo de su lado, que incluye hablando con los usuarios empresariales y expertos de dominio.

En cualquier caso, puede elegir el enfoque que necesita. Pero la inicial retrasa enfoque: cuando se genera los eventos antes de confirmar, por lo que usar una sola transacción, es el enfoque más sencillo cuando se utiliza una base de datos relacional y los núcleos de EF. Es más fácil de implementar y en muchos casos empresariales es válido. También es el enfoque usado en la ordenación microservicio en eShopOnContainers.

¿Pero cómo realmente enviar los eventos a sus controladores de eventos correspondientes? ¿Qué es la \_objeto mediador que se ve en el ejemplo anterior? Que tiene que ver con las técnicas y los artefactos que se puede usar para asignar entre los eventos y sus controladores de eventos.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>El distribuidor de eventos de dominio: asignación de eventos a controladores de eventos

Una vez que pueden enviar o publicar los eventos, necesita algún tipo de artefacto que vaya a publicar el evento para que cada controlador relacionado puede obtenerlo y efectos secundarios de proceso basada en ese evento.

Un enfoque es un sistema de mensajería real o incluso un bus de eventos, basándose en un bus de servicio en lugar de en la memoria de eventos es posible. Sin embargo, para el primer caso, mensajería real sería excesivos para procesar eventos de dominio, ya que solo tiene que procesar esos eventos dentro del mismo proceso (es decir, dentro de la misma capa de aplicación y de dominio).

Es otra manera de eventos se asignan a varios controladores de eventos utilizando el registro de tipos en un contenedor de IoC infiera dónde enviar los eventos de forma dinámica. En otras palabras, debe saber lo que necesitan controladores de eventos para obtener un evento específico. Figura 9-16 se muestra un enfoque simplificado para.

![](./media/image17.png)

**Figura 9-16**. Distribuidor de eventos de dominio con IoC

Puede crear todos los artefactos que se va a implementar este enfoque y mecánica. Sin embargo, también puede utilizar las bibliotecas disponibles como [MediatR](https://github.com/jbogard/MediatR), que interiormente usa el contenedor de IoT. Por lo tanto, puede usar directamente las interfaces predefinidas y los mediador métodos del objeto de publicación y distribución.

En el código, primero debe registrar los tipos de controlador de eventos en el contenedor de IoC, tal como se muestra en el ejemplo siguiente:

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

En primer lugar, el código identifica el ensamblado que contiene los controladores de eventos de dominio ubicando el ensamblado que contiene cualquiera de los controladores (usar typeof(ValidateOrAddBuyerAggregateWhenXxxx), pero podría haber elegido cualquier otro controlador de eventos para buscar el ensamblado). Puesto que todos los controladores de eventos implementan la interfaz IAsyncNotificationHandler, a continuación, el código solo busca los tipos y registra todos los controladores de eventos.

### <a name="how-to-subscribe-to-domain-events"></a>Cómo suscribirse a eventos de dominio

Cuando usas MediatR, cada controlador de eventos debe usar un tipo de evento que se proporciona en el parámetro genérico de la interfaz IAsyncNotificationHandler, como puede ver en el código siguiente:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

En función de la relación entre eventos y el controlador de eventos, que puede considerarse la suscripción, el artefacto MediatR puede detectar todos los controladores de eventos para cada evento y desencadenar cada uno de esos controladores de eventos.

### <a name="how-to-handle-domain-events"></a>Cómo controlar eventos de dominio

Por último, el controlador de eventos normalmente implementa código de capa de aplicación que utiliza los repositorios de infraestructura para obtener los agregados adicionales necesarios y para ejecutar la lógica del dominio de efectos secundarios. En el código siguiente se muestra un ejemplo.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
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
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

Este código de controlador de eventos se considera código de capa de aplicación porque utiliza repositorios de infraestructura, como se explica en la sección siguiente de la capa de persistencia de la infraestructura. Controladores de eventos también pudieron usar otros componentes de infraestructura.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Eventos de dominio pueden generar eventos de integración para publicarse fuera de los límites de microservicio

Por último, es importante mencionar que en ocasiones, podría interesarle propague eventos a través de varios microservicios. Que se considera un evento de integración y que se puede publicar a través de un bus de eventos desde cualquier controlador de eventos de dominio específico.

## <a name="conclusions-on-domain-events"></a>Conclusiones sobre los eventos de dominio 

Como se mencionó, usar eventos de dominio para implementar explícitamente los efectos secundarios de los cambios de su dominio. Para usar la terminología DDD, usar eventos de dominio para implementar explícitamente los efectos secundarios a través de uno o varios agregados. Además, mejora la escalabilidad y el menor impacto sobre los bloqueos de base de datos, utilice coherencia definitiva entre agregados dentro del mismo dominio.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Greg Young. ¿Qué es un evento de dominio? ** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)

-   **Stenberg de enero. Eventos de dominio y coherencia definitiva**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)

-   **Jimmy Bogard. Un patrón de eventos de dominio mejor**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)

-   **Vaughn Vernon. Efectivo agregado diseño parte II: Realizar agregados trabajo juntos**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_artículos/Vernon\_de2011\_ 2. pdf de*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

-   **Jimmy Bogard. Refuerzo de su dominio: dominio eventos**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*

-   **Tony Truong. Ejemplo de modelo de eventos de dominio**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)

-   **UDI Dahan. Cómo crear totalmente encapsula modelos de dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)

-   **UDI Dahan. Eventos de dominio, hacer 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)

-   **UDI Dahan. Eventos de dominio: salvación**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)

-   **Kronquist de enero. No publicar eventos de dominio, estos valores. ** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)

-   **Cesar de la Torre. Dominio frente a eventos. Eventos de integración en arquitecturas DDD y microservicios**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)


>[!div class="step-by-step"]
[Anterior] (cliente-lado-validation.md) [siguiente] (infraestructura de persistencia-capa design.md)
