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
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementación de la capa de persistencia de infraestructura con Entity Framework Core

Cuando se utiliza bases de datos relacionales, como SQL Server, Oracle o PostgreSQL, una solución recomendada es implementar la capa de persistencia basada en Entity Framework (EF). EF es compatible con LINQ y proporciona objetos fuertemente tipados para el modelo, así como la persistencia simplificada en la base de datos.

Entity Framework tiene una larga historia como parte de .NET Framework. Cuando se usa .NET Core, también debe usar Entity Framework Core, que se ejecuta en Windows o Linux de la misma manera que .NET Core. EF Core es una nueva escritura completa de Entity Framework, que se implementa con una superficie mucho menor y mejoras importantes en el rendimiento.

## <a name="introduction-to-entity-framework-core"></a>Introducción a Entity Framework Core

Núcleo de Entity Framework (EF) es una ligera, extensible, y tecnología de acceso de versión entre plataformas de los datos de Entity Framework populares. Se introdujo con .NET Core en mid 2016.

Puesto que una introducción a EF Core ya está disponible en la documentación de Microsoft, en este caso simplemente proporcionamos vínculos a esa información.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)

-   **Introducción a Entity Framework Core con Visual Studio y ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)

-   **Clase DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)

-   **Comparar EF Core & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Infraestructura en Entity Framework Core desde una perspectiva DDD

