---
title: Implementación del nivel de persistencia de la infraestructura con Entity Framework Core
description: Arquitectura de microservicios de .NET para aplicaciones de .NET en contenedor | Información sobre la implementación del nivel de persistencia de la infraestructura con Entity Framework Core.
ms.date: 01/30/2020
ms.openlocfilehash: 7ab3be0d6a5affda478f7ec8f6c356571e304759
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805483"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementación del nivel de persistencia de infraestructura con Entity Framework Core

Al utilizar bases de datos relacionales, como SQL Server, Oracle o PostgreSQL, se recomienda implementar el nivel de persistencia basado en Entity Framework (EF). EF es compatible con LINQ y proporciona objetos fuertemente tipados para el modelo, así como una persistencia simplificada en la base de datos.

Entity Framework hace mucho tiempo que forma parte de .NET Framework. Al utilizar .NET Core, también debe usar Entity Framework Core, que se ejecuta en Windows o Linux de la misma manera que .NET Core. EF Core es una reescritura completa de Entity Framework, que se implementa con una superficie mucho menor y con mejoras importantes en el rendimiento.

## <a name="introduction-to-entity-framework-core"></a>Introducción a Entity Framework Core

Entity Framework (EF) Core es una versión ligera, extensible y multiplataforma de la popular tecnología de acceso a datos Entity Framework. Se introdujo con .NET Core a mediados de 2016.

Puesto que en la documentación de Microsoft ya hay una introducción a EF Core, aquí nos limitaremos a proporcionar vínculos a dicha información.

### <a name="additional-resources"></a>Recursos adicionales

- **Entity Framework Core** \
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- **ASP.NET Core MVC con EF Core: serie de tutoriales** \
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- **Clase DbContext** \
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- **Comparación de EF Core y EF6** \
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Infraestructura en Entity Framework Core desde una perspectiva DDD

