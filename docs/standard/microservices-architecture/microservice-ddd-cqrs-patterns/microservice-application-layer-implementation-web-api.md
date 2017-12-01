---
title: "Implementar el nivel de aplicación de microservicio mediante la API de Web"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar el nivel de aplicación de microservicio mediante la API de Web"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a>Implementar el nivel de aplicación de microservicio mediante la API de Web

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Mediante la inserción de dependencia para insertar objetos de la infraestructura en la capa de aplicación

Como se mencionó anteriormente, la capa de aplicación puede implementarse como parte del artefacto que está creando, tal como dentro de un proyecto de API Web o un proyecto de aplicación web MVC. En el caso de un microservicio compilada con ASP.NET Core, el nivel de aplicación normalmente será la biblioteca de API Web. Si desea separar próximas novedades de ASP.NET Core (su infraestructura y los controladores) desde el código de capa de aplicación personalizada, también puede colocar la capa de aplicación en una biblioteca de clases independiente, pero que es opcional.

Por ejemplo, el código de capa de aplicación de la ordenación microservicio directamente se implementa como parte de la **Ordering.API** proyecto (una API Web de ASP.NET Core), como se muestra en la figura 9-19.

![](./media/image20.png)

**Figura 9-19**. La capa de aplicación en el proyecto Ordering.API ASP.NET Core Web API

