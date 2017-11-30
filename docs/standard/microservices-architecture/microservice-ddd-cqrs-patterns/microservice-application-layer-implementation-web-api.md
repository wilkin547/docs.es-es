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
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="2c9b5-104">Implementar el nivel de aplicación de microservicio mediante la API de Web</span><span class="sxs-lookup"><span data-stu-id="2c9b5-104">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="2c9b5-105">Mediante la inserción de dependencia para insertar objetos de la infraestructura en la capa de aplicación</span><span class="sxs-lookup"><span data-stu-id="2c9b5-105">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="2c9b5-106">Como se mencionó anteriormente, la capa de aplicación puede implementarse como parte del artefacto que está creando, tal como dentro de un proyecto de API Web o un proyecto de aplicación web MVC.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-106">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="2c9b5-107">En el caso de un microservicio compilada con ASP.NET Core, el nivel de aplicación normalmente será la biblioteca de API Web.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-107">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="2c9b5-108">Si desea separar próximas novedades de ASP.NET Core (su infraestructura y los controladores) desde el código de capa de aplicación personalizada, también puede colocar la capa de aplicación en una biblioteca de clases independiente, pero que es opcional.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-108">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="2c9b5-109">Por ejemplo, el código de capa de aplicación de la ordenación microservicio directamente se implementa como parte de la **Ordering.API** proyecto (una API Web de ASP.NET Core), como se muestra en la figura 9-19.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-109">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="2c9b5-110">**Figura 9-19**.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-110">**Figure 9-19**.</span></span> <span data-ttu-id="2c9b5-111">La capa de aplicación en el proyecto Ordering.API ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="2c9b5-111">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="2c9b5-112">ASP.NET Core incluye un sencillo [integrado contenedor de IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (representado por la interfaz IServiceProvider) que admite la inserción del constructor de forma predeterminada y ASP.NET pone a disposición a través de DI determinados servicios.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-112">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="2c9b5-113">ASP.NET Core utiliza el término *servicio* para cualquiera de los tipos que registra que se insertará mediante DI.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-113">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="2c9b5-114">Configurar los servicios del contenedor integrados en el método ConfigureServices de clase de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-114">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="2c9b5-115">Las dependencias se implementan en los servicios que necesita un tipo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-115">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="2c9b5-116">Normalmente, desea insertar las dependencias que implementan objetos de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-116">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="2c9b5-117">Una dependencia muy habitual para insertar es un repositorio.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-117">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="2c9b5-118">Pero también puede insertar cualquier dependencia de infraestructura que surgen.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-118">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="2c9b5-119">Para las implementaciones más sencillas, también podría insertar directamente el objeto de patrón de la unidad de trabajo (el objeto DbContext EF), porque DBContext también es la implementación de los objetos de persistencia de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-119">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="2c9b5-120">En el ejemplo siguiente, puede ver cómo .NET Core es insertar los objetos de repositorio necesaria a través del constructor.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-120">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="2c9b5-121">La clase es un controlador de comandos, que se explica en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-121">The class is a command handler, which we will cover in the next section.</span></span>

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

<span data-ttu-id="2c9b5-122">La clase utiliza los repositorios insertados para ejecutar la transacción y conservar los cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-122">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="2c9b5-123">No importa si esa clase es un controlador de comandos, un método de controlador de API Web de ASP.NET Core, o un [DDD aplicación servicio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-123">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="2c9b5-124">En última instancia es una clase simple que utiliza repositorios, entidades de dominio y otro coordinación de las aplicaciones de forma similar a un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-124">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="2c9b5-125">Inyección de dependencia funciona igual en todas las clases mencionadas, como se muestra en el ejemplo de cómo utilizar DI basado en el constructor.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-125">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="2c9b5-126">Registrar los tipos de implementación de dependencia y interfaces o abstracciones</span><span class="sxs-lookup"><span data-stu-id="2c9b5-126">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="2c9b5-127">Antes de usar los objetos insertados mediante constructores, debe saber dónde registrar las interfaces y clases que generan los objetos que se insertan en las clases de aplicación a través de DI.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-127">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="2c9b5-128">(Como DI en función del constructor, tal y como se ha mostrado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-128">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="2c9b5-129">Usando el contenedor de IoC integrado proporcionado por ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2c9b5-129">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="2c9b5-130">Cuando se usa el contenedor de IoC integrado proporcionado por ASP.NET Core, registre los tipos que desee insertar en el método ConfigureServices en el archivo Startup.cs, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-130">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

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

