---
title: Trabajar con datos en aplicaciones de ASP.NET Core
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | trabajar con datos en asp"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="37864-103">Trabajar con datos en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37864-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="37864-104">"Los datos es algo muy valioso y duran más de los sistemas por sí mismos."</span><span class="sxs-lookup"><span data-stu-id="37864-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="37864-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="37864-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="37864-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="37864-106">Summary</span></span>

<span data-ttu-id="37864-107">Acceso a datos es una parte importante de la mayoría de las aplicaciones de software.</span><span class="sxs-lookup"><span data-stu-id="37864-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="37864-108">ASP.NET Core admite una variedad de opciones de acceso a datos, incluido Entity Framework Core (y también Entity Framework 6) y pueden funcionar con cualquier acceso de datos de .NET framework.</span><span class="sxs-lookup"><span data-stu-id="37864-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="37864-109">La elección de los cuales de acceso a datos framework se utilizará depende de las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37864-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="37864-110">La abstracción de estas opciones de los proyectos ApplicationCore e interfaz de usuario y encapsular los detalles de implementación de infraestructura, ayuda a producir software de acoplamiento flexible, comprobable.</span><span class="sxs-lookup"><span data-stu-id="37864-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="37864-111">Entity Framework Core (para bases de datos relacionales)</span><span class="sxs-lookup"><span data-stu-id="37864-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="37864-112">Si va a escribir una nueva aplicación de ASP.NET Core que necesita para trabajar con datos relacionales, Entity Framework Core (EF núcleos) es la manera recomendada para la aplicación tener acceso a sus datos.</span><span class="sxs-lookup"><span data-stu-id="37864-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="37864-113">Núcleo EF es un asignador relacional de objetos (O/RM) que permite a los desarrolladores de .NET conservar los objetos a y desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="37864-114">Elimina la necesidad para la mayoría de los desarrolladores normalmente tendría que escribir el código de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="37864-115">Al igual que ASP.NET Core, Core EF ha vuelto a escribir desde el principio hasta aplicaciones multiplataforma modular de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="37864-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="37864-116">Agregar a la aplicación como un paquete de NuGet, configurarlo en Inicio y solicitar a través de la inyección de dependencia siempre que lo necesite.</span><span class="sxs-lookup"><span data-stu-id="37864-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="37864-117">Para usar EF núcleo con una base de datos de SQL Server, ejecute el siguiente comando CLI de dotnet:</span><span class="sxs-lookup"><span data-stu-id="37864-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="37864-118">dotnet Agregar paquete Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="37864-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="37864-119">Para agregar compatibilidad para un origen de datos InMemory, para las pruebas:</span><span class="sxs-lookup"><span data-stu-id="37864-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="37864-120">dotnet Agregar paquete Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="37864-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="37864-121">DbContext</span><span class="sxs-lookup"><span data-stu-id="37864-121">The DbContext</span></span>

<span data-ttu-id="37864-122">Para trabajar con EF Core, necesita una subclase de DbContext.</span><span class="sxs-lookup"><span data-stu-id="37864-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="37864-123">Esta clase contiene propiedades que representan las colecciones de las entidades de con que la aplicación funcionará.</span><span class="sxs-lookup"><span data-stu-id="37864-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="37864-124">El ejemplo de eShopOnWeb incluye una CatalogContext con colecciones de elementos, las marcas y los tipos:</span><span class="sxs-lookup"><span data-stu-id="37864-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="37864-125">Su DbContext debe tener un constructor que acepta DbContextOptions y pasar este argumento para el constructor DbContext base.</span><span class="sxs-lookup"><span data-stu-id="37864-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="37864-126">Tenga en cuenta que si tiene solo un DbContext en la aplicación, puede pasar una instancia de DbContextOptions, pero si tiene más de un debe usar el genérico DbContextOptions<T> tipo, que se pasa en el tipo de DbContext como el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="37864-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="37864-127">Configuración básica EF</span><span class="sxs-lookup"><span data-stu-id="37864-127">Configuring EF Core</span></span>

