---
title: Implementación del nivel de aplicación de microservicios mediante la API web
description: Comprenda los procesos de inserción de dependencias y los patrones de mediador y sus detalles de implementación en la capa de aplicación de la API web.
ms.date: 01/30/2020
ms.openlocfilehash: a88f3bfd11ea06df085ca82ed7265cb37006fc31
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502446"
---
# <a name="implement-the-microservice-application-layer-using-the-web-api"></a>Implementación del nivel de aplicación de microservicios mediante la API web

## <a name="use-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Uso de la inserción de dependencias para insertar objetos de la infraestructura en el nivel de aplicación

Como se ha mencionado anteriormente, el nivel de aplicación se puede implementar como parte del artefacto (ensamblado) que se está creando, por ejemplo, dentro de un proyecto de API web o de aplicación web MVC. En el caso de un microservicio compilado con ASP.NET Core, el nivel de aplicación normalmente será la biblioteca de API web. Si quiere separar lo que proviene de ASP.NET Core (su infraestructura y los controladores) del código de nivel de aplicación personalizado, también puede colocar el nivel de aplicación en una biblioteca de clases independiente, pero es algo opcional.

Por ejemplo, el código de nivel de aplicación del microservicio de pedidos se implementa directamente como parte del proyecto **Ordering.API** (un proyecto de API web de ASP.NET Core), como se muestra en la figura 7-23.

:::image type="complex" source="./media/microservice-application-layer-implementation-web-api/ordering-api-microservice.png" alt-text="Captura de pantalla del microservicio Ordering.API en el Explorador de soluciones.":::
Vista del Explorador de soluciones del microservicio Ordering.API que muestra las subcarpetas de la carpeta Application: Behaviors, Commands, DomainEventHandlers, IntegrationEvents, Models, Queries y Validations.
:::image-end:::

**Figura 7-23.** Nivel de aplicación en el proyecto de API web de ASP.NET Core Ordering.API

En ASP.NET Core se incluye un simple [contenedor de IoC integrado](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (representado por la interfaz IServiceProvider) que admite la inserción de constructores de forma predeterminada, y ASP.NET hace que determinados servicios estén disponibles a través de DI. En ASP.NET Core se usa el término *servicio* para cualquiera de los tipos que se registran para la inserción mediante DI. Los servicios del contenedor integrado se configuran en el método ConfigureServices de la clase Startup de la aplicación. Las dependencias se implementan en los servicios que un tipo necesita y que se registran en el contenedor IoC.

Normalmente, le interesará insertar dependencias que implementen objetos de infraestructura. Una dependencia muy habitual para insertar es un repositorio. Pero también podría insertar cualquier otra dependencia de infraestructura que pueda tener. Para las implementaciones más sencillas, también podría insertar directamente el objeto de patrón de unidades de trabajo (el objeto DbContext de EF), porque DBContext también es la implementación de los objetos de persistencia de infraestructura.

En el ejemplo siguiente, puede ver cómo .NET Core inserta los objetos de repositorio necesarios a través del constructor. La clase es un controlador de comandos, que se explica en la sección siguiente.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

En la clase se usan los repositorios insertados para ejecutar la transacción y conservar los cambios de estado. No importa si esa clase es un controlador de comandos, un método de controlador de API web de ASP.NET Core, o un [servicio de aplicación DDD](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). En última instancia, es una clase simple que usa repositorios, entidades de dominio y otra coordinación de aplicaciones de forma similar a un controlador de comandos. La inserción de dependencias funciona igual en todas las clases mencionadas, como en el ejemplo de uso de DI según el constructor.

### <a name="register-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registro de los tipos de implementación de dependencias e interfaces o abstracciones

Antes de usar los objetos insertados mediante constructores, debe saber dónde registrar las interfaces y clases que generan los objetos que se insertan en las clases de aplicación a través de DI. (Como la inserción de dependencias basada en el constructor, tal y como se mostró anteriormente).

#### <a name="use-the-built-in-ioc-container-provided-by-aspnet-core"></a>Uso del contenedor de IoC integrado proporcionado por ASP.NET Core

Cuando use el contenedor de IoC integrado proporcionado por ASP.NET Core, registre los tipos que quiera insertar en el método ConfigureServices del archivo Startup.cs, como se muestra en el código siguiente:

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
        c.UseSqlServer(Configuration["ConnectionString"]),
        ServiceLifetime.Scoped);

    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

El modelo más común al registrar los tipos en un contenedor de IoC es registrar un par de tipos: una interfaz y su clase de implementación relacionada. Después, cuando se solicita un objeto del contenedor de IoC a través de cualquier constructor, se solicita un objeto de un tipo de interfaz determinado. En el ejemplo anterior, la última línea indica que, cuando cualquiera de los constructores tiene una dependencia de IMyCustomRepository (interfaz o abstracción), el contenedor de IoC insertará una instancia de la clase de implementación MyCustomSQLServerRepository.

#### <a name="use-the-scrutor-library-for-automatic-types-registration"></a>Uso de la biblioteca Scrutor para el registro de tipos automático

