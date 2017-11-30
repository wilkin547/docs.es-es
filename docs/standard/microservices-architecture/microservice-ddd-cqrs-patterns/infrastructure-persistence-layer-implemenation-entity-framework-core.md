---
title: "Implementación de la capa de persistencia de infraestructura con Entity Framework Core"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de la capa de persistencia de infraestructura con Entity Framework Core"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="c82d9-104">Implementación de la capa de persistencia de infraestructura con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c82d9-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="c82d9-105">Cuando se utiliza bases de datos relacionales, como SQL Server, Oracle o PostgreSQL, una solución recomendada es implementar la capa de persistencia basada en Entity Framework (EF).</span><span class="sxs-lookup"><span data-stu-id="c82d9-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="c82d9-106">EF es compatible con LINQ y proporciona objetos fuertemente tipados para el modelo, así como la persistencia simplificada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="c82d9-107">Entity Framework tiene una larga historia como parte de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c82d9-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="c82d9-108">Cuando se usa .NET Core, también debe usar Entity Framework Core, que se ejecuta en Windows o Linux de la misma manera que .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c82d9-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="c82d9-109">EF Core es una nueva escritura completa de Entity Framework, que se implementa con una superficie mucho menor y mejoras importantes en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c82d9-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="c82d9-110">Introducción a Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c82d9-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="c82d9-111">Núcleo de Entity Framework (EF) es una ligera, extensible, y tecnología de acceso de versión entre plataformas de los datos de Entity Framework populares.</span><span class="sxs-lookup"><span data-stu-id="c82d9-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="c82d9-112">Se introdujo con .NET Core en mid 2016.</span><span class="sxs-lookup"><span data-stu-id="c82d9-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="c82d9-113">Puesto que una introducción a EF Core ya está disponible en la documentación de Microsoft, en este caso simplemente proporcionamos vínculos a esa información.</span><span class="sxs-lookup"><span data-stu-id="c82d9-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c82d9-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c82d9-114">Additional resources</span></span>