<span data-ttu-id="2c9b5-131">El modelo más común al registrar los tipos en un contenedor de IoC es registrar un par de tipos: una interfaz y su clase de implementación relacionada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-131">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="2c9b5-132">A continuación, cuando se solicita un objeto desde el contenedor de IoC a través de cualquier constructor, solicitar un objeto de un determinado tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-132">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="2c9b5-133">Por ejemplo, en el ejemplo anterior, la última línea indica que, cuando cualquiera de sus constructores tiene una dependencia en IMyCustomRepository (interfaz o abstracción), el contenedor de IoC insertará una instancia de la implementación de MyCustomSQLServerRepository clase.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-133">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="2c9b5-134">Uso de la biblioteca de Scrutor para el registro de tipos automática</span><span class="sxs-lookup"><span data-stu-id="2c9b5-134">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="2c9b5-135">Al utilizar DI en .NET Core, debe poder examinar un ensamblado y registrar automáticamente sus tipos por convención.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-135">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="2c9b5-136">Esta característica no está disponible actualmente en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-136">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="2c9b5-137">Sin embargo, puede usar el [Scrutor](https://github.com/khellang/Scrutor) biblioteca para que.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-137">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="2c9b5-138">Este enfoque resulta conveniente cuando existen docenas de tipos que tienen que ser registrados en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-138">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2c9b5-139">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9b5-139">Additional resources</span></span>

