---
title: Implementación del nivel de aplicación de microservicios mediante la API web
description: Comprenda los procesos de inserción de dependencias y los patrones de mediador y sus detalles de implementación en la capa de aplicación de la API web.
ms.date: 08/17/2020
ms.openlocfilehash: 56d4eecb2831a57460b01ff4da8150d6dcce5bc5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173424"
---
# <a name="implement-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="80bb5-103">Implementación del nivel de aplicación de microservicios mediante la API web</span><span class="sxs-lookup"><span data-stu-id="80bb5-103">Implement the microservice application layer using the Web API</span></span>

## <a name="use-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="80bb5-104">Uso de la inserción de dependencias para insertar objetos de la infraestructura en el nivel de aplicación</span><span class="sxs-lookup"><span data-stu-id="80bb5-104">Use Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="80bb5-105">Como se ha mencionado anteriormente, el nivel de aplicación se puede implementar como parte del artefacto (ensamblado) que se está creando, por ejemplo, dentro de un proyecto de API web o de aplicación web MVC.</span><span class="sxs-lookup"><span data-stu-id="80bb5-105">As mentioned previously, the application layer can be implemented as part of the artifact (assembly) you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="80bb5-106">En el caso de un microservicio compilado con ASP.NET Core, el nivel de aplicación normalmente será la biblioteca de API web.</span><span class="sxs-lookup"><span data-stu-id="80bb5-106">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="80bb5-107">Si quiere separar lo que proviene de ASP.NET Core (su infraestructura y los controladores) del código de nivel de aplicación personalizado, también puede colocar el nivel de aplicación en una biblioteca de clases independiente, pero es algo opcional.</span><span class="sxs-lookup"><span data-stu-id="80bb5-107">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="80bb5-108">Por ejemplo, el código de nivel de aplicación del microservicio de pedidos se implementa directamente como parte del proyecto **Ordering.API** (un proyecto de API web de ASP.NET Core), como se muestra en la figura 7-23.</span><span class="sxs-lookup"><span data-stu-id="80bb5-108">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 7-23.</span></span>

:::image type="complex" source="./media/microservice-application-layer-implementation-web-api/ordering-api-microservice.png" alt-text="Captura de pantalla del microservicio Ordering.API en el Explorador de soluciones.":::
<span data-ttu-id="80bb5-110">Vista del Explorador de soluciones del microservicio Ordering.API que muestra las subcarpetas de la carpeta Application: Behaviors, Commands, DomainEventHandlers, IntegrationEvents, Models, Queries y Validations.</span><span class="sxs-lookup"><span data-stu-id="80bb5-110">The Solution Explorer view of the Ordering.API microservice, showing the subfolders under the Application folder: Behaviors, Commands, DomainEventHandlers, IntegrationEvents, Models, Queries, and Validations.</span></span>
:::image-end:::

<span data-ttu-id="80bb5-111">**Figura 7-23.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-111">**Figure 7-23**.</span></span> <span data-ttu-id="80bb5-112">Nivel de aplicación en el proyecto de API web de ASP.NET Core Ordering.API</span><span class="sxs-lookup"><span data-stu-id="80bb5-112">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="80bb5-113">En ASP.NET Core se incluye un simple [contenedor de IoC integrado](/aspnet/core/fundamentals/dependency-injection) (representado por la interfaz IServiceProvider) que admite la inserción de constructores de forma predeterminada, y ASP.NET hace que determinados servicios estén disponibles a través de DI.</span><span class="sxs-lookup"><span data-stu-id="80bb5-113">ASP.NET Core includes a simple [built-in IoC container](/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="80bb5-114">En ASP.NET Core se usa el término *servicio* para cualquiera de los tipos que se registran para la inserción mediante DI.</span><span class="sxs-lookup"><span data-stu-id="80bb5-114">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="80bb5-115">Los servicios del contenedor integrado se configuran en el método ConfigureServices de la clase Startup de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="80bb5-115">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="80bb5-116">Las dependencias se implementan en los servicios que un tipo necesita y que se registran en el contenedor IoC.</span><span class="sxs-lookup"><span data-stu-id="80bb5-116">Your dependencies are implemented in the services that a type needs and that you register in the IoC container.</span></span>

<span data-ttu-id="80bb5-117">Normalmente, le interesará insertar dependencias que implementen objetos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="80bb5-117">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="80bb5-118">Una dependencia habitual para insertar es un repositorio.</span><span class="sxs-lookup"><span data-stu-id="80bb5-118">A typical dependency to inject is a repository.</span></span> <span data-ttu-id="80bb5-119">Pero también podría insertar cualquier otra dependencia de infraestructura que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="80bb5-119">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="80bb5-120">Para las implementaciones más sencillas, también podría insertar directamente el objeto de patrón de unidades de trabajo (el objeto DbContext de EF), porque DBContext también es la implementación de los objetos de persistencia de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="80bb5-120">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="80bb5-121">En el ejemplo siguiente, puede ver cómo .NET Core inserta los objetos de repositorio necesarios a través del constructor.</span><span class="sxs-lookup"><span data-stu-id="80bb5-121">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="80bb5-122">La clase es un controlador de comandos, que se explica en esta sección.</span><span class="sxs-lookup"><span data-stu-id="80bb5-122">The class is a command handler, which will get covered in the next section.</span></span>

```csharp
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}

```

<span data-ttu-id="80bb5-123">En la clase se usan los repositorios insertados para ejecutar la transacción y conservar los cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-123">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="80bb5-124">No importa si esa clase es un controlador de comandos, un método de controlador de API web de ASP.NET Core, o un [servicio de aplicación DDD](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="80bb5-124">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="80bb5-125">En última instancia, es una clase simple que usa repositorios, entidades de dominio y otra coordinación de aplicaciones de forma similar a un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-125">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="80bb5-126">La inserción de dependencias funciona igual en todas las clases mencionadas, como en el ejemplo de uso de DI según el constructor.</span><span class="sxs-lookup"><span data-stu-id="80bb5-126">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="register-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="80bb5-127">Registro de los tipos de implementación de dependencias e interfaces o abstracciones</span><span class="sxs-lookup"><span data-stu-id="80bb5-127">Register the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="80bb5-128">Antes de usar los objetos insertados mediante constructores, debe saber dónde registrar las interfaces y clases que generan los objetos que se insertan en las clases de aplicación a través de DI.</span><span class="sxs-lookup"><span data-stu-id="80bb5-128">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="80bb5-129">(Como la inserción de dependencias basada en el constructor, tal y como se mostró anteriormente).</span><span class="sxs-lookup"><span data-stu-id="80bb5-129">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="use-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="80bb5-130">Uso del contenedor de IoC integrado proporcionado por ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="80bb5-130">Use the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="80bb5-131">Cuando use el contenedor de IoC integrado proporcionado por ASP.NET Core, registre los tipos que quiera insertar en el método ConfigureServices del archivo Startup.cs, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-131">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

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