-   <span data-ttu-id="c82d9-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="c82d9-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="c82d9-116">**Introducción a Entity Framework Core con Visual Studio y ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="c82d9-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="c82d9-117">**Clase DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="c82d9-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="c82d9-118">**Comparar EF Core & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="c82d9-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="c82d9-119">Infraestructura en Entity Framework Core desde una perspectiva DDD</span><span class="sxs-lookup"><span data-stu-id="c82d9-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="c82d9-120">Desde un punto de vista DDD, una capacidad importante de EF es la capacidad para utilizar las entidades de dominio, también se conoce en terminología EF como POCO *código basado en entidades*.</span><span class="sxs-lookup"><span data-stu-id="c82d9-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="c82d9-121">Si usa las entidades de dominio, las clases de modelo de dominio están que ignoran la persistencia, siguiendo el [omisión de persistencia](http://deviq.com/persistence-ignorance/) y [omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance) principios.</span><span class="sxs-lookup"><span data-stu-id="c82d9-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="c82d9-122">Por patrones DDD, debe encapsular el comportamiento de dominio y las reglas dentro de la clase de entidad, por lo que puede controlar las invariantes, validaciones y reglas al tener acceso a cualquier colección.</span><span class="sxs-lookup"><span data-stu-id="c82d9-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="c82d9-123">Por lo tanto, no es una buena práctica en DDD para permitir el acceso público a colecciones de secundarios entidades u objetos de valor.</span><span class="sxs-lookup"><span data-stu-id="c82d9-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="c82d9-124">En su lugar, desea exponer los métodos que controlan cómo y cuándo se pueden actualizar los campos y las colecciones de propiedades, y qué comportamiento y las acciones se realizarán cuando esto ocurre.</span><span class="sxs-lookup"><span data-stu-id="c82d9-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="c82d9-125">En EF Core 1.1, para satisfacer los requisitos de DDD puede tener campos sin formato en las entidades en lugar de propiedades con establecedores públicas y privadas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="c82d9-126">Si no desea que un campo de entidad sea accesible desde el exterior, solo puede crear el campo en lugar de una propiedad o atributo.</span><span class="sxs-lookup"><span data-stu-id="c82d9-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="c82d9-127">No hay ninguna necesidad de usar establecedores privados si prefiere este método de limpieza.</span><span class="sxs-lookup"><span data-stu-id="c82d9-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="c82d9-128">De forma similar, ahora puede tener acceso a las colecciones de solo lectura mediante el uso de una propiedad pública de tipo IEnumerable&lt;T&gt;, que está respaldado por un miembro de campo privado en la colección (como una lista&lt;&gt;) en el entidad que se basa en EF para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="c82d9-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="c82d9-129">Las versiones anteriores de Entity Framework requerían propiedades de colección para admitir ICollection&lt;T&gt;, lo que significaba que cualquier desarrollador que usa la clase de entidad primaria puede agregar o quitar elementos de sus colecciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c82d9-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="c82d9-130">Esa posibilidad sería con respecto a los modelos recomendados en DDD.</span><span class="sxs-lookup"><span data-stu-id="c82d9-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="c82d9-131">Puede usar una colección privada al exponer un objeto IEnumerable de sólo lectura, como se muestra en el ejemplo de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c82d9-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
        decimal unitPrice, decimal discount,
        string pictureUrl, int units = 1)
    {
        // Validation logic...
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="c82d9-132">Tenga en cuenta que solo puede acceder a la propiedad OrderItems como de solo lectura con lista&lt;&gt;. AsReadOnly().</span><span class="sxs-lookup"><span data-stu-id="c82d9-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="c82d9-133">Este método crea un contenedor de solo lectura alrededor de la lista privada para que esté protegido frente a las actualizaciones externas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="c82d9-134">Resulta mucho más económico que el uso del método ToList porque no tiene que copiar todos los elementos de una colección nueva; en su lugar, realiza una sola operación de asignación del montón para la instancia del contenedor.</span><span class="sxs-lookup"><span data-stu-id="c82d9-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="c82d9-135">Núcleo EF proporciona una manera de asignar el modelo de dominio a la base de datos físico sin que contaminen el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="c82d9-136">Es POCO .NET código puro, dado que la acción de asignación se implementa en la capa de persistencia.</span><span class="sxs-lookup"><span data-stu-id="c82d9-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="c82d9-137">En dicha acción de asignación, debe configurar la asignación de campos en base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="c82d9-138">En el siguiente ejemplo de un método OnModelCreating, el código resaltado indica EF Core para tener acceso a la propiedad OrderItems a través de su campo.</span><span class="sxs-lookup"><span data-stu-id="c82d9-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

<span data-ttu-id="c82d9-139">Cuando usas campos en lugar de propiedades, se conserva la entidad OrderItem como si tuviera una lista&lt;OrderItem&gt; propiedad.</span><span class="sxs-lookup"><span data-stu-id="c82d9-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="c82d9-140">Sin embargo, que expone un único descriptor de acceso (el método AddOrderItem) para agregar nuevos elementos en el orden.</span><span class="sxs-lookup"><span data-stu-id="c82d9-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="c82d9-141">Como resultado, comportamiento y los datos están unidos entre sí y serán coherentes a lo largo de cualquier código de aplicación que utiliza el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="c82d9-142">Implementación de los repositorios personalizados con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c82d9-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="c82d9-143">En el nivel de implementación, un repositorio es simplemente una clase con el código de persistencia de datos coordinada por una unidad de trabajo (DBContext en EF Core) al realizar actualizaciones, como se muestra en la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="c82d9-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;

        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

<span data-ttu-id="c82d9-144">Tenga en cuenta que la interfaz IBuyerRepository proviene de la capa del modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="c82d9-145">Sin embargo, la implementación del repositorio se realiza en la persistencia y el nivel de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="c82d9-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="c82d9-146">DbContext EF procede a través del constructor a través de la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="c82d9-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="c82d9-147">Estos se comparten entre varios repositorios dentro del mismo ámbito de solicitud HTTP, gracias a su duración predeterminada (ServiceLifetime.Scoped) en el contenedor de IoC (que puede también establecerse explícitamente con los servicios. AddDbContext&lt;&gt;).</span><span class="sxs-lookup"><span data-stu-id="c82d9-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="c82d9-148">Métodos que se implementan en un repositorio (actualizaciones o transacciones frente a las consultas)</span><span class="sxs-lookup"><span data-stu-id="c82d9-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="c82d9-149">Dentro de cada clase de repositorio, debe colocar los métodos de persistencia que actualizan el estado de entidades que contiene su agregado relacionados.</span><span class="sxs-lookup"><span data-stu-id="c82d9-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="c82d9-150">Recuerde que hay una relación uno a uno entre un agregado y su repositorio relacionado.</span><span class="sxs-lookup"><span data-stu-id="c82d9-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="c82d9-151">Tenga en cuenta que un objeto de entidad raíz agregada podría tienen las entidades secundarias dentro de su gráfico EF incrustados.</span><span class="sxs-lookup"><span data-stu-id="c82d9-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="c82d9-152">Por ejemplo, un comprador podría tener varios métodos de pago como las entidades secundarias relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="c82d9-153">Puesto que el enfoque para la ordenación microservicio en eShopOnContainers también se basa en CQS/CQRS, la mayoría de las consultas no se implementa en repositorios personalizados.</span><span class="sxs-lookup"><span data-stu-id="c82d9-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="c82d9-154">Los desarrolladores tienen la libertad para crear las consultas y combinaciones que necesitan para la capa de presentación sin las restricciones impuestas por agregados, los repositorios personalizados por agregado y DDD en general.</span><span class="sxs-lookup"><span data-stu-id="c82d9-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="c82d9-155">La mayoría de los repositorios personalizados sugeridos por esta guía tiene varias actualizaciones o métodos transaccionales, pero solo los métodos de consulta necesario para que se actualicen los datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="c82d9-156">Por ejemplo, el repositorio BuyerRepository implementa un método aplica findasync a, porque la aplicación necesita saber si existe un comprador determinado antes de crear un nuevo comprador relacionada con el orden.</span><span class="sxs-lookup"><span data-stu-id="c82d9-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="c82d9-157">Sin embargo, se implementan los métodos de consulta real para obtener los datos que se envían a las aplicaciones de cliente o de capa de presentación, como se ha mencionado, en las consultas CQRS basadas en consultas flexibles mediante Dapper.</span><span class="sxs-lookup"><span data-stu-id="c82d9-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="c82d9-158">Uso de un repositorio personalizado frente al uso de DbContext EF directamente</span><span class="sxs-lookup"><span data-stu-id="c82d9-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="c82d9-159">La clase DbContext de Entity Framework se basa en los patrones de unidad de trabajo y del repositorio y puede utilizarse directamente desde el código, como desde un controlador de MVC de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c82d9-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="c82d9-160">Que es la forma puede crear el código más simple, como se muestra en el microservicio de catálogo CRUD en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c82d9-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="c82d9-161">En casos donde desea que el código más simple posible, puede utilizar directamente la clase DbContext, igual que muchos desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="c82d9-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="c82d9-162">Sin embargo, implementar repositorios personalizados ofrece varias ventajas al implementar aplicaciones o microservicios más complejos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="c82d9-163">Los patrones de unidad de trabajo y del repositorio están diseñados para encapsular la capa de persistencia de infraestructura, por lo que se separa de la aplicación y los niveles de modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="c82d9-164">Implementar estos patrones puede facilitar el uso de repositorios ficticios simular el acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="c82d9-165">En la figura 9-18 puede ver las diferencias entre usar no repositorios (directamente mediante DbContext EF) frente al uso de repositorios que resulten más fácil simular los repositorios.</span><span class="sxs-lookup"><span data-stu-id="c82d9-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="c82d9-166">**Figura 9-18**.</span><span class="sxs-lookup"><span data-stu-id="c82d9-166">**Figure 9-18**.</span></span> <span data-ttu-id="c82d9-167">Uso de repositorios personalizados frente a un DbContext sin formato</span><span class="sxs-lookup"><span data-stu-id="c82d9-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="c82d9-168">Hay varias alternativas de simulación.</span><span class="sxs-lookup"><span data-stu-id="c82d9-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="c82d9-169">Puede simular repositorios solo o puede simular una unidad de trabajo completa.</span><span class="sxs-lookup"><span data-stu-id="c82d9-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="c82d9-170">Solo los repositorios de simulación normalmente es suficiente, y la complejidad para abstraer y simular una unidad de trabajo normalmente no es necesario.</span><span class="sxs-lookup"><span data-stu-id="c82d9-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="c82d9-171">Más adelante, cuando nos centramos en el nivel de aplicación, verá cómo funciona la inyección de dependencia en el núcleo de ASP.NET y cómo se implementa cuando el uso de repositorios.</span><span class="sxs-lookup"><span data-stu-id="c82d9-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="c82d9-172">En resumen, los repositorios personalizados le permiten probar más fácilmente el código con pruebas unitarias que no se ven afectadas por el estado de la capa de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="c82d9-173">Si ejecuta pruebas que también tienen acceso a la base de datos real a través de Entity Framework, no son pruebas unitarias pero las pruebas de integración, que son mucho más lentas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="c82d9-174">Si estaba usando DbContext directamente, la única opción que tendría sería ejecutar pruebas unitarias mediante el uso de un servidor en la memoria de SQL Server con datos predecible para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="c82d9-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="c82d9-175">No sería capaz de controlar objetos ficticios y datos falsos de la misma manera en el nivel de repositorio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="c82d9-176">Por supuesto, siempre puede probar los controladores MVC.</span><span class="sxs-lookup"><span data-stu-id="c82d9-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="c82d9-177">Duración de la instancia de DbContext EF y IUnitOfWork en el contenedor de IoC</span><span class="sxs-lookup"><span data-stu-id="c82d9-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="c82d9-178">El objeto de DbContext (expuesto como un objeto IUnitOfWork) deba compartirse entre varias bases de datos dentro del mismo ámbito de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="c82d9-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="c82d9-179">Por ejemplo, esto es cierto cuando la operación que se está ejecutando debe tratar con varios agregados o simplemente porque está usando varias instancias de repositorio.</span><span class="sxs-lookup"><span data-stu-id="c82d9-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="c82d9-180">También es importante mencionar que la interfaz de IUnitOfWork forma parte del dominio, no un tipo EF.</span><span class="sxs-lookup"><span data-stu-id="c82d9-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="c82d9-181">Para ello, la instancia del objeto DbContext debe tener su duración del servicio ServiceLifetime.Scoped.</span><span class="sxs-lookup"><span data-stu-id="c82d9-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="c82d9-182">Se trata de la duración predeterminada al registrar un DbContext con los servicios. AddDbContext en el contenedor de IoC desde el método ConfigureServices del archivo Startup.cs en el proyecto de ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="c82d9-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="c82d9-183">Esto se ilustra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c82d9-183">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
    .AddDbContext<OrderingContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

<span data-ttu-id="c82d9-184">No se debe configurar el modo de creación de instancias de DbContext como ServiceLifetime.Transient o ServiceLifetime.Singleton.</span><span class="sxs-lookup"><span data-stu-id="c82d9-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="c82d9-185">La duración de la instancia de repositorio en el contenedor de IoC</span><span class="sxs-lookup"><span data-stu-id="c82d9-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="c82d9-186">De forma similar, duración del repositorio normalmente se debe establecer como ámbito (InstancePerLifetimeScope en Autofac).</span><span class="sxs-lookup"><span data-stu-id="c82d9-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="c82d9-187">También podría ser transitorio (InstancePerDependency en Autofac), pero el servicio será más eficaz en lo que respecta memoria cuando se usa la duración de ámbito.</span><span class="sxs-lookup"><span data-stu-id="c82d9-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="c82d9-188">Tenga en cuenta que con la duración de singleton para el repositorio podría producir problemas de simultaneidad grave cuando su DbContext está establecida en el ámbito de duración (InstancePerLifetimeScope) (las duraciones predeterminadas para un DBContext).</span><span class="sxs-lookup"><span data-stu-id="c82d9-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c82d9-189">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c82d9-189">Additional resources</span></span>

-   <span data-ttu-id="c82d9-190">**Implementar el repositorio y una unidad de patrones de trabajo en una aplicación de ASP.NET MVC**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="c82d9-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="c82d9-191">**Jonathan Allen. Estrategias de implementación para el repositorio de patrón con Entity Framework, Dapper y la cadena**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="c82d9-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="c82d9-192">**Cesar de la Torre. Comparar las duraciones de servicio de contenedor de ASP.NET Core IoC con ámbitos de instancia del contenedor de IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="c82d9-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="c82d9-193">Asignación de tabla</span><span class="sxs-lookup"><span data-stu-id="c82d9-193">Table mapping</span></span>

<span data-ttu-id="c82d9-194">Asignación de tabla identifica los datos de la tabla va a consultar de y se guarda en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="c82d9-195">Previamente se ha visto cómo entidades de dominio (por ejemplo, un dominio de producto o el orden) se pueden usar para generar un esquema de base de datos relacionada.</span><span class="sxs-lookup"><span data-stu-id="c82d9-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="c82d9-196">EF fuertemente está diseñado basándose en el concepto de *convenciones*.</span><span class="sxs-lookup"><span data-stu-id="c82d9-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="c82d9-197">Dirección a convenciones preguntas como "¿qué el nombre de una tabla puede?"</span><span class="sxs-lookup"><span data-stu-id="c82d9-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="c82d9-198">o "¿qué propiedad es la clave principal?"</span><span class="sxs-lookup"><span data-stu-id="c82d9-198">or “What property is the primary key?”</span></span> <span data-ttu-id="c82d9-199">Convenciones normalmente se basan en nombres convencionales, por ejemplo, es habitual para la clave principal que es una propiedad que termina por identificador.</span><span class="sxs-lookup"><span data-stu-id="c82d9-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="c82d9-200">Por convención, cada entidad se configurará para asignar a una tabla con el mismo nombre que el DbSet&lt;TEntity&gt; que expone la entidad en el contexto derivada.</span><span class="sxs-lookup"><span data-stu-id="c82d9-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="c82d9-201">Si no hay DbSet&lt;TEntity&gt; valor es proporcionado para la entidad determinada, se usa el nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="c82d9-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="c82d9-202">Anotaciones de datos frente a la API fluida</span><span class="sxs-lookup"><span data-stu-id="c82d9-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="c82d9-203">Hay muchas convenciones EF núcleos adicionales, y la mayoría de ellos se puede cambiar mediante las anotaciones de datos o la API fluida, implementa dentro del método OnModelCreating.</span><span class="sxs-lookup"><span data-stu-id="c82d9-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="c82d9-204">Las anotaciones de datos deben utilizarse en las clases del modelo de entidad, que es una manera más intrusiva desde un punto de vista DDD.</span><span class="sxs-lookup"><span data-stu-id="c82d9-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="c82d9-205">Esto es porque se que contaminen el modelo con las anotaciones de datos relacionadas con la base de datos de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="c82d9-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="c82d9-206">Por otro lado, la API fluida es una manera cómoda de cambiar la mayoría de las convenciones y asignaciones en el nivel de infraestructura de persistencia de datos, por lo que será el modelo de entidad limpia y desacoplada de la infraestructura de persistencia.</span><span class="sxs-lookup"><span data-stu-id="c82d9-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="c82d9-207">API fluida y el método OnModelCreating</span><span class="sxs-lookup"><span data-stu-id="c82d9-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="c82d9-208">Como se mencionó, con el fin de cambiar las convenciones y asignaciones, puede usar el método OnModelCreating en la clase DbContext.</span><span class="sxs-lookup"><span data-stu-id="c82d9-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="c82d9-209">En el ejemplo siguiente se muestra cómo hacer esto en la ordenación microservicio en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c82d9-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

<span data-ttu-id="c82d9-210">Puede establecer todas las asignaciones de la API fluida dentro del método OnModelCreating mismo, pero es aconsejable crear particiones que el código y tiene varios submethods, uno por cada entidad, tal como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c82d9-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="c82d9-211">Para los modelos de grandes tamaño, incluso puede ser aconsejable tener archivos de código fuente independiente (clases estáticas) para configurar los tipos de entidad diferentes.</span><span class="sxs-lookup"><span data-stu-id="c82d9-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="c82d9-212">El código en el ejemplo es explícito.</span><span class="sxs-lookup"><span data-stu-id="c82d9-212">The code in the example is explicit.</span></span> <span data-ttu-id="c82d9-213">Sin embargo, las convenciones de EF Core realizar la mayoría de esto automáticamente, por lo que el código real que tendría que escribir lograr lo mismo sería mucho más pequeño.</span><span class="sxs-lookup"><span data-stu-id="c82d9-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="c82d9-214">El algoritmo de Hi/Lo EF núcleo</span><span class="sxs-lookup"><span data-stu-id="c82d9-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="c82d9-215">Un aspecto interesante de código en el ejemplo anterior es que utiliza la [Hi/Lo algoritmo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) como la estrategia de generación de claves.</span><span class="sxs-lookup"><span data-stu-id="c82d9-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="c82d9-216">El algoritmo de Hi/Lo es útil cuando necesita claves únicas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="c82d9-217">Como un resumen, el algoritmo Hi-Lo asigna identificadores únicos a filas de la tabla mientras no función almacena la fila en la base de datos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c82d9-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="c82d9-218">Esto le permite empezar a usar los identificadores de forma inmediata, como sucede con la base de datos secuencial normal identificadores.</span><span class="sxs-lookup"><span data-stu-id="c82d9-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="c82d9-219">El algoritmo de Hi/Lo describe un mecanismo para la generación de identificadores seguros en el lado del cliente en lugar de en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="c82d9-220">*Seguro* en este contexto significa sin conflictos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="c82d9-221">Este algoritmo es interesante por estos motivos:</span><span class="sxs-lookup"><span data-stu-id="c82d9-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="c82d9-222">No se interrumpe el patrón de la unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c82d9-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="c82d9-223">No requerir viajes de ida y los generadores de secuencias de manera hacer en otros DBMS.</span><span class="sxs-lookup"><span data-stu-id="c82d9-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="c82d9-224">Genera un identificador legible humano, a diferencia de las técnicas que utilizan identificadores GUID.</span><span class="sxs-lookup"><span data-stu-id="c82d9-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="c82d9-225">EF Core es compatible con [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con el método ForSqlServerUseSequenceHiLo, tal como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c82d9-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="c82d9-226">Asignar campos en lugar de propiedades</span><span class="sxs-lookup"><span data-stu-id="c82d9-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="c82d9-227">Con la característica de EF Core 1.1 que asigna las columnas a campos, es posible que no utilizan las propiedades de la clase de entidad y para asignar columnas de una tabla a campos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="c82d9-228">Un uso común para los sería campos privados para cualquier estado interno que no es necesario tener acceso desde fuera de la entidad.</span><span class="sxs-lookup"><span data-stu-id="c82d9-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="c82d9-229">EF 1.1 es compatible con un método para asignar un campo sin una propiedad relacionada a una columna de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="c82d9-230">Para hacer esto con campos únicos o también con las colecciones, como una lista&lt; &gt; campo.</span><span class="sxs-lookup"><span data-stu-id="c82d9-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="c82d9-231">Este punto se mencionó anteriormente cuando analizamos las clases del modelo de dominio de modelado, pero aquí puede ver cómo se realiza la asignación con la configuración de PropertyAccessMode.Field resaltada en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="c82d9-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="c82d9-232">Usar propiedades de instantáneas en objetos de valor para identificadores ocultos en el nivel de infraestructura</span><span class="sxs-lookup"><span data-stu-id="c82d9-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="c82d9-233">Propiedades de sombra de EF Core son propiedades que no existen en el modelo de clase de entidad.</span><span class="sxs-lookup"><span data-stu-id="c82d9-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="c82d9-234">Los valores y Estados de estas propiedades se mantienen exclusivamente en el [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) clase en el nivel de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="c82d9-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="c82d9-235">Desde un punto de vista DDD, reemplazar propiedades son una manera cómoda para implementar objetos de valor ocultando el identificador como una clave principal de propiedad de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="c82d9-236">Esto es importante, porque un objeto de valor no debe tener la identidad (al menos, no es necesario el identificador en el nivel de modelo de dominio cuando la forma de objetos de valor).</span><span class="sxs-lookup"><span data-stu-id="c82d9-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="c82d9-237">El punto aquí es que, a partir de la versión actual de núcleo de EF, Core EF no tiene una forma de implementar objetos de valor como [tipos complejos](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), ya que es posible en EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="c82d9-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="c82d9-238">Para eso están actualmente debe implementar un objeto de valor como un conjunto de entidades con un identificador oculto (clave principal) como una propiedad de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="c82d9-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="c82d9-239">Como puede ver en la [objeto de valor de dirección](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) en eShopOnContainers, en el modelo de dirección no verá un Id.:</span><span class="sxs-lookup"><span data-stu-id="c82d9-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

<span data-ttu-id="c82d9-240">Pero tras los bastidores, es necesario proporcionar un identificador para que EF Core es capaz de almacenar estos datos en las tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c82d9-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="c82d9-241">Se establece en el método ConfigureAddress de la [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) clase en el nivel de infraestructura, por lo que no contamina el modelo de dominio con código de infraestructura EF.</span><span class="sxs-lookup"><span data-stu-id="c82d9-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a><span data-ttu-id="c82d9-242">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c82d9-242">Additional resources</span></span>

-   <span data-ttu-id="c82d9-243">**Asignación de tabla**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="c82d9-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="c82d9-244">**Use HiLo para generar claves con Entity Framework Core**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="c82d9-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="c82d9-245">**Realizar una copia de los campos**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="c82d9-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="c82d9-246">**Steve Smith. Encapsula las colecciones en Entity Framework Core**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="c82d9-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="c82d9-247">**Ocultar propiedades**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="c82d9-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c82d9-248">[Anterior] (infraestructura-persistencia-layer-design.md) [siguiente] (nosql-base de datos de persistencia-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="c82d9-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