ASP.NET Core incluye un sencillo [integrado contenedor de IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (representado por la interfaz IServiceProvider) que admite la inserción del constructor de forma predeterminada y ASP.NET pone a disposición a través de DI determinados servicios. ASP.NET Core utiliza el término *servicio* para cualquiera de los tipos que registra que se insertará mediante DI. Configurar los servicios del contenedor integrados en el método ConfigureServices de clase de inicio de la aplicación. Las dependencias se implementan en los servicios que necesita un tipo.

Normalmente, desea insertar las dependencias que implementan objetos de la infraestructura. Una dependencia muy habitual para insertar es un repositorio. Pero también puede insertar cualquier dependencia de infraestructura que surgen. Para las implementaciones más sencillas, también podría insertar directamente el objeto de patrón de la unidad de trabajo (el objeto DbContext EF), porque DBContext también es la implementación de los objetos de persistencia de infraestructura.

En el ejemplo siguiente, puede ver cómo .NET Core es insertar los objetos de repositorio necesaria a través del constructor. La clase es un controlador de comandos, que se explica en la sección siguiente.

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

La clase utiliza los repositorios insertados para ejecutar la transacción y conservar los cambios de estado. No importa si esa clase es un controlador de comandos, un método de controlador de API Web de ASP.NET Core, o un [DDD aplicación servicio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). En última instancia es una clase simple que utiliza repositorios, entidades de dominio y otro coordinación de las aplicaciones de forma similar a un controlador de comandos. Inyección de dependencia funciona igual en todas las clases mencionadas, como se muestra en el ejemplo de cómo utilizar DI basado en el constructor.

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registrar los tipos de implementación de dependencia y interfaces o abstracciones

Antes de usar los objetos insertados mediante constructores, debe saber dónde registrar las interfaces y clases que generan los objetos que se insertan en las clases de aplicación a través de DI. (Como DI en función del constructor, tal y como se ha mostrado anteriormente).

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a>Usando el contenedor de IoC integrado proporcionado por ASP.NET Core

Cuando se usa el contenedor de IoC integrado proporcionado por ASP.NET Core, registre los tipos que desee insertar en el método ConfigureServices en el archivo Startup.cs, como se muestra en el código siguiente:

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

El modelo más común al registrar los tipos en un contenedor de IoC es registrar un par de tipos: una interfaz y su clase de implementación relacionada. A continuación, cuando se solicita un objeto desde el contenedor de IoC a través de cualquier constructor, solicitar un objeto de un determinado tipo de interfaz. Por ejemplo, en el ejemplo anterior, la última línea indica que, cuando cualquiera de sus constructores tiene una dependencia en IMyCustomRepository (interfaz o abstracción), el contenedor de IoC insertará una instancia de la implementación de MyCustomSQLServerRepository clase.

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a>Uso de la biblioteca de Scrutor para el registro de tipos automática

Al utilizar DI en .NET Core, debe poder examinar un ensamblado y registrar automáticamente sus tipos por convención. Esta característica no está disponible actualmente en ASP.NET Core. Sin embargo, puede usar el [Scrutor](https://github.com/khellang/Scrutor) biblioteca para que. Este enfoque resulta conveniente cuando existen docenas de tipos que tienen que ser registrados en el contenedor de IoC.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Matthew rey. Registro de los servicios con Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)

<!-- -->

-   **Kristian Hellang. Scrutor.** Repositorio de GitHub.
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a>Usa Autofac como un contenedor de IoC

También puede utilizar los contenedores de IoC adicionales y conéctelos a la canalización de ASP.NET Core, como se muestra en la ordenación microservicio en eShopOnContainers, que utiliza [Autofac](https://autofac.org/). Cuando se usa Autofac normalmente registrar los tipos a través de módulos, lo que permite dividir los tipos de registro entre varios archivos, dependiendo de dónde encuentran sus tipos, tal y como podría tener los tipos de aplicaciones distribuidos a través de varias bibliotecas de clases.

Por ejemplo, el siguiente es el [módulo de aplicación de Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) para el [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) proyecto con los tipos que desea insertar.

```csharp
public class ApplicationModule
    :Autofac.Module
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

El proceso de registro y los conceptos son muy similares a la manera en que puede registrar tipos con el contenedor de iOS de ASP.NET Core integrado, pero la sintaxis cuando se usa Autofac es un poco diferente.

En el código de ejemplo se registra la abstracción IOrderRepository junto con la clase de implementación OrderRepository. Esto significa que cada vez que un constructor es declarar una dependencia a través de la abstracción de IOrderRepository o la interfaz, el contenedor de IoC insertará una instancia de la clase OrderRepository.

El tipo de ámbito de la instancia determina cómo se comparte una instancia entre solicitudes para el mismo servicio o dependencia. Cuando se realiza una solicitud para una dependencia, el contenedor de IoC puede devolver lo siguiente:

-   Una sola instancia por ámbito de duración (mencionado en el contenedor de ASP.NET Core IoC como *ámbito*).

-   Una nueva instancia por dependencia (mencionado en el contenedor de ASP.NET Core IoC como *transitorio*).

-   Una única instancia que se comparte entre todos los objetos mediante el contenedor de IoC (mencionado en el contenedor de ASP.NET Core IoC como *singleton*).

#### <a name="additional-resources"></a>Recursos adicionales

-   **Introducción a la inyección de dependencia en ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)

-   **Autofac.** Documentación oficial.
    [*http://docs.autofac.org/en/Latest/*](http://docs.autofac.org/en/latest/)

-   **Cesar de la Torre. Comparar las duraciones de servicio de contenedor de ASP.NET Core IoC con ámbitos de instancia del contenedor de IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="implementing-the-command-and-command-handler-patterns"></a>Implementar los patrones de comando y el controlador de comandos

En el ejemplo de DI a través de constructor que se muestra en la sección anterior, el contenedor de IoC se está insertando repositorios a través de un constructor en una clase. ¿Pero exactamente donde se insertados? En una API Web simple (por ejemplo, el catálogo de microservicio en eShopOnContainers), se insertan en el nivel de controladores MVC, en un constructor de controlador. Sin embargo, en el código inicial de esta sección (el [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) clase del servicio Ordering.API en eShopOnContainers), la inserción de dependencias se realiza a través del constructor de un comando determinado controlador. Permítanos explican qué un controlador de comandos es y por qué desearía utilizarla.

El modelo de comando intrínsecamente está relacionado con el patrón CQRS que se presentó anteriormente en esta guía. CQRS tienen dos lados. La primera área es consultas, mediante consultas simplificadas con el [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, que se ha explicado anteriormente. La segunda área es comandos, que son el punto inicial para las transacciones y el canal de entrada desde el exterior del servicio.

Como se muestra en la figura 9-20, el patrón está basado en acepta comandos en el cliente, procesarlos según las reglas del modelo de dominio y, por último, conservar los Estados con transacciones.

![](./media/image21.png)

**Figura 9-20**. Vista de alto nivel de los comandos o el "lado transaccional" en un patrón CQRS

### <a name="the-command-class"></a>La clase de comando

Un comando es una solicitud para el sistema realizar una acción que cambia el estado del sistema. Comandos son imperativos y se deben procesar de una sola vez.

Puesto que comandos son imperativos, normalmente se denominan con un verbo en el ambiente imperativo (por ejemplo, "crear" o "actualización"), y puede incluir el tipo agregado, como CreateOrderCommand. A diferencia de un evento, un comando no es un hecho en el pasado; es sólo una solicitud y, por tanto, podrá ser denegada.

Comandos pueden originarse desde la interfaz de usuario como resultado de un usuario que inicia una solicitud, o desde un administrador de procesos cuando el Administrador de procesos está dirigiendo un agregado para realizar una acción.

Una característica importante de un comando es que debe procesarse con solo una vez un único receptor. Esto es porque un comando es una sola acción o la transacción que desea realizar en la aplicación. Por ejemplo, el mismo comando de creación de orden no debe procesarse más de una vez. Se trata de una diferencia importante entre los comandos y eventos. Los eventos se pueden procesar varias veces, dado que muchos sistemas o microservicios podrían estar interesados en el evento.

Además, es importante que se procesa un comando solo una vez en caso de que el comando no es idempotente. Un comando es idempotente si se puede ejecutar varias veces sin cambiar el resultado, ya sea debido a la naturaleza del comando, o debido al modo en que el sistema controla el comando.

Es una buena práctica para hacer que sus comandos y actualiza idempotente cuando tiene sentido en las reglas de negocios de su dominio e invariables. Por ejemplo, para usar el mismo ejemplo, si por algún motivo (lógica de reintento, piratería, etc.) del mismo comando CreateOrder alcanza su sistema varias veces, puede identificarlo y asegurarse de que no se creen varios pedidos. Para ello, debe adjuntar algún tipo de identidad en las operaciones e identificar si ya se está procesando el comando o la actualización.

Enviar un comando a un receptor único; no publique un comando. La publicación es para los eventos de integración que notifican un hecho: algo ha sucedido y podría ser interesante para los receptores de eventos. En el caso de eventos, produce sin preocupaciones sobre qué destinatarios obtengan el evento o las acciones que realizan en el publicador. Pero los sucesos de integración son algo diferente que ya se introdujeron en las secciones anteriores.

Un comando se implementa con una clase que contiene campos de datos o colecciones con toda la información que se necesita para ejecutar este comando. Un comando es un tipo especial de datos transferir objetos (DTO), que se utiliza específicamente para solicitar cambios o transacciones. Se basa en el propio comando exactamente la información que se necesita para procesar el comando y nada más.

En el ejemplo siguiente se muestra la clase CreateOrderCommand simplificada. Se trata de un comando inmutable que se usa en la ordenación microservicio en eShopOnContainers.

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
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

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
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

Básicamente, la clase de comando contiene todos los datos que necesita para llevar a cabo una transacción empresarial mediante el uso de los objetos de modelo de dominio. Por lo tanto, los comandos son simplemente las estructuras de datos que contienen datos de solo lectura y ningún comportamiento. El nombre del comando indica su propósito. En muchos lenguajes como C\#, comandos se representan como clases, pero no son clases true en el sentido real orientado a objetos.

Como una característica adicional, los comandos son inmutables, dado que el uso esperado es que se procesan directamente por el modelo de dominio. No deben cambiar durante su duración prevista. En una C\# (clase), será posible inmutabilidad al no tener los establecedores u otros métodos que cambian el estado interno.

Por ejemplo, la clase de comando para crear un pedido probablemente es similar en cuanto a datos en el orden que desee para crear, pero probable que no necesitan los mismos atributos. Por ejemplo, CreateOrderCommand no tiene un identificador de pedido, porque el pedido aún no se ha creado.

Muchas clases de comando pueden ser simples, que requiere solo unos cuantos campos sobre algún estado, que debe cambiarse. Que sería el caso si solo va a cambiar el estado de un pedido "en proceso" a "pago" o "enviado" con un comando similar al siguiente:

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

Algunos desarrolladores sus objetos de solicitud de interfaz de usuario independiente de sus dto de comando, pero es simplemente una cuestión de preferencia. Es una separación tediosa con no un gran valor añadido, y los objetos son casi exactamente de la misma forma. Por ejemplo, en eShopOnContainers, los comandos proceden directamente desde el lado del cliente.

### <a name="the-command-handler-class"></a>La clase de controlador de comandos.

Debe implementar una clase de controlador de comandos específicos para cada comando. Es cómo funciona el patrón, y es donde usará el objeto de comando, los objetos de dominio y los objetos del repositorio de infraestructura. De hecho, el controlador de comandos es el núcleo de la capa de aplicación en cuanto a CQRS y DDD. Sin embargo, toda la lógica del dominio debe estar dentro de las clases de dominio, dentro de las raíces agregadas (entidades raíz), las entidades secundarias, o [los servicios de dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), pero no en el controlador de comandos, que es una clase de la aplicación capa.

Un controlador de comandos recibe un comando y obtiene un resultado de la función de agregado que se utiliza. El resultado debe ser la ejecución correcta del comando, o bien una excepción. En el caso de una excepción, el estado del sistema debe ser sin cambios.

Normalmente, el controlador de comandos realiza los pasos siguientes:

-   Recibe el objeto de comando, como un DTO (desde el [mediador](https://en.wikipedia.org/wiki/Mediator_pattern) u otro objeto de infraestructura).

-   Valida que el comando es válido (si no valida el mediador).

-   Crea una instancia de la instancia raíz agregada que es el destino del comando actual.

-   El método ejecuta en la instancia raíz agregada, obtener los datos necesarios del comando.

-   Conserva el nuevo estado del agregado a su base de datos relacionada. Esta última operación es la transacción real.

Normalmente, un controlador de comandos afecta a un único agregado controlado por su raíz agregada (entidad raíz). Si varios agregados deberían verse afectados por la recepción de un único comando, podría utilizar eventos de dominio propague Estados o acciones a través de varios agregados

La cuestión importante aquí es que cuando se procesa un comando, toda la lógica del dominio debe ser dentro del modelo de dominio (agregados), completamente encapsulado y listo para las pruebas unitarias. El controlador de comandos solo actúa como una manera de obtener el modelo de dominio de la base de datos y como último paso, para indicar el nivel de infraestructura (repositorios) para conservar los cambios cuando se cambia el modelo. La ventaja de este enfoque es que la lógica del dominio en un modelo de dominio aislado, completamente encapsulado, enriquecida, comportamiento, puede refactorizar sin cambiar el código de la aplicación o capas de infraestructura, que son el nivel de establecimiento (controladores de comandos, la API Web, repositorios, etcetera).

Al llegar a controladores de comandos complejos, con demasiada lógica, que puede ser un olor de código. Revisarlos y, si encuentra lógica del dominio, refactorizar el código para mover ese comportamiento de dominio a los métodos de los objetos de dominio (el agregado raíz y secundario entidad).

Como ejemplo de una clase de controlador de comandos, el código siguiente muestra la misma clase CreateOrderCommandHandler que vio al principio de este capítulo. En este caso hemos resaltado el método Handle y las operaciones con los objetos del modelo de dominio/agregados.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

Estos son los pasos adicionales que debe tener un controlador de comandos:

-   Usar datos del comando para que funcione con métodos y el comportamiento de la raíz agregada.

-   Internamente dentro de los objetos de dominio, si se producen eventos de dominio mientras se ejecuta la transacción, pero que es transparente desde un punto de vista de comando controlador.

-   Si el resultado de la operación de agregado es correcta y una vez finalizada la transacción, genera el controlador de comandos de eventos de integración. (Estos también se podrían generar clases de infraestructura como repositorios.)

#### <a name="additional-resources"></a>Recursos adicionales

-   **Mark Seemann. En los límites, las aplicaciones están orientados a objetos no**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, orientados a ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)

-   **Comandos y eventos de**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)

-   **¿Qué hace el controlador de comandos? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)

-   **Jimmy Bogard. Patrones de comando de dominio: controladores**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)

-   **Jimmy Bogard. Patrones de comando de dominio: validación**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>La canalización del proceso de comando: cómo desencadenar un controlador de comandos.

La siguiente pregunta es cómo invocar un controlador de comandos. Se podría llamar manualmente desde cada controlador de ASP.NET Core relacionado. Sin embargo, el enfoque sería demasiado acoplado y no es lo ideal.

Las otras dos opciones principales, que son las opciones recomendadas, son:

-   A través de un artefacto de patrón de mediador en memoria.

-   Con una cola de mensajes asincrónicos, entre los controladores y los controladores.

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Mediante el patrón de mediador (en memoria) en la canalización de comandos

Como se muestra en la figura 9-21, en un enfoque CQRS utilizará un mediador inteligente, similar a un bus de memoria, que es lo suficientemente inteligente como para redirigir al controlador de comando correcta según el tipo del comando o DTO recibe. Las flechas de color negras únicas entre los componentes representan las dependencias entre objetos (en muchos casos, insertados mediante DI) con sus interacciones relacionadas.

![](./media/image22.png)

**Figura 9-21**. Mediante el patrón de mediador en curso en un único microservicio CQRS

Motivo por el que se relacione con el patrón de mediador es que en las aplicaciones empresariales, las solicitudes de procesamiento pueden resultar complicadas. Desea poder agregar un número abierto de preocupaciones transversales como registro, validaciones, auditoría y seguridad. En estos casos, puede basarse en una canalización de mediador (vea [patrón mediador](https://en.wikipedia.org/wiki/Mediator_pattern)) para proporcionar un medio de estos comportamientos adicionales o preocupaciones transversales.

Un mediador es un objeto que encapsula el "cómo" de este proceso: coordina basada en estado de ejecución, se invoca la forma en que un controlador de comandos o la carga de proporcionar al controlador. Con un componente de mediador puede aplicar preocupaciones transversales de forma centralizada y transparente aplicando decoradores (o [comportamientos de canalización](https://github.com/jbogard/MediatR/wiki/Behaviors) desde mediador v3). (Para obtener más información, consulte el [patrón Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)

Decoradores y comportamientos son similares a [de programación orientada a aspectos (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), solo se aplica a una canalización de proceso específico administrada por el componente de mediador. Se aplican en función de aspectos en AOP que implementan preocupaciones transversales *Tejedores aspecto* insertado en tiempo de compilación o en función de intercepción de llamada de objeto. A veces se dice que ambos enfoques típicos de AOP funcionan "como"mágica", porque no es fácil ver cómo AOP realice su trabajo. Cuando se trabaja con graves problemas o errores, AOP puede ser difícil de depurar. Por otro lado, estos comportamientos de decoradores son explícita aplicada únicamente en el contexto de mediador, por lo que la depuración es mucho más sencillo y predecible.

Por ejemplo, en eShopOnContainers microservicio de ordenación, se implementan dos decoradores de ejemplo, un [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) clase y un [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) clase. Implementación del decorador se explica en la sección siguiente. Tenga en cuenta que en una versión futura, eShopOnContainers va a migrar a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) y mover a [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) en lugar de usar decoradores.

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a>Uso de colas de mensajes (fuera de proceso) de canalización del comando

Otra opción consiste en utilizar asincrónicos mensajes basados en los agentes o colas de mensajes, como se muestra en la figura 9-22. Esta opción también se pueden combinar con el componente de mediador justo antes que el controlador de comandos.

![](./media/image23.png)

**Figura 9-22**. Uso de las colas de mensajes (fuera de proceso y la comunicación entre procesos) con comandos CQRS

Mediante mensaje de colas para aceptar que los comandos pueden más complican la canalización del comando, ya que probablemente necesitará dividir la canalización en dos procesos conectados a través de la cola de mensajes externo. No obstante, debe usarse si necesita ofrecer mayor escalabilidad y rendimiento en comparación con la mensajería asincrónica. Tenga en cuenta que en el caso de la figura 9-22, el controlador simplemente envía el mensaje de comando en la cola y se devuelve. A continuación, los controladores de comando procesan los mensajes a su propio ritmo. Es decir, un gran ventaja de colas, la cola de mensajes puede actuar como un búfer en casos cuando hyper escalabilidad es necesario, como las existencias o cualquier otro escenario con un gran volumen de datos de entrada.

Sin embargo, debido a la naturaleza asincrónica de las colas de mensajes, debe saber cómo comunicarse con la aplicación cliente sobre el éxito o error del proceso del comando. Como norma, nunca debería utilizar los comandos de "desencadenar y omitir". Cada aplicación empresarial necesita saber si un comando se ha procesado correctamente, o al menos valido y aceptado.

De este modo, poder responder al cliente después de validar un mensaje de comando que se envió a una cola asincrónica agrega complejidad al sistema, en comparación con un proceso de comando de proceso que devuelve el resultado de la operación después de ejecutar la transacción. Uso de colas, deberá devolver el resultado del proceso de comando a través de otros mensajes de resultado de la operación, lo que requiere comunicación personalizada y componentes adicionales en el sistema.

Además, comandos asincrónicos son comandos unidireccionales, que, en muchos casos, quizás no sea necesario, tal y como se explica en el siguiente intercambio interesante entre Burtsev Alexey y Greg Young en un [conversación en línea](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

\[Burtsev Alexey\] encontrar una gran cantidad de código que los usuarios utilicen async gestión de comandos o un comando de una manera de mensajería sin ningún motivo para hacerlo (que no están haciendo una operación larga, no se ejecutan código asincrónico externo, que no crucen incluso aplicación límite de la utilización de bus de mensajes). ¿Por qué agrega esta complejidad innecesaria? Y, en realidad, no he visto un ejemplo de código CQRS con controladores de comandos de bloqueo hasta ahora, aunque funcionará correctamente en la mayoría de los casos.

\[Greg Young\] \[... \] no existe un comando asincrónico; es realmente otro evento. Si debe aceptar lo que me envíe y genera un evento si no acepto, ya no es que me pide que realizar alguna acción. Se trata de usted dice que algo se ha realizado. Esto parece ser una pequeña diferencia en un primer momento, pero tiene muchas implicaciones.

Comandos asincrónicos aumentan en gran medida la complejidad de un sistema, porque no hay ninguna manera sencilla para indicar errores. Por lo tanto, comandos asincrónicos no se recomiendan distinto cuando se necesitan requisitos de escala o en casos especiales cuando se comunica el microservicios interno a través de mensajería. En esos casos, debe diseñar un sistema independiente de informes y la recuperación de errores.

En la versión inicial de eShopOnContainers, hemos decidido utilizar el procesamiento de comandos sincrónicos, se iniciaron en las solicitudes HTTP y controlado por el patrón de mediador. Fácilmente que permite devolver el éxito o error del proceso, como en el [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementación.

En cualquier caso, debe ser una decisión basada en los requisitos empresariales de su aplicación o de microservicio.

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementar la canalización del proceso de comando con un patrón de mediador (MediatR)

Como una implementación de ejemplo, esta guía propone mediante la canalización de proceso basado en el patrón de mediador para ingesta de comando de unidad y enrutarlos, en memoria, los controladores de comando correcta. La guía también propone aplicar decoradores o [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) para separar los problemas de corte del cruce.

Para la implementación en .NET Core, hay varias bibliotecas de código abierto disponibles que implementan el patrón de mediador. La biblioteca utilizada en esta guía es la [MediatR](https://github.com/jbogard/MediatR) biblioteca de código abierto (creado por Jimmy Bogard), pero puede usar otro enfoque. MediatR es una biblioteca pequeña y simple que permite procesar mensajes en la memoria como un comando, al aplicar decoradores o comportamientos.

Mediante el patrón de mediador le ayuda a reducir el acoplamiento y para aislar los problemas del trabajo solicitado, mientras se conecta automáticamente al controlador que lleva a cabo ese trabajo, en este caso, para controladores de comandos.

Otra buena razón para utilizar el patrón de mediador se explica mediante Jimmy Bogard al revisar a esta guía:

Creo que es posible que vale la pena mencionar aquí pruebas: proporciona una ventana coherente "nice" en el comportamiento del sistema. Solicitud, respuesta de salida. Hemos encontrado ese aspecto muy valioso en edificio que se comporta de forma coherente las pruebas.

En primer lugar, permítanos echar un vistazo al código de controlador donde realmente utilizaría el objeto mediador. Si no se usa el objeto mediador, necesitará insertar todas las dependencias para ese controlador cosas como un objeto de registrador y otros. Por lo tanto, el constructor sería bastante complicado. Por otro lado, si utiliza el objeto mediador, el constructor del controlador de puede ser mucho más sencillo, con unos pocos dependencias en lugar de muchas dependencias que tendría si hubiera uno por cada operación de corte del cruce, como en el ejemplo siguiente:

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

Puede ver que el mediador proporciona un constructor de controlador de API Web limpio y eficiente. Además, dentro de los métodos de controlador, el código para enviar un comando al objeto mediador es prácticamente una línea:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

En orden para MediatR ser consciente de las clases de controlador de comandos, debe registrar las clases de mediador y las clases de controlador de comandos en el contenedor de IoC. De forma predeterminada, MediatR utiliza Autofac como el contenedor de IoC, pero también puede usar el contenedor de ASP.NET Core IoC integrado o cualquier otro contenedor compatible con MediatR.

El código siguiente muestra cómo registrar los tipos y los comandos del mediador al utilizar los módulos de Autofac.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

Dado que cada controlador de comandos implementa la interfaz con IAsyncRequestHandler genérico&lt;T&gt; y, a continuación, se inspecciona el RegisteredAssemblyTypes de objeto, el controlador es capaz de relacionar cada comando con su controlador de comandos, ya que relación se indica en la clase CommandHandler, como en el ejemplo siguiente:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Éste es el código que se correlacionan comandos con controladores de comandos. El controlador es simplemente una clase simple, pero hereda de RequestHandler&lt;T&gt;, y MediatR se asegura de se invoca con la carga correcta.

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a>Aplicar preocupaciones transversales al procesar comandos con los patrones de mediador y decorador

Hay otra cosa: poder transversales preocupaciones se aplican a la canalización de mediador. También puede ver al final del código del módulo de registro de Autofac cómo se está registrando un decorador escribe, en concreto, una clase LogDecorator personalizada.

De nuevo, tenga en cuenta que una versión futura de eShopOnContainers migrará a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) y mover a [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) en lugar de usar decoradores.

Que [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) clase puede implementarse como el código siguiente, que registra información sobre el controlador de comandos que se está ejecutando y si se realizó correctamente o no.

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

Implementando esta clase decorador y decorando la canalización con él, todos los comandos que se procesan a través de MediatR iniciará sesión información sobre la ejecución.

El eShopOnContainers orden microservicio también aplica un segundo decorador para validaciones básicas, el [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) clase que se basa en el [FluentValidation](https://github.com/JeremySkinner/FluentValidation) biblioteca, como se muestra en el código siguiente:

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

A continuación, según la [FluentValidation](https://github.com/JeremySkinner/FluentValidation) biblioteca, hemos creado la validación de los datos pasados con CreateOrderCommand, como se muestra en el código siguiente:

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
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
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

Puede crear validaciones adicionales. Se trata de una forma muy limpia y elegante para implementar sus validaciones de comando.

De forma similar, podría implementar otras decoradores para aspectos adicionales o preocupaciones transversales que desea aplicar a los comandos cuando su administración.

#### <a name="additional-resources"></a>Recursos adicionales

##### <a name="the-mediator-pattern"></a>El patrón de mediador

-   **Patrón de mediador**
    [*https://en.wikipedia.org/wiki/Mediator\_patrón*](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>El patrón de decorador

-   **Patrón de decorador**
    [*https://en.wikipedia.org/wiki/Decorator\_patrón*](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

-   **MediatR.** Repositorio de GitHub.
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   **CQRS con MediatR y AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)

-   **Poner los controladores en una alimentación: entradas y comandos. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)

-   **Abordar problemas de corte del cruce con una canalización mediador**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)

-   **CQRS y REST: la coincidencia exacta**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)

-   **Ejemplos de canalización MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)

-   **Accesorios de prueba de segmento vertical para MediatR y ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*

-   **MediatR extensiones para la inyección de dependencia de Microsoft publicado**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)

##### <a name="fluent-validation"></a>Validación fluida

-   **Jeremy Skinner. FluentValidation.** Repositorio de GitHub.
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
[Anterior] (microservice-application-layer-web-api-design.md) [siguiente] (.. /Implement-Resilient-Applications/Index.MD)