Desde un punto de vista DDD, una capacidad importante de EF es la capacidad para utilizar las entidades de dominio, también se conoce en terminología EF como POCO *código basado en entidades*. Si usa las entidades de dominio, las clases de modelo de dominio están que ignoran la persistencia, siguiendo el [omisión de persistencia](http://deviq.com/persistence-ignorance/) y [omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance) principios.

Por patrones DDD, debe encapsular el comportamiento de dominio y las reglas dentro de la clase de entidad, por lo que puede controlar las invariantes, validaciones y reglas al tener acceso a cualquier colección. Por lo tanto, no es una buena práctica en DDD para permitir el acceso público a colecciones de secundarios entidades u objetos de valor. En su lugar, desea exponer los métodos que controlan cómo y cuándo se pueden actualizar los campos y las colecciones de propiedades, y qué comportamiento y las acciones se realizarán cuando esto ocurre.

En EF Core 1.1, para satisfacer los requisitos de DDD puede tener campos sin formato en las entidades en lugar de propiedades con establecedores públicas y privadas. Si no desea que un campo de entidad sea accesible desde el exterior, solo puede crear el campo en lugar de una propiedad o atributo. No hay ninguna necesidad de usar establecedores privados si prefiere este método de limpieza.

De forma similar, ahora puede tener acceso a las colecciones de solo lectura mediante el uso de una propiedad pública de tipo IEnumerable&lt;T&gt;, que está respaldado por un miembro de campo privado en la colección (como una lista&lt;&gt;) en el entidad que se basa en EF para la persistencia. Las versiones anteriores de Entity Framework requerían propiedades de colección para admitir ICollection&lt;T&gt;, lo que significaba que cualquier desarrollador que usa la clase de entidad primaria puede agregar o quitar elementos de sus colecciones de propiedades. Esa posibilidad sería con respecto a los modelos recomendados en DDD.

Puede usar una colección privada al exponer un objeto IEnumerable de sólo lectura, como se muestra en el ejemplo de código siguiente:

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

Tenga en cuenta que solo puede acceder a la propiedad OrderItems como de solo lectura con lista&lt;&gt;. AsReadOnly(). Este método crea un contenedor de solo lectura alrededor de la lista privada para que esté protegido frente a las actualizaciones externas. Resulta mucho más económico que el uso del método ToList porque no tiene que copiar todos los elementos de una colección nueva; en su lugar, realiza una sola operación de asignación del montón para la instancia del contenedor.

Núcleo EF proporciona una manera de asignar el modelo de dominio a la base de datos físico sin que contaminen el modelo de dominio. Es POCO .NET código puro, dado que la acción de asignación se implementa en la capa de persistencia. En dicha acción de asignación, debe configurar la asignación de campos en base de datos. En el siguiente ejemplo de un método OnModelCreating, el código resaltado indica EF Core para tener acceso a la propiedad OrderItems a través de su campo.

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

Cuando usas campos en lugar de propiedades, se conserva la entidad OrderItem como si tuviera una lista&lt;OrderItem&gt; propiedad. Sin embargo, que expone un único descriptor de acceso (el método AddOrderItem) para agregar nuevos elementos en el orden. Como resultado, comportamiento y los datos están unidos entre sí y serán coherentes a lo largo de cualquier código de aplicación que utiliza el modelo de dominio.

## <a name="implementing-custom-repositories-with-entity-framework-core"></a>Implementación de los repositorios personalizados con Entity Framework Core

En el nivel de implementación, un repositorio es simplemente una clase con el código de persistencia de datos coordinada por una unidad de trabajo (DBContext en EF Core) al realizar actualizaciones, como se muestra en la siguiente clase:

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

Tenga en cuenta que la interfaz IBuyerRepository proviene de la capa del modelo de dominio. Sin embargo, la implementación del repositorio se realiza en la persistencia y el nivel de infraestructura.

DbContext EF procede a través del constructor a través de la inserción de dependencias. Estos se comparten entre varios repositorios dentro del mismo ámbito de solicitud HTTP, gracias a su duración predeterminada (ServiceLifetime.Scoped) en el contenedor de IoC (que puede también establecerse explícitamente con los servicios. AddDbContext&lt;&gt;).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Métodos que se implementan en un repositorio (actualizaciones o transacciones frente a las consultas)

Dentro de cada clase de repositorio, debe colocar los métodos de persistencia que actualizan el estado de entidades que contiene su agregado relacionados. Recuerde que hay una relación uno a uno entre un agregado y su repositorio relacionado. Tenga en cuenta que un objeto de entidad raíz agregada podría tienen las entidades secundarias dentro de su gráfico EF incrustados. Por ejemplo, un comprador podría tener varios métodos de pago como las entidades secundarias relacionadas.

Puesto que el enfoque para la ordenación microservicio en eShopOnContainers también se basa en CQS/CQRS, la mayoría de las consultas no se implementa en repositorios personalizados. Los desarrolladores tienen la libertad para crear las consultas y combinaciones que necesitan para la capa de presentación sin las restricciones impuestas por agregados, los repositorios personalizados por agregado y DDD en general. La mayoría de los repositorios personalizados sugeridos por esta guía tiene varias actualizaciones o métodos transaccionales, pero solo los métodos de consulta necesario para que se actualicen los datos. Por ejemplo, el repositorio BuyerRepository implementa un método aplica findasync a, porque la aplicación necesita saber si existe un comprador determinado antes de crear un nuevo comprador relacionada con el orden.

Sin embargo, se implementan los métodos de consulta real para obtener los datos que se envían a las aplicaciones de cliente o de capa de presentación, como se ha mencionado, en las consultas CQRS basadas en consultas flexibles mediante Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Uso de un repositorio personalizado frente al uso de DbContext EF directamente

La clase DbContext de Entity Framework se basa en los patrones de unidad de trabajo y del repositorio y puede utilizarse directamente desde el código, como desde un controlador de MVC de ASP.NET Core. Que es la forma puede crear el código más simple, como se muestra en el microservicio de catálogo CRUD en eShopOnContainers. En casos donde desea que el código más simple posible, puede utilizar directamente la clase DbContext, igual que muchos desarrolladores.

Sin embargo, implementar repositorios personalizados ofrece varias ventajas al implementar aplicaciones o microservicios más complejos. Los patrones de unidad de trabajo y del repositorio están diseñados para encapsular la capa de persistencia de infraestructura, por lo que se separa de la aplicación y los niveles de modelo de dominio. Implementar estos patrones puede facilitar el uso de repositorios ficticios simular el acceso a la base de datos.

En la figura 9-18 puede ver las diferencias entre usar no repositorios (directamente mediante DbContext EF) frente al uso de repositorios que resulten más fácil simular los repositorios.

![](./media/image19.png)

**Figura 9-18**. Uso de repositorios personalizados frente a un DbContext sin formato

Hay varias alternativas de simulación. Puede simular repositorios solo o puede simular una unidad de trabajo completa. Solo los repositorios de simulación normalmente es suficiente, y la complejidad para abstraer y simular una unidad de trabajo normalmente no es necesario.

Más adelante, cuando nos centramos en el nivel de aplicación, verá cómo funciona la inyección de dependencia en el núcleo de ASP.NET y cómo se implementa cuando el uso de repositorios.

En resumen, los repositorios personalizados le permiten probar más fácilmente el código con pruebas unitarias que no se ven afectadas por el estado de la capa de datos. Si ejecuta pruebas que también tienen acceso a la base de datos real a través de Entity Framework, no son pruebas unitarias pero las pruebas de integración, que son mucho más lentas.

Si estaba usando DbContext directamente, la única opción que tendría sería ejecutar pruebas unitarias mediante el uso de un servidor en la memoria de SQL Server con datos predecible para las pruebas unitarias. No sería capaz de controlar objetos ficticios y datos falsos de la misma manera en el nivel de repositorio. Por supuesto, siempre puede probar los controladores MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Duración de la instancia de DbContext EF y IUnitOfWork en el contenedor de IoC

El objeto de DbContext (expuesto como un objeto IUnitOfWork) deba compartirse entre varias bases de datos dentro del mismo ámbito de la solicitud HTTP. Por ejemplo, esto es cierto cuando la operación que se está ejecutando debe tratar con varios agregados o simplemente porque está usando varias instancias de repositorio. También es importante mencionar que la interfaz de IUnitOfWork forma parte del dominio, no un tipo EF.

Para ello, la instancia del objeto DbContext debe tener su duración del servicio ServiceLifetime.Scoped. Se trata de la duración predeterminada al registrar un DbContext con los servicios. AddDbContext en el contenedor de IoC desde el método ConfigureServices del archivo Startup.cs en el proyecto de ASP.NET Core Web API. Esto se ilustra en el código siguiente:

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

No se debe configurar el modo de creación de instancias de DbContext como ServiceLifetime.Transient o ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>La duración de la instancia de repositorio en el contenedor de IoC

De forma similar, duración del repositorio normalmente se debe establecer como ámbito (InstancePerLifetimeScope en Autofac). También podría ser transitorio (InstancePerDependency en Autofac), pero el servicio será más eficaz en lo que respecta memoria cuando se usa la duración de ámbito.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Tenga en cuenta que con la duración de singleton para el repositorio podría producir problemas de simultaneidad grave cuando su DbContext está establecida en el ámbito de duración (InstancePerLifetimeScope) (las duraciones predeterminadas para un DBContext).

#### <a name="additional-resources"></a>Recursos adicionales

-   **Implementar el repositorio y una unidad de patrones de trabajo en una aplicación de ASP.NET MVC**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

-   **Jonathan Allen. Estrategias de implementación para el repositorio de patrón con Entity Framework, Dapper y la cadena**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)