<span data-ttu-id="37864-128">En la aplicación ASP.NET Core, configurará normalmente EF principales en el método ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="37864-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="37864-129">Núcleo EF usa un DbContextOptionsBuilder, que admite varios métodos de extensión útil para optimizar su configuración.</span><span class="sxs-lookup"><span data-stu-id="37864-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="37864-130">Para configurar CatalogContext para utilizar una base de datos de SQL Server con una cadena de conexión definida en la configuración, debe agregar el código siguiente en ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="37864-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="37864-131">Para usar la base de datos en memoria:</span><span class="sxs-lookup"><span data-stu-id="37864-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="37864-132">Una vez instalado el núcleo de EF, crea un tipo de elemento secundario de DbContext y configurado en ConfigureServices, está listo para usar EF Core.</span><span class="sxs-lookup"><span data-stu-id="37864-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="37864-133">Puede solicitar una instancia de su tipo de DbContext en cualquier servicio que lo necesite y empezar a trabajar con las entidades persistentes con LINQ como si fueran simplemente en una colección.</span><span class="sxs-lookup"><span data-stu-id="37864-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="37864-134">Núcleo EF realiza el trabajo de la traducción de las expresiones de LINQ a consultas SQL para almacenar y recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="37864-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="37864-135">Puede ver las consultas que se está ejecutando el núcleo de EF configurando un registrador y garantizar el nivel se establece en al menos información, tal como se muestra en la figura 8-1.</span><span class="sxs-lookup"><span data-stu-id="37864-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="37864-136">Consultas de registro principal de EF figura 8-1 en la consola</span><span class="sxs-lookup"><span data-stu-id="37864-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="37864-137">Capturar y almacenar los datos</span><span class="sxs-lookup"><span data-stu-id="37864-137">Fetching and Storing Data</span></span>

<span data-ttu-id="37864-138">Para recuperar datos de EF Core, tener acceso a la propiedad adecuada y usar LINQ para filtrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="37864-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="37864-139">También puede usar LINQ para realizar la proyección, transformar el resultado de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="37864-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="37864-140">En el ejemplo siguiente se recuperaría CatalogBrands, ordenados por nombre, filtrados por su propiedad Enabled y proyectan en un tipo SelectListItem:</span><span class="sxs-lookup"><span data-stu-id="37864-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="37864-141">Es importante en el ejemplo anterior para agregar la llamada a ToListAsync para ejecutar la consulta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="37864-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="37864-142">En caso contrario, la instrucción asignará un tipo IQueryable<SelectListItem> a brandItems, que no se ejecutará hasta que se enumere.</span><span class="sxs-lookup"><span data-stu-id="37864-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="37864-143">Hay ventajas y desventajas para devolver resultados de IQueryable de métodos.</span><span class="sxs-lookup"><span data-stu-id="37864-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="37864-144">Permite que la consulta que EF Core construirá para modificarse, pero también pueden generan errores que solo se producen en tiempo de ejecución, si las operaciones se agregan a la consulta que no puede traducir EF Core.</span><span class="sxs-lookup"><span data-stu-id="37864-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="37864-145">Es generalmente más segura pasar los filtros en el método que realiza el acceso a datos, y devuelven una colección en memoria (por ejemplo, una lista de<T>) como resultado.</span><span class="sxs-lookup"><span data-stu-id="37864-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="37864-146">Núcleo EF realiza un seguimiento de cambios en las entidades que se recupera de la persistencia.</span><span class="sxs-lookup"><span data-stu-id="37864-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="37864-147">Para guardar los cambios en una entidad realiza un seguimiento, llama simplemente al método SaveChanges en DbContext, asegurándose de que es la misma instancia de DbContext que se usó para capturar la entidad.</span><span class="sxs-lookup"><span data-stu-id="37864-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="37864-148">Adición y eliminación de entidades son directamente en la propiedad DbSet adecuada, nuevo con una llamada a SaveChanges para ejecutar los comandos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="37864-149">En el ejemplo siguiente se muestra cómo agregar, actualizar y quitar entidades de persistencia.</span><span class="sxs-lookup"><span data-stu-id="37864-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="37864-150">EF Core es compatible con ambos sincrónica y asincrónica de métodos para capturar y guardar.</span><span class="sxs-lookup"><span data-stu-id="37864-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="37864-151">En las aplicaciones web, se recomienda utilizar el patrón de async y await con los métodos asincrónicos, para que los subprocesos de servidor web no se bloquean mientras se espera a que finalicen operaciones de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="37864-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="37864-152">Capturar los datos relacionados</span><span class="sxs-lookup"><span data-stu-id="37864-152">Fetching Related Data</span></span>