Al usar DI en .NET Core, es posible que le interese poder examinar un ensamblado y registrar sus tipos de manera automática por convención. Actualmente, esta característica no está disponible en ASP.NET Core, pero puede usar la biblioteca [Scrutor](https://github.com/khellang/Scrutor) para hacerlo. Este enfoque resulta conveniente cuando existen docenas de tipos que deben registrarse en el contenedor de IoC.

#### <a name="additional-resources"></a>Recursos adicionales

- **Matthew King. Registering services with Scrutor** (Registro de servicios con Scrutor) \
  <https://www.mking.net/blog/registering-services-with-scrutor>

- **Kristian Hellang. Scrutor.** Repositorio de GitHub. \
  <https://github.com/khellang/Scrutor>

#### <a name="use-autofac-as-an-ioc-container"></a>Uso de Autofac como un contenedor de IoC

También se pueden usar contenedores de IoC adicionales y conectarlos a la canalización de ASP.NET Core, como se muestra en el microservicio de pedidos en eShopOnContainers, donde se usa [Autofac](https://autofac.org/). Cuando se usa Autofac normalmente los tipos se registran a través de módulos, lo que permite dividir los tipos de registro entre varios archivos, en función de dónde se encuentren los tipos, al igual que los tipos de aplicaciones podrían estar distribuidos entre varias bibliotecas de clases.

Por ejemplo, el siguiente es el [módulo de aplicación de Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) para el proyecto de [API web Ordering.API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) con los tipos que se quieren insertar.

```csharp
public class ApplicationModule : Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

Autofac también tiene una característica para [analizar ensamblados y registrar tipos por convenciones de nombre](https://autofac.readthedocs.io/en/latest/register/scanning.html).

El proceso de registro y los conceptos son muy similares a la manera en que se pueden registrar tipos con el contenedor integrado de IoC de ASP.NET Core, pero cuando se usa Autofac la sintaxis es un poco diferente.

En el código de ejemplo, la abstracción IOrderRepository se registra junto con la clase de implementación OrderRepository. Esto significa que cada vez que un constructor declare una dependencia a través de la abstracción o la interfaz IOrderRepository, el contenedor de IoC insertará una instancia de la clase OrderRepository.

El tipo de ámbito de la instancia determina cómo se comparte una instancia entre las solicitudes del mismo servicio o dependencia. Cuando se realiza una solicitud de una dependencia, el contenedor de IoC puede devolver lo siguiente:

- Una sola instancia por ámbito de duración (denominada *con ámbito* en el contenedor de IoC de ASP.NET Core).

- Una nueva instancia por dependencia (denominada *transitoria* en el contenedor de IoC de ASP.NET Core).

- Una única instancia que se comparte entre todos los objetos que usan el contenedor de IoC (denominada *singleton* en el contenedor de IoC de ASP.NET Core).

#### <a name="additional-resources"></a>Recursos adicionales

- **Introduction to Dependency Injection in ASP.NET Core** (Introducción a la inserción de dependencias en ASP.NET Core) \
  [https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection](/aspnet/core/fundamentals/dependency-injection)

- **Autofac.** Documentación oficial. \
  <https://docs.autofac.org/en/latest/>

- **Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes** (Comparación de las duraciones de servicio del contenedor IoC de ASP.NET Core con ámbitos de instancia de contenedor Autofac IoC) - Cesar de la Torre. \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="implement-the-command-and-command-handler-patterns"></a>Implementación de los patrones de comando y controlador de comandos

En el ejemplo de DI a través del constructor mostrado en la sección anterior, el contenedor de IoC insertaba repositorios a través de un constructor en una clase. ¿Pero exactamente dónde se insertaban? En una API web simple (por ejemplo, el microservicio de catálogo de eShopOnContainers), se insertan en el nivel de controladores de MVC, en un constructor de controlador, como parte de la canalización de solicitud de ASP.NET Core. Pero en el código inicial de esta sección (la clase [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) del servicio Ordering.API en eShopOnContainers), la inserción de dependencias se realiza a través del constructor de un determinado controlador de comandos. Vamos a explicar qué es un controlador de comandos y por qué le interesaría usarlo.

El patrón de comandos está intrínsecamente relacionado con el patrón CQRS que se presentó anteriormente en esta guía. CQRS tiene dos lados. La primera área son las consultas, mediante consultas simplificadas con el micro-ORM [Dapper](https://github.com/StackExchange/dapper-dot-net), que se explicó anteriormente. La segunda área son los comandos, el punto inicial para las transacciones y el canal de entrada desde el exterior del servicio.

Como se muestra en la figura 7-24, el patrón se basa en la aceptación de comandos del lado cliente, su procesamiento según las reglas del modelo de dominio y, por último, la conservación de los estados con transacciones.

![Diagrama que muestra el flujo de datos general del cliente a la base de datos.](./media/microservice-application-layer-implementation-web-api/high-level-writes-side.png)

**Figura 7-24.** Vista general de los comandos o el "lado transaccional" en un patrón CQRS

En la figura 7-24 se muestra que la aplicación de interfaz de usuario envía un comando a través de la API que llega a un elemento `CommandHandler`, que depende del modelo de dominio y de la infraestructura para actualizar la base de datos.

### <a name="the-command-class"></a>La clase de comando

Un comando es una solicitud para que el sistema realice una acción que cambia el estado del sistema. Los comandos son imperativos y se deben procesar una sola vez.

Como los comandos son imperativos, normalmente se denominan con un verbo en modo imperativo (por ejemplo, "create" o "update"), y es posible que incluyan el tipo agregado, como CreateOrderCommand. A diferencia de un evento, un comando no es un hecho del pasado; es solo una solicitud y, por tanto, se puede denegar.

Los comandos se pueden originar desde la interfaz de usuario como resultado de un usuario que inicia una solicitud, o desde un administrador de procesos cuando está dirigiendo un agregado para realizar una acción.

Una característica importante de un comando es que debe procesarse una sola vez por un único receptor. Esto se debe a que un comando es una única acción o transacción que se quiere realizar en la aplicación. Por ejemplo, el mismo comando de creación de pedidos no se debe procesar más de una vez. Se trata de una diferencia importante entre los comandos y los eventos. Los eventos se pueden procesar varias veces, dado que es posible que muchos sistemas o microservicios estén interesados en el evento.

Además, es importante que un comando solo se procese una vez en caso de que no sea idempotente. Un comando es idempotente si se puede ejecutar varias veces sin cambiar el resultado, ya sea debido a la naturaleza del comando, o bien al modo en que el sistema lo controla.

Un procedimiento recomendado consiste en hacer que los comandos y las actualizaciones sean idempotentes cuando tenga sentido según las reglas de negocio e invariables del dominio. Para usar el mismo ejemplo, si por algún motivo (lógica de reintento, piratería, etc.) el mismo comando CreateOrder llega varias veces al sistema, debería poder identificarlo y asegurarse de que no se crean varios pedidos. Para ello, debe adjuntar algún tipo de identidad en las operaciones e identificar si el comando o la actualización ya se ha procesado.

Un comando se envía a un único receptor; no se publica. La publicación es para los eventos que notifican un hecho: que ha sucedido algo y que podría ser interesante para los receptores de eventos. En el caso de los eventos, al publicador no le interesa qué receptores obtienen el evento o las acciones que realizan. Pero los eventos de integración o de dominio son diferentes y ya se presentaron en secciones anteriores.

Un comando se implementa con una clase que contiene campos de datos o colecciones con toda la información necesaria para ejecutar ese comando. Un comando es un tipo especial de objeto de transferencia de datos (DTO), que se usa específicamente para solicitar cambios o transacciones. El propio comando se basa en la información exacta que se necesita para procesar el comando y nada más.

En el siguiente ejemplo se muestra la clase `CreateOrderCommand` simplificada. Se trata de un comando inmutable que se usa en el microservicio de pedidos de eShopOnContainers.

```csharp
// DDD and CQRS patterns comment
// Note that we recommend that you implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;
    [DataMember]
    public string City { get; private set; }
    [DataMember]
    public string Street { get; private set; }
    [DataMember]
    public string State { get; private set; }
    [DataMember]
    public string Country { get; private set; }
    [DataMember]
    public string ZipCode { get; private set; }
    [DataMember]
    public string CardNumber { get; private set; }
    [DataMember]
    public string CardHolderName { get; private set; }
    [DataMember]
    public DateTime CardExpiration { get; private set; }
    [DataMember]
    public string CardSecurityNumber { get; private set; }
    [DataMember]
    public int CardTypeId { get; private set; }
    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<BasketItem> basketItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = MapToOrderItems(basketItems);
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

Básicamente, la clase de comando contiene todos los datos que se necesitan para llevar a cabo una transacción empresarial mediante los objetos de modelo de dominio. Por tanto, los comandos son simplemente las estructuras de datos que contienen datos de solo lectura y ningún comportamiento. El nombre del comando indica su propósito. En muchos lenguajes como C#, los comandos se representan como clases, pero no son verdaderas clases en el sentido real orientado a objetos.

Como una característica adicional, los comandos son inmutables, dado que el uso esperado es que el modelo de dominio los procese directamente. No deben cambiar durante su duración prevista. En una clase de C#, se puede lograr la inmutabilidad si no hay establecedores ni otros métodos que cambien el estado interno.

Tenga en cuenta que si quiere o espera que los comandos pasen por un proceso de serialización o deserialización, las propiedades deben tener un establecedor privado y el atributo `[DataMember]` (o `[JsonProperty]`). De lo contrario, el deserializador no podrá reconstruir el objeto en el destino con los valores necesarios. También puede usar propiedades que realmente sean de solo lectura si la clase tiene un constructor con parámetros para todas las propiedades, con la convención de nomenclatura de camelCase habitual, y anotar el constructor como `[JsonConstructor]`. Sin embargo, esta opción requiere más código.

Por ejemplo, la clase de comando para crear un pedido probablemente sea similar en cuanto a los datos del pedido que se quiere crear, pero es probable que no se necesiten los mismos atributos. Por ejemplo, `CreateOrderCommand` no tiene un identificador de pedido, porque el pedido aún no se ha creado.

Muchas clases de comando pueden ser simples y requerir solo unos cuantos campos sobre algún estado que deba cambiarse. Ese sería el caso si solo se va a cambiar el estado de un pedido de "en proceso" a "pagado" o "enviado" con un comando similar al siguiente:

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

Algunos desarrolladores separan los objetos de solicitud de interfaz de usuario de los DTO de comando, pero es solo una cuestión de preferencia. Es una separación tediosa sin demasiado valor añadido y los objetos tienen prácticamente la misma forma. Por ejemplo, en eShopOnContainers, algunos comandos proceden directamente del lado cliente.

### <a name="the-command-handler-class"></a>Clase de controlador de comandos

Debe implementar una clase de controlador de comandos específica para cada comando. Ese es el funcionamiento del patrón y el lugar en el que se usarán el objeto de comando, los objetos de dominio y los objetos de repositorio de infraestructura. De hecho, el controlador de comandos es el núcleo del nivel de aplicación en lo que a CQRS y DDD respecta. Sin embargo, toda la lógica del dominio debe incluirse en las clases de dominio, dentro de las raíces agregadas (entidades raíz), las entidades secundarias o [los servicios de dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), pero no en el controlador de comandos, que es una clase del nivel de aplicación.

La clase de controlador de comandos ofrece un punto de partida seguro en la forma de lograr el principio de responsabilidad única (SRP) mencionado en una sección anterior.

Un controlador de comandos recibe un comando y obtiene un resultado del agregado que se usa. El resultado debe ser la ejecución correcta del comando, o bien una excepción. En el caso de una excepción, el estado del sistema no debe cambiar.

Normalmente, el controlador de comandos realiza estos pasos:

- Recibe el objeto de comando, como un DTO (desde el [mediador](https://en.wikipedia.org/wiki/Mediator_pattern) u otro objeto de infraestructura).

- Valida que el comando sea válido (si no lo hace el mediador).

- Crea una instancia de la instancia de raíz agregada que es el destino del comando actual.

- Ejecuta el método en la instancia de raíz agregada y obtiene los datos necesarios del comando.

- Conserva el nuevo estado del agregado en su base de datos relacionada. Esta última operación es la transacción real.

Normalmente, un controlador de comandos administra un único agregado controlado por su raíz agregada (la entidad raíz). Si varios agregados deben verse afectados por la recepción de un único comando, podría usar eventos de dominio para propagar los estados o las acciones entre varios agregados.

El aspecto importante aquí es que cuando se procesa un comando, toda la lógica del dominio debe incluirse en el modelo de dominio (los agregados), completamente encapsulada y lista para las pruebas unitarias. El controlador de comandos solo actúa como una manera de obtener el modelo de dominio de la base de datos y, como último paso, para indicar al nivel de infraestructura (los repositorios) que conserve los cambios cuando el modelo cambie. La ventaja de este enfoque es que se puede refactorizar la lógica del dominio en un modelo de dominio de comportamiento aislado, completamente encapsulado y enriquecido sin cambiar el código del nivel de aplicación o infraestructura, que forman el nivel de establecimiento (controladores de comandos, la API web, repositorios, etc.).

Cuando los controladores de comandos se complican, con demasiada lógica, se puede producir un problema en el código. Revíselos y, si encuentra lógica de dominio, refactorice el código para mover ese comportamiento de dominio a los métodos de los objetos de dominio (la raíz agregada y la entidad secundaria).

Como ejemplo de clase de controlador de comandos, en el código siguiente se muestra la misma clase `CreateOrderCommandHandler` que se vio al principio de este capítulo. En este caso, se pretende resaltar el método Handle y las operaciones con los objetos de modelo de dominio y agregados.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

Estos son los pasos adicionales que debe realizar un controlador de comandos:

- Usar los datos del comando para funcionar con los métodos y el comportamiento de la raíz agregada.

- Dentro de los objetos de dominio, generar eventos de dominio mientras se ejecuta la transacción, pero de forma transparente desde el punto de vista de un controlador de comandos.

- Si el resultado de la operación del agregado es correcta y una vez finalizada la transacción, generar eventos de integración. (Es posible que clases de infraestructura como repositorios también los generen).

#### <a name="additional-resources"></a>Recursos adicionales

- **Mark Seemann. At the Boundaries, Applications are Not Object-Oriented (En los límites, las aplicaciones no están orientadas a objetos)**  \
  <https://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/>

- **Commands and events (Comandos y eventos)**  \
  <https://cqrs.nu/Faq/commands-and-events>

- **What does a command handler do?** (¿De qué se encarga un controlador de comandos?) \
  <https://cqrs.nu/Faq/command-handlers>

- **Jimmy Bogard. Domain Command Patterns – Handlers (Patrones de comandos de dominio: controladores)**  \
  <https://jimmybogard.com/domain-command-patterns-handlers/>

- **Jimmy Bogard. Domain Command Patterns – Validation (Patrones de comandos de dominio: validación)**  \
  <https://jimmybogard.com/domain-command-patterns-validation/>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>La canalización del proceso de comando: cómo desencadenar un controlador de comandos

La siguiente pregunta es cómo invocar un controlador de comandos. Se podría llamar manualmente desde cada controlador de ASP.NET Core relacionado. Pero ese enfoque sería demasiado acoplado y no es lo ideal.

Las otras dos opciones principales, que son las recomendadas, son estas:

- A través de un artefacto de patrón de mediador en memoria.

- Con una cola de mensajes asincrónicos, entre los controladores.

### <a name="use-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Uso del patrón de mediador (en memoria) en la canalización de comandos

Como se muestra en la figura 7-25, en un enfoque CQRS se usa un mediador inteligente, similar a un bus en memoria, que es lo suficientemente inteligente como para redirigir al controlador de comandos correcto según el tipo del comando o DTO que se recibe. Las flechas simples de color negro entre los componentes representan las dependencias entre los objetos (en muchos casos, insertados mediante DI) con sus interacciones relacionadas.

![Diagrama que muestra un flujo de datos más detallado del cliente a la base de datos.](./media/microservice-application-layer-implementation-web-api/mediator-cqrs-microservice.png)

**Figura 7-25.** Uso del patrón de mediador en proceso en un único microservicio CQRS

En el diagrama anterior se muestra más detalle de la imagen 7-24: el controlador ASP.NET Core envía el comando a la canalización de comandos MediatR para que llegue al controlador adecuado.

El motivo por el que tiene sentido usar el patrón de mediador es que, en las aplicaciones empresariales, las solicitudes de procesamiento pueden resultar complicadas. Le interesa poder agregar un número abierto de cuestiones transversales como registro, validaciones, auditoría y seguridad. En estos casos, puede basarse en una canalización de mediador (vea [Patrón de mediador](https://en.wikipedia.org/wiki/Mediator_pattern)) para proporcionar un medio para estos comportamientos adicionales o cuestiones transversales.

Un mediador es un objeto que encapsula el "cómo" de este proceso: coordina la ejecución en función del estado, la forma de invocar un controlador de comandos o la carga que se proporciona al controlador. Con un componente de mediador se pueden aplicar cuestiones transversales de forma centralizada y transparente aplicando elementos Decorator (o [comportamientos de canalización](https://github.com/jbogard/MediatR/wiki/Behaviors) desde [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)). Para obtener más información, vea el [Patrón de Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).

Los elementos Decorator y los comportamientos son similares a la [Programación orientada a aspectos (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), solo se aplican a una canalización de proceso específica administrada por el componente de mediador. Los aspectos en AOP que implementan cuestiones transversales se aplican en función de *tejedores de aspectos* que se insertan en tiempo de compilación o en función de la intercepción de llamadas de objeto. En ocasiones, se dice que ambos enfoques típicos de AOP funcionan "de forma mágica", porque no es fácil ver cómo realiza AOP su trabajo. Cuando se trabaja con problemas graves o errores, AOP puede ser difícil de depurar. Por otro lado, estos elementos Decorator o comportamientos son explícitos y solo se aplican en el contexto del mediador, por lo que la depuración es mucho más sencilla y predecible.

Por ejemplo, en el microservicio de pedidos de eShopOnContainers, se implementaron dos comportamientos de ejemplo, las clases [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) y [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs). En la siguiente sección se explica la implementación de los comportamientos y se muestra cómo eShopOnContainers usa los [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) de [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0).

### <a name="use-message-queues-out-of-proc-in-the-commands-pipeline"></a>Uso de colas de mensajes (fuera de proceso) en la canalización del comando

Otra opción consiste en usar mensajes asincrónicos basados en agentes o colas de mensajes, como se muestra en la figura 7-26. Esa opción también se podría combinar con el componente de mediador justo antes del controlador de comandos.

![Diagrama que muestra el flujo de datos mediante una cola de mensajes de alta disponibilidad.](./media/microservice-application-layer-implementation-web-api/add-ha-message-queue.png)

**Figura 7-26.** Uso de colas de mensajes (comunicación fuera de proceso y entre procesos) con comandos CQRS

La canalización del comando también puede controlarse mediante una cola de mensajes de alta disponibilidad para entregar los comandos en el controlador adecuado. El uso de colas de mensajes para aceptar los comandos puede complicar más la canalización del comando, ya que probablemente será necesario dividir la canalización en dos procesos conectados a través de la cola de mensajes externos. Pero se debe usar si hay que ofrecer mayor escalabilidad y rendimiento según la mensajería asincrónica. Téngalo en cuenta en el caso de la figura 7-26, donde el controlador simplemente envía el mensaje de comando a la cola y vuelve. Después, los controladores de comandos procesan los mensajes a su propio ritmo. Esa es una gran ventaja de las colas: la cola de mensajes puede actuar como un búfer en casos en que se necesita hiperescalabilidad (por ejemplo, para existencias o cualquier otro escenario con un gran volumen de datos de entrada).

En cambio, debido a la naturaleza asincrónica de las colas de mensajes, debe saber cómo comunicar a la aplicación cliente si el proceso del comando se ha realizado correctamente o no. Como norma, nunca debería usar comandos "Fire and Forget" (dispare y olvídese). Cada aplicación empresarial necesita saber si un comando se ha procesado correctamente, o al menos se ha validado y aceptado.

De este modo, la capacidad de responder al cliente después de validar un mensaje de comando que se envió a una cola asincrónica agrega complejidad al sistema, en comparación con un proceso de comando en proceso que devuelve el resultado de la operación después de ejecutar la transacción. Mediante las colas, es posible que tenga que devolver el resultado del proceso de comando a través de otros mensajes de resultado de la operación, lo que requiere componentes adicionales y comunicación personalizada en el sistema.

Además, los comandos asincrónicos son unidireccionales, lo que es posible que en muchos casos no sea necesario, tal y como se explica en el siguiente e interesante intercambio entre Burtsev Alexey y Greg Young en una [conversación en línea](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

> \[Burtsev Alexey\] Veo gran cantidad de código en la que los usuarios usan el control de comandos asincrónicos o la mensajería de comandos unidireccionales sin ningún motivo para hacerlo (no están realizando una operación extensa, no ejecutan código asincrónico externo, ni siquiera cruzan los límites de la aplicación para usar bus de mensajes). ¿Por qué agregan esta complejidad innecesaria? Y en realidad, hasta ahora no he visto ningún ejemplo de código CQRS con controladores de comandos de bloqueo, aunque funcionaría correctamente en la mayoría de los casos.
>
> \[Greg Young\] \[...\] un comando asincrónico no existe; en realidad es otro evento. Si tengo que aceptar lo que se me envía y generar un evento si no estoy de acuerdo, ya no se me está pidiendo que realice una acción \[es decir, no es un comando\]. Se me está diciendo que se ha realizado algo. Al principio puede parecer una pequeña diferencia, pero tiene muchas implicaciones.

Los comandos asincrónicos aumentan considerablemente la complejidad de un sistema, porque no hay ninguna manera sencilla de indicar los errores. Por tanto, los comandos asincrónicos no son recomendables a no ser que se necesiten requisitos de escalado o en casos especiales de comunicación de microservicios internos a través de mensajería. En esos casos, se debe diseñar un sistema independiente de informes y recuperación de errores del sistema.

En la versión inicial de eShopOnContainers, decidimos usar el procesamiento de comandos sincrónicos, iniciados desde solicitudes HTTP y controlados por el patrón de mediador. Eso permite devolver con facilidad si el proceso se ha realizado correctamente o no, como en la implementación [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs).

En cualquier caso, debe ser una decisión basada en los requisitos empresariales de la aplicación o el microservicio.

## <a name="implement-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementación de la canalización del proceso de comando con un patrón de mediador (MediatR)

Como implementación de ejemplo, en esta guía se propone el uso de la canalización de proceso basada en el patrón de mediador para controlar la ingesta de comandos y enrutarlos, en memoria, a los controladores de comandos correctos. En la guía también se propone la aplicación de [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) para separar las cuestiones transversales.

Para la implementación en .NET Core, hay varias bibliotecas de código abierto disponibles que implementan el patrón de mediador. En esta guía se usa la biblioteca de código abierto [MediatR](https://github.com/jbogard/MediatR) (creada por Jimmy Bogard), pero puede usar otro enfoque. MediatR es una biblioteca pequeña y simple que permite procesar mensajes en memoria como un comando, mientras se aplican elementos Decorator o comportamientos.

El uso del patrón de mediador ayuda a reducir el acoplamiento y aislar los problemas del trabajo solicitado, mientras se conecta automáticamente al controlador que lleva a cabo ese trabajo, en este caso, a controladores de comandos.

En la revisión de esta guía, Jimmy Bogard explica otra buena razón para usar el patrón de mediador:

> Creo que aquí valdría la pena mencionar las pruebas: proporcionan una ventana coherente al comportamiento del sistema. Solicitud de entrada, respuesta de salida. Hemos comprobado que es un aspecto muy valioso a la hora de generar pruebas que se comporten de forma coherente.

En primer lugar, veremos un controlador WebAPI de ejemplo donde se usaría realmente el objeto de mediador. Si no se usara el objeto de mediador, sería necesario insertar todas las dependencias para ese controlador, elementos como un objeto de registrador y otros. Por tanto, el constructor sería bastante complicado. Por otra parte, si se usa el objeto de mediador, el constructor del controlador puede ser mucho más sencillo, con solo algunas dependencias en lugar de muchas si hubiera una por cada operación transversal, como en el ejemplo siguiente:

```csharp
public class MyMicroserviceController : Controller
{
    public MyMicroserviceController(IMediator mediator,
                                    IMyMicroserviceQueries microserviceQueries)
    {
        // ...
    }
}
```

Se puede ver que el mediador proporciona un constructor de controlador de API web limpio y eficiente. Además, dentro de los métodos de controlador, el código para enviar un comando al objeto de mediador es prácticamente una línea:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> ExecuteBusinessOperation([FromBody]RunOpCommand
                                                               runOperationCommand)
{
    var commandResult = await _mediator.SendAsync(runOperationCommand);

    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

### <a name="implement-idempotent-commands"></a>Implementación de comandos idempotentes

En **eShopOnContainers**, un ejemplo más avanzado que el anterior es el envío de un objeto CreateOrderCommand desde el microservicio Ordering. Pero como el proceso empresarial Ordering es un poco más complejo y, en nuestro caso, se inicia realmente en el microservicio Basket, esta acción de enviar el objeto CreateOrderCommand se realiza desde un controlador de eventos de integración denominado [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs), en lugar de un controlador WebAPI sencillo al que se llama desde la aplicación cliente, como ocurre en el ejemplo anterior más sencillo.

Pero la acción de enviar el comando a MediatR es bastante similar, como se muestra en el código siguiente.

```csharp
var createOrderCommand = new CreateOrderCommand(eventMsg.Basket.Items,
                                                eventMsg.UserId, eventMsg.City,
                                                eventMsg.Street, eventMsg.State,
                                                eventMsg.Country, eventMsg.ZipCode,
                                                eventMsg.CardNumber,
                                                eventMsg.CardHolderName,
                                                eventMsg.CardExpiration,
                                                eventMsg.CardSecurityNumber,
                                                eventMsg.CardTypeId);

var requestCreateOrder = new IdentifiedCommand<CreateOrderCommand,bool>(createOrderCommand,
                                                                        eventMsg.RequestId);
result = await _mediator.Send(requestCreateOrder);
```

Pero este caso también es un poco más avanzado porque también se implementan comandos idempotentes. El proceso CreateOrderCommand debe ser idempotente, por lo que si el mismo mensaje procede duplicado a través de la red, por cualquier motivo, como un reintento, el mismo pedido se procesará una sola vez.

Esto se implementa mediante la encapsulación del comando de negocio (en este caso CreateOrderCommand) y su inserción en un IdentifiedCommand genérico del que se realiza el seguimiento con un identificador de todos los mensajes que lleguen a través de la red que tienen que ser idempotentes.

En el código siguiente, puede ver que el IdentifiedCommand no es más que un DTO con un identificador junto con el objeto de comando de negocio insertado.

```csharp
public class IdentifiedCommand<T, R> : IRequest<R>
    where T : IRequest<R>
{
    public T Command { get; }
    public Guid Id { get; }
    public IdentifiedCommand(T command, Guid id)
    {
        Command = command;
        Id = id;
    }
}
```

Después, el CommandHandler para el IdentifiedCommand denominado [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) básicamente comprobará si el identificador que procede como parte del mensaje ya existe en una tabla. Si ya existe, ese comando no se volverá a procesar, por lo que se comporta como un comando idempotente. Ese código de infraestructura se ejecuta mediante la llamada al método `_requestManager.ExistAsync` siguiente.

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> :
                                   IAsyncRequestHandler<IdentifiedCommand<T, R>, R>
                                   where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;

    public IdentifiedCommandHandler(IMediator mediator,
                                    IRequestManager requestManager)
    {
        _mediator = mediator;
        _requestManager = requestManager;
    }

    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    public async Task<R> Handle(IdentifiedCommand<T, R> message)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);

            // Send the embedded business command to mediator
            // so it runs its related CommandHandler
            var result = await _mediator.Send(message.Command);

            return result;
        }
    }
}
```

Dado que IdentifiedCommand actúa como la envoltura de un comando de negocios, cuando el comando de negocios se debe procesar porque no es un identificador repetido, toma ese comando de negocios interno y lo vuelve a enviar al mediador, como se muestra en la última parte del código anterior al ejecutar `_mediator.Send(message.Command)` desde [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).

Al hacerlo, se vincula y ejecuta el controlador de comandos de negocios, en este caso, [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) que ejecuta transacciones en la base de datos Ordering, como se muestra en el código siguiente.

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
                                   : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Add/Update the Buyer AggregateRoot
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

### <a name="register-the-types-used-by-mediatr"></a>Registro de los tipos usados por MediatR

Para que MediatR sea consciente de las clases de controlador de comandos, debe registrar las clases de mediador y las de controlador de comandos en el contenedor de IoC. De forma predeterminada, MediatR usa Autofac como el contenedor de IoC, pero también se puede usar el contenedor de IoC integrado de ASP.NET Core o cualquier otro contenedor compatible con MediatR.

En el código siguiente se muestra cómo registrar los tipos y comandos del mediador al usar módulos de Autofac.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

Aquí es donde "ocurre la magia" con MediatR.

Como cada controlador de comandos implementa la interfaz genérica `IAsyncRequestHandler<T>`, al registrar los ensamblados, el código registra con `RegisteredAssemblyTypes` todos los tipos marcados como `IAsyncRequestHandler` mientras relaciona los `CommandHandlers` con sus `Commands`, gracias a la relación indicada en la clase `CommandHandler`, como en el siguiente ejemplo:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Ese es el código que pone en correlación los comandos y los controladores de comandos. El controlador es simplemente una clase, pero hereda de `RequestHandler<T>`, donde T es el tipo de comando, y MediatR se asegura de que se invoque con la carga correcta (el comando).

## <a name="apply-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-mediatr"></a>Aplicación de cuestiones transversales al procesar comandos con los comportamientos de MediatR

Hay otro aspecto: la capacidad de aplicar cuestiones transversales a la canalización de mediador. También puede ver al final del código del módulo de registro de Autofac cómo registra un tipo de comportamiento, en concreto una clase LoggingBehavior personalizada y una clase ValidatorBehavior. Pero también se podrían agregar otros comportamientos personalizados.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

Esa clase [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) se puede implementar como el código siguiente, que registra información sobre el controlador de comandos que se está ejecutando y si se ha realizado correctamente o no.

```csharp
public class LoggingBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly ILogger<LoggingBehavior<TRequest, TResponse>> _logger;
    public LoggingBehavior(ILogger<LoggingBehavior<TRequest, TResponse>> logger) =>
                                                                  _logger = logger;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        _logger.LogInformation($"Handling {typeof(TRequest).Name}");
        var response = await next();
        _logger.LogInformation($"Handled {typeof(TResponse).Name}");
        return response;
    }
}
```

Con la simple implementación de esta clase de comportamiento y su registro en la canalización (en el MediatorModule anterior), todos los comandos que se procesan a través de MediatR registrarán información sobre la ejecución.

El microservicio de pedidos de eShopOnContainers también aplica un segundo comportamiento para validaciones básicas, la clase [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) que se basa en la biblioteca [FluentValidation](https://github.com/JeremySkinner/FluentValidation), como se muestra en el código siguiente:

```csharp
public class ValidatorBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly IValidator<TRequest>[] _validators;
    public ValidatorBehavior(IValidator<TRequest>[] validators) =>
                                                         _validators = validators;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        var failures = _validators
            .Select(v => v.Validate(request))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (failures.Any())
        {
            throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                        new ValidationException("Validation exception", failures));
        }

        var response = await next();
        return response;
    }
}
```

El comportamiento aquí está generando una excepción si se produce un error de validación, pero también podría devolver un objeto de resultado, que contiene el resultado del comando si se realiza correctamente o la validación de mensajes en caso de que no lo hiciese. Esto probablemente facilitaría mostrar los resultados de validación al usuario.

Después, en función de la biblioteca [FluentValidation](https://github.com/JeremySkinner/FluentValidation), se crea la validación de los datos pasados con CreateOrderCommand, como se muestra en el código siguiente:

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19);
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).Must(ContainOrderItems).WithMessage("No order items found");
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}

```

Podría crear validaciones adicionales. Se trata de una forma muy limpia y elegante de implementar las validaciones de comandos.

De forma similar, podría implementar otros comportamientos para aspectos adicionales o cuestiones transversales que quiera aplicar a los comandos cuando los administre.

#### <a name="additional-resources"></a>Recursos adicionales

##### <a name="the-mediator-pattern"></a>El patrón de mediador

- **Patrón de mediador** \
  [https://en.wikipedia.org/wiki/Mediator\_pattern](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>El patrón Decorator

- **Patrón Decorator** \
  [https://en.wikipedia.org/wiki/Decorator\_pattern](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

- **MediatR.** Repositorio de GitHub. \
  <https://github.com/jbogard/MediatR>

- **CQRS with MediatR and AutoMapper (CQRS con MediatR y AutoMapper)**  \
  <https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/>

- **Put your controllers on a diet: POSTs and commands** (Poner los controladores a dieta: POST y comandos). \
  <https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/>

- **Tackling cross-cutting concerns with a mediator pipeline (Abordar cuestiones transversales con una canalización de mediador)**  \
  <https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/>

- **CQRS and REST: the perfect match (CQRS y REST: la combinación perfecta)**  \
  <https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/>

- **MediatR Pipeline Examples (Ejemplos de canalización de MediatR)**  \
  <https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/>

- **Vertical Slice Test Fixtures for MediatR and ASP.NET Core (Accesorios de prueba de segmentos verticales para MediatR y ASP.NET Core)**  \
  <https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>

- **MediatR Extensions for Microsoft Dependency Injection Released (Extensiones de MediatR para el lanzamiento de inserciones de dependencias de Microsoft)**  \
  <https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/>

##### <a name="fluent-validation"></a>Validación fluida

- **Jeremy Skinner. Validación fluida.** Repositorio de GitHub. \
  <https://github.com/JeremySkinner/FluentValidation>

> [!div class="step-by-step"]
> [Anterior](microservice-application-layer-web-api-design.md)
> [Siguiente](../implement-resilient-applications/index.md)