-   **Cesar de la Torre. Comparar las duraciones de servicio de contenedor de ASP.NET Core IoC con ámbitos de instancia del contenedor de IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="table-mapping"></a>Asignación de tabla

Asignación de tabla identifica los datos de la tabla va a consultar de y se guarda en la base de datos. Previamente se ha visto cómo entidades de dominio (por ejemplo, un dominio de producto o el orden) se pueden usar para generar un esquema de base de datos relacionada. EF fuertemente está diseñado basándose en el concepto de *convenciones*. Dirección a convenciones preguntas como "¿qué el nombre de una tabla puede?" o "¿qué propiedad es la clave principal?" Convenciones normalmente se basan en nombres convencionales, por ejemplo, es habitual para la clave principal que es una propiedad que termina por identificador.

Por convención, cada entidad se configurará para asignar a una tabla con el mismo nombre que el DbSet&lt;TEntity&gt; que expone la entidad en el contexto derivada. Si no hay DbSet&lt;TEntity&gt; valor es proporcionado para la entidad determinada, se usa el nombre de clase.

### <a name="data-annotations-versus-fluent-api"></a>Anotaciones de datos frente a la API fluida

Hay muchas convenciones EF núcleos adicionales, y la mayoría de ellos se puede cambiar mediante las anotaciones de datos o la API fluida, implementa dentro del método OnModelCreating.

Las anotaciones de datos deben utilizarse en las clases del modelo de entidad, que es una manera más intrusiva desde un punto de vista DDD. Esto es porque se que contaminen el modelo con las anotaciones de datos relacionadas con la base de datos de la infraestructura. Por otro lado, la API fluida es una manera cómoda de cambiar la mayoría de las convenciones y asignaciones en el nivel de infraestructura de persistencia de datos, por lo que será el modelo de entidad limpia y desacoplada de la infraestructura de persistencia.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>API fluida y el método OnModelCreating

Como se mencionó, con el fin de cambiar las convenciones y asignaciones, puede usar el método OnModelCreating en la clase DbContext. En el ejemplo siguiente se muestra cómo hacer esto en la ordenación microservicio en eShopOnContainers.

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