<span data-ttu-id="37864-153">Cuando el núcleo de EF recupera entidades, rellena todas las propiedades que se almacenan directamente a esa entidad en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="37864-154">Propiedades de navegación, como las listas de entidades relacionadas, no se llenan y puede tener su valor establecido en null.</span><span class="sxs-lookup"><span data-stu-id="37864-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="37864-155">Esto garantiza que EF Core está no obteniendo más datos que es necesario, que es especialmente importante para las aplicaciones web, que deben procesar las solicitudes rápidamente y se devuelven respuestas de una manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="37864-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="37864-156">Para incluir relaciones con una entidad con *carga diligente*, especifique la propiedad mediante el método de extensión de inclusión en la consulta, como se muestra:</span><span class="sxs-lookup"><span data-stu-id="37864-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="37864-157">Puede incluir varias relaciones, y también pueden incluir relaciones secundarias mediante ThenInclude.</span><span class="sxs-lookup"><span data-stu-id="37864-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="37864-158">Núcleo EF ejecutará una sola consulta para recuperar el conjunto resultante de entidades.</span><span class="sxs-lookup"><span data-stu-id="37864-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="37864-159">Otra opción para cargar los datos relacionados es usar *carga explícita*.</span><span class="sxs-lookup"><span data-stu-id="37864-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="37864-160">Carga explícita permite cargar datos adicionales en una entidad que ya se han recuperado.</span><span class="sxs-lookup"><span data-stu-id="37864-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="37864-161">Puesto que esto implica una solicitud independiente a la base de datos, no se recomienda para las aplicaciones web, que se deben minimizar el número de la base de datos de ida y vuelta realizados por solicitud.</span><span class="sxs-lookup"><span data-stu-id="37864-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="37864-162">*Carga diferida* es una característica que se carga automáticamente los datos relacionados tal y como se hace referencia a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37864-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="37864-163">Actualmente no es compatible con EF Core, pero como con carga explícita normalmente se debe deshabilitar para aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="37864-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="37864-164">Conexiones resistentes</span><span class="sxs-lookup"><span data-stu-id="37864-164">Resilient Connections</span></span>

<span data-ttu-id="37864-165">Recursos externos como bases de datos SQL en ocasiones pueden ser no está disponible.</span><span class="sxs-lookup"><span data-stu-id="37864-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="37864-166">En los casos de falta de disponibilidad temporal, las aplicaciones pueden utilizar lógica de reintento para evitar que se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="37864-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="37864-167">Esta técnica se conoce normalmente como *resistencia de conexión*.</span><span class="sxs-lookup"><span data-stu-id="37864-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="37864-168">Puede implementar su [propio reintento con retroceso exponencial](https://docs.microsoft.com/azure/architecture/patterns/retry) técnica intentando reintento con un tiempo de espera aumenta exponencialmente, hasta que se ha alcanzado un número máximo de reintentos.</span><span class="sxs-lookup"><span data-stu-id="37864-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="37864-169">Esta técnica adopta el hecho de que los recursos de nube no de vez en cuando estén disponibles durante breves períodos de tiempo, que se produjo un error de algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="37864-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="37864-170">Base de datos de SQL Azure, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="37864-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="37864-171">Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si desea tener conexiones de núcleo de EF resistentes.</span><span class="sxs-lookup"><span data-stu-id="37864-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="37864-172">Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite resistentes conexiones de SQL que se vuelve a intentar si se produce un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="37864-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.EnableRetryOnFailure(
            maxRetryCount: 5,
            maxRetryDelay: TimeSpan.FromSeconds(30), 
            errorNumbersToAdd: null); 
        });
    });
}
//...
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="37864-173">Estrategias de ejecución y las transacciones explícitas mediante BeginTransaction y varios DbContexts</span><span class="sxs-lookup"><span data-stu-id="37864-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="37864-174">Cuando reintentos están habilitados en las conexiones de núcleo de EF, cada operación que se realiza mediante EF principal se convierte en su propia operación reintentable.</span><span class="sxs-lookup"><span data-stu-id="37864-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="37864-175">Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.</span><span class="sxs-lookup"><span data-stu-id="37864-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="37864-176">Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad, todo dentro de la transacción se revierte si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="37864-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="37864-177">Verá una excepción similar al siguiente si intenta ejecutar esa transacción cuando se utiliza una estrategia de ejecución de EF (directiva de reintentos) e incluye varias SaveChanges desde varios DbContexts en ella.</span><span class="sxs-lookup"><span data-stu-id="37864-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="37864-178">System.InvalidOperationException: La estrategia de ejecución configurada 'SqlServerRetryingExecutionStrategy' no es compatible con las transacciones iniciadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="37864-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="37864-179">Utilice la estrategia de ejecución devuelta por 'DbContext.Database.CreateExecutionStrategy()' para ejecutar todas las operaciones en la transacción como una unidad reintentable.</span><span class="sxs-lookup"><span data-stu-id="37864-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="37864-180">La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa todos los elementos que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="37864-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="37864-181">Si se produce un error transitorio, la estrategia de ejecución invoca al delegado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37864-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="37864-182">El código siguiente muestra cómo implementar este enfoque:</span><span class="sxs-lookup"><span data-stu-id="37864-182">The following code shows how to implement this approach:</span></span>

```csharp
// Use of an EF Core resiliency strategy when using multiple DbContexts
// within an explicit transaction
// See:
// https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
var strategy = _catalogContext.Database.CreateExecutionStrategy(); 
await strategy.ExecuteAsync(async () =>
{
    // Achieving atomicity between original Catalog database operation and the
    // IntegrationEventLog thanks to a local transaction
    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);
        await _catalogContext.SaveChangesAsync();
        
        // Save to EventLog only if product price changed
        if (raiseProductPriceChangedEvent)
        await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
    }
});
```