Desde un punto de vista DDD, una capacidad importante de EF es la de utilizar las entidades de dominio POCO, también conocidas en terminología de EF como *entidades Code First* de POCO. Si usa las entidades de dominio POCO, las clases de modelo de dominio ignoran la persistencia, siguiendo los principios de [omisión de persistencia](https://deviq.com/persistence-ignorance/) y [omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance).

Según los patrones DDD, debe encapsular las reglas y el comportamiento de dominio dentro de la misma clase de entidad, por lo que puede controlar las invariantes, las validaciones y las reglas al acceder a cualquier colección. Por lo tanto, en DDD no se recomienda permitir el acceso público a colecciones de entidades secundarias u objetos de valor. En cambio, es interesante exponer métodos que controlen cómo y cuándo se pueden actualizar los campos y las colecciones de propiedades, y qué comportamiento y qué acciones se producirán cuando esto ocurra.

Desde la versión 1.1 de EF Core, para satisfacer estos requisitos de DDD, puede tener campos sin formato en las entidades en lugar de propiedades públicas. Si no quiere que se pueda acceder a un campo de entidad desde el exterior, solo puede crear un campo o un atributo en vez de una propiedad. También puede utilizar establecedores de propiedades privadas.

De forma parecida, ahora puede tener acceso de solo lectura a las colecciones usando una propiedad pública del tipo `IReadOnlyCollection<T>`, que está respaldada por un miembro de campo privado para la colección (como `List<T>`) en la entidad que se basa en EF para la persistencia. En las versiones anteriores de Entity Framework, se requerían propiedades de colección para admitir `ICollection<T>`, lo que significaba que cualquier desarrollador que usara la clase de entidad primaria podía agregar o quitar elementos a través de sus colecciones de propiedades. Esa posibilidad iría en contra de los patrones recomendados en DDD.

Puede usar una colección privada al mismo tiempo que expone un objeto `IReadOnlyCollection<T>` de solo lectura, como se muestra en el ejemplo de código siguiente:

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

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

        var orderItem = new OrderItem(productId, productName,
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

Solo se puede tener acceso de solo lectura a la propiedad `OrderItems` con `IReadOnlyCollection<OrderItem>`. Este tipo es de solo lectura, por lo que está protegido frente a las actualizaciones externas normales.

EF Core proporciona una manera de asignar el modelo de dominio a la base de datos física sin que "contamine" el modelo de dominio. Se trata de código POCO puro de .NET, puesto que la acción de asignación se implementa en el nivel de persistencia. En esa acción de asignación, debe configurar la asignación de campos a base de datos. En el siguiente ejemplo del método `OnModelCreating` de `OrderingContext` y la clase `OrderEntityTypeConfiguration`, la llamada a `SetPropertyAccessMode` indica a EF Core que debe acceder a la propiedad `OrderItems` a través de su campo.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation =
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

Al usar campos en lugar de propiedades, se conserva la entidad `OrderItem` como si tuviera una propiedad `List<OrderItem>`. Pero expone un descriptor de acceso único, el método `AddOrderItem`, para agregar nuevos elementos al pedido. Como resultado, el comportamiento y los datos permanecen unidos y son coherentes a lo largo de cualquier código de aplicación que utilice el modelo de dominio.

## <a name="implement-custom-repositories-with-entity-framework-core"></a>Implementación de los repositorios personalizados con Entity Framework Core

En el nivel de implementación, un repositorio no es más que una clase con código de persistencia de datos coordinada por una unidad de trabajo (DBContext en EF Core) al realizar actualizaciones, como se muestra en la clase siguiente:

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

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity;
        }

        public async Task<Buyer> FindAsync(string buyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == buyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

La interfaz `IBuyerRepository` proviene del nivel de modelo de dominio como contrato. Pero la implementación del repositorio se realiza en el nivel de persistencia e infraestructura.

DbContext de EF pasa mediante el constructor a través de la inserción de dependencias. Se comparte entre varios repositorios dentro del mismo ámbito de solicitud HTTP gracias a su duración predeterminada (`ServiceLifetime.Scoped`) en el contenedor de IoC (que también puede establecerse explícitamente con `services.AddDbContext<>`).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Métodos que se pueden implementar en un repositorio (actualizaciones o transacciones frente a consultas)

Dentro de cada clase de repositorio, debe colocar los métodos de persistencia que actualizan el estado de las entidades de forma que queden contenidos por su agregado relacionado. Recuerde que hay una relación de uno a uno entre un agregado y su repositorio relacionado. Tenga en cuenta que un objeto entidad de raíz agregada podría tener entidades secundarias insertadas en su gráfico de EF. Por ejemplo, un comprador puede tener varias formas de pago como entidades secundarias relacionadas.

Como el enfoque para el microservicio de ordenación en eShopOnContainers también se basa en CQS/CQRS, la mayoría de consultas no se implementa en repositorios personalizados. Los desarrolladores pueden crear libremente las consultas y combinaciones que necesiten para el nivel de presentación sin las restricciones impuestas por agregados, repositorios personalizados por agregado y DDD en general. La mayoría de repositorios personalizados sugeridos por esta guía tiene varios métodos de actualización o transacción, pero solo se actualizan los métodos de consulta necesarios para obtener los datos. Por ejemplo, el repositorio BuyerRepository implementa un método FindAsync, porque la aplicación necesita saber si existe un comprador determinado antes de crear un nuevo comprador relacionado con el pedido.

Pero los métodos de consulta reales para obtener los datos que se van a enviar al nivel de presentación o a las aplicaciones cliente se implementan, como se ha mencionado, en las consultas CQRS basadas en consultas flexibles mediante Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Uso de un repositorio personalizado frente al uso de DbContext EF directamente

La clase DbContext de Entity Framework se basa en los patrones de unidad de trabajo y repositorio, y puede utilizarse directamente desde el código, así como desde un controlador de ASP.NET Core MVC. Los patrones de unidad de trabajo y repositorio dan como resultado el código más sencillo, como en el microservicio de catálogo CRUD en eShopOnContainers. En los casos en los que quiera disponer del código más sencillo posible, puede utilizar directamente la clase DbContext, igual que muchos desarrolladores.

Pero implementar repositorios personalizados ofrece varias ventajas al implementar aplicaciones o microservicios más complejos. Los patrones de unidad de trabajo y repositorio están diseñados para encapsular el nivel de persistencia de infraestructura de tal modo que se separe de los niveles de aplicación y de modelo de dominio. Implementar estos patrones puede facilitar el uso de repositorios ficticios que simulen el acceso a la base de datos.

En la figura 7-18 puede ver las diferencias entre no usar repositorios (directamente mediante DbContext de EF) y usar repositorios que faciliten la simulación de los repositorios.

![Diagrama que muestra los componentes y el flujo de datos en los dos repositorios.](./media/infrastructure-persistence-layer-implemenation-entity-framework-core/custom-repo-versus-db-context.png)

**Figura 7-18**. Uso de repositorios personalizados frente a DbContext sin formato

En la figura 7-18 se muestra que el uso de un repositorio personalizado agrega una capa de abstracción que permite simular el repositorio para facilitar las pruebas. Hay varias alternativas al plantear una simulación. Puede limitarse a simular repositorios o puede simular una unidad de trabajo completa. Normalmente es suficiente con simular repositorios y no suele ser necesario pasar por la complejidad de tener que abstraer y simular una unidad de trabajo.

Más adelante, cuando nos centremos en el nivel de aplicación, verá cómo funciona la inserción de dependencias en ASP.NET Core y cómo se implementa al utilizar repositorios.

En resumen, los repositorios personalizados le permiten probar el código más fácilmente con pruebas unitarias que no se ven afectadas por el estado de la capa de datos. Si ejecuta pruebas que también tienen acceso a la base de datos real a través de Entity Framework, no se trata de pruebas unitarias sino de pruebas de integración, que son mucho más lentas.

Si estaba usando DbContext directamente, tendría que simularlo o ejecutar pruebas unitarias mediante el uso de SQL Server en la memoria con datos predecibles para pruebas unitarias. Pero simular la clase DbContext o controlar datos falsos requiere más trabajo que la simulación en el nivel de repositorio. Por supuesto, siempre puede probar los controladores MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Duración de DbContext de EF y de la instancia IUnitOfWork en el contenedor de IoC

El objeto `DbContext` (expuesto como un objeto `IUnitOfWork`) debería compartirse entre varios repositorios dentro del mismo ámbito de solicitud HTTP. Por ejemplo, esto sucede cuando la operación que se está ejecutando debe tratar con varios agregados o simplemente porque está usando varias instancias de repositorio. También es importante mencionar que la interfaz de `IUnitOfWork` forma parte del nivel de dominio, no es un tipo de EF Core.

Para ello, hay que establecer la duración del servicio de la instancia del objeto `DbContext` en ServiceLifetime.Scoped. Se trata de la duración predeterminada al registrar `DbContext` con `services.AddDbContext` en el contenedor de IoC desde el método ConfigureServices del archivo `Startup.cs` en el proyecto de ASP.NET Core Web API. Esto se ilustra en el código siguiente:

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
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

El modo de creación de instancias de DbContext no se debe configurar como ServiceLifetime.Transient o ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Duración de la instancia de repositorio en su contenedor IoC

De forma similar, la duración del repositorio normalmente se establece como con ámbito (InstancePerLifetimeScope en Autofac). También puede ser transitorio (InstancePerDependency en Autofac), pero el servicio será más eficaz en lo que respecta a la memoria si se usa la duración de ámbito.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

El uso de la duración de singleton para el repositorio puede causar problemas de simultaneidad graves al establecer DbContext en una duración con ámbito (InstancePerLifetimeScope) (las duraciones predeterminadas para DBContext).

### <a name="additional-resources"></a>Recursos adicionales

- **Implementación de los patrones de repositorio y unidad de trabajo en una aplicación ASP.NET MVC** \
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- **Jonathan Allen. Estrategias de implementación para el patrón de repositorio con Entity Framework, Dapper y Chain** \
  <https://www.infoq.com/articles/repository-implementation-strategies>

- **Cesar de la Torre. Comparación de las duraciones de servicio del contenedor IoC de ASP-NET Core con ámbitos de instancia de contenedor Autofac IoC** \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a>Asignación de tabla

La asignación de tabla identifica los datos de tabla que se van a consultar en la base de datos y que se guardarán en ella. Anteriormente, vimos cómo las entidades de domino (por ejemplo, un dominio de producto o de pedido) se podían usar para generar un esquema de base de datos relacionado. EF está diseñado basándose en el concepto de *convenciones*. Las convenciones generan preguntas como "¿Cuál será el nombre de la tabla?" o "¿Qué propiedad es la clave principal?". Las convenciones suelen basarse en nombres convencionales. Por ejemplo, es habitual que la clave principal sea una propiedad que termine con `Id`.

Por convención, cada entidad se configurará para asignarse a una tabla que tenga el mismo nombre que la propiedad `DbSet<TEntity>` que expone la entidad en el contexto derivado. Si no se proporciona ningún valor `DbSet<TEntity>` a la entidad determinada, se utiliza el nombre de clase.

### <a name="data-annotations-versus-fluent-api"></a>Anotaciones de datos frente a API fluida

Hay muchas convenciones de EF Core adicionales, la mayoría de las cuales se puede cambiar mediante anotaciones de datos o la API fluida, que se implementan con el método OnModelCreating.

Las anotaciones de datos se utilizan en las mismas clases del modelo de entidad, lo que supone un método más intrusivo desde el punto de vista de DDD. Esto es así porque el modelo se contamina con anotaciones de datos relacionadas con la base de datos de la infraestructura. Por otro lado, la API fluida es una forma práctica de cambiar la mayoría de convenciones y asignaciones en el nivel de infraestructura de la persistencia de datos, por lo que el modelo de entidad estará limpio y desacoplado de la infraestructura de persistencia.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>API fluida y el método OnModelCreating

Como se ha indicado, puede usar el método OnModelCreating en la clase DbContext con el fin de cambiar las convenciones y las asignaciones.

El microservicio de ordenación en eShopOnContainers implementa configuraciones y asignaciones explícitas, cuando es necesario, tal y como se muestra en el código siguiente.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

        orderConfiguration.HasKey(o => o.Id);

        orderConfiguration.Ignore(b => b.DomainEvents);

        orderConfiguration.Property(o => o.Id)
            .UseHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

        //Address value object persisted as owned entity type supported since EF Core 2.0
        orderConfiguration
            .OwnsOne(o => o.Address, a =>
            {
                a.WithOwner();
            });

        orderConfiguration
            .Property<int?>("_buyerId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("BuyerId")
            .IsRequired(false);

        orderConfiguration
            .Property<DateTime>("_orderDate")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderDate")
            .IsRequired();

        orderConfiguration
            .Property<int>("_orderStatusId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderStatusId")
            .IsRequired();

        orderConfiguration
            .Property<int?>("_paymentMethodId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("PaymentMethodId")
            .IsRequired(false);

        orderConfiguration.Property<string>("Description").IsRequired(false);

        var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        // DDD Patterns comment:
        //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        orderConfiguration.HasOne<PaymentMethod>()
            .WithMany()
            .HasForeignKey("_paymentMethodId")
            .IsRequired(false)
            .OnDelete(DeleteBehavior.Restrict);

        orderConfiguration.HasOne<Buyer>()
            .WithMany()
            .IsRequired(false)
            .HasForeignKey("_buyerId");

        orderConfiguration.HasOne(o => o.OrderStatus)
            .WithMany()
            .HasForeignKey("_orderStatusId");
    }
}
```

Puede establecer todas las asignaciones de la API fluida dentro del mismo método `OnModelCreating`, pero se aconseja crear particiones en el código y tener varias clases de configuración, una por cada entidad, tal y como se muestra en el ejemplo. En particular en el caso de los modelos grandes, es aconsejable tener clases de configuración independientes para configurar diferentes tipos de entidad.

En el código de ejemplo se muestran algunas asignaciones y declaraciones explícitas. Pero las convenciones de EF Core realizan muchas de esas asignaciones automáticamente, por lo que, en su caso, podría necesitar un código más pequeño.

### <a name="the-hilo-algorithm-in-ef-core"></a>Algoritmo Hi/Lo en EF Core

Un aspecto interesante del código de ejemplo anterior es que utiliza el [algoritmo Hi/Lo](https://vladmihalcea.com/the-hilo-algorithm/) como estrategia de generación de claves.

El algoritmo Hi-Lo es útil cuando se necesitan claves únicas antes de confirmar los cambios. A modo de resumen, el algoritmo Hi-Lo asigna identificadores únicos a filas de la tabla, pero no depende del almacenaje inmediato de la fila en la base de datos. Esto le permite empezar a usar los identificadores de forma inmediata, como sucede con los identificadores de la base de datos secuencial normal.

El algoritmo Hi-Lo describe un mecanismo para obtener un lote de identificadores únicos de una secuencia de una base de datos relacionada. Estos identificadores son seguros porque la base de datos garantiza que son únicos, por lo que no se producirán colisiones entre los usuarios. Este algoritmo es interesante por los siguientes motivos:

- No interrumpe el patrón de la unidad de trabajo.

- Obtiene la secuencia de id. por lotes, para minimizar los recorridos de ida y vuelta a la base de datos.

- Genera un identificador que pueden leer los humanos, a diferencia de las técnicas que utilizan los identificadores GUID.

EF Core admite [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con el método `UseHiLo`, tal t como se muestra en el ejemplo anterior.

### <a name="map-fields-instead-of-properties"></a>Asignación de campos en lugar de propiedades

Con esta característica, disponible desde la versión 1.1 de EF Core, puede asignar directamente columnas a los campos. Es posible no utilizar propiedades en la clase de entidad y simplemente asignar columnas de una tabla a los campos. Un uso habitual de ello serían los campos privados para cualquier estado interno, al que no sea necesario acceder desde fuera de la entidad.

Puede hacerlo con campos únicos o también con colecciones, como si se tratara de un campo `List<>`. Este punto se mencionó anteriormente cuando analizamos el modelado de las clases de modelo de dominio, pero aquí puede ver cómo se realiza esta asignación con la configuración `PropertyAccessMode.Field` resaltada en el código anterior.

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a>Uso de propiedades reemplazadas en EF Core y ocultas en el nivel de infraestructura

Las propiedades reemplazadas en EF Core son propiedades que no existen en su modelo de clase de entidad. Los valores y estados de estas propiedades se mantienen exclusivamente en la clase [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker), en el nivel de infraestructura.

## <a name="implement-the-query-specification-pattern"></a>Implementación del patrón de especificación de consultas

Como se mencionó anteriormente en la sección de diseño, el patrón de especificación de consultas es un modelo de diseño controlado por dominios diseñado como el lugar donde se puede incluir la definición de una consulta con lógica opcional de ordenación y paginación.

El patrón de especificación de consultas define una consulta en un objeto. Por ejemplo, para encapsular una consulta paginada que busque algunos productos, se puede crear una especificación PagedProduct que tome los parámetros de entrada necesarios (pageNumber, pageSize, filter, etc.). Después, dentro de cualquier método del repositorio (normalmente una sobrecarga de List()) aceptaría una IQuerySpecification y ejecutaría la consulta esperada según esa especificación.

Un ejemplo de una interfaz Specification genérica es el siguiente código de [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

La siguiente es la implementación de una clase base de especificación genérica.

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb

public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } =
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();

    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }

    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

La siguiente especificación carga una entidad de cesta única a partir del identificador de cesta o del identificador del comprador al que pertenece la cesta y realiza una [carga diligente](/ef/core/querying/related-data) de la colección `Items` de la cesta.

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }

    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

Por último, puede ver a continuación cómo un repositorio de EF genérico puede usar una especificación de este tipo para filtrar y cargar de forma diligente los datos relacionados con un determinado tipo de entidad T.

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));

    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));

    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```

Además de encapsular la lógica de filtro, puede especificar la forma de los datos que se van a devolver, incluidas las propiedades que se van a rellenar.

Aunque no se recomienda devolver `IQueryable` desde un repositorio, se puede usar perfectamente dentro de este para crear un conjunto de resultados. Puede ver cómo se usa este enfoque en el método List anterior, en el que se utilizan expresiones `IQueryable` intermedias para generar la lista de consultas de inclusión antes de ejecutar la consulta con los criterios de especificación de la última línea.

### <a name="additional-resources"></a>Recursos adicionales

- **Asignación de tabla** \
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- **Uso de Hi-Lo para generar claves con Entity Framework Core** \
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- **Campos de respaldo** \
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- **Steve Smith. Colecciones encapsuladas en Entity Framework Core** \
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- **Propiedades reemplazadas** \
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- **Patrón de especificación** \
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> [Anterior](infrastructure-persistence-layer-design.md)
> [Siguiente](nosql-database-persistence-infrastructure.md)