-   <span data-ttu-id="2c9b5-140">**Matthew rey. Registro de los servicios con Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-140">**Matthew King. Registering services with Scrutor**
[*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="2c9b5-141">**Kristian Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="2c9b5-141">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="2c9b5-142">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-142">GitHub repo.</span></span>
    [<span data-ttu-id="2c9b5-143">*https://github.com/khellang/Scrutor*</span><span class="sxs-lookup"><span data-stu-id="2c9b5-143">*https://github.com/khellang/Scrutor*</span></span>](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="2c9b5-144">Usa Autofac como un contenedor de IoC</span><span class="sxs-lookup"><span data-stu-id="2c9b5-144">Using Autofac as an IoC container</span></span>

<span data-ttu-id="2c9b5-145">También puede utilizar los contenedores de IoC adicionales y conéctelos a la canalización de ASP.NET Core, como se muestra en la ordenación microservicio en eShopOnContainers, que utiliza [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="2c9b5-146">Cuando se usa Autofac normalmente registrar los tipos a través de módulos, lo que permite dividir los tipos de registro entre varios archivos, dependiendo de dónde encuentran sus tipos, tal y como podría tener los tipos de aplicaciones distribuidos a través de varias bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="2c9b5-147">Por ejemplo, el siguiente es el [módulo de aplicación de Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) para el [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) proyecto con los tipos que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

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

<span data-ttu-id="2c9b5-148">El proceso de registro y los conceptos son muy similares a la manera en que puede registrar tipos con el contenedor de iOS de ASP.NET Core integrado, pero la sintaxis cuando se usa Autofac es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-148">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core iOS container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="2c9b5-149">En el código de ejemplo se registra la abstracción IOrderRepository junto con la clase de implementación OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-149">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="2c9b5-150">Esto significa que cada vez que un constructor es declarar una dependencia a través de la abstracción de IOrderRepository o la interfaz, el contenedor de IoC insertará una instancia de la clase OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-150">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="2c9b5-151">El tipo de ámbito de la instancia determina cómo se comparte una instancia entre solicitudes para el mismo servicio o dependencia.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-151">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="2c9b5-152">Cuando se realiza una solicitud para una dependencia, el contenedor de IoC puede devolver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-152">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="2c9b5-153">Una sola instancia por ámbito de duración (mencionado en el contenedor de ASP.NET Core IoC como *ámbito*).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-153">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="2c9b5-154">Una nueva instancia por dependencia (mencionado en el contenedor de ASP.NET Core IoC como *transitorio*).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-154">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="2c9b5-155">Una única instancia que se comparte entre todos los objetos mediante el contenedor de IoC (mencionado en el contenedor de ASP.NET Core IoC como *singleton*).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-155">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2c9b5-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9b5-156">Additional resources</span></span>

-   <span data-ttu-id="2c9b5-157">**Introducción a la inyección de dependencia en ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-157">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="2c9b5-158">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="2c9b5-158">**Autofac.**</span></span> <span data-ttu-id="2c9b5-159">Documentación oficial.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-159">Official documentation.</span></span>
    [<span data-ttu-id="2c9b5-160">*http://docs.autofac.org/en/Latest/*</span><span class="sxs-lookup"><span data-stu-id="2c9b5-160">*http://docs.autofac.org/en/latest/*</span></span>](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="2c9b5-161">**Cesar de la Torre. Comparar las duraciones de servicio de contenedor de ASP.NET Core IoC con ámbitos de instancia del contenedor de IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-161">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="2c9b5-162">Implementar los patrones de comando y el controlador de comandos</span><span class="sxs-lookup"><span data-stu-id="2c9b5-162">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="2c9b5-163">En el ejemplo de DI a través de constructor que se muestra en la sección anterior, el contenedor de IoC se está insertando repositorios a través de un constructor en una clase.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="2c9b5-164">¿Pero exactamente donde se insertados?</span><span class="sxs-lookup"><span data-stu-id="2c9b5-164">But exactly where were they injected?</span></span> <span data-ttu-id="2c9b5-165">En una API Web simple (por ejemplo, el catálogo de microservicio en eShopOnContainers), se insertan en el nivel de controladores MVC, en un constructor de controlador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="2c9b5-166">Sin embargo, en el código inicial de esta sección (el [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) clase del servicio Ordering.API en eShopOnContainers), la inserción de dependencias se realiza a través del constructor de un comando determinado controlador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="2c9b5-167">Permítanos explican qué un controlador de comandos es y por qué desearía utilizarla.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="2c9b5-168">El modelo de comando intrínsecamente está relacionado con el patrón CQRS que se presentó anteriormente en esta guía.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="2c9b5-169">CQRS tienen dos lados.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-169">CQRS has two sides.</span></span> <span data-ttu-id="2c9b5-170">La primera área es consultas, mediante consultas simplificadas con el [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, que se ha explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="2c9b5-171">La segunda área es comandos, que son el punto inicial para las transacciones y el canal de entrada desde el exterior del servicio.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="2c9b5-172">Como se muestra en la figura 9-20, el patrón está basado en acepta comandos en el cliente, procesarlos según las reglas del modelo de dominio y, por último, conservar los Estados con transacciones.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-172">As shown in Figure 9-20, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="2c9b5-173">**Figura 9-20**.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-173">**Figure 9-20**.</span></span> <span data-ttu-id="2c9b5-174">Vista de alto nivel de los comandos o el "lado transaccional" en un patrón CQRS</span><span class="sxs-lookup"><span data-stu-id="2c9b5-174">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="2c9b5-175">La clase de comando</span><span class="sxs-lookup"><span data-stu-id="2c9b5-175">The command class</span></span>

<span data-ttu-id="2c9b5-176">Un comando es una solicitud para el sistema realizar una acción que cambia el estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-176">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="2c9b5-177">Comandos son imperativos y se deben procesar de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-177">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="2c9b5-178">Puesto que comandos son imperativos, normalmente se denominan con un verbo en el ambiente imperativo (por ejemplo, "crear" o "actualización"), y puede incluir el tipo agregado, como CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-178">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="2c9b5-179">A diferencia de un evento, un comando no es un hecho en el pasado; es sólo una solicitud y, por tanto, podrá ser denegada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-179">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="2c9b5-180">Comandos pueden originarse desde la interfaz de usuario como resultado de un usuario que inicia una solicitud, o desde un administrador de procesos cuando el Administrador de procesos está dirigiendo un agregado para realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-180">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="2c9b5-181">Una característica importante de un comando es que debe procesarse con solo una vez un único receptor.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-181">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="2c9b5-182">Esto es porque un comando es una sola acción o la transacción que desea realizar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-182">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="2c9b5-183">Por ejemplo, el mismo comando de creación de orden no debe procesarse más de una vez.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-183">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="2c9b5-184">Se trata de una diferencia importante entre los comandos y eventos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-184">This is an important difference between commands and events.</span></span> <span data-ttu-id="2c9b5-185">Los eventos se pueden procesar varias veces, dado que muchos sistemas o microservicios podrían estar interesados en el evento.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-185">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="2c9b5-186">Además, es importante que se procesa un comando solo una vez en caso de que el comando no es idempotente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-186">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="2c9b5-187">Un comando es idempotente si se puede ejecutar varias veces sin cambiar el resultado, ya sea debido a la naturaleza del comando, o debido al modo en que el sistema controla el comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-187">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="2c9b5-188">Es una buena práctica para hacer que sus comandos y actualiza idempotente cuando tiene sentido en las reglas de negocios de su dominio e invariables.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-188">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="2c9b5-189">Por ejemplo, para usar el mismo ejemplo, si por algún motivo (lógica de reintento, piratería, etc.) del mismo comando CreateOrder alcanza su sistema varias veces, puede identificarlo y asegurarse de que no se creen varios pedidos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-189">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="2c9b5-190">Para ello, debe adjuntar algún tipo de identidad en las operaciones e identificar si ya se está procesando el comando o la actualización.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-190">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="2c9b5-191">Enviar un comando a un receptor único; no publique un comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-191">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="2c9b5-192">La publicación es para los eventos de integración que notifican un hecho: algo ha sucedido y podría ser interesante para los receptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-192">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="2c9b5-193">En el caso de eventos, produce sin preocupaciones sobre qué destinatarios obtengan el evento o las acciones que realizan en el publicador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-193">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="2c9b5-194">Pero los sucesos de integración son algo diferente que ya se introdujeron en las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-194">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="2c9b5-195">Un comando se implementa con una clase que contiene campos de datos o colecciones con toda la información que se necesita para ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-195">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="2c9b5-196">Un comando es un tipo especial de datos transferir objetos (DTO), que se utiliza específicamente para solicitar cambios o transacciones.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-196">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="2c9b5-197">Se basa en el propio comando exactamente la información que se necesita para procesar el comando y nada más.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-197">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="2c9b5-198">En el ejemplo siguiente se muestra la clase CreateOrderCommand simplificada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-198">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="2c9b5-199">Se trata de un comando inmutable que se usa en la ordenación microservicio en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-199">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

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

<span data-ttu-id="2c9b5-200">Básicamente, la clase de comando contiene todos los datos que necesita para llevar a cabo una transacción empresarial mediante el uso de los objetos de modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-200">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="2c9b5-201">Por lo tanto, los comandos son simplemente las estructuras de datos que contienen datos de solo lectura y ningún comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-201">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="2c9b5-202">El nombre del comando indica su propósito.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-202">The command’s name indicates its purpose.</span></span> <span data-ttu-id="2c9b5-203">En muchos lenguajes como C\#, comandos se representan como clases, pero no son clases true en el sentido real orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-203">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="2c9b5-204">Como una característica adicional, los comandos son inmutables, dado que el uso esperado es que se procesan directamente por el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-204">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="2c9b5-205">No deben cambiar durante su duración prevista.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-205">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="2c9b5-206">En una C\# (clase), será posible inmutabilidad al no tener los establecedores u otros métodos que cambian el estado interno.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-206">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="2c9b5-207">Por ejemplo, la clase de comando para crear un pedido probablemente es similar en cuanto a datos en el orden que desee para crear, pero probable que no necesitan los mismos atributos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-207">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="2c9b5-208">Por ejemplo, CreateOrderCommand no tiene un identificador de pedido, porque el pedido aún no se ha creado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-208">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="2c9b5-209">Muchas clases de comando pueden ser simples, que requiere solo unos cuantos campos sobre algún estado, que debe cambiarse.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-209">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="2c9b5-210">Que sería el caso si solo va a cambiar el estado de un pedido "en proceso" a "pago" o "enviado" con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-210">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

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

<span data-ttu-id="2c9b5-211">Algunos desarrolladores sus objetos de solicitud de interfaz de usuario independiente de sus dto de comando, pero es simplemente una cuestión de preferencia.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-211">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="2c9b5-212">Es una separación tediosa con no un gran valor añadido, y los objetos son casi exactamente de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-212">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="2c9b5-213">Por ejemplo, en eShopOnContainers, los comandos proceden directamente desde el lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-213">For instance, in eShopOnContainers, the commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="2c9b5-214">La clase de controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-214">The Command Handler class</span></span>

<span data-ttu-id="2c9b5-215">Debe implementar una clase de controlador de comandos específicos para cada comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-215">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="2c9b5-216">Es cómo funciona el patrón, y es donde usará el objeto de comando, los objetos de dominio y los objetos del repositorio de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-216">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="2c9b5-217">De hecho, el controlador de comandos es el núcleo de la capa de aplicación en cuanto a CQRS y DDD.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-217">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="2c9b5-218">Sin embargo, toda la lógica del dominio debe estar dentro de las clases de dominio, dentro de las raíces agregadas (entidades raíz), las entidades secundarias, o [los servicios de dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), pero no en el controlador de comandos, que es una clase de la aplicación capa.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-218">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="2c9b5-219">Un controlador de comandos recibe un comando y obtiene un resultado de la función de agregado que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-219">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="2c9b5-220">El resultado debe ser la ejecución correcta del comando, o bien una excepción.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-220">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="2c9b5-221">En el caso de una excepción, el estado del sistema debe ser sin cambios.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-221">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="2c9b5-222">Normalmente, el controlador de comandos realiza los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-222">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="2c9b5-223">Recibe el objeto de comando, como un DTO (desde el [mediador](https://en.wikipedia.org/wiki/Mediator_pattern) u otro objeto de infraestructura).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-223">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="2c9b5-224">Valida que el comando es válido (si no valida el mediador).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-224">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="2c9b5-225">Crea una instancia de la instancia raíz agregada que es el destino del comando actual.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-225">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="2c9b5-226">El método ejecuta en la instancia raíz agregada, obtener los datos necesarios del comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-226">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="2c9b5-227">Conserva el nuevo estado del agregado a su base de datos relacionada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-227">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="2c9b5-228">Esta última operación es la transacción real.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-228">This last operation is the actual transaction.</span></span>

<span data-ttu-id="2c9b5-229">Normalmente, un controlador de comandos afecta a un único agregado controlado por su raíz agregada (entidad raíz).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-229">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="2c9b5-230">Si varios agregados deberían verse afectados por la recepción de un único comando, podría utilizar eventos de dominio propague Estados o acciones a través de varios agregados</span><span class="sxs-lookup"><span data-stu-id="2c9b5-230">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates</span></span>

<span data-ttu-id="2c9b5-231">La cuestión importante aquí es que cuando se procesa un comando, toda la lógica del dominio debe ser dentro del modelo de dominio (agregados), completamente encapsulado y listo para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-231">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="2c9b5-232">El controlador de comandos solo actúa como una manera de obtener el modelo de dominio de la base de datos y como último paso, para indicar el nivel de infraestructura (repositorios) para conservar los cambios cuando se cambia el modelo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-232">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="2c9b5-233">La ventaja de este enfoque es que la lógica del dominio en un modelo de dominio aislado, completamente encapsulado, enriquecida, comportamiento, puede refactorizar sin cambiar el código de la aplicación o capas de infraestructura, que son el nivel de establecimiento (controladores de comandos, la API Web, repositorios, etcetera).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-233">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="2c9b5-234">Al llegar a controladores de comandos complejos, con demasiada lógica, que puede ser un olor de código.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-234">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="2c9b5-235">Revisarlos y, si encuentra lógica del dominio, refactorizar el código para mover ese comportamiento de dominio a los métodos de los objetos de dominio (el agregado raíz y secundario entidad).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-235">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="2c9b5-236">Como ejemplo de una clase de controlador de comandos, el código siguiente muestra la misma clase CreateOrderCommandHandler que vio al principio de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-236">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="2c9b5-237">En este caso hemos resaltado el método Handle y las operaciones con los objetos del modelo de dominio/agregados.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-237">In this case we have highlighted the Handle method and the operations with the domain model objects/aggregates.</span></span>

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

<span data-ttu-id="2c9b5-238">Estos son los pasos adicionales que debe tener un controlador de comandos:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-238">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="2c9b5-239">Usar datos del comando para que funcione con métodos y el comportamiento de la raíz agregada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-239">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="2c9b5-240">Internamente dentro de los objetos de dominio, si se producen eventos de dominio mientras se ejecuta la transacción, pero que es transparente desde un punto de vista de comando controlador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-240">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="2c9b5-241">Si el resultado de la operación de agregado es correcta y una vez finalizada la transacción, genera el controlador de comandos de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-241">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="2c9b5-242">(Estos también se podrían generar clases de infraestructura como repositorios.)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-242">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2c9b5-243">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9b5-243">Additional resources</span></span>

-   <span data-ttu-id="2c9b5-244">**Mark Seemann. En los límites, las aplicaciones están orientados a objetos no**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, orientados a ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-244">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="2c9b5-245">**Comandos y eventos de**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-245">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="2c9b5-246">**¿Qué hace el controlador de comandos? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-246">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="2c9b5-247">**Jimmy Bogard. Patrones de comando de dominio: controladores**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-247">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="2c9b5-248">**Jimmy Bogard. Patrones de comando de dominio: validación**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-248">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="2c9b5-249">La canalización del proceso de comando: cómo desencadenar un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-249">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="2c9b5-250">La siguiente pregunta es cómo invocar un controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-250">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="2c9b5-251">Se podría llamar manualmente desde cada controlador de ASP.NET Core relacionado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-251">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="2c9b5-252">Sin embargo, el enfoque sería demasiado acoplado y no es lo ideal.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-252">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="2c9b5-253">Las otras dos opciones principales, que son las opciones recomendadas, son:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-253">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="2c9b5-254">A través de un artefacto de patrón de mediador en memoria.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-254">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="2c9b5-255">Con una cola de mensajes asincrónicos, entre los controladores y los controladores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-255">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="2c9b5-256">Mediante el patrón de mediador (en memoria) en la canalización de comandos</span><span class="sxs-lookup"><span data-stu-id="2c9b5-256">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="2c9b5-257">Como se muestra en la figura 9-21, en un enfoque CQRS utilizará un mediador inteligente, similar a un bus de memoria, que es lo suficientemente inteligente como para redirigir al controlador de comando correcta según el tipo del comando o DTO recibe.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-257">As shown in Figure 9-21, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="2c9b5-258">Las flechas de color negras únicas entre los componentes representan las dependencias entre objetos (en muchos casos, insertados mediante DI) con sus interacciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-258">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="2c9b5-259">**Figura 9-21**.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-259">**Figure 9-21**.</span></span> <span data-ttu-id="2c9b5-260">Mediante el patrón de mediador en curso en un único microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="2c9b5-260">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="2c9b5-261">Motivo por el que se relacione con el patrón de mediador es que en las aplicaciones empresariales, las solicitudes de procesamiento pueden resultar complicadas.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-261">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="2c9b5-262">Desea poder agregar un número abierto de preocupaciones transversales como registro, validaciones, auditoría y seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-262">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="2c9b5-263">En estos casos, puede basarse en una canalización de mediador (vea [patrón mediador](https://en.wikipedia.org/wiki/Mediator_pattern)) para proporcionar un medio de estos comportamientos adicionales o preocupaciones transversales.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-263">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="2c9b5-264">Un mediador es un objeto que encapsula el "cómo" de este proceso: coordina basada en estado de ejecución, se invoca la forma en que un controlador de comandos o la carga de proporcionar al controlador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-264">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="2c9b5-265">Con un componente de mediador puede aplicar preocupaciones transversales de forma centralizada y transparente aplicando decoradores (o [comportamientos de canalización](https://github.com/jbogard/MediatR/wiki/Behaviors) desde mediador v3).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-265">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since Mediator v3).</span></span> <span data-ttu-id="2c9b5-266">(Para obtener más información, consulte el [patrón Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-266">(For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).)</span></span>

<span data-ttu-id="2c9b5-267">Decoradores y comportamientos son similares a [de programación orientada a aspectos (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), solo se aplica a una canalización de proceso específico administrada por el componente de mediador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-267">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="2c9b5-268">Se aplican en función de aspectos en AOP que implementan preocupaciones transversales *Tejedores aspecto* insertado en tiempo de compilación o en función de intercepción de llamada de objeto.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-268">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="2c9b5-269">A veces se dice que ambos enfoques típicos de AOP funcionan "como"mágica", porque no es fácil ver cómo AOP realice su trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-269">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="2c9b5-270">Cuando se trabaja con graves problemas o errores, AOP puede ser difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-270">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="2c9b5-271">Por otro lado, estos comportamientos de decoradores son explícita aplicada únicamente en el contexto de mediador, por lo que la depuración es mucho más sencillo y predecible.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-271">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="2c9b5-272">Por ejemplo, en eShopOnContainers microservicio de ordenación, se implementan dos decoradores de ejemplo, un [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) clase y un [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) clase.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-272">For example, in the eShopOnContainers ordering microservice, we implemented two sample decorators, a [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class and a [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class.</span></span> <span data-ttu-id="2c9b5-273">Implementación del decorador se explica en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-273">The decorator’s implementation is explained in the next section.</span></span> <span data-ttu-id="2c9b5-274">Tenga en cuenta que en una versión futura, eShopOnContainers va a migrar a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) y mover a [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) en lugar de usar decoradores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-274">Note that in a future version, eShopOnContainers will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="2c9b5-275">Uso de colas de mensajes (fuera de proceso) de canalización del comando</span><span class="sxs-lookup"><span data-stu-id="2c9b5-275">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="2c9b5-276">Otra opción consiste en utilizar asincrónicos mensajes basados en los agentes o colas de mensajes, como se muestra en la figura 9-22.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-276">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-22.</span></span> <span data-ttu-id="2c9b5-277">Esta opción también se pueden combinar con el componente de mediador justo antes que el controlador de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-277">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="2c9b5-278">**Figura 9-22**.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-278">**Figure 9-22**.</span></span> <span data-ttu-id="2c9b5-279">Uso de las colas de mensajes (fuera de proceso y la comunicación entre procesos) con comandos CQRS</span><span class="sxs-lookup"><span data-stu-id="2c9b5-279">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="2c9b5-280">Mediante mensaje de colas para aceptar que los comandos pueden más complican la canalización del comando, ya que probablemente necesitará dividir la canalización en dos procesos conectados a través de la cola de mensajes externo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-280">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="2c9b5-281">No obstante, debe usarse si necesita ofrecer mayor escalabilidad y rendimiento en comparación con la mensajería asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-281">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="2c9b5-282">Tenga en cuenta que en el caso de la figura 9-22, el controlador simplemente envía el mensaje de comando en la cola y se devuelve.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-282">Consider that in the case of Figure 9-22, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="2c9b5-283">A continuación, los controladores de comando procesan los mensajes a su propio ritmo.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-283">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="2c9b5-284">Es decir, un gran ventaja de colas, la cola de mensajes puede actuar como un búfer en casos cuando hyper escalabilidad es necesario, como las existencias o cualquier otro escenario con un gran volumen de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-284">That is a great benefit of queues—the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="2c9b5-285">Sin embargo, debido a la naturaleza asincrónica de las colas de mensajes, debe saber cómo comunicarse con la aplicación cliente sobre el éxito o error del proceso del comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-285">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="2c9b5-286">Como norma, nunca debería utilizar los comandos de "desencadenar y omitir".</span><span class="sxs-lookup"><span data-stu-id="2c9b5-286">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="2c9b5-287">Cada aplicación empresarial necesita saber si un comando se ha procesado correctamente, o al menos valido y aceptado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-287">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="2c9b5-288">De este modo, poder responder al cliente después de validar un mensaje de comando que se envió a una cola asincrónica agrega complejidad al sistema, en comparación con un proceso de comando de proceso que devuelve el resultado de la operación después de ejecutar la transacción.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-288">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="2c9b5-289">Uso de colas, deberá devolver el resultado del proceso de comando a través de otros mensajes de resultado de la operación, lo que requiere comunicación personalizada y componentes adicionales en el sistema.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-289">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="2c9b5-290">Además, comandos asincrónicos son comandos unidireccionales, que, en muchos casos, quizás no sea necesario, tal y como se explica en el siguiente intercambio interesante entre Burtsev Alexey y Greg Young en un [conversación en línea](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="2c9b5-290">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="2c9b5-291">\[Burtsev Alexey\] encontrar una gran cantidad de código que los usuarios utilicen async gestión de comandos o un comando de una manera de mensajería sin ningún motivo para hacerlo (que no están haciendo una operación larga, no se ejecutan código asincrónico externo, que no crucen incluso aplicación límite de la utilización de bus de mensajes).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-291">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="2c9b5-292">¿Por qué agrega esta complejidad innecesaria?</span><span class="sxs-lookup"><span data-stu-id="2c9b5-292">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="2c9b5-293">Y, en realidad, no he visto un ejemplo de código CQRS con controladores de comandos de bloqueo hasta ahora, aunque funcionará correctamente en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-293">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="2c9b5-294">\[Greg Young\] \[... \] no existe un comando asincrónico; es realmente otro evento.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-294">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="2c9b5-295">Si debe aceptar lo que me envíe y genera un evento si no acepto, ya no es que me pide que realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-295">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="2c9b5-296">Se trata de usted dice que algo se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-296">It's you telling me something has been done.</span></span> <span data-ttu-id="2c9b5-297">Esto parece ser una pequeña diferencia en un primer momento, pero tiene muchas implicaciones.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-297">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="2c9b5-298">Comandos asincrónicos aumentan en gran medida la complejidad de un sistema, porque no hay ninguna manera sencilla para indicar errores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-298">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="2c9b5-299">Por lo tanto, comandos asincrónicos no se recomiendan distinto cuando se necesitan requisitos de escala o en casos especiales cuando se comunica el microservicios interno a través de mensajería.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-299">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="2c9b5-300">En esos casos, debe diseñar un sistema independiente de informes y la recuperación de errores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-300">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="2c9b5-301">En la versión inicial de eShopOnContainers, hemos decidido utilizar el procesamiento de comandos sincrónicos, se iniciaron en las solicitudes HTTP y controlado por el patrón de mediador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-301">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="2c9b5-302">Fácilmente que permite devolver el éxito o error del proceso, como en el [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementación.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-302">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="2c9b5-303">En cualquier caso, debe ser una decisión basada en los requisitos empresariales de su aplicación o de microservicio.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-303">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="2c9b5-304">Implementar la canalización del proceso de comando con un patrón de mediador (MediatR)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-304">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="2c9b5-305">Como una implementación de ejemplo, esta guía propone mediante la canalización de proceso basado en el patrón de mediador para ingesta de comando de unidad y enrutarlos, en memoria, los controladores de comando correcta.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-305">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and routing them, in memory, to the right command handlers.</span></span> <span data-ttu-id="2c9b5-306">La guía también propone aplicar decoradores o [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) para separar los problemas de corte del cruce.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-306">The guide also proposes applying decorators or [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="2c9b5-307">Para la implementación en .NET Core, hay varias bibliotecas de código abierto disponibles que implementan el patrón de mediador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-307">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="2c9b5-308">La biblioteca utilizada en esta guía es la [MediatR](https://github.com/jbogard/MediatR) biblioteca de código abierto (creado por Jimmy Bogard), pero puede usar otro enfoque.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-308">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="2c9b5-309">MediatR es una biblioteca pequeña y simple que permite procesar mensajes en la memoria como un comando, al aplicar decoradores o comportamientos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-309">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="2c9b5-310">Mediante el patrón de mediador le ayuda a reducir el acoplamiento y para aislar los problemas del trabajo solicitado, mientras se conecta automáticamente al controlador que lleva a cabo ese trabajo, en este caso, para controladores de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-310">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="2c9b5-311">Otra buena razón para utilizar el patrón de mediador se explica mediante Jimmy Bogard al revisar a esta guía:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-311">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="2c9b5-312">Creo que es posible que vale la pena mencionar aquí pruebas: proporciona una ventana coherente "nice" en el comportamiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-312">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="2c9b5-313">Solicitud, respuesta de salida. Hemos encontrado ese aspecto muy valioso en edificio que se comporta de forma coherente las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-313">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="2c9b5-314">En primer lugar, permítanos echar un vistazo al código de controlador donde realmente utilizaría el objeto mediador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-314">First, let us take a look to the controller code where you actually would use the mediator object.</span></span> <span data-ttu-id="2c9b5-315">Si no se usa el objeto mediador, necesitará insertar todas las dependencias para ese controlador cosas como un objeto de registrador y otros.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-315">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="2c9b5-316">Por lo tanto, el constructor sería bastante complicado.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-316">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="2c9b5-317">Por otro lado, si utiliza el objeto mediador, el constructor del controlador de puede ser mucho más sencillo, con unos pocos dependencias en lugar de muchas dependencias que tendría si hubiera uno por cada operación de corte del cruce, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-317">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies that you would have if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

<span data-ttu-id="2c9b5-318">Puede ver que el mediador proporciona un constructor de controlador de API Web limpio y eficiente.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-318">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="2c9b5-319">Además, dentro de los métodos de controlador, el código para enviar un comando al objeto mediador es prácticamente una línea:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-319">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

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

<span data-ttu-id="2c9b5-320">En orden para MediatR ser consciente de las clases de controlador de comandos, debe registrar las clases de mediador y las clases de controlador de comandos en el contenedor de IoC.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-320">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="2c9b5-321">De forma predeterminada, MediatR utiliza Autofac como el contenedor de IoC, pero también puede usar el contenedor de ASP.NET Core IoC integrado o cualquier otro contenedor compatible con MediatR.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-321">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="2c9b5-322">El código siguiente muestra cómo registrar los tipos y los comandos del mediador al utilizar los módulos de Autofac.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-322">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

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

<span data-ttu-id="2c9b5-323">Dado que cada controlador de comandos implementa la interfaz con IAsyncRequestHandler genérico&lt;T&gt; y, a continuación, se inspecciona el RegisteredAssemblyTypes de objeto, el controlador es capaz de relacionar cada comando con su controlador de comandos, ya que relación se indica en la clase CommandHandler, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-323">Because each command handler implements the interface with generic IAsyncRequestHandler&lt;T&gt; and then inspects the RegisteredAssemblyTypes object, the handler is able to relate each command with its command handler, because that relationship is stated in the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="2c9b5-324">Éste es el código que se correlacionan comandos con controladores de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-324">This is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="2c9b5-325">El controlador es simplemente una clase simple, pero hereda de RequestHandler&lt;T&gt;, y MediatR se asegura de se invoca con la carga correcta.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-325">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it gets invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a><span data-ttu-id="2c9b5-326">Aplicar preocupaciones transversales al procesar comandos con los patrones de mediador y decorador</span><span class="sxs-lookup"><span data-stu-id="2c9b5-326">Applying cross-cutting concerns when processing commands with the Mediator and Decorator patterns</span></span>

<span data-ttu-id="2c9b5-327">Hay otra cosa: poder transversales preocupaciones se aplican a la canalización de mediador.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-327">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="2c9b5-328">También puede ver al final del código del módulo de registro de Autofac cómo se está registrando un decorador escribe, en concreto, una clase LogDecorator personalizada.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-328">You can also see at the end of the Autofac registration module code how it is registering a decorator type, specifically, a custom LogDecorator class.</span></span>

<span data-ttu-id="2c9b5-329">De nuevo, tenga en cuenta que una versión futura de eShopOnContainers migrará a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) y mover a [comportamientos](https://github.com/jbogard/MediatR/wiki/Behaviors) en lugar de usar decoradores.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-329">Again, note that a future version of eShopOnContainers it will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

<span data-ttu-id="2c9b5-330">Que [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) clase puede implementarse como el código siguiente, que registra información sobre el controlador de comandos que se está ejecutando y si se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-330">That [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

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

<span data-ttu-id="2c9b5-331">Implementando esta clase decorador y decorando la canalización con él, todos los comandos que se procesan a través de MediatR iniciará sesión información sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-331">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="2c9b5-332">El eShopOnContainers orden microservicio también aplica un segundo decorador para validaciones básicas, el [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) clase que se basa en el [FluentValidation](https://github.com/JeremySkinner/FluentValidation) biblioteca, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-332">The eShopOnContainers ordering microservice also applies a second decorator for basic validations, the [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

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

<span data-ttu-id="2c9b5-333">A continuación, según la [FluentValidation](https://github.com/JeremySkinner/FluentValidation) biblioteca, hemos creado la validación de los datos pasados con CreateOrderCommand, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9b5-333">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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

<span data-ttu-id="2c9b5-334">Puede crear validaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-334">You could create additional validations.</span></span> <span data-ttu-id="2c9b5-335">Se trata de una forma muy limpia y elegante para implementar sus validaciones de comando.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-335">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="2c9b5-336">De forma similar, podría implementar otras decoradores para aspectos adicionales o preocupaciones transversales que desea aplicar a los comandos cuando su administración.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-336">In a similar way, you could implement other decorators for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2c9b5-337">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9b5-337">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="2c9b5-338">El patrón de mediador</span><span class="sxs-lookup"><span data-stu-id="2c9b5-338">The mediator pattern</span></span>

-   <span data-ttu-id="2c9b5-339">**Patrón de mediador**
    [*https://en.wikipedia.org/wiki/Mediator\_patrón*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-339">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="2c9b5-340">El patrón de decorador</span><span class="sxs-lookup"><span data-stu-id="2c9b5-340">The decorator pattern</span></span>

-   <span data-ttu-id="2c9b5-341">**Patrón de decorador**
    [*https://en.wikipedia.org/wiki/Decorator\_patrón*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-341">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="2c9b5-342">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-342">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="2c9b5-343">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="2c9b5-343">**MediatR.**</span></span> <span data-ttu-id="2c9b5-344">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-344">GitHub repo.</span></span>
    [<span data-ttu-id="2c9b5-345">*https://github.com/jbogard/MediatR*</span><span class="sxs-lookup"><span data-stu-id="2c9b5-345">*https://github.com/jbogard/MediatR*</span></span>](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="2c9b5-346">**CQRS con MediatR y AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-346">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="2c9b5-347">**Poner los controladores en una alimentación: entradas y comandos. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-347">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="2c9b5-348">**Abordar problemas de corte del cruce con una canalización mediador**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-348">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="2c9b5-349">**CQRS y REST: la coincidencia exacta**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-349">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="2c9b5-350">**Ejemplos de canalización MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-350">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="2c9b5-351">**Accesorios de prueba de segmento vertical para MediatR y ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*</span><span class="sxs-lookup"><span data-stu-id="2c9b5-351">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="2c9b5-352">**MediatR extensiones para la inyección de dependencia de Microsoft publicado**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-352">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="2c9b5-353">Validación fluida</span><span class="sxs-lookup"><span data-stu-id="2c9b5-353">Fluent validation</span></span>

-   <span data-ttu-id="2c9b5-354">**Jeremy Skinner. FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="2c9b5-354">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="2c9b5-355">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-355">GitHub repo.</span></span>
    [<span data-ttu-id="2c9b5-356">*https://github.com/JeremySkinner/FluentValidation*</span><span class="sxs-lookup"><span data-stu-id="2c9b5-356">*https://github.com/JeremySkinner/FluentValidation*</span></span>](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="2c9b5-357">[Anterior] (microservice-application-layer-web-api-design.md) [siguiente] (.. /Implement-Resilient-Applications/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-357">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