Puede establecer todas las asignaciones de la API fluida dentro del método OnModelCreating mismo, pero es aconsejable crear particiones que el código y tiene varios submethods, uno por cada entidad, tal como se muestra en el ejemplo. Para los modelos de grandes tamaño, incluso puede ser aconsejable tener archivos de código fuente independiente (clases estáticas) para configurar los tipos de entidad diferentes.

El código en el ejemplo es explícito. Sin embargo, las convenciones de EF Core realizar la mayoría de esto automáticamente, por lo que el código real que tendría que escribir lograr lo mismo sería mucho más pequeño.

### <a name="the-hilo-algorithm-in-ef-core"></a>El algoritmo de Hi/Lo EF núcleo

Un aspecto interesante de código en el ejemplo anterior es que utiliza la [Hi/Lo algoritmo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) como la estrategia de generación de claves.

El algoritmo de Hi/Lo es útil cuando necesita claves únicas. Como un resumen, el algoritmo Hi-Lo asigna identificadores únicos a filas de la tabla mientras no función almacena la fila en la base de datos inmediatamente. Esto le permite empezar a usar los identificadores de forma inmediata, como sucede con la base de datos secuencial normal identificadores.

El algoritmo de Hi/Lo describe un mecanismo para la generación de identificadores seguros en el lado del cliente en lugar de en la base de datos. *Seguro* en este contexto significa sin conflictos. Este algoritmo es interesante por estos motivos:

-   No se interrumpe el patrón de la unidad de trabajo.

-   No requerir viajes de ida y los generadores de secuencias de manera hacer en otros DBMS.

-   Genera un identificador legible humano, a diferencia de las técnicas que utilizan identificadores GUID.

EF Core es compatible con [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con el método ForSqlServerUseSequenceHiLo, tal como se muestra en el ejemplo anterior.

### <a name="mapping-fields-instead-of-properties"></a>Asignar campos en lugar de propiedades

Con la característica de EF Core 1.1 que asigna las columnas a campos, es posible que no utilizan las propiedades de la clase de entidad y para asignar columnas de una tabla a campos. Un uso común para los sería campos privados para cualquier estado interno que no es necesario tener acceso desde fuera de la entidad.

EF 1.1 es compatible con un método para asignar un campo sin una propiedad relacionada a una columna de la base de datos. Para hacer esto con campos únicos o también con las colecciones, como una lista&lt; &gt; campo. Este punto se mencionó anteriormente cuando analizamos las clases del modelo de dominio de modelado, pero aquí puede ver cómo se realiza la asignación con la configuración de PropertyAccessMode.Field resaltada en el código anterior.

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a>Usar propiedades de instantáneas en objetos de valor para identificadores ocultos en el nivel de infraestructura

Propiedades de sombra de EF Core son propiedades que no existen en el modelo de clase de entidad. Los valores y Estados de estas propiedades se mantienen exclusivamente en el [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) clase en el nivel de infraestructura.

Desde un punto de vista DDD, reemplazar propiedades son una manera cómoda para implementar objetos de valor ocultando el identificador como una clave principal de propiedad de instantáneas. Esto es importante, porque un objeto de valor no debe tener la identidad (al menos, no es necesario el identificador en el nivel de modelo de dominio cuando la forma de objetos de valor). El punto aquí es que, a partir de la versión actual de núcleo de EF, Core EF no tiene una forma de implementar objetos de valor como [tipos complejos](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), ya que es posible en EF 6.x. Para eso están actualmente debe implementar un objeto de valor como un conjunto de entidades con un identificador oculto (clave principal) como una propiedad de instantáneas.

Como puede ver en la [objeto de valor de dirección](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) en eShopOnContainers, en el modelo de dirección no verá un Id.:

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

Pero tras los bastidores, es necesario proporcionar un identificador para que EF Core es capaz de almacenar estos datos en las tablas de base de datos. Se establece en el método ConfigureAddress de la [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) clase en el nivel de infraestructura, por lo que no contamina el modelo de dominio con código de infraestructura EF.

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

#### <a name="additional-resources"></a>Recursos adicionales

-   **Asignación de tabla**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)

-   **Use HiLo para generar claves con Entity Framework Core**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)

-   **Realizar una copia de los campos**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)

-   **Steve Smith. Encapsula las colecciones en Entity Framework Core**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)

-   **Ocultar propiedades**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)


>[!div class="step-by-step"]
[Anterior] (infraestructura-persistencia-layer-design.md) [siguiente] (nosql-base de datos de persistencia-infrastructure.md)