<span data-ttu-id="37864-183">Es el primer DbContext el \_catalogContext y el segundo DbContext está dentro de la \_integrationEventLogService objeto.</span><span class="sxs-lookup"><span data-stu-id="37864-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="37864-184">Por último, la confirmación sería acción realiza varias DbContexts y el uso de una estrategia de ejecución de EF.</span><span class="sxs-lookup"><span data-stu-id="37864-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="37864-185">Referencias: Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="37864-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="37864-186">**Documentos EF básicos**</span><span class="sxs-lookup"><span data-stu-id="37864-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="37864-187"><https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="37864-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="37864-188">**EF principal: Datos relacionados**</span><span class="sxs-lookup"><span data-stu-id="37864-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="37864-189"><https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="37864-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="37864-190">**Evite las entidades de la carga diferida de las aplicaciones de ASPNET**</span><span class="sxs-lookup"><span data-stu-id="37864-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="37864-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="37864-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="37864-192">¿Núcleo EF o micro-ORM?</span><span class="sxs-lookup"><span data-stu-id="37864-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="37864-193">Aunque el núcleo de EF es una excelente opción para administrar la persistencia y en su mayor parte encapsula los detalles de base de datos de los desarrolladores de aplicaciones, no es la única opción.</span><span class="sxs-lookup"><span data-stu-id="37864-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="37864-194">Otra alternativa de código abierto populares es [Dapper](https://github.com/StackExchange/Dapper), un micro-ORM como los denominados.</span><span class="sxs-lookup"><span data-stu-id="37864-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="37864-195">Un micro-ORM es una ligera, menos completa herramienta para la asignación de objetos a las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="37864-196">En el caso de Dapper, su diseño de objetivos de centran en el rendimiento, en lugar de encapsular totalmente subyacente la consulta se utiliza para recuperar y actualizar datos.</span><span class="sxs-lookup"><span data-stu-id="37864-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="37864-197">Dado que no abstracta SQL del programador, Dapper es "más cercano para el sistema operativo" y permite a los desarrolladores escribir exactamente las consultas que desean usar para un determinado de datos tener acceso a la operación.</span><span class="sxs-lookup"><span data-stu-id="37864-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="37864-198">Núcleo EF tiene dos características importantes proporciona separarlo de Dapper, pero también se agregue a su sobrecarga de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="37864-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="37864-199">La primera es la traducción de expresiones LINQ a SQL.</span><span class="sxs-lookup"><span data-stu-id="37864-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="37864-200">Las traducciones se almacenan en caché, pero aún así hay una sobrecarga en la realización de la primera vez.</span><span class="sxs-lookup"><span data-stu-id="37864-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="37864-201">El segundo es el seguimiento de cambios en las entidades (de modo que se pueden generar instrucciones de actualización eficaz).</span><span class="sxs-lookup"><span data-stu-id="37864-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="37864-202">Este comportamiento puede estar desactivada para consultas específicas mediante la extensión de AsNotTracking.</span><span class="sxs-lookup"><span data-stu-id="37864-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="37864-203">Núcleo EF también genera consultas SQL que suelen ser muy eficaces y en cualquier caso absolutamente aceptable desde la perspectiva del rendimiento, pero si necesita un preciso control sobre la consulta precisa que se ejecute, se puede pasar en SQL personalizada (o ejecutar un procedimiento almacenado) usan EF Principales, demasiado.</span><span class="sxs-lookup"><span data-stu-id="37864-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="37864-204">En este caso, sigue Dapper supera EF Core, pero solo ligeramente.</span><span class="sxs-lookup"><span data-stu-id="37864-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="37864-205">Presenta Julie Lerman algunos datos de rendimiento en ella pueden artículo de MSDN de 2016 [Dapper, Entity Framework y aplicaciones híbridas](https://msdn.microsoft.com/magazine/mt703432.aspx).</span><span class="sxs-lookup"><span data-stu-id="37864-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="37864-206">Datos de pruebas comparativas de rendimiento adicionales para una amplia variedad de métodos de acceso de datos pueden encontrarse en [el sitio Dapper](https://github.com/StackExchange/Dapper).</span><span class="sxs-lookup"><span data-stu-id="37864-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="37864-207">Para ver cómo la sintaxis de Dapper varía en función del núcleo de EF, tenga en cuenta estas dos versiones del mismo método para recuperar una lista de elementos:</span><span class="sxs-lookup"><span data-stu-id="37864-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="37864-208">Si tiene que generar gráficos de objetos más complejos con Dapper, debe escribir las consultas asociadas (en lugar de agregar un archivo de inclusión como lo haría en EF Core).</span><span class="sxs-lookup"><span data-stu-id="37864-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="37864-209">Esto se admite a través de una serie de sintaxis, incluida una característica denominada asignación múltiple que le permite asignar filas individuales a varios objetos asignados.</span><span class="sxs-lookup"><span data-stu-id="37864-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="37864-210">Por ejemplo, dada una clase Post con un propietario de la propiedad de tipo de usuario, el código SQL siguiente devuelve todos los datos necesarios:</span><span class="sxs-lookup"><span data-stu-id="37864-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="37864-211">Cada fila devuelta incluye los datos de usuario y Post.</span><span class="sxs-lookup"><span data-stu-id="37864-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="37864-212">Dado que los datos de usuario deben asociarse a los datos de entrada a través de su propiedad de propietario, se utiliza la función siguiente:</span><span class="sxs-lookup"><span data-stu-id="37864-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="37864-213">La lista de código completa para devolver una colección de entradas con su propiedad de propietario que se rellena con los datos de usuario asociado sería:</span><span class="sxs-lookup"><span data-stu-id="37864-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="37864-214">Dado que ofrece menos encapsulación, Dapper requiere que los programadores podrán obtener más información acerca de cómo se almacenan sus datos, cómo consultar de forma eficaz y escribir más código para capturarlo.</span><span class="sxs-lookup"><span data-stu-id="37864-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="37864-215">Cuando se cambia el modelo, en lugar de simplemente crear una nueva migración (otra característica de EF Core) o actualizar la información de asignación en una posición en un DbContext, deben actualizarse todas las consultas que se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="37864-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="37864-216">Estas consultas tienen no garantías en tiempo de compilación, por lo que pueden dividir en tiempo de ejecución en respuesta a los cambios a la base de datos, lo más difíciles de detectar rápidamente los errores o el modelo.</span><span class="sxs-lookup"><span data-stu-id="37864-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="37864-217">A cambio de estos inconvenientes, Dapper ofrece un rendimiento extremadamente rápido.</span><span class="sxs-lookup"><span data-stu-id="37864-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="37864-218">Para la mayoría de las aplicaciones y la mayoría de las partes de casi todas las aplicaciones, EF Core ofrece un rendimiento aceptable.</span><span class="sxs-lookup"><span data-stu-id="37864-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="37864-219">Por lo tanto, sus ventajas de productividad para desarrolladores suelen superan a su sobrecarga de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="37864-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="37864-220">Para las consultas que pueden beneficiarse del almacenamiento en caché, solo se puede ejecutar la consulta real sea irrelevante de diferencias de rendimiento de consultas de un pequeño porcentaje de los casos, realizar relativamente pequeño.</span><span class="sxs-lookup"><span data-stu-id="37864-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="37864-221">SQL o NoSQL</span><span class="sxs-lookup"><span data-stu-id="37864-221">SQL or NoSQL</span></span>

<span data-ttu-id="37864-222">Tradicionalmente, las bases de datos relacional como SQL Server han dominado marketplace para el almacenamiento de datos persistentes, pero no son la única solución disponible.</span><span class="sxs-lookup"><span data-stu-id="37864-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="37864-223">Al igual que las bases de datos NoSQL [MongoDB](https://www.mongodb.com/what-is-mongodb) ofrecer un enfoque diferente para almacenar los objetos.</span><span class="sxs-lookup"><span data-stu-id="37864-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="37864-224">En lugar de asignar objetos a las tablas y filas, otra opción es serializar el objeto gráfico completo y almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="37864-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="37864-225">Las ventajas de este enfoque, al menos inicialmente, están mayor simplicidad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="37864-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="37864-226">Es ciertamente más simple almacenar un objeto serializado único con una clave que al descomponer el objeto en muchas tablas con relaciones y actualización y las filas que pueden haber cambiado desde la último el objeto se recuperan de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="37864-227">Del mismo modo, la obtención y deserializar un objeto único de un almacén basado en clave suele ser mucho más rápida y sencilla que combinaciones complejas o varias consultas de base de datos necesarias para crear completamente el mismo objeto de base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="37864-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="37864-228">La falta de bloqueos de transacciones o de un esquema fijo también hace que las bases de datos NoSQL muy sensibles al escalar entre varias máquinas, compatibilidad con grandes conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="37864-229">Por otro lado, las bases de datos NoSQL (como normalmente se denominan) tienen sus desventajas.</span><span class="sxs-lookup"><span data-stu-id="37864-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="37864-230">Bases de datos relacionales use normalización para exigir la coherencia y evitar la duplicación de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="37864-231">Esto reduce el tamaño total de la base de datos y garantiza que las actualizaciones a los datos compartidos están disponibles inmediatamente a lo largo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="37864-232">En una base de datos relacional, una tabla de direcciones puede referencia a una tabla de país con el identificador, tal que si se cambia el nombre de un país, los registros de direcciones se beneficiarían de la actualización sin ellos mismos tener que actualizarse.</span><span class="sxs-lookup"><span data-stu-id="37864-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="37864-233">Sin embargo, en una base de datos NoSQL, dirección y su país asociado pueden serializarse como parte de muchos objetos almacenados.</span><span class="sxs-lookup"><span data-stu-id="37864-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="37864-234">Una actualización en un nombre de país requeriría todos esos objetos actualizarse, en lugar de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="37864-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="37864-235">Bases de datos relacionales también pueden asegurar la integridad relacional aplicando reglas, como claves externas.</span><span class="sxs-lookup"><span data-stu-id="37864-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="37864-236">Normalmente, las bases de datos NoSQL no ofrecen estas restricciones en sus datos.</span><span class="sxs-lookup"><span data-stu-id="37864-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="37864-237">Otro complejidad NoSQL deben ocuparse de las bases de datos es control de versiones.</span><span class="sxs-lookup"><span data-stu-id="37864-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="37864-238">Cuando cambian las propiedades de un objeto, puede no ser capaz de deserializar en las versiones anteriores que se almacenaron.</span><span class="sxs-lookup"><span data-stu-id="37864-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="37864-239">Por lo tanto, todos los objetos existentes que tengan una versión (anterior) serializada del objeto deben actualizarse para que se ajuste a su esquema de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37864-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="37864-240">Esto no es conceptualmente diferente de una base de datos relacional, que cambia el esquema a veces requieren secuencias de comandos de actualización o asignación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="37864-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="37864-241">Sin embargo, el número de entradas que se debe modificar suele ser mucho mayor en el enfoque de NoSQL, porque no hay más de duplicación de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="37864-242">Es posible en las bases de datos NoSQL para almacenar varias versiones de objetos, no admiten bases de datos relacionales de esquema fijo algo normalmente.</span><span class="sxs-lookup"><span data-stu-id="37864-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="37864-243">Sin embargo, en este caso el código de aplicación deberá tener en cuenta la existencia de versiones anteriores de objetos, la adición de complejidad adicional.</span><span class="sxs-lookup"><span data-stu-id="37864-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="37864-244">Las bases de datos NoSQL normalmente no exigir [ACID](http://en.wikipedia.org/wiki/ACID), lo que significa que tienen ventajas de rendimiento y escalabilidad a través de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="37864-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="37864-245">Son adecuadas para conjuntos de datos muy grandes y los objetos que no son adecuados para el almacenamiento en las estructuras de tabla normalizada.</span><span class="sxs-lookup"><span data-stu-id="37864-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="37864-246">No hay ninguna razón para una sola aplicación no puede aprovechar las ventajas de ambos relacional y bases de datos NoSQL, con cada uno sea mejor adecuado.</span><span class="sxs-lookup"><span data-stu-id="37864-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="37864-247">Documentos de Azure</span><span class="sxs-lookup"><span data-stu-id="37864-247">Azure DocumentDB</span></span>

<span data-ttu-id="37864-248">Documentos de Azure es un servicio de base de datos NoSQL completamente administrado que ofrece el almacenamiento de datos de esquema en la nube.</span><span class="sxs-lookup"><span data-stu-id="37864-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="37864-249">Documentos se crean para rendimiento rápido y predecible, la alta disponibilidad, la escala elástica y la distribución global.</span><span class="sxs-lookup"><span data-stu-id="37864-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="37864-250">A pesar de ser una base de datos NoSQL, los desarrolladores pueden usar enriquecidas y familiar capacidades de consulta SQL sobre datos JSON.</span><span class="sxs-lookup"><span data-stu-id="37864-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="37864-251">Todos los recursos de documentos se almacenan como documentos JSON.</span><span class="sxs-lookup"><span data-stu-id="37864-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="37864-252">Los recursos se administran como *elementos*, que son documentos que contiene los metadatos, y *fuentes*, que son colecciones de elementos.</span><span class="sxs-lookup"><span data-stu-id="37864-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="37864-253">Figura 8-2 muestra la relación entre los diferentes recursos.</span><span class="sxs-lookup"><span data-stu-id="37864-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![La relación jerárquica entre los recursos en DocumentDB, una base de datos NoSQL JSON](./media/image8-2.png)

<span data-ttu-id="37864-255">**Figura 8-2.**</span><span class="sxs-lookup"><span data-stu-id="37864-255">**Figure 8-2.**</span></span> <span data-ttu-id="37864-256">Organización de recursos de DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="37864-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="37864-257">El lenguaje de consulta de documentos es una interfaz sencilla pero eficaz para consultar los documentos JSON.</span><span class="sxs-lookup"><span data-stu-id="37864-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="37864-258">El lenguaje admite un subconjunto de la gramática de ANSI SQL y agrega integración profunda de objeto JavaScript, matrices, la construcción de objetos y la invocación de función.</span><span class="sxs-lookup"><span data-stu-id="37864-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="37864-259">**Referencias a documentos**</span><span class="sxs-lookup"><span data-stu-id="37864-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="37864-260">Introduction\ de documentos</span><span class="sxs-lookup"><span data-stu-id="37864-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="37864-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span><span class="sxs-lookup"><span data-stu-id="37864-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="37864-262">Otras opciones de persistencia</span><span class="sxs-lookup"><span data-stu-id="37864-262">Other Persistence Options</span></span>

<span data-ttu-id="37864-263">Además relacionales y NoSQL opciones de almacenamiento, aplicaciones de ASP.NET Core pueden utilizar el almacenamiento de Azure para almacenar una variedad de formatos de datos y archivos de forma escalable y basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="37864-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="37864-264">Almacenamiento de Azure es escalable de forma masiva, para que pueda empezar a almacenar pequeñas cantidades de datos y la escala hasta almacenar cientos o terabytes si así lo requiere la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37864-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="37864-265">Almacenamiento de Azure admite cuatro tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="37864-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="37864-266">Almacenamiento de blobs para almacenamiento binario, que también se denomina almacenamiento de objetos o texto no estructurado.</span><span class="sxs-lookup"><span data-stu-id="37864-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="37864-267">Almacenamiento de tablas para conjuntos de datos estructurados, accesible a través de las claves de fila.</span><span class="sxs-lookup"><span data-stu-id="37864-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="37864-268">Almacenamiento de cola para la mensajería de confianza basada en cola.</span><span class="sxs-lookup"><span data-stu-id="37864-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="37864-269">Almacenamiento de archivos para el acceso a archivos compartidos entre máquinas virtuales de Azure y aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="37864-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="37864-270">**Referencias: almacenamiento de Azure**</span><span class="sxs-lookup"><span data-stu-id="37864-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="37864-271">Introduction\ de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="37864-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="37864-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="37864-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="37864-273">Almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="37864-273">Caching</span></span>

<span data-ttu-id="37864-274">En las aplicaciones web, cada solicitud web se debe completar en el menor tiempo posible.</span><span class="sxs-lookup"><span data-stu-id="37864-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="37864-275">Una manera de conseguirlo es limitar el número de llamadas externas, que el servidor debe realizar para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="37864-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="37864-276">Almacenamiento en caché requiere almacenar una copia de datos en el servidor (u otros del almacén de datos que es más fácil consultar el origen de los datos de).</span><span class="sxs-lookup"><span data-stu-id="37864-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="37864-277">Aplicaciones Web y especialmente las aplicaciones web tradicionales no SPA, necesitan generar la interfaz de usuario completo con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="37864-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="37864-278">Con frecuencia, esto implica realizar muchas de las mismas consultas de base de datos varias veces de solicitud de un usuario a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="37864-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="37864-279">En la mayoría de los casos, estos datos en contadas ocasiones, cambian de modo que no hay motivos para realizar dicha solicitud constantemente desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="37864-280">ASP.NET Core es compatible con las respuestas en caché, para almacenar en caché páginas completas y almacenamiento en caché de datos, que admite el comportamiento de almacenamiento en caché más granular.</span><span class="sxs-lookup"><span data-stu-id="37864-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="37864-281">Al implementar el almacenamiento en caché, es importante tener en la separación de la cuenta de problemas.</span><span class="sxs-lookup"><span data-stu-id="37864-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="37864-282">No implementa la lógica de almacenamiento en caché en la lógica de acceso a datos o en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="37864-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="37864-283">En su lugar, encapsular el almacenamiento en caché en sus propias clases y usar la configuración para administrar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="37864-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="37864-284">Esto sigue los principios de responsabilidad única y abierto o cerrado y le resultará más fácil de administrar cómo usar almacenamiento en caché en la aplicación cuando crece.</span><span class="sxs-lookup"><span data-stu-id="37864-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="37864-285">Las respuestas en caché de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37864-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="37864-286">ASP.NET Core admite dos niveles de almacenamiento en caché de respuesta.</span><span class="sxs-lookup"><span data-stu-id="37864-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="37864-287">El primer nivel no almacena en caché nada en el servidor, pero agrega encabezados HTTP que indicar a los clientes y servidores proxy a la memoria caché las respuestas.</span><span class="sxs-lookup"><span data-stu-id="37864-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="37864-288">Esto se implementa mediante la adición del atributo ResponseCache a los controladores individuales o acciones:</span><span class="sxs-lookup"><span data-stu-id="37864-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="37864-289">El Middleware de almacenamiento en caché de respuesta automáticamente almacenará en memoria caché las respuestas basándose en un conjunto de condiciones que puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="37864-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="37864-290">De forma predeterminada, se almacenan en caché respuestas sólo 200 (Aceptar) solicitadas a través de métodos GET o HEAD.</span><span class="sxs-lookup"><span data-stu-id="37864-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="37864-291">Además, las solicitudes deben tener una respuesta con un valor de Cache-Control: encabezado público y no puede incluir encabezados de autorización o Set-Cookie.</span><span class="sxs-lookup"><span data-stu-id="37864-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="37864-292">Vea una [lista completa de las condiciones de almacenamiento en caché utilizado por la respuesta de almacenamiento en caché middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="37864-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="37864-293">Almacenamiento en caché de datos</span><span class="sxs-lookup"><span data-stu-id="37864-293">Data Caching</span></span>

<span data-ttu-id="37864-294">En lugar de (o además de) el almacenamiento en caché las respuestas web completo, puede almacenar en caché los resultados de consultas de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="37864-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="37864-295">Para ello, puede usar en la memoria caché en el servidor web o usar [una memoria caché distribuida](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="37864-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="37864-296">En esta sección se muestra cómo implementar en almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="37864-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="37864-297">Agregar compatibilidad para memoria (o distribuida) almacenamiento en caché en ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="37864-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="37864-298">Asegúrese de agregar el paquete de Microsoft.Extensions.Caching.Memory NuGet así.</span><span class="sxs-lookup"><span data-stu-id="37864-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="37864-299">Una vez que haya agregado el servicio, solicitar IMemoryCache a través de la inyección de dependencia siempre que necesite obtener acceso a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="37864-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="37864-300">En este ejemplo, el CachedCatalogService está usando el patrón de diseño de Proxy (o decorador), proporcionando una implementación alternativa de ICatalogService que controla el acceso a (o agrega comportamiento a) la implementación de CatalogService subyacente.</span><span class="sxs-lookup"><span data-stu-id="37864-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="37864-301">Para configurar la aplicación para usar la versión en caché del servicio, pero seguirá permitiendo el servicio para obtener la instancia de CatalogService que necesita en su constructor, debe agregar lo siguiente en ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="37864-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="37864-302">Teniendo esto en su lugar, las llamadas de base de datos para capturar los datos del catálogo sólo se realizará una vez por minuto, en lugar de en cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="37864-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="37864-303">Según el tráfico al sitio, esto puede tener un impacto muy significativo en el número de consultas realizadas en la base de datos y el tiempo de carga de página promedio de la página principal que actualmente depende de las tres de las consultas expuestas por este servicio.</span><span class="sxs-lookup"><span data-stu-id="37864-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="37864-304">Es un problema que surge cuando se implementa el almacenamiento en caché *datos obsoletos* : es decir, datos que han cambiado en el origen, pero una versión obsoleta permanecen en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="37864-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="37864-305">Una manera sencilla para mitigar este problema es utilizar duraciones de caché pequeño, ya que para una aplicación ocupada hay limitado ventaja adicional para extender la longitud de los datos en caché.</span><span class="sxs-lookup"><span data-stu-id="37864-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="37864-306">Por ejemplo, considere la posibilidad de una página que realiza una consulta de base de datos única, y se solicita 10 veces por segundo.</span><span class="sxs-lookup"><span data-stu-id="37864-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="37864-307">Si esta página se almacena en caché durante un minuto, se producirá un error en el número de consultas de base de datos realizadas por minuto para quitar de 600 en 1, una reducción del 99,8%.</span><span class="sxs-lookup"><span data-stu-id="37864-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="37864-308">Si en su lugar, la duración de la caché se ha realizado una hora, la reducción general sería 99,997%, pero ahora la antigüedad de probabilidad y potencial de datos obsoletos son ambos aumentados considerablemente.</span><span class="sxs-lookup"><span data-stu-id="37864-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="37864-309">Otro enfoque consiste en Quitar proactivamente las entradas de caché cuando se actualizan los datos que contienen.</span><span class="sxs-lookup"><span data-stu-id="37864-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="37864-310">Cualquier entrada individual puede quitarse si se conoce su clave:</span><span class="sxs-lookup"><span data-stu-id="37864-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="37864-311">Si la aplicación expone funcionalidad para actualizar las entradas que almacena en caché, puede quitar las entradas de caché correspondiente en el código que realiza las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="37864-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="37864-312">En ocasiones puede haber varias entradas diferentes que dependen de un determinado conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="37864-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="37864-313">En ese caso, puede ser útil crear las dependencias existentes entre las entradas de caché, mediante el uso de un CancellationChangeToken.</span><span class="sxs-lookup"><span data-stu-id="37864-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="37864-314">Con un CancellationChangeToken puede expirar varias entradas de caché a la vez si se cancela el token.</span><span class="sxs-lookup"><span data-stu-id="37864-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="37864-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="37864-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