<span data-ttu-id="80bb5-132">El modelo más común al registrar los tipos en un contenedor de IoC es registrar un par de tipos: una interfaz y su clase de implementación relacionada.</span><span class="sxs-lookup"><span data-stu-id="80bb5-132">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="80bb5-133">Después, cuando se solicita un objeto del contenedor de IoC a través de cualquier constructor, se solicita un objeto de un tipo de interfaz determinado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-133">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="80bb5-134">En el ejemplo anterior, la última línea indica que, cuando cualquiera de los constructores tiene una dependencia de IMyCustomRepository (interfaz o abstracción), el contenedor de IoC insertará una instancia de la clase de implementación MyCustomSQLServerRepository.</span><span class="sxs-lookup"><span data-stu-id="80bb5-134">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="use-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="80bb5-135">Uso de la biblioteca Scrutor para el registro de tipos automático</span><span class="sxs-lookup"><span data-stu-id="80bb5-135">Use the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="80bb5-136">Al usar DI en .NET Core, es posible que le interese poder examinar un ensamblado y registrar sus tipos de manera automática por convención.</span><span class="sxs-lookup"><span data-stu-id="80bb5-136">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="80bb5-137">Actualmente, esta característica no está disponible en ASP.NET Core,</span><span class="sxs-lookup"><span data-stu-id="80bb5-137">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="80bb5-138">pero puede usar la biblioteca [Scrutor](https://github.com/khellang/Scrutor) para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-138">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="80bb5-139">Este enfoque resulta conveniente cuando existen docenas de tipos que deben registrarse en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="80bb5-139">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="80bb5-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="80bb5-140">Additional resources</span></span>

- <span data-ttu-id="80bb5-141">**Matthew King. Registering services with Scrutor** (Registro de servicios con Scrutor) </span><span class="sxs-lookup"><span data-stu-id="80bb5-141">**Matthew King. Registering services with Scrutor** </span></span>\
  <https://www.mking.net/blog/registering-services-with-scrutor>

- <span data-ttu-id="80bb5-142">**Kristian Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-142">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="80bb5-143">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="80bb5-143">GitHub repo.</span></span> \
  <https://github.com/khellang/Scrutor>

#### <a name="use-autofac-as-an-ioc-container"></a><span data-ttu-id="80bb5-144">Uso de Autofac como un contenedor de IoC</span><span class="sxs-lookup"><span data-stu-id="80bb5-144">Use Autofac as an IoC container</span></span>

<span data-ttu-id="80bb5-145">También se pueden usar contenedores de IoC adicionales y conectarlos a la canalización de ASP.NET Core, como se muestra en el microservicio de pedidos en eShopOnContainers, donde se usa [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="80bb5-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="80bb5-146">Cuando se usa Autofac normalmente los tipos se registran a través de módulos, lo que permite dividir los tipos de registro entre varios archivos, en función de dónde se encuentren los tipos, al igual que los tipos de aplicaciones podrían estar distribuidos entre varias bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="80bb5-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="80bb5-147">Por ejemplo, el siguiente es el [módulo de aplicación de Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) para el proyecto de [API web Ordering.API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) con los tipos que se quieren insertar.</span><span class="sxs-lookup"><span data-stu-id="80bb5-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

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

<span data-ttu-id="80bb5-148">Autofac también tiene una característica para [analizar ensamblados y registrar tipos por convenciones de nombre](https://autofac.readthedocs.io/en/latest/register/scanning.html).</span><span class="sxs-lookup"><span data-stu-id="80bb5-148">Autofac also has a feature to [scan assemblies and register types by name conventions](https://autofac.readthedocs.io/en/latest/register/scanning.html).</span></span>

<span data-ttu-id="80bb5-149">El proceso de registro y los conceptos son muy similares a la manera en que se pueden registrar tipos con el contenedor integrado de IoC de ASP.NET Core, pero cuando se usa Autofac la sintaxis es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-149">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core IoC container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="80bb5-150">En el código de ejemplo, la abstracción IOrderRepository se registra junto con la clase de implementación OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="80bb5-150">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="80bb5-151">Esto significa que cada vez que un constructor declare una dependencia a través de la abstracción o la interfaz IOrderRepository, el contenedor de IoC insertará una instancia de la clase OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="80bb5-151">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="80bb5-152">El tipo de ámbito de la instancia determina cómo se comparte una instancia entre las solicitudes del mismo servicio o dependencia.</span><span class="sxs-lookup"><span data-stu-id="80bb5-152">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="80bb5-153">Cuando se realiza una solicitud de una dependencia, el contenedor de IoC puede devolver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-153">When a request is made for a dependency, the IoC container can return the following:</span></span>

- <span data-ttu-id="80bb5-154">Una sola instancia por ámbito de duración (denominada *con ámbito* en el contenedor de IoC de ASP.NET Core).</span><span class="sxs-lookup"><span data-stu-id="80bb5-154">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

- <span data-ttu-id="80bb5-155">Una nueva instancia por dependencia (denominada *transitoria* en el contenedor de IoC de ASP.NET Core).</span><span class="sxs-lookup"><span data-stu-id="80bb5-155">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

- <span data-ttu-id="80bb5-156">Una única instancia que se comparte entre todos los objetos que usan el contenedor de IoC (denominada *singleton* en el contenedor de IoC de ASP.NET Core).</span><span class="sxs-lookup"><span data-stu-id="80bb5-156">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="80bb5-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="80bb5-157">Additional resources</span></span>

- <span data-ttu-id="80bb5-158">**Introduction to Dependency Injection in ASP.NET Core** (Introducción a la inserción de dependencias en ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="80bb5-158">**Introduction to Dependency Injection in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection](/aspnet/core/fundamentals/dependency-injection)

- <span data-ttu-id="80bb5-159">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-159">**Autofac.**</span></span> <span data-ttu-id="80bb5-160">Documentación oficial.</span><span class="sxs-lookup"><span data-stu-id="80bb5-160">Official documentation.</span></span> \
  <https://docs.autofac.org/en/latest/>

- <span data-ttu-id="80bb5-161">**Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes** (Comparación de las duraciones de servicio del contenedor IoC de ASP.NET Core con ámbitos de instancia de contenedor Autofac IoC) - Cesar de la Torre.</span><span class="sxs-lookup"><span data-stu-id="80bb5-161">**Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes - Cesar de la Torre.**</span></span> \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="implement-the-command-and-command-handler-patterns"></a><span data-ttu-id="80bb5-162">Implementación de los patrones de comando y controlador de comandos</span><span class="sxs-lookup"><span data-stu-id="80bb5-162">Implement the Command and Command Handler patterns</span></span>

<span data-ttu-id="80bb5-163">En el ejemplo de DI a través del constructor mostrado en la sección anterior, el contenedor de IoC insertaba repositorios a través de un constructor en una clase.</span><span class="sxs-lookup"><span data-stu-id="80bb5-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="80bb5-164">¿Pero exactamente dónde se insertaban?</span><span class="sxs-lookup"><span data-stu-id="80bb5-164">But exactly where were they injected?</span></span> <span data-ttu-id="80bb5-165">En una API web simple (por ejemplo, el microservicio de catálogo de eShopOnContainers), se insertan en el nivel de controladores de MVC, en un constructor de controlador, como parte de la canalización de solicitud de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="80bb5-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers' level, in a controller constructor, as part of the request pipeline of ASP.NET Core.</span></span> <span data-ttu-id="80bb5-166">Pero en el código inicial de esta sección (la clase [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) del servicio Ordering.API en eShopOnContainers), la inserción de dependencias se realiza a través del constructor de un determinado controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="80bb5-167">Vamos a explicar qué es un controlador de comandos y por qué le interesaría usarlo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="80bb5-168">El patrón de comandos está intrínsecamente relacionado con el patrón CQRS que se presentó anteriormente en esta guía.</span><span class="sxs-lookup"><span data-stu-id="80bb5-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="80bb5-169">CQRS tiene dos lados.</span><span class="sxs-lookup"><span data-stu-id="80bb5-169">CQRS has two sides.</span></span> <span data-ttu-id="80bb5-170">La primera área son las consultas, mediante consultas simplificadas con el micro-ORM [Dapper](https://github.com/StackExchange/dapper-dot-net), que se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="80bb5-171">La segunda área son los comandos, el punto inicial para las transacciones y el canal de entrada desde el exterior del servicio.</span><span class="sxs-lookup"><span data-stu-id="80bb5-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="80bb5-172">Como se muestra en la figura 7-24, el patrón se basa en la aceptación de comandos del lado cliente, su procesamiento según las reglas del modelo de dominio y, por último, la conservación de los estados con transacciones.</span><span class="sxs-lookup"><span data-stu-id="80bb5-172">As shown in Figure 7-24, the pattern is based on accepting commands from the client-side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![Diagrama que muestra el flujo de datos general del cliente a la base de datos.](./media/microservice-application-layer-implementation-web-api/high-level-writes-side.png)

<span data-ttu-id="80bb5-174">**Figura 7-24.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-174">**Figure 7-24**.</span></span> <span data-ttu-id="80bb5-175">Vista general de los comandos o el "lado transaccional" en un patrón CQRS</span><span class="sxs-lookup"><span data-stu-id="80bb5-175">High-level view of the commands or "transactional side" in a CQRS pattern</span></span>

<span data-ttu-id="80bb5-176">En la figura 7-24 se muestra que la aplicación de interfaz de usuario envía un comando a través de la API que llega a un elemento `CommandHandler`, que depende del modelo de dominio y de la infraestructura para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-176">Figure 7-24 shows that the UI app sends a command through the API that gets to a `CommandHandler`, that depends on the Domain model and the Infrastructure, to update the database.</span></span>

### <a name="the-command-class"></a><span data-ttu-id="80bb5-177">La clase de comando</span><span class="sxs-lookup"><span data-stu-id="80bb5-177">The command class</span></span>

<span data-ttu-id="80bb5-178">Un comando es una solicitud para que el sistema realice una acción que cambia el estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="80bb5-178">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="80bb5-179">Los comandos son imperativos y se deben procesar una sola vez.</span><span class="sxs-lookup"><span data-stu-id="80bb5-179">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="80bb5-180">Como los comandos son imperativos, normalmente se denominan con un verbo en modo imperativo (por ejemplo, "create" o "update"), y es posible que incluyan el tipo agregado, como CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="80bb5-180">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="80bb5-181">A diferencia de un evento, un comando no es un hecho del pasado; es solo una solicitud y, por tanto, se puede denegar.</span><span class="sxs-lookup"><span data-stu-id="80bb5-181">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="80bb5-182">Los comandos se pueden originar desde la interfaz de usuario como resultado de un usuario que inicia una solicitud, o desde un administrador de procesos cuando está dirigiendo un agregado para realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="80bb5-182">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="80bb5-183">Una característica importante de un comando es que debe procesarse una sola vez por un único receptor.</span><span class="sxs-lookup"><span data-stu-id="80bb5-183">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="80bb5-184">Esto se debe a que un comando es una única acción o transacción que se quiere realizar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="80bb5-184">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="80bb5-185">Por ejemplo, el mismo comando de creación de pedidos no se debe procesar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="80bb5-185">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="80bb5-186">Se trata de una diferencia importante entre los comandos y los eventos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-186">This is an important difference between commands and events.</span></span> <span data-ttu-id="80bb5-187">Los eventos se pueden procesar varias veces, dado que es posible que muchos sistemas o microservicios estén interesados en el evento.</span><span class="sxs-lookup"><span data-stu-id="80bb5-187">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="80bb5-188">Además, es importante que un comando solo se procese una vez en caso de que no sea idempotente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-188">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="80bb5-189">Un comando es idempotente si se puede ejecutar varias veces sin cambiar el resultado, ya sea debido a la naturaleza del comando, o bien al modo en que el sistema lo controla.</span><span class="sxs-lookup"><span data-stu-id="80bb5-189">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="80bb5-190">Un procedimiento recomendado consiste en hacer que los comandos y las actualizaciones sean idempotentes cuando tenga sentido según las reglas de negocio y los elementos invariables del dominio.</span><span class="sxs-lookup"><span data-stu-id="80bb5-190">It is a good practice to make your commands and updates idempotent when it makes sense under your domain's business rules and invariants.</span></span> <span data-ttu-id="80bb5-191">Para usar el mismo ejemplo, si por algún motivo (lógica de reintento, piratería, etc.) el mismo comando CreateOrder llega varias veces al sistema, debería poder identificarlo y asegurarse de que no se crean varios pedidos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-191">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="80bb5-192">Para ello, debe adjuntar algún tipo de identidad en las operaciones e identificar si el comando o la actualización ya se ha procesado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-192">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="80bb5-193">Un comando se envía a un único receptor; no se publica.</span><span class="sxs-lookup"><span data-stu-id="80bb5-193">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="80bb5-194">La publicación es para los eventos que notifican un hecho: que ha sucedido algo y que podría ser interesante para los receptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-194">Publishing is for events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="80bb5-195">En el caso de los eventos, al publicador no le interesa qué receptores obtienen el evento o las acciones que realizan.</span><span class="sxs-lookup"><span data-stu-id="80bb5-195">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="80bb5-196">Pero los eventos de integración o de dominio son diferentes y ya se presentaron en secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="80bb5-196">But domain or integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="80bb5-197">Un comando se implementa con una clase que contiene campos de datos o colecciones con toda la información necesaria para ejecutar ese comando.</span><span class="sxs-lookup"><span data-stu-id="80bb5-197">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="80bb5-198">Un comando es un tipo especial de objeto de transferencia de datos (DTO), que se usa específicamente para solicitar cambios o transacciones.</span><span class="sxs-lookup"><span data-stu-id="80bb5-198">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="80bb5-199">El propio comando se basa en la información exacta que se necesita para procesar el comando y nada más.</span><span class="sxs-lookup"><span data-stu-id="80bb5-199">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="80bb5-200">En el siguiente ejemplo se muestra la clase `CreateOrderCommand` simplificada.</span><span class="sxs-lookup"><span data-stu-id="80bb5-200">The following example shows the simplified `CreateOrderCommand` class.</span></span> <span data-ttu-id="80bb5-201">Se trata de un comando inmutable que se usa en el microservicio de pedidos de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="80bb5-201">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

```csharp
// DDD and CQRS patterns comment: Note that it is recommended to implement immutable Commands
// In this case, its immutability is achieved by having all the setters as private
// plus only being able to update the data just once, when creating the object through its constructor.
// References on Immutable Commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties

[DataContract]
public class CreateOrderCommand
    : IRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;

    [DataMember]
    public string UserId { get; private set; }

    [DataMember]
    public string UserName { get; private set; }

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

    public CreateOrderCommand(List<BasketItem> basketItems, string userId, string userName, string city, string street, string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = basketItems.ToOrderItemsDTO().ToList();
        UserId = userId;
        UserName = userName;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
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

<span data-ttu-id="80bb5-202">Básicamente, la clase de comando contiene todos los datos que se necesitan para llevar a cabo una transacción empresarial mediante los objetos de modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="80bb5-202">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="80bb5-203">Por tanto, los comandos son simplemente las estructuras de datos que contienen datos de solo lectura y ningún comportamiento.</span><span class="sxs-lookup"><span data-stu-id="80bb5-203">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="80bb5-204">El nombre del comando indica su propósito.</span><span class="sxs-lookup"><span data-stu-id="80bb5-204">The command's name indicates its purpose.</span></span> <span data-ttu-id="80bb5-205">En muchos lenguajes como C#, los comandos se representan como clases, pero no son verdaderas clases en el sentido real orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-205">In many languages like C#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="80bb5-206">Como una característica adicional, los comandos son inmutables, dado que el uso esperado es que el modelo de dominio los procese directamente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-206">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="80bb5-207">No deben cambiar durante su duración prevista.</span><span class="sxs-lookup"><span data-stu-id="80bb5-207">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="80bb5-208">En una clase de C#, se puede lograr la inmutabilidad si no hay establecedores ni otros métodos que cambien el estado interno.</span><span class="sxs-lookup"><span data-stu-id="80bb5-208">In a C# class, immutability can be achieved by not having any setters or other methods that change the internal state.</span></span>

<span data-ttu-id="80bb5-209">Tenga en cuenta que si quiere o espera que los comandos pasen por un proceso de serialización o deserialización, las propiedades deben tener un establecedor privado y el atributo `[DataMember]` (o `[JsonProperty]`).</span><span class="sxs-lookup"><span data-stu-id="80bb5-209">Keep in mind that if you intend or expect commands to go through a serializing/deserializing process, the properties must have a private setter, and the `[DataMember]` (or `[JsonProperty]`) attribute.</span></span> <span data-ttu-id="80bb5-210">De lo contrario, el deserializador no podrá reconstruir el objeto en el destino con los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="80bb5-210">Otherwise, the deserializer won't be able to reconstruct the object at the destination with the required values.</span></span> <span data-ttu-id="80bb5-211">También puede usar propiedades que realmente sean de solo lectura si la clase tiene un constructor con parámetros para todas las propiedades, con la convención de nomenclatura de camelCase habitual, y anotar el constructor como `[JsonConstructor]`.</span><span class="sxs-lookup"><span data-stu-id="80bb5-211">You can also use truly read-only properties if the class has a constructor with parameters for all properties, with the usual camelCase naming convention, and annotate the constructor as `[JsonConstructor]`.</span></span> <span data-ttu-id="80bb5-212">Sin embargo, esta opción requiere más código.</span><span class="sxs-lookup"><span data-stu-id="80bb5-212">However, this option requires more code.</span></span>

<span data-ttu-id="80bb5-213">Por ejemplo, la clase de comando para crear un pedido probablemente sea similar en cuanto a los datos del pedido que se quiere crear, pero es probable que no se necesiten los mismos atributos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-213">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="80bb5-214">Por ejemplo, `CreateOrderCommand` no tiene un identificador de pedido, porque el pedido aún no se ha creado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-214">For instance, `CreateOrderCommand` does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="80bb5-215">Muchas clases de comando pueden ser simples y requerir solo unos cuantos campos sobre algún estado que deba cambiarse.</span><span class="sxs-lookup"><span data-stu-id="80bb5-215">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="80bb5-216">Ese sería el caso si solo se va a cambiar el estado de un pedido de "en proceso" a "pagado" o "enviado" con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-216">That would be the case if you are just changing the status of an order from "in process" to "paid" or "shipped" by using a command similar to the following:</span></span>

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

<span data-ttu-id="80bb5-217">Algunos desarrolladores separan los objetos de solicitud de interfaz de usuario de los DTO de comando, pero es solo una cuestión de preferencia.</span><span class="sxs-lookup"><span data-stu-id="80bb5-217">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="80bb5-218">Es una separación tediosa sin demasiado valor añadido y los objetos tienen prácticamente la misma forma.</span><span class="sxs-lookup"><span data-stu-id="80bb5-218">It is a tedious separation with not much additional value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="80bb5-219">Por ejemplo, en eShopOnContainers, algunos comandos proceden directamente del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-219">For instance, in eShopOnContainers, some commands come directly from the client-side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="80bb5-220">Clase de controlador de comandos</span><span class="sxs-lookup"><span data-stu-id="80bb5-220">The Command handler class</span></span>

<span data-ttu-id="80bb5-221">Debe implementar una clase de controlador de comandos específica para cada comando.</span><span class="sxs-lookup"><span data-stu-id="80bb5-221">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="80bb5-222">Ese es el funcionamiento del patrón y el lugar en el que se usarán el objeto de comando, los objetos de dominio y los objetos de repositorio de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="80bb5-222">That is how the pattern works, and it's where you'll use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="80bb5-223">De hecho, el controlador de comandos es el núcleo del nivel de aplicación en lo que a CQRS y DDD respecta.</span><span class="sxs-lookup"><span data-stu-id="80bb5-223">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="80bb5-224">Sin embargo, toda la lógica del dominio debe incluirse en las clases de dominio, dentro de las raíces agregadas (entidades raíz), las entidades secundarias o [los servicios de dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), pero no en el controlador de comandos, que es una clase del nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="80bb5-224">However, all the domain logic should be contained in the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="80bb5-225">La clase de controlador de comandos ofrece un punto de partida seguro en la forma de lograr el principio de responsabilidad única (SRP) mencionado en una sección anterior.</span><span class="sxs-lookup"><span data-stu-id="80bb5-225">The command handler class offers a strong stepping stone in the way to achieve the Single Responsibility Principle (SRP) mentioned in a previous section.</span></span>

<span data-ttu-id="80bb5-226">Un controlador de comandos recibe un comando y obtiene un resultado del agregado que se usa.</span><span class="sxs-lookup"><span data-stu-id="80bb5-226">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="80bb5-227">El resultado debe ser la ejecución correcta del comando, o bien una excepción.</span><span class="sxs-lookup"><span data-stu-id="80bb5-227">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="80bb5-228">En el caso de una excepción, el estado del sistema no debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="80bb5-228">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="80bb5-229">Normalmente, el controlador de comandos realiza estos pasos:</span><span class="sxs-lookup"><span data-stu-id="80bb5-229">The command handler usually takes the following steps:</span></span>

- <span data-ttu-id="80bb5-230">Recibe el objeto de comando, como un DTO (desde el [mediador](https://en.wikipedia.org/wiki/Mediator_pattern) u otro objeto de infraestructura).</span><span class="sxs-lookup"><span data-stu-id="80bb5-230">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

- <span data-ttu-id="80bb5-231">Valida que el comando sea válido (si no lo hace el mediador).</span><span class="sxs-lookup"><span data-stu-id="80bb5-231">It validates that the command is valid (if not validated by the mediator).</span></span>

- <span data-ttu-id="80bb5-232">Crea una instancia de la instancia de raíz agregada que es el destino del comando actual.</span><span class="sxs-lookup"><span data-stu-id="80bb5-232">It instantiates the aggregate root instance that is the target of the current command.</span></span>

- <span data-ttu-id="80bb5-233">Ejecuta el método en la instancia de raíz agregada y obtiene los datos necesarios del comando.</span><span class="sxs-lookup"><span data-stu-id="80bb5-233">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

- <span data-ttu-id="80bb5-234">Conserva el nuevo estado del agregado en su base de datos relacionada.</span><span class="sxs-lookup"><span data-stu-id="80bb5-234">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="80bb5-235">Esta última operación es la transacción real.</span><span class="sxs-lookup"><span data-stu-id="80bb5-235">This last operation is the actual transaction.</span></span>

<span data-ttu-id="80bb5-236">Normalmente, un controlador de comandos administra un único agregado controlado por su raíz agregada (la entidad raíz).</span><span class="sxs-lookup"><span data-stu-id="80bb5-236">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="80bb5-237">Si varios agregados deben verse afectados por la recepción de un único comando, podría usar eventos de dominio para propagar los estados o las acciones entre varios agregados.</span><span class="sxs-lookup"><span data-stu-id="80bb5-237">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates.</span></span>

<span data-ttu-id="80bb5-238">El aspecto importante aquí es que cuando se procesa un comando, toda la lógica del dominio debe incluirse en el modelo de dominio (los agregados), completamente encapsulada y lista para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="80bb5-238">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="80bb5-239">El controlador de comandos solo actúa como una manera de obtener el modelo de dominio de la base de datos y, como último paso, para indicar al nivel de infraestructura (los repositorios) que conserve los cambios cuando el modelo cambie.</span><span class="sxs-lookup"><span data-stu-id="80bb5-239">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="80bb5-240">La ventaja de este enfoque es que se puede refactorizar la lógica del dominio en un modelo de dominio de comportamiento aislado, completamente encapsulado y enriquecido sin cambiar el código del nivel de aplicación o infraestructura, que forman el nivel de establecimiento (controladores de comandos, la API web, repositorios, etc.).</span><span class="sxs-lookup"><span data-stu-id="80bb5-240">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="80bb5-241">Cuando los controladores de comandos se complican, con demasiada lógica, se puede producir un problema en el código.</span><span class="sxs-lookup"><span data-stu-id="80bb5-241">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="80bb5-242">Revíselos y, si encuentra lógica de dominio, refactorice el código para mover ese comportamiento de dominio a los métodos de los objetos de dominio (la raíz agregada y la entidad secundaria).</span><span class="sxs-lookup"><span data-stu-id="80bb5-242">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="80bb5-243">Como ejemplo de clase de controlador de comandos, en el código siguiente se muestra la misma clase `CreateOrderCommandHandler` que se vio al principio de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-243">As an example of a command handler class, the following code shows the same `CreateOrderCommandHandler` class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="80bb5-244">En este caso, también se resalta el método Handle y las operaciones con los objetos de modelo de dominio y agregados.</span><span class="sxs-lookup"><span data-stu-id="80bb5-244">In this case, it also highlights the Handle method and the operations with the domain model objects/aggregates.</span></span>

```csharp
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}
```

<span data-ttu-id="80bb5-245">Estos son los pasos adicionales que debe realizar un controlador de comandos:</span><span class="sxs-lookup"><span data-stu-id="80bb5-245">These are additional steps a command handler should take:</span></span>

- <span data-ttu-id="80bb5-246">Usar los datos del comando para funcionar con los métodos y el comportamiento de la raíz agregada.</span><span class="sxs-lookup"><span data-stu-id="80bb5-246">Use the command's data to operate with the aggregate root's methods and behavior.</span></span>

- <span data-ttu-id="80bb5-247">Dentro de los objetos de dominio, generar eventos de dominio mientras se ejecuta la transacción, pero de forma transparente desde el punto de vista de un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-247">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

- <span data-ttu-id="80bb5-248">Si el resultado de la operación del agregado es correcto y una vez finalizada la transacción, generar eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="80bb5-248">If the aggregate's operation result is successful and after the transaction is finished, raise integration events.</span></span> <span data-ttu-id="80bb5-249">(Es posible que clases de infraestructura como repositorios también los generen).</span><span class="sxs-lookup"><span data-stu-id="80bb5-249">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="80bb5-250">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="80bb5-250">Additional resources</span></span>

- <span data-ttu-id="80bb5-251">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented (En los límites, las aplicaciones no están orientadas a objetos)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-251">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented** </span></span>\
  <https://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/>

- <span data-ttu-id="80bb5-252">**Commands and events (Comandos y eventos)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-252">**Commands and events** </span></span>\
  <https://cqrs.nu/Faq/commands-and-events>

- <span data-ttu-id="80bb5-253">**What does a command handler do?** (¿De qué se encarga un controlador de comandos?)</span><span class="sxs-lookup"><span data-stu-id="80bb5-253">**What does a command handler do?**</span></span> \
  <https://cqrs.nu/Faq/command-handlers>

- <span data-ttu-id="80bb5-254">**Jimmy Bogard. Domain Command Patterns – Handlers (Patrones de comandos de dominio: controladores)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-254">**Jimmy Bogard. Domain Command Patterns – Handlers** </span></span>\
  <https://jimmybogard.com/domain-command-patterns-handlers/>

- <span data-ttu-id="80bb5-255">**Jimmy Bogard. Domain Command Patterns – Validation (Patrones de comandos de dominio: validación)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-255">**Jimmy Bogard. Domain Command Patterns – Validation** </span></span>\
  <https://jimmybogard.com/domain-command-patterns-validation/>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="80bb5-256">La canalización del proceso de comando: cómo desencadenar un controlador de comandos</span><span class="sxs-lookup"><span data-stu-id="80bb5-256">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="80bb5-257">La siguiente pregunta es cómo invocar un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-257">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="80bb5-258">Se podría llamar manualmente desde cada controlador de ASP.NET Core relacionado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-258">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="80bb5-259">Pero ese enfoque sería demasiado acoplado y no es lo ideal.</span><span class="sxs-lookup"><span data-stu-id="80bb5-259">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="80bb5-260">Las otras dos opciones principales, que son las recomendadas, son estas:</span><span class="sxs-lookup"><span data-stu-id="80bb5-260">The other two main options, which are the recommended options, are:</span></span>

- <span data-ttu-id="80bb5-261">A través de un artefacto de patrón de mediador en memoria.</span><span class="sxs-lookup"><span data-stu-id="80bb5-261">Through an in-memory Mediator pattern artifact.</span></span>

- <span data-ttu-id="80bb5-262">Con una cola de mensajes asincrónicos, entre los controladores.</span><span class="sxs-lookup"><span data-stu-id="80bb5-262">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="use-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="80bb5-263">Uso del patrón de mediador (en memoria) en la canalización de comandos</span><span class="sxs-lookup"><span data-stu-id="80bb5-263">Use the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="80bb5-264">Como se muestra en la figura 7-25, en un enfoque CQRS se usa un mediador inteligente, similar a un bus en memoria, que es lo suficientemente inteligente como para redirigir al controlador de comandos correcto según el tipo del comando o DTO que se recibe.</span><span class="sxs-lookup"><span data-stu-id="80bb5-264">As shown in Figure 7-25, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="80bb5-265">Las flechas simples de color negro entre los componentes representan las dependencias entre los objetos (en muchos casos, insertados mediante DI) con sus interacciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="80bb5-265">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![Diagrama que muestra un flujo de datos más detallado del cliente a la base de datos.](./media/microservice-application-layer-implementation-web-api/mediator-cqrs-microservice.png)

<span data-ttu-id="80bb5-267">**Figura 7-25.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-267">**Figure 7-25**.</span></span> <span data-ttu-id="80bb5-268">Uso del patrón de mediador en proceso en un único microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="80bb5-268">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="80bb5-269">En el diagrama anterior se muestra más detalle de la imagen 7-24: el controlador ASP.NET Core envía el comando a la canalización de comandos MediatR para que llegue al controlador adecuado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-269">The above diagram shows a zoom-in from image 7-24: the ASP.NET Core controller sends the command to MediatR's command pipeline, so they get to the appropriate handler.</span></span>

<span data-ttu-id="80bb5-270">El motivo por el que tiene sentido usar el patrón de mediador es que, en las aplicaciones empresariales, las solicitudes de procesamiento pueden resultar complicadas.</span><span class="sxs-lookup"><span data-stu-id="80bb5-270">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="80bb5-271">Le interesa poder agregar un número abierto de cuestiones transversales como registro, validaciones, auditoría y seguridad.</span><span class="sxs-lookup"><span data-stu-id="80bb5-271">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="80bb5-272">En estos casos, puede basarse en una canalización de mediador (vea [Patrón de mediador](https://en.wikipedia.org/wiki/Mediator_pattern)) para proporcionar un medio para estos comportamientos adicionales o cuestiones transversales.</span><span class="sxs-lookup"><span data-stu-id="80bb5-272">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="80bb5-273">Un mediador es un objeto que encapsula el "cómo" de este proceso: coordina la ejecución en función del estado, la forma de invocar un controlador de comandos o la carga que se proporciona al controlador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-273">A mediator is an object that encapsulates the "how" of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="80bb5-274">Con un componente de mediador se pueden aplicar cuestiones transversales de forma centralizada y transparente aplicando elementos Decorator (o [comportamientos de canalización](https://github.com/jbogard/MediatR/wiki/Behaviors) desde [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)).</span><span class="sxs-lookup"><span data-stu-id="80bb5-274">With a mediator component, you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)).</span></span> <span data-ttu-id="80bb5-275">Para obtener más información, vea el [Patrón de Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).</span><span class="sxs-lookup"><span data-stu-id="80bb5-275">For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).</span></span>

<span data-ttu-id="80bb5-276">Los elementos Decorator y los comportamientos son similares a la [Programación orientada a aspectos (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), solo se aplican a una canalización de proceso específica administrada por el componente de mediador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-276">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="80bb5-277">Los aspectos en AOP que implementan cuestiones transversales se aplican en función de *tejedores de aspectos* que se insertan en tiempo de compilación o en función de la intercepción de llamadas de objeto.</span><span class="sxs-lookup"><span data-stu-id="80bb5-277">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="80bb5-278">En ocasiones, se dice que ambos enfoques típicos de AOP funcionan "de forma mágica", porque no es fácil ver cómo realiza AOP su trabajo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-278">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="80bb5-279">Cuando se trabaja con problemas graves o errores, AOP puede ser difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="80bb5-279">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="80bb5-280">Por otro lado, estos elementos Decorator o comportamientos son explícitos y solo se aplican en el contexto del mediador, por lo que la depuración es mucho más sencilla y predecible.</span><span class="sxs-lookup"><span data-stu-id="80bb5-280">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="80bb5-281">Por ejemplo, el microservicio de pedidos de eShopOnContainers tiene implementados dos comportamientos de ejemplo, las clases [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) y [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs).</span><span class="sxs-lookup"><span data-stu-id="80bb5-281">For example, in the eShopOnContainers ordering microservice, has an implementation of two sample behaviors, a [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class and a [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class.</span></span> <span data-ttu-id="80bb5-282">En esta sección se explica la implementación de los comportamientos mostrando cómo eShopOnContainers usa los [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) de [MediatR](https://www.nuget.org/packages/MediatR).</span><span class="sxs-lookup"><span data-stu-id="80bb5-282">The implementation of the behaviors is explained in the next section by showing how eShopOnContainers uses [MediatR](https://www.nuget.org/packages/MediatR) [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors).</span></span>

### <a name="use-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="80bb5-283">Uso de colas de mensajes (fuera de proceso) en la canalización del comando</span><span class="sxs-lookup"><span data-stu-id="80bb5-283">Use message queues (out-of-proc) in the command's pipeline</span></span>

<span data-ttu-id="80bb5-284">Otra opción consiste en usar mensajes asincrónicos basados en agentes o colas de mensajes, como se muestra en la figura 7-26.</span><span class="sxs-lookup"><span data-stu-id="80bb5-284">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 7-26.</span></span> <span data-ttu-id="80bb5-285">Esa opción también se podría combinar con el componente de mediador justo antes del controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-285">That option could also be combined with the mediator component right before the command handler.</span></span>

![Diagrama que muestra el flujo de datos mediante una cola de mensajes de alta disponibilidad.](./media/microservice-application-layer-implementation-web-api/add-ha-message-queue.png)

<span data-ttu-id="80bb5-287">**Figura 7-26.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-287">**Figure 7-26**.</span></span> <span data-ttu-id="80bb5-288">Uso de colas de mensajes (comunicación fuera de proceso y entre procesos) con comandos CQRS</span><span class="sxs-lookup"><span data-stu-id="80bb5-288">Using message queues (out of the process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="80bb5-289">La canalización del comando también puede controlarse mediante una cola de mensajes de alta disponibilidad para entregar los comandos en el controlador adecuado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-289">Command's pipeline can also be handled by a high availability message queue to deliver the commands to the appropriate handler.</span></span> <span data-ttu-id="80bb5-290">El uso de colas de mensajes para aceptar los comandos puede complicar más la canalización del comando, ya que probablemente sea necesario dividir la canalización en dos procesos conectados a través de la cola de mensajes externos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-290">Using message queues to accept the commands can further complicate your command's pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="80bb5-291">Pero se debe usar si hay que ofrecer mayor escalabilidad y rendimiento según la mensajería asincrónica.</span><span class="sxs-lookup"><span data-stu-id="80bb5-291">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="80bb5-292">Téngalo en cuenta en el caso de la figura 7-26, donde el controlador simplemente envía el mensaje de comando a la cola y vuelve.</span><span class="sxs-lookup"><span data-stu-id="80bb5-292">Consider that in the case of Figure 7-26, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="80bb5-293">Después, los controladores de comandos procesan los mensajes a su propio ritmo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-293">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="80bb5-294">Esa es una gran ventaja de las colas: la cola de mensajes puede actuar como un búfer en casos en que se necesita hiperescalabilidad (por ejemplo, para existencias o cualquier otro escenario con un gran volumen de datos de entrada).</span><span class="sxs-lookup"><span data-stu-id="80bb5-294">That is a great benefit of queues: the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="80bb5-295">En cambio, debido a la naturaleza asincrónica de las colas de mensajes, debe saber cómo comunicar a la aplicación cliente si el proceso del comando se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="80bb5-295">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command's process.</span></span> <span data-ttu-id="80bb5-296">Como norma, nunca debería usar comandos "Fire and Forget" (dispare y olvídese).</span><span class="sxs-lookup"><span data-stu-id="80bb5-296">As a rule, you should never use "fire and forget" commands.</span></span> <span data-ttu-id="80bb5-297">Cada aplicación empresarial necesita saber si un comando se ha procesado correctamente, o al menos se ha validado y aceptado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-297">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="80bb5-298">De este modo, la capacidad de responder al cliente después de validar un mensaje de comando que se envió a una cola asincrónica agrega complejidad al sistema, en comparación con un proceso de comando en proceso que devuelve el resultado de la operación después de ejecutar la transacción.</span><span class="sxs-lookup"><span data-stu-id="80bb5-298">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation's result after running the transaction.</span></span> <span data-ttu-id="80bb5-299">Mediante las colas, es posible que tenga que devolver el resultado del proceso de comando a través de otros mensajes de resultado de la operación, lo que requiere componentes adicionales y comunicación personalizada en el sistema.</span><span class="sxs-lookup"><span data-stu-id="80bb5-299">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="80bb5-300">Además, los comandos asincrónicos son unidireccionales, lo que es posible que en muchos casos no sea necesario, tal y como se explica en el siguiente e interesante intercambio entre Burtsev Alexey y Greg Young en una [conversación en línea](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="80bb5-300">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

> <span data-ttu-id="80bb5-301">\[Burtsev Alexey\] Veo gran cantidad de código en la que los usuarios usan el control de comandos asincrónicos o la mensajería de comandos unidireccionales sin ningún motivo para hacerlo (no están realizando una operación extensa, no ejecutan código asincrónico externo, ni siquiera cruzan los límites de la aplicación para usar bus de mensajes).</span><span class="sxs-lookup"><span data-stu-id="80bb5-301">\[Burtsev Alexey\] I find lots of code where people use async command handling or one-way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross-application boundary to be using message bus).</span></span> <span data-ttu-id="80bb5-302">¿Por qué agregan esta complejidad innecesaria?</span><span class="sxs-lookup"><span data-stu-id="80bb5-302">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="80bb5-303">Y en realidad, hasta ahora no he visto ningún ejemplo de código CQRS con controladores de comandos de bloqueo, aunque funcionaría correctamente en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-303">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>
>
> <span data-ttu-id="80bb5-304">\[Greg Young\] \[...\] un comando asincrónico no existe; en realidad es otro evento.</span><span class="sxs-lookup"><span data-stu-id="80bb5-304">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="80bb5-305">Si tengo que aceptar lo que se me envía y generar un evento si no estoy de acuerdo, ya no se me está pidiendo que realice una acción \[es decir, no es un comando\].</span><span class="sxs-lookup"><span data-stu-id="80bb5-305">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something \[that is, it's not a command\].</span></span> <span data-ttu-id="80bb5-306">Se me está diciendo que se ha realizado algo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-306">It's you telling me something has been done.</span></span> <span data-ttu-id="80bb5-307">Al principio puede parecer una pequeña diferencia, pero tiene muchas implicaciones.</span><span class="sxs-lookup"><span data-stu-id="80bb5-307">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="80bb5-308">Los comandos asincrónicos aumentan considerablemente la complejidad de un sistema, porque no hay ninguna manera sencilla de indicar los errores.</span><span class="sxs-lookup"><span data-stu-id="80bb5-308">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="80bb5-309">Por tanto, los comandos asincrónicos no son recomendables a no ser que se necesiten requisitos de escalado o en casos especiales de comunicación de microservicios internos a través de mensajería.</span><span class="sxs-lookup"><span data-stu-id="80bb5-309">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="80bb5-310">En esos casos, se debe diseñar un sistema independiente de informes y recuperación de errores del sistema.</span><span class="sxs-lookup"><span data-stu-id="80bb5-310">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="80bb5-311">En la versión inicial de eShopOnContainers, decidimos usar el procesamiento de comandos sincrónicos, iniciados desde solicitudes HTTP y controlados por el patrón de mediador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-311">In the initial version of eShopOnContainers, it was decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="80bb5-312">Eso permite devolver con facilidad si el proceso se ha realizado correctamente o no, como en la implementación [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/netcore1.1/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs).</span><span class="sxs-lookup"><span data-stu-id="80bb5-312">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/netcore1.1/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="80bb5-313">En cualquier caso, debe ser una decisión basada en los requisitos empresariales de la aplicación o el microservicio.</span><span class="sxs-lookup"><span data-stu-id="80bb5-313">In any case, this should be a decision based on your application's or microservice's business requirements.</span></span>

## <a name="implement-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="80bb5-314">Implementación de la canalización del proceso de comando con un patrón de mediador (MediatR)</span><span class="sxs-lookup"><span data-stu-id="80bb5-314">Implement the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="80bb5-315">Como implementación de ejemplo, en esta guía se propone el uso de la canalización de proceso basada en el patrón de mediador para controlar la ingesta de comandos y enrutarlos, en memoria, a los controladores de comandos correctos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-315">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and route commands, in memory, to the right command handlers.</span></span> <span data-ttu-id="80bb5-316">En la guía también se propone la aplicación de [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) para separar las cuestiones transversales.</span><span class="sxs-lookup"><span data-stu-id="80bb5-316">The guide also proposes applying [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="80bb5-317">Para la implementación en .NET Core, hay varias bibliotecas de código abierto disponibles que implementan el patrón de mediador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-317">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="80bb5-318">En esta guía se usa la biblioteca de código abierto [MediatR](https://github.com/jbogard/MediatR) (creada por Jimmy Bogard), pero puede usar otro enfoque.</span><span class="sxs-lookup"><span data-stu-id="80bb5-318">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="80bb5-319">MediatR es una biblioteca pequeña y simple que permite procesar mensajes en memoria como un comando, mientras se aplican elementos Decorator o comportamientos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-319">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="80bb5-320">El uso del patrón de mediador ayuda a reducir el acoplamiento y aislar los problemas del trabajo solicitado, mientras se conecta automáticamente al controlador que lleva a cabo ese trabajo, en este caso, a controladores de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-320">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="80bb5-321">En la revisión de esta guía, Jimmy Bogard explica otra buena razón para usar el patrón de mediador:</span><span class="sxs-lookup"><span data-stu-id="80bb5-321">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

> <span data-ttu-id="80bb5-322">Creo que aquí valdría la pena mencionar las pruebas: proporcionan una ventana coherente al comportamiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="80bb5-322">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="80bb5-323">Solicitud de entrada, respuesta de salida. Hemos comprobado que es un aspecto muy valioso a la hora de generar pruebas que se comporten de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-323">Request-in, response-out. We've found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="80bb5-324">En primer lugar, veremos un controlador WebAPI de ejemplo donde se usaría realmente el objeto de mediador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-324">First, let's look at a sample WebAPI controller where you actually would use the mediator object.</span></span> <span data-ttu-id="80bb5-325">Si no se usara el objeto de mediador, sería necesario insertar todas las dependencias para ese controlador, elementos como un objeto de registrador y otros.</span><span class="sxs-lookup"><span data-stu-id="80bb5-325">If you weren't using the mediator object, you'd need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="80bb5-326">Por tanto, el constructor sería complicado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-326">Therefore, the constructor would be complicated.</span></span> <span data-ttu-id="80bb5-327">Por otra parte, si se usa el objeto de mediador, el constructor del controlador puede ser mucho más sencillo, con solo algunas dependencias en lugar de muchas si hubiera una por cada operación transversal, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-327">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies if you had one per cross-cutting operation, as in the following example:</span></span>

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

<span data-ttu-id="80bb5-328">Se puede ver que el mediador proporciona un constructor de controlador de API web limpio y eficiente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-328">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="80bb5-329">Además, dentro de los métodos de controlador, el código para enviar un comando al objeto de mediador es prácticamente una línea:</span><span class="sxs-lookup"><span data-stu-id="80bb5-329">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

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

### <a name="implement-idempotent-commands"></a><span data-ttu-id="80bb5-330">Implementación de comandos idempotentes</span><span class="sxs-lookup"><span data-stu-id="80bb5-330">Implement idempotent Commands</span></span>

<span data-ttu-id="80bb5-331">En **eShopOnContainers**, un ejemplo más avanzado que el anterior es el envío de un objeto CreateOrderCommand desde el microservicio Ordering.</span><span class="sxs-lookup"><span data-stu-id="80bb5-331">In **eShopOnContainers**, a more advanced example than the above is submitting a CreateOrderCommand object from the Ordering microservice.</span></span> <span data-ttu-id="80bb5-332">Pero como el proceso empresarial Ordering es un poco más complejo y, en nuestro caso, se inicia realmente en el microservicio Basket, esta acción de enviar el objeto CreateOrderCommand se realiza desde un controlador de eventos de integración denominado [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs), en lugar de un controlador WebAPI sencillo al que se llama desde la aplicación cliente, como ocurre en el ejemplo anterior más sencillo.</span><span class="sxs-lookup"><span data-stu-id="80bb5-332">But since the Ordering business process is a bit more complex and, in our case, it actually starts in the Basket microservice, this action of submitting the CreateOrderCommand object is performed from an integration-event handler named [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) instead of a simple WebAPI controller called from the client App as in the previous simpler example.</span></span>

<span data-ttu-id="80bb5-333">Pero la acción de enviar el comando a MediatR es bastante similar, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-333">Nevertheless, the action of submitting the Command to MediatR is pretty similar, as shown in the following code.</span></span>

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

<span data-ttu-id="80bb5-334">Sin embargo, este caso también es ligeramente más avanzado porque también se implementan comandos idempotentes.</span><span class="sxs-lookup"><span data-stu-id="80bb5-334">However, this case is also slightly more advanced because we're also implementing idempotent commands.</span></span> <span data-ttu-id="80bb5-335">El proceso CreateOrderCommand debe ser idempotente, por lo que si el mismo mensaje procede duplicado a través de la red, por cualquier motivo, como un reintento, el mismo pedido se procesará una sola vez.</span><span class="sxs-lookup"><span data-stu-id="80bb5-335">The CreateOrderCommand process should be idempotent, so if the same message comes duplicated through the network, because of any reason, like retries, the same business order will be processed just once.</span></span>

<span data-ttu-id="80bb5-336">Esto se implementa mediante la encapsulación del comando de negocio (en este caso, CreateOrderCommand) y su inserción en un IdentifiedCommand genérico, cuyo seguimiento se realiza a través de un identificador de todos los mensajes que lleguen a través de la red que tienen que ser idempotentes.</span><span class="sxs-lookup"><span data-stu-id="80bb5-336">This is implemented by wrapping the business command (in this case CreateOrderCommand) and embedding it into a generic IdentifiedCommand, which is tracked by an ID of every message coming through the network that has to be idempotent.</span></span>

<span data-ttu-id="80bb5-337">En el código siguiente, puede ver que el IdentifiedCommand no es más que un DTO con un identificador junto con el objeto de comando de negocio insertado.</span><span class="sxs-lookup"><span data-stu-id="80bb5-337">In the code below, you can see that the IdentifiedCommand is nothing more than a DTO with and ID plus the wrapped business command object.</span></span>

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

<span data-ttu-id="80bb5-338">Después, el CommandHandler para el IdentifiedCommand denominado [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) básicamente comprobará si el identificador que procede como parte del mensaje ya existe en una tabla.</span><span class="sxs-lookup"><span data-stu-id="80bb5-338">Then the CommandHandler for the IdentifiedCommand named [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) will basically check if the ID coming as part of the message already exists in a table.</span></span> <span data-ttu-id="80bb5-339">Si ya existe, ese comando no se volverá a procesar, por lo que se comporta como un comando idempotente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-339">If it already exists, that command won't be processed again, so it behaves as an idempotent command.</span></span> <span data-ttu-id="80bb5-340">Ese código de infraestructura se ejecuta mediante la llamada al método `_requestManager.ExistAsync` siguiente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-340">That infrastructure code is performed by the `_requestManager.ExistAsync` method call below.</span></span>

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> : IRequestHandler<IdentifiedCommand<T, R>, R>
        where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;
    private readonly ILogger<IdentifiedCommandHandler<T, R>> _logger;

    public IdentifiedCommandHandler(
        IMediator mediator,
        IRequestManager requestManager,
        ILogger<IdentifiedCommandHandler<T, R>> logger)
    {
        _mediator = mediator;
        _requestManager = requestManager;
        _logger = logger ?? throw new System.ArgumentNullException(nameof(logger));
    }

    /// <summary>
    /// Creates the result value to return if a previous request was found
    /// </summary>
    /// <returns></returns>
    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    /// <summary>
    /// This method handles the command. It just ensures that no other request exists with the same ID, and if this is the case
    /// just enqueues the original inner command.
    /// </summary>
    /// <param name="message">IdentifiedCommand which contains both original command & request ID</param>
    /// <returns>Return value of inner command or default value if request same ID was found</returns>
    public async Task<R> Handle(IdentifiedCommand<T, R> message, CancellationToken cancellationToken)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);
            try
            {
                var command = message.Command;
                var commandName = command.GetGenericTypeName();
                var idProperty = string.Empty;
                var commandId = string.Empty;

                switch (command)
                {
                    case CreateOrderCommand createOrderCommand:
                        idProperty = nameof(createOrderCommand.UserId);
                        commandId = createOrderCommand.UserId;
                        break;

                    case CancelOrderCommand cancelOrderCommand:
                        idProperty = nameof(cancelOrderCommand.OrderNumber);
                        commandId = $"{cancelOrderCommand.OrderNumber}";
                        break;

                    case ShipOrderCommand shipOrderCommand:
                        idProperty = nameof(shipOrderCommand.OrderNumber);
                        commandId = $"{shipOrderCommand.OrderNumber}";
                        break;

                    default:
                        idProperty = "Id?";
                        commandId = "n/a";
                        break;
                }

                _logger.LogInformation(
                    "----- Sending command: {CommandName} - {IdProperty}: {CommandId} ({@Command})",
                    commandName,
                    idProperty,
                    commandId,
                    command);

                // Send the embeded business command to mediator so it runs its related CommandHandler
                var result = await _mediator.Send(command, cancellationToken);

                _logger.LogInformation(
                    "----- Command result: {@Result} - {CommandName} - {IdProperty}: {CommandId} ({@Command})",
                    result,
                    commandName,
                    idProperty,
                    commandId,
                    command);

                return result;
            }
            catch
            {
                return default(R);
            }
        }
    }
}
```

<span data-ttu-id="80bb5-341">Dado que IdentifiedCommand actúa como sobre de un comando de negocios, cuando el comando de negocios se debe procesar porque no es un identificador repetido, toma ese comando de negocios interno y lo vuelve a enviar al mediador, como se muestra en la última parte del código anterior al ejecutar `_mediator.Send(message.Command)` desde [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span><span class="sxs-lookup"><span data-stu-id="80bb5-341">Since the IdentifiedCommand acts like a business command's envelope, when the business command needs to be processed because it is not a repeated ID, then it takes that inner business command and resubmits it to Mediator, as in the last part of the code shown above when running `_mediator.Send(message.Command)`, from the [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span></span>

<span data-ttu-id="80bb5-342">Al hacerlo, se vincula y ejecuta el controlador de comandos de negocios, en este caso, [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs), que ejecuta transacciones con la base de datos Ordering, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="80bb5-342">When doing that, it will link and run the business command handler, in this case, the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs), which is running transactions against the Ordering database, as shown in the following code.</span></span>

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}
```

### <a name="register-the-types-used-by-mediatr"></a><span data-ttu-id="80bb5-343">Registro de los tipos usados por MediatR</span><span class="sxs-lookup"><span data-stu-id="80bb5-343">Register the types used by MediatR</span></span>

<span data-ttu-id="80bb5-344">Para que MediatR sea consciente de las clases de controlador de comandos, debe registrar las clases de mediador y las de controlador de comandos en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="80bb5-344">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="80bb5-345">De forma predeterminada, MediatR usa Autofac como el contenedor de IoC, pero también se puede usar el contenedor de IoC integrado de ASP.NET Core o cualquier otro contenedor compatible con MediatR.</span><span class="sxs-lookup"><span data-stu-id="80bb5-345">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="80bb5-346">En el código siguiente se muestra cómo registrar los tipos y comandos del mediador al usar módulos de Autofac.</span><span class="sxs-lookup"><span data-stu-id="80bb5-346">The following code shows how to register Mediator's types and commands when using Autofac modules.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand).GetTypeInfo().Assembly)
                .AsClosedTypesOf(typeof(IRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

<span data-ttu-id="80bb5-347">Aquí es donde "ocurre la magia" con MediatR.</span><span class="sxs-lookup"><span data-stu-id="80bb5-347">This is where "the magic happens" with MediatR.</span></span>

<span data-ttu-id="80bb5-348">Como cada controlador de comandos implementa la interfaz de `IRequestHandler<T>` genérica, cuando se registran los ensamblados mediante el método `RegisteredAssemblyTypes`, todos los tipos marcados como `IRequestHandler` también se registran con sus `Commands`.</span><span class="sxs-lookup"><span data-stu-id="80bb5-348">As each command handler implements the generic `IRequestHandler<T>` interface, when you register the assemblies using `RegisteredAssemblyTypes` method all the types marked as `IRequestHandler` also gets registered with their `Commands`.</span></span> <span data-ttu-id="80bb5-349">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="80bb5-349">For   example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="80bb5-350">Ese es el código que pone en correlación los comandos y los controladores de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-350">That is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="80bb5-351">El controlador es simplemente una clase, pero hereda de `RequestHandler<T>`, donde T es el tipo de comando, y MediatR se asegura de que se invoque con la carga correcta (el comando).</span><span class="sxs-lookup"><span data-stu-id="80bb5-351">The handler is just a simple class, but it inherits from `RequestHandler<T>`, where T is the command type, and MediatR makes sure it is invoked with the correct payload (the command).</span></span>

## <a name="apply-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-mediatr"></a><span data-ttu-id="80bb5-352">Aplicación de cuestiones transversales al procesar comandos con los comportamientos de MediatR</span><span class="sxs-lookup"><span data-stu-id="80bb5-352">Apply cross-cutting concerns when processing commands with the Behaviors in MediatR</span></span>

<span data-ttu-id="80bb5-353">Hay otro aspecto: la capacidad de aplicar cuestiones transversales a la canalización de mediador.</span><span class="sxs-lookup"><span data-stu-id="80bb5-353">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="80bb5-354">También puede ver al final del código del módulo de registro de Autofac cómo registra un tipo de comportamiento, en concreto una clase LoggingBehavior personalizada y una clase ValidatorBehavior.</span><span class="sxs-lookup"><span data-stu-id="80bb5-354">You can also see at the end of the Autofac registration module code how it registers a behavior type, specifically, a custom LoggingBehavior class and a ValidatorBehavior class.</span></span> <span data-ttu-id="80bb5-355">Pero también se podrían agregar otros comportamientos personalizados.</span><span class="sxs-lookup"><span data-stu-id="80bb5-355">But you could add other custom behaviors, too.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IRequestHandler<,>));
        // Other types registration
        //...
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

<span data-ttu-id="80bb5-356">Esa clase [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) se puede implementar como el código siguiente, que registra información sobre el controlador de comandos que se está ejecutando y si se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="80bb5-356">That [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

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

<span data-ttu-id="80bb5-357">Con la simple implementación de esta clase de comportamiento y su registro en la canalización (en el MediatorModule anterior), todos los comandos que se procesan a través de MediatR registrarán información sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="80bb5-357">Just by implementing this behavior class and by registering it in the pipeline (in the MediatorModule above), all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="80bb5-358">El microservicio de pedidos de eShopOnContainers también aplica un segundo comportamiento para validaciones básicas, la clase [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) que se basa en la biblioteca [FluentValidation](https://github.com/JeremySkinner/FluentValidation), como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-358">The eShopOnContainers ordering microservice also applies a second behavior for basic validations, the [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

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

<span data-ttu-id="80bb5-359">Aquí, el comportamiento está generando una excepción si se produce un error de validación, pero también podría devolver un objeto de resultado, que contiene el resultado del comando si se realiza correctamente o la validación de mensajes en caso de que no lo hiciese.</span><span class="sxs-lookup"><span data-stu-id="80bb5-359">Here the behavior is raising an exception if validation fails, but you could also return a result object, containing the command result if it succeeded or the validation messages in case it didn't.</span></span> <span data-ttu-id="80bb5-360">Esto probablemente facilitaría mostrar los resultados de validación al usuario.</span><span class="sxs-lookup"><span data-stu-id="80bb5-360">This would probably make it easier to display validation results to the user.</span></span>

<span data-ttu-id="80bb5-361">Después, en función de la biblioteca [FluentValidation](https://github.com/JeremySkinner/FluentValidation), se crea la validación de los datos pasados con CreateOrderCommand, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80bb5-361">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, you would create validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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

<span data-ttu-id="80bb5-362">Podría crear validaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="80bb5-362">You could create additional validations.</span></span> <span data-ttu-id="80bb5-363">Se trata de una forma muy limpia y elegante de implementar las validaciones de comandos.</span><span class="sxs-lookup"><span data-stu-id="80bb5-363">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="80bb5-364">De forma similar, podría implementar otros comportamientos para aspectos adicionales o cuestiones transversales que quiera aplicar a los comandos cuando los administre.</span><span class="sxs-lookup"><span data-stu-id="80bb5-364">In a similar way, you could implement other behaviors for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="80bb5-365">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="80bb5-365">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="80bb5-366">El patrón de mediador</span><span class="sxs-lookup"><span data-stu-id="80bb5-366">The mediator pattern</span></span>

- <span data-ttu-id="80bb5-367">**Patrón de mediador** </span><span class="sxs-lookup"><span data-stu-id="80bb5-367">**Mediator pattern** </span></span>\
  [https://en.wikipedia.org/wiki/Mediator\_pattern](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a><span data-ttu-id="80bb5-368">El patrón Decorator</span><span class="sxs-lookup"><span data-stu-id="80bb5-368">The decorator pattern</span></span>

- <span data-ttu-id="80bb5-369">**Patrón Decorator** </span><span class="sxs-lookup"><span data-stu-id="80bb5-369">**Decorator pattern** </span></span>\
  [https://en.wikipedia.org/wiki/Decorator\_pattern](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="80bb5-370">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="80bb5-370">MediatR (Jimmy Bogard)</span></span>

- <span data-ttu-id="80bb5-371">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-371">**MediatR.**</span></span> <span data-ttu-id="80bb5-372">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="80bb5-372">GitHub repo.</span></span> \
  <https://github.com/jbogard/MediatR>

- <span data-ttu-id="80bb5-373">**CQRS with MediatR and AutoMapper (CQRS con MediatR y AutoMapper)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-373">**CQRS with MediatR and AutoMapper** </span></span>\
  <https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/>

- <span data-ttu-id="80bb5-374">**Put your controllers on a diet: POSTs and commands** (Poner los controladores a dieta: POST y comandos).</span><span class="sxs-lookup"><span data-stu-id="80bb5-374">**Put your controllers on a diet: POSTs and commands.**</span></span> \
  <https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/>

- <span data-ttu-id="80bb5-375">**Tackling cross-cutting concerns with a mediator pipeline (Abordar cuestiones transversales con una canalización de mediador)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-375">**Tackling cross-cutting concerns with a mediator pipeline** </span></span>\
  <https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/>

- <span data-ttu-id="80bb5-376">**CQRS and REST: the perfect match (CQRS y REST: la combinación perfecta)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-376">**CQRS and REST: the perfect match** </span></span>\
  <https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/>

- <span data-ttu-id="80bb5-377">**MediatR Pipeline Examples (Ejemplos de canalización de MediatR)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-377">**MediatR Pipeline Examples** </span></span>\
  <https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/>

- <span data-ttu-id="80bb5-378">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core (Accesorios de prueba de segmentos verticales para MediatR y ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-378">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core** </span></span>\
  <https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>

- <span data-ttu-id="80bb5-379">**MediatR Extensions for Microsoft Dependency Injection Released (Extensiones de MediatR para el lanzamiento de inserciones de dependencias de Microsoft)**  </span><span class="sxs-lookup"><span data-stu-id="80bb5-379">**MediatR Extensions for Microsoft Dependency Injection Released** </span></span>\
  <https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/>

##### <a name="fluent-validation"></a><span data-ttu-id="80bb5-380">Validación fluida</span><span class="sxs-lookup"><span data-stu-id="80bb5-380">Fluent validation</span></span>

- <span data-ttu-id="80bb5-381">**Jeremy Skinner. Validación fluida.**</span><span class="sxs-lookup"><span data-stu-id="80bb5-381">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="80bb5-382">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="80bb5-382">GitHub repo.</span></span> \
  <https://github.com/JeremySkinner/FluentValidation>

> [!div class="step-by-step"]
> <span data-ttu-id="80bb5-383">[Anterior](microservice-application-layer-web-api-design.md)
> [Siguiente](../implement-resilient-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="80bb5-383">[Previous](microservice-application-layer-web-api-design.md)
[Next](../implement-resilient-applications/index.md)</span></span>
