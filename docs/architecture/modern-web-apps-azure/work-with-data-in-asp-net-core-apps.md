---
title: Trabajar con datos en aplicaciones ASP.NET Core
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Trabajar con datos en aplicaciones ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 08/12/2020
no-loc:
- Blazor
- WebAssembly
ms.openlocfilehash: 4668922de8f0efc775acf6e505d56143b7ead8e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169068"
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="07fa6-103">Trabajar con datos en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07fa6-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="07fa6-104">"Los datos son algo muy valioso y durarán más que los propios sistemas".</span><span class="sxs-lookup"><span data-stu-id="07fa6-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>
>
> <span data-ttu-id="07fa6-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="07fa6-105">Tim Berners-Lee</span></span>

<span data-ttu-id="07fa6-106">El acceso a datos es una parte importante de la mayoría de las aplicaciones de software.</span><span class="sxs-lookup"><span data-stu-id="07fa6-106">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="07fa6-107">ASP.NET Core admite una variedad de opciones de acceso a datos, incluido Entity Framework Core (y también Entity Framework 6) y puede funcionar con cualquier marco de acceso a datos de .NET.</span><span class="sxs-lookup"><span data-stu-id="07fa6-107">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="07fa6-108">La elección del marco de acceso a datos que se va a usar depende de las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07fa6-108">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="07fa6-109">La abstracción de estas opciones de los proyectos ApplicationCore y UI, y la encapsulación de los detalles de implementación en la infraestructura, ayuda a crear software de acoplamiento flexible y que se pueda probar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-109">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="07fa6-110">Entity Framework Core (para bases de datos relacionales)</span><span class="sxs-lookup"><span data-stu-id="07fa6-110">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="07fa6-111">Si va a escribir una aplicación ASP.NET Core nueva que tenga que trabajar con datos relacionales, Entity Framework Core (EF Core) es la manera recomendada para que la aplicación tenga acceso a sus datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-111">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="07fa6-112">EF Core es un asignador relacional de objetos (O/RM) que permite a los desarrolladores de .NET persistir objetos en y desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-112">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="07fa6-113">Elimina la necesidad de la mayor parte del código de acceso a datos que los desarrolladores normalmente tendrían que escribir.</span><span class="sxs-lookup"><span data-stu-id="07fa6-113">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="07fa6-114">Al igual que ASP.NET Core, EF Core se ha vuelto a escribir desde el principio para admitir aplicaciones multiplataforma modulares.</span><span class="sxs-lookup"><span data-stu-id="07fa6-114">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="07fa6-115">Se agrega a la aplicación como un paquete NuGet, se configura en Inicio y se solicita a través de la inserción de dependencias siempre que se necesite.</span><span class="sxs-lookup"><span data-stu-id="07fa6-115">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="07fa6-116">Para usar EF Core con una base de datos de SQL Server, ejecute el comando siguiente de la CLI de DotNet:</span><span class="sxs-lookup"><span data-stu-id="07fa6-116">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

<span data-ttu-id="07fa6-117">Para agregar compatibilidad para un origen de datos InMemory, para las pruebas:</span><span class="sxs-lookup"><span data-stu-id="07fa6-117">To add support for an InMemory data source, for testing:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore.InMemory
```

### <a name="the-dbcontext"></a><span data-ttu-id="07fa6-118">DbContext</span><span class="sxs-lookup"><span data-stu-id="07fa6-118">The DbContext</span></span>

<span data-ttu-id="07fa6-119">Para trabajar con EF Core, necesita una subclase de <xref:Microsoft.EntityFrameworkCore.DbContext>.</span><span class="sxs-lookup"><span data-stu-id="07fa6-119">To work with EF Core, you need a subclass of <xref:Microsoft.EntityFrameworkCore.DbContext>.</span></span> <span data-ttu-id="07fa6-120">Esta clase contiene propiedades que representan las colecciones de las entidades con las que la aplicación va a trabajar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-120">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="07fa6-121">En el ejemplo eShopOnWeb se incluye un CatalogContext con colecciones de productos, marcas y tipos:</span><span class="sxs-lookup"><span data-stu-id="07fa6-121">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

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

<span data-ttu-id="07fa6-122">El DbContext debe tener un constructor que acepte DbContextOptions y pase este argumento al constructor DbContext base.</span><span class="sxs-lookup"><span data-stu-id="07fa6-122">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="07fa6-123">Si solo tiene un DbContext en la aplicación, puede pasar una instancia de DbContextOptions, pero, si tiene más, tendrá que usar el tipo DbContextOptions\<T> genérico y pasar el tipo de DbContext como el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="07fa6-123">If you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions\<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="07fa6-124">Configuración de EF Core</span><span class="sxs-lookup"><span data-stu-id="07fa6-124">Configuring EF Core</span></span>

<span data-ttu-id="07fa6-125">En la aplicación ASP.NET Core, normalmente configurará EF Core en el método ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="07fa6-125">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="07fa6-126">EF Core usa un DbContextOptionsBuilder, que admite varios métodos de extensión útiles para optimizar su configuración.</span><span class="sxs-lookup"><span data-stu-id="07fa6-126">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="07fa6-127">Para configurar CatalogContext para usar una base de datos de SQL Server con una cadena de conexión definida en la configuración, se debe agregar el código siguiente a ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="07fa6-127">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="07fa6-128">Para usar la base de datos en memoria:</span><span class="sxs-lookup"><span data-stu-id="07fa6-128">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="07fa6-129">Después de instalar EF Core, crear un tipo secundario de DbContext y configurarlo en ConfigureServices, ya está listo para usar EF Core.</span><span class="sxs-lookup"><span data-stu-id="07fa6-129">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="07fa6-130">Puede solicitar una instancia del tipo de DbContext en cualquier servicio que lo necesite y empezar a trabajar con las entidades persistentes con LINQ como si simplemente estuvieran en una colección.</span><span class="sxs-lookup"><span data-stu-id="07fa6-130">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="07fa6-131">EF Core realiza el trabajo de traducir las expresiones de LINQ a consultas SQL para almacenar y recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-131">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="07fa6-132">Puede ver las consultas que ejecuta EF Core si configura un registrador y se asegura de que su nivel se establece al menos en Información, como se muestra en la figura 8-1.</span><span class="sxs-lookup"><span data-stu-id="07fa6-132">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![Registro de consultas de EF Core en la consola](./media/image8-1.png)

<span data-ttu-id="07fa6-134">**Figura 8-1**.</span><span class="sxs-lookup"><span data-stu-id="07fa6-134">**Figure 8-1**.</span></span> <span data-ttu-id="07fa6-135">Registro de consultas de EF Core en la consola</span><span class="sxs-lookup"><span data-stu-id="07fa6-135">Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="07fa6-136">Recuperación y almacenamiento de los datos</span><span class="sxs-lookup"><span data-stu-id="07fa6-136">Fetching and storing Data</span></span>

<span data-ttu-id="07fa6-137">Para recuperar datos de EF Core, se obtiene acceso a la propiedad adecuada y se usa LINQ para filtrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-137">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="07fa6-138">También se puede usar LINQ para realizar la proyección, y transformar el resultado de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="07fa6-138">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="07fa6-139">En el ejemplo siguiente se recuperaría CatalogBrands, ordenadas por nombre, filtradas por su propiedad Enabled y proyectadas en un tipo SelectListItem:</span><span class="sxs-lookup"><span data-stu-id="07fa6-139">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="07fa6-140">En el ejemplo anterior es importante agregar la llamada a ToListAsync para ejecutar la consulta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="07fa6-140">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="07fa6-141">En caso contrario, la instrucción asignará un tipo IQueryable\<SelectListItem> a brandItems, que no se ejecutará hasta que se enumere.</span><span class="sxs-lookup"><span data-stu-id="07fa6-141">Otherwise, the statement will assign an IQueryable\<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="07fa6-142">Devolver resultados de IQueryable de los métodos tiene sus ventajas y desventajas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-142">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="07fa6-143">Permite modificar más la consulta que EF Core va a construir, pero también se pueden generan errores que solo se producen en tiempo de ejecución, si se agregan a la consulta operaciones que EF Core no puede traducir.</span><span class="sxs-lookup"><span data-stu-id="07fa6-143">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="07fa6-144">Generalmente es más seguro pasar los filtros al método que realiza el acceso a datos, y devolver una colección en memoria (por ejemplo, List\<T>) como resultado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-144">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List\<T>) as the result.</span></span>

<span data-ttu-id="07fa6-145">EF Core realiza el seguimiento de los cambios en las entidades que recupera de la persistencia.</span><span class="sxs-lookup"><span data-stu-id="07fa6-145">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="07fa6-146">Para guardar los cambios en una entidad de la que se realiza el seguimiento, simplemente llame al método SaveChanges en DbContext, asegurándose de que sea la misma instancia de DbContext que se usó para recuperar la entidad.</span><span class="sxs-lookup"><span data-stu-id="07fa6-146">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="07fa6-147">La adición y eliminación de entidades se realiza directamente en la propiedad DbSet adecuada, de nuevo con una llamada a SaveChanges para ejecutar los comandos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-147">Adding and removing entities is directly done on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="07fa6-148">En el ejemplo siguiente se muestra cómo agregar, actualizar y quitar entidades de la persistencia.</span><span class="sxs-lookup"><span data-stu-id="07fa6-148">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

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

<span data-ttu-id="07fa6-149">EF Core es compatible con métodos sincrónicos y asincrónicos para recuperar y guardar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-149">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="07fa6-150">En las aplicaciones web, se recomienda usar el patrón async/await con los métodos asincrónicos, para que los subprocesos de servidor web no se bloqueen mientras se espera a que finalicen las operaciones de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-150">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="07fa6-151">Recuperación de datos relacionados</span><span class="sxs-lookup"><span data-stu-id="07fa6-151">Fetching related data</span></span>

<span data-ttu-id="07fa6-152">Cuando EF Core recupera entidades, rellena todas las propiedades que se almacenan directamente con esa entidad en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-152">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="07fa6-153">Las propiedades de navegación, como las listas de entidades relacionadas, no se rellenan y pueden tener su valor establecido en NULL.</span><span class="sxs-lookup"><span data-stu-id="07fa6-153">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="07fa6-154">Esto garantiza que EF Core no recupere más datos de los necesarios, lo que es especialmente importante para las aplicaciones web, que deben procesar las solicitudes rápidamente y devolver respuestas de una manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="07fa6-154">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="07fa6-155">Para incluir las relaciones con una entidad mediante la _carga diligente_, especifique la propiedad con el método de extensión Include en la consulta, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="07fa6-155">To include relationships with an entity using _eager loading_, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="07fa6-156">Puede incluir varias relaciones y también relaciones secundarias mediante ThenInclude.</span><span class="sxs-lookup"><span data-stu-id="07fa6-156">You can include multiple relationships, and you can also include subrelationships using ThenInclude.</span></span> <span data-ttu-id="07fa6-157">EF Core ejecutará una sola consulta para recuperar el conjunto resultante de entidades.</span><span class="sxs-lookup"><span data-stu-id="07fa6-157">EF Core will execute a single query to retrieve the resulting set of entities.</span></span> <span data-ttu-id="07fa6-158">Como alternativa, puede incluir propiedades de navegación de las propiedades de navegación; para ello, pase una cadena separada por "." al método de extensión `.Include()`. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="07fa6-158">Alternately you can include navigation properties of navigation properties by passing a '.'-separated string to the `.Include()` extension method, like so:</span></span>

```csharp
    .Include("Items.Products")
```

<span data-ttu-id="07fa6-159">Además de encapsular la lógica de filtro, puede especificar la forma de los datos que se van a devolver, incluidas las propiedades que se van a rellenar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-159">In addition to encapsulating filtering logic, a specification can specify the shape of the data to be returned, including which properties to populate.</span></span> <span data-ttu-id="07fa6-160">En el ejemplo de eShopOnWeb se incluyen varias especificaciones que demuestran cómo encapsular información de carga diligente dentro de la especificación.</span><span class="sxs-lookup"><span data-stu-id="07fa6-160">The eShopOnWeb sample includes several specifications that demonstrate encapsulating eager loading information within the specification.</span></span> <span data-ttu-id="07fa6-161">Puede ver cómo se usa la especificación como parte de una consulta aquí:</span><span class="sxs-lookup"><span data-stu-id="07fa6-161">You can see how the specification is used as part of a query here:</span></span>

```csharp
// Includes all expression-based includes
query = specification.Includes.Aggregate(query,
            (current, include) => current.Include(include));

// Include any string-based include statements
query = specification.IncludeStrings.Aggregate(query,
            (current, include) => current.Include(include));
```

<span data-ttu-id="07fa6-162">Otra opción para cargar los datos relacionados consiste en usar la _carga explícita_.</span><span class="sxs-lookup"><span data-stu-id="07fa6-162">Another option for loading related data is to use _explicit loading_.</span></span> <span data-ttu-id="07fa6-163">La carga explícita permite cargar datos adicionales en una entidad que ya se ha recuperado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-163">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="07fa6-164">Como esto implica una solicitud independiente a la base de datos, no se recomienda para las aplicaciones web, que deben minimizar el número de recorridos de ida y vuelta a la base de datos por solicitud.</span><span class="sxs-lookup"><span data-stu-id="07fa6-164">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="07fa6-165">La _carga diferida_ es una característica que carga automáticamente los datos relacionados tal y como la aplicación hace referencia a ellos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-165">_Lazy loading_ is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="07fa6-166">EF Core ha agregado compatibilidad para la carga diferida en la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="07fa6-166">EF Core has added support for lazy loading in version 2.1.</span></span> <span data-ttu-id="07fa6-167">La carga diferida no está habilitada de forma predeterminada y requiere que se instale `Microsoft.EntityFrameworkCore.Proxies`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-167">Lazy loading is not enabled by default and requires installing the `Microsoft.EntityFrameworkCore.Proxies`.</span></span> <span data-ttu-id="07fa6-168">Como sucede con la carga explícita, normalmente la carga diferida se debe deshabilitar para las aplicaciones web, ya que su uso dará como resultado que se realicen consultas de base de datos adicionales dentro de cada solicitud web.</span><span class="sxs-lookup"><span data-stu-id="07fa6-168">As with explicit loading, lazy loading should typically be disabled for web applications, since its use will result in additional database queries being made within each web request.</span></span> <span data-ttu-id="07fa6-169">Desafortunadamente, la sobrecarga producida por la carga diferida a menudo pasa desapercibida en tiempo de desarrollo, cuando la latencia es reducida y los conjuntos de datos que se usan para las pruebas normalmente son pequeños.</span><span class="sxs-lookup"><span data-stu-id="07fa6-169">Unfortunately, the overhead incurred by lazy loading often goes unnoticed at development time, when latency is small and often the data sets used for testing are small.</span></span> <span data-ttu-id="07fa6-170">Pero en producción, con más usuarios, datos y latencia, las solicitudes de base de datos adicionales pueden causar un bajo rendimiento para las aplicaciones web que hacen un uso intensivo de la carga diferida.</span><span class="sxs-lookup"><span data-stu-id="07fa6-170">However, in production, with more users, more data, and more latency, the additional database requests can often result in poor performance for web applications that make heavy use of lazy loading.</span></span>

<span data-ttu-id="07fa6-171">[Avoid Lazy Loading Entities in ASPNET Applications](https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications) (Evitar la carga diferida de entidades en aplicaciones ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="07fa6-171">[Avoid Lazy Loading Entities in Web Applications](https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications)</span></span>

### <a name="encapsulating-data"></a><span data-ttu-id="07fa6-172">Encapsulación de datos</span><span class="sxs-lookup"><span data-stu-id="07fa6-172">Encapsulating data</span></span>

<span data-ttu-id="07fa6-173">EF Core admite varias características que permiten que el modelo encapsule correctamente su estado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-173">EF Core supports several features that allow your model to properly encapsulate its state.</span></span> <span data-ttu-id="07fa6-174">Un problema habitual de los modelos de dominio es que exponen propiedades de navegación de colecciones como tipos de lista públicamente accesibles.</span><span class="sxs-lookup"><span data-stu-id="07fa6-174">A common problem in domain models is that they expose collection navigation properties as publicly accessible list types.</span></span> <span data-ttu-id="07fa6-175">Esto permite que cualquier colaborador manipule el contenido de estos tipos de colecciones, con lo que se pueden omitir importantes reglas de negocio relacionadas con la colección, lo que podría dejar el objeto en un estado no válido.</span><span class="sxs-lookup"><span data-stu-id="07fa6-175">This allows any collaborator to manipulate the contents of these collection types, which may bypass important business rules related to the collection, possibly leaving the object in an invalid state.</span></span> <span data-ttu-id="07fa6-176">La solución es conceder acceso de solo lectura a las colecciones relacionadas y proporcionar explícitamente métodos que definan formas para que los clientes las manipulen, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07fa6-176">The solution to this is to expose read-only access to related collections, and explicitly provide methods defining ways in which clients can manipulate them, as in this example:</span></span>

```csharp
public class Basket : BaseEntity
{
    public string BuyerId { get; set; }
    private readonly List<BasketItem> _items = new List<BasketItem>();
    public IReadOnlyCollection<BasketItem> Items => _items.AsReadOnly();

    public void AddItem(int catalogItemId, decimal unitPrice, int quantity = 1)
    {
        if (!Items.Any(i => i.CatalogItemId == catalogItemId))
        {
            _items.Add(new BasketItem()
            {
                CatalogItemId = catalogItemId,
                Quantity = quantity,
                UnitPrice = unitPrice
            });
            return;
        }
        var existingItem = Items.FirstOrDefault(i => i.CatalogItemId == catalogItemId);
        existingItem.Quantity += quantity;
    }
}
```

<span data-ttu-id="07fa6-177">Este tipo de entidad no expone ninguna propiedad `List` o `ICollection` pública, sino que expone un tipo `IReadOnlyCollection` que encapsula el tipo de lista subyacente.</span><span class="sxs-lookup"><span data-stu-id="07fa6-177">This entity type doesn't expose a public `List` or `ICollection` property, but instead exposes an `IReadOnlyCollection` type that wraps the underlying List type.</span></span> <span data-ttu-id="07fa6-178">Al usar este patrón, puede indicar a Entity Framework Core que use el campo de respaldo de esta manera:</span><span class="sxs-lookup"><span data-stu-id="07fa6-178">When using this pattern, you can indicate to Entity Framework Core to use the backing field like so:</span></span>

```csharp
private void ConfigureBasket(EntityTypeBuilder<Basket> builder)
{
    var navigation = builder.Metadata.FindNavigation(nameof(Basket.Items));

    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
}
```

<span data-ttu-id="07fa6-179">Otra manera de mejorar el modelo de dominio es usar objetos de valor para los tipos que carecen de identidad y solo se distinguen por sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="07fa6-179">Another way in which you can improve your domain model is through the use of value objects for types that lack identity and are only distinguished by their properties.</span></span> <span data-ttu-id="07fa6-180">Usar estos tipos como propiedades de sus entidades puede ayudar a mantener la lógica específica del objeto de valor al que pertenece y evitar que se duplique la lógica en varias entidades que usen el mismo concepto.</span><span class="sxs-lookup"><span data-stu-id="07fa6-180">Using such types as properties of your entities can help keep logic specific to the value object where it belongs, and can avoid duplicate logic between multiple entities that use the same concept.</span></span> <span data-ttu-id="07fa6-181">En Entity Framework Core, puede conservar los objetos de valor en la misma tabla que su entidad en propiedad configurando el tipo como entidad en propiedad. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="07fa6-181">In Entity Framework Core, you can persist value objects in the same table as their owning entity by configuring the type as an owned entity, like so:</span></span>

```csharp
private void ConfigureOrder(EntityTypeBuilder<Order> builder)
{
    builder.OwnsOne(o => o.ShipToAddress);
}
```

<span data-ttu-id="07fa6-182">En este ejemplo, la propiedad `ShipToAddress` es del tipo `Address`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-182">In this example, the `ShipToAddress` property is of type `Address`.</span></span> <span data-ttu-id="07fa6-183">`Address` es un objeto de valor con varias propiedades, como `Street` y `City`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-183">`Address` is a value object with several properties such as `Street` and `City`.</span></span> <span data-ttu-id="07fa6-184">EF Core asigna el objeto `Order` a su tabla con una columna por propiedad `Address` y agrega el nombre de la propiedad como prefijo a cada nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="07fa6-184">EF Core maps the `Order` object to its table with one column per `Address` property, prefixing each column name with the name of the property.</span></span> <span data-ttu-id="07fa6-185">En este ejemplo, la tabla `Order` incluye columnas como `ShipToAddress_Street` y `ShipToAddress_City`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-185">In this example, the `Order` table would include columns such as `ShipToAddress_Street` and `ShipToAddress_City`.</span></span> <span data-ttu-id="07fa6-186">También es posible almacenar los tipos de propiedad en tablas independientes, si es lo que se busca hacer.</span><span class="sxs-lookup"><span data-stu-id="07fa6-186">It's also possible to store owned types in separate tables, if desired.</span></span>

<span data-ttu-id="07fa6-187">Obtenga más información sobre la [compatibilidad con entidades en EF Core](/ef/core/modeling/owned-entities).</span><span class="sxs-lookup"><span data-stu-id="07fa6-187">Learn more about owned [entity support in EF Core](/ef/core/modeling/owned-entities).</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="07fa6-188">Conexiones resistentes</span><span class="sxs-lookup"><span data-stu-id="07fa6-188">Resilient connections</span></span>

<span data-ttu-id="07fa6-189">En ocasiones, los recursos externos como las bases de datos SQL pueden no estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="07fa6-189">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="07fa6-190">En casos de indisponibilidad temporal, las aplicaciones pueden usar lógica de reintento para evitar que se genere una excepción.</span><span class="sxs-lookup"><span data-stu-id="07fa6-190">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="07fa6-191">Esta técnica se conoce normalmente como _resistencia de la conexión_.</span><span class="sxs-lookup"><span data-stu-id="07fa6-191">This technique is commonly referred to as _connection resiliency_.</span></span> <span data-ttu-id="07fa6-192">Se puede implementar una técnica de [reintento con retroceso exponencial propia](/azure/architecture/patterns/retry) intentando el reintento con un tiempo de espera que aumenta exponencialmente, hasta que se alcance un número máximo de reintentos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-192">You can implement your [own retry with exponential backoff](/azure/architecture/patterns/retry) technique by attempting to retry with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="07fa6-193">Esta técnica se basa en el hecho de que es posible que los recursos en la nube no estén disponibles de forma intermitente durante breves periodos de tiempos, lo que produciría un error en algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="07fa6-193">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="07fa6-194">Para Azure SQL DB, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="07fa6-194">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="07fa6-195">Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si quiere tener conexiones resistentes de EF Core.</span><span class="sxs-lookup"><span data-stu-id="07fa6-195">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="07fa6-196">Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite conexiones resistentes de SQL que se vuelven a intentar si se produce un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="07fa6-196">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

#### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="07fa6-197">Estrategias de ejecución y transacciones explícitas mediante BeginTransaction y varios DbContexts</span><span class="sxs-lookup"><span data-stu-id="07fa6-197">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="07fa6-198">Cuando se habilitan los reintentos en las conexiones de EF Core, cada operación que se realiza mediante EF Core se convierte en su propia operación que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-198">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="07fa6-199">Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.</span><span class="sxs-lookup"><span data-stu-id="07fa6-199">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="07fa6-200">Pero si el código inicia una transacción con BeginTransaction, va a definir un grupo de operaciones propio que se deben tratar como una unidad; todo dentro de la transacción se debe revertir si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="07fa6-200">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit; everything inside the transaction has to be rolled back if a failure occurs.</span></span> <span data-ttu-id="07fa6-201">Verá una excepción similar a la siguiente si intenta ejecutar esa transacción cuando se usa una estrategia de ejecución de EF (directiva de reintentos) y se incluyen varias llamadas de SaveChanges de varios DbContext en la transacción.</span><span class="sxs-lookup"><span data-stu-id="07fa6-201">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="07fa6-202">System.InvalidOperationException: la estrategia de ejecución configurada "SqlServerRetryingExecutionStrategy" no es compatible con las transacciones que el usuario inicie.</span><span class="sxs-lookup"><span data-stu-id="07fa6-202">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="07fa6-203">Use la estrategia de ejecución que devuelve "DbContext.Database.CreateExecutionStrategy()" para ejecutar todas las operaciones en la transacción como una unidad que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-203">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retryable unit.</span></span>

<span data-ttu-id="07fa6-204">La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa a todos los elementos que se deben ejecutar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-204">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="07fa6-205">Si se produce un error transitorio, la estrategia de ejecución vuelve a invocar al delegado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-205">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="07fa6-206">En el código siguiente se muestra cómo implementar este enfoque:</span><span class="sxs-lookup"><span data-stu-id="07fa6-206">The following code shows how to implement this approach:</span></span>

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

<span data-ttu-id="07fa6-207">El primer DbContext es \_catalogContext y el segundo DbContext está dentro del objeto \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="07fa6-207">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="07fa6-208">Por último, la acción Commit se realizará en varios DbContext mediante una estrategia de ejecución de EF.</span><span class="sxs-lookup"><span data-stu-id="07fa6-208">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="07fa6-209">Referencias: Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="07fa6-209">References – Entity Framework Core</span></span>
>
> - <span data-ttu-id="07fa6-210">**Documentación de EF Core**
>   <https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="07fa6-210">**EF Core Docs**
<https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="07fa6-211">**EF Core: datos relacionados**
>   <https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="07fa6-211">**EF Core: Related Data**
<https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="07fa6-212">**Evitar la carga diferida de entidades en aplicaciones ASP.NET**
>   <https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="07fa6-212">**Avoid Lazy Loading Entities in ASPNET Applications**
<https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="07fa6-213">¿EF Core o micro-ORM?</span><span class="sxs-lookup"><span data-stu-id="07fa6-213">EF Core or micro-ORM?</span></span>

<span data-ttu-id="07fa6-214">Aunque EF Core es una opción excelente para administrar la persistencia, y en su mayor parte encapsula los detalles de base de datos de los desarrolladores de aplicaciones, no es la única opción.</span><span class="sxs-lookup"><span data-stu-id="07fa6-214">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it isn't the only choice.</span></span> <span data-ttu-id="07fa6-215">Otra alternativa de código abierto popular es [Dapper](https://github.com/StackExchange/Dapper), lo que se denomina un micro-ORM.</span><span class="sxs-lookup"><span data-stu-id="07fa6-215">Another popular open-source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="07fa6-216">Un micro-ORM es una herramienta ligera y menos completa para la asignación de objetos a estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-216">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="07fa6-217">En el caso de Dapper, sus objetivos de diseño se centran en el rendimiento, en lugar de encapsular totalmente las consultas subyacentes que usa para recuperar y actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-217">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="07fa6-218">Como no abstrae SQL del desarrollador, Dapper es "más cercano al sistema operativo" y permite a los desarrolladores escribir las consultas exactas que quieren usar para una operación de acceso a datos determinada.</span><span class="sxs-lookup"><span data-stu-id="07fa6-218">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="07fa6-219">EF Core proporciona dos características importantes que lo diferencian de Dapper, pero que también se agregan a su sobrecarga de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="07fa6-219">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="07fa6-220">La primera es la traducción de expresiones LINQ a SQL.</span><span class="sxs-lookup"><span data-stu-id="07fa6-220">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="07fa6-221">Estas traducciones se almacenan en caché, pero aun así hay sobrecarga la primera vez que se realizan.</span><span class="sxs-lookup"><span data-stu-id="07fa6-221">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="07fa6-222">La segunda es el seguimiento de los cambios en las entidades (para poder generar instrucciones de actualización eficaces).</span><span class="sxs-lookup"><span data-stu-id="07fa6-222">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="07fa6-223">Este comportamiento se puede desactivar para consultas específicas mediante la extensión AsNotTracking.</span><span class="sxs-lookup"><span data-stu-id="07fa6-223">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="07fa6-224">EF Core también genera consultas SQL que suelen ser muy eficaces y en cualquier caso perfectamente aceptables desde la perspectiva del rendimiento, pero si se necesita un control preciso sobre la consulta específica que se va a ejecutar, también se puede pasar código SQL personalizado (o ejecutar un procedimiento almacenado) con EF Core.</span><span class="sxs-lookup"><span data-stu-id="07fa6-224">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="07fa6-225">En este caso, Dapper también supera a EF Core, pero solo ligeramente.</span><span class="sxs-lookup"><span data-stu-id="07fa6-225">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="07fa6-226">Julie Lerman presenta algunos datos de rendimiento en su artículo de MSDN de mayo de 2016 [Dapper, Entity Framework y aplicaciones híbridas](/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps).</span><span class="sxs-lookup"><span data-stu-id="07fa6-226">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps).</span></span> <span data-ttu-id="07fa6-227">En [el sitio de Dapper](https://github.com/StackExchange/Dapper) se pueden encontrar datos de pruebas comparativas de rendimiento adicionales para una amplia variedad de métodos de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-227">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="07fa6-228">Para ver cómo varía la sintaxis de Dapper con respecto a EF Core, tenga en cuenta estas dos versiones del mismo método para recuperar una lista de elementos:</span><span class="sxs-lookup"><span data-stu-id="07fa6-228">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

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

<span data-ttu-id="07fa6-229">Si tiene que generar gráficos de objetos más complejos con Dapper, tendrá que escribir personalmente las consultas asociadas (en lugar de agregar un archivo de inclusión como haría en EF Core).</span><span class="sxs-lookup"><span data-stu-id="07fa6-229">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="07fa6-230">Esto se admite a través de diferentes sintaxis, incluida una característica denominada Asignación múltiple que permite asignar filas individuales a varios objetos asignados.</span><span class="sxs-lookup"><span data-stu-id="07fa6-230">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="07fa6-231">Por ejemplo, dada una clase Post con una propiedad Owner de tipo User, el código SQL siguiente devolvería todos los datos necesarios:</span><span class="sxs-lookup"><span data-stu-id="07fa6-231">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="07fa6-232">Cada fila devuelta incluye los datos de User y Post.</span><span class="sxs-lookup"><span data-stu-id="07fa6-232">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="07fa6-233">Como los datos de User se deben asociar a los datos de Post a través de su propiedad Owner, se usa la función siguiente:</span><span class="sxs-lookup"><span data-stu-id="07fa6-233">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="07fa6-234">La lista de código completa para devolver una colección de entradas con su propiedad Owner rellenada con los datos de usuario asociados sería esta:</span><span class="sxs-lookup"><span data-stu-id="07fa6-234">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="07fa6-235">Como ofrece menos encapsulación, Dapper requiere que los desarrolladores tengan más información sobre cómo se almacenan los datos, cómo consultarlos de forma eficaz y escribir más código para recuperarlos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-235">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="07fa6-236">Cuando el modelo cambia, en lugar de crear simplemente una migración (otra característica de EF Core) o actualizar la información de asignación en una posición en un DbContext, se deben actualizar todas las consultas que se van a ver afectadas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-236">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="07fa6-237">Estas consultas no tienen garantías en tiempo de compilación, por lo que se pueden interrumpir en tiempo de ejecución en respuesta a cambios en el modelo o la base de datos, lo que dificulta más la detección rápida de los errores.</span><span class="sxs-lookup"><span data-stu-id="07fa6-237">These queries have no compile-time guarantees, so they may break at run time in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="07fa6-238">A cambio de estos inconvenientes, Dapper ofrece un rendimiento extremadamente rápido.</span><span class="sxs-lookup"><span data-stu-id="07fa6-238">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="07fa6-239">Para la mayoría de las aplicaciones y la mayoría de los elementos de casi todas las aplicaciones, EF Core ofrece un rendimiento aceptable.</span><span class="sxs-lookup"><span data-stu-id="07fa6-239">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="07fa6-240">Por tanto, sus ventajas de productividad para los desarrolladores suelen superar su sobrecarga de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="07fa6-240">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="07fa6-241">Para las consultas que se pueden beneficiar del almacenamiento en caché, es posible que solo se pueda ejecutar la consulta real en un pequeño porcentaje de los casos, lo que hace que las diferencias de rendimiento de las consultas de pequeño tamaño sean irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="07fa6-241">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="07fa6-242">SQL o NoSQL</span><span class="sxs-lookup"><span data-stu-id="07fa6-242">SQL or NoSQL</span></span>

<span data-ttu-id="07fa6-243">Tradicionalmente, las bases de datos relacionales como SQL Server han dominado el mercado del almacenamiento de datos persistentes, pero no son la única solución disponible.</span><span class="sxs-lookup"><span data-stu-id="07fa6-243">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="07fa6-244">Las bases de datos NoSQL como [MongoDB](https://www.mongodb.com/what-is-mongodb) ofrecen un enfoque diferente para el almacenamiento de objetos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-244">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="07fa6-245">En lugar de asignar objetos a tablas y filas, otra opción consiste en serializar el gráfico de objetos completo y almacenar el resultado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-245">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="07fa6-246">Las ventajas de este enfoque, al menos inicialmente, son la simplicidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="07fa6-246">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="07fa6-247">Es más simple almacenar un único objeto serializado con una clave que descomponerlo en muchas tablas con relaciones, actualizaciones y filas que pueden haber cambiado desde la última vez que se recuperó el objeto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-247">It's simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="07fa6-248">Del mismo modo, la recuperación y deserialización de un único objeto de un almacén basado en claves suele ser mucho más rápida y sencilla que combinaciones complejas o varias consultas de base de datos necesarias para crear completamente el mismo objeto de una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="07fa6-248">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="07fa6-249">La falta de bloqueos o transacciones, o de un esquema fijo, también hace que las bases de datos NoSQL sean sensibles al escalado entre varios equipos, admitiendo grandes conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-249">The lack of locks or transactions or a fixed schema also makes NoSQL databases amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="07fa6-250">Por otro lado, las bases de datos NoSQL (como normalmente se denominan) tienen sus desventajas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-250">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="07fa6-251">Las bases de datos relacionales usan la normalización para aplicar la coherencia y evitar la duplicación de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-251">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="07fa6-252">Esto reduce el tamaño total de la base de datos y garantiza que las actualizaciones de los datos compartidos estén disponibles inmediatamente en toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-252">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="07fa6-253">En una base de datos relacional, es posible que una tabla de direcciones haga referencia a una tabla de país por el id., de forma que, si se cambiara el nombre de un país o región, los registros de direcciones se beneficiarían de la actualización sin tener que actualizarlos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-253">In a relational database, an Address table might reference a Country table by ID, such that if the name of a country/region were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="07fa6-254">Pero en una base de datos NoSQL, es posible que la dirección y su país o región asociado se serialicen como parte de muchos objetos almacenados.</span><span class="sxs-lookup"><span data-stu-id="07fa6-254">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="07fa6-255">Una actualización en un nombre de país o región requeriría actualizar todos esos objetos, en lugar de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="07fa6-255">An update to a country/region name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="07fa6-256">Las bases de datos relacionales también pueden asegurar la integridad relacional mediante la aplicación de reglas como claves externas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-256">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="07fa6-257">Normalmente, las bases de datos NoSQL no ofrecen estas restricciones en sus datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-257">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="07fa6-258">Otra complejidad que las bases de datos NoSQL deben superar es el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="07fa6-258">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="07fa6-259">Cuando cambian las propiedades de un objeto, es posible que no se pueda deserializar de las versiones anteriores que se almacenaron.</span><span class="sxs-lookup"><span data-stu-id="07fa6-259">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="07fa6-260">Por tanto, todos los objetos existentes que tengan una versión serializada (anterior) del objeto tendrán que actualizarse para que se ajusten a su esquema nuevo.</span><span class="sxs-lookup"><span data-stu-id="07fa6-260">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="07fa6-261">Conceptualmente, esto no es diferente a una base de datos relacional, en la que los cambios del esquema a veces requieren scripts de actualización o asignación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="07fa6-261">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="07fa6-262">Pero el número de entradas que se deben modificar suele ser mucho mayor en el enfoque de NoSQL, porque hay más duplicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-262">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="07fa6-263">En las bases de datos NoSQL se pueden almacenar varias versiones de los objetos, algo que las bases de datos relacionales de esquema fijo normalmente no admiten.</span><span class="sxs-lookup"><span data-stu-id="07fa6-263">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="07fa6-264">Pero en este caso, el código de la aplicación tendrá que tener en cuenta la existencia de versiones anteriores de los objetos, lo que agrega complejidad adicional.</span><span class="sxs-lookup"><span data-stu-id="07fa6-264">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="07fa6-265">Las bases de datos NoSQL normalmente no aplican [ACID](https://en.wikipedia.org/wiki/ACID), lo que significa que tienen ventajas de rendimiento y escalabilidad con respecto a las bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="07fa6-265">NoSQL databases typically do not enforce [ACID](https://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="07fa6-266">Son adecuadas para conjuntos de datos y objetos muy grandes que no son adecuados para el almacenamiento en estructuras de tabla normalizadas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-266">They're well suited to extremely large datasets and objects that are not well suited to storage in normalized table structures.</span></span> <span data-ttu-id="07fa6-267">No hay ninguna razón para que una aplicación no pueda aprovechar las ventajas de las bases de datos relacionales y NoSQL, y usar cada una cuando sea más adecuado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-267">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-cosmos-db"></a><span data-ttu-id="07fa6-268">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="07fa6-268">Azure Cosmos DB</span></span>

<span data-ttu-id="07fa6-269">Azure Cosmos DB es un servicio de base de datos NoSQL completamente administrado que ofrece almacenamiento de datos sin esquema basado en la nube.</span><span class="sxs-lookup"><span data-stu-id="07fa6-269">Azure Cosmos DB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="07fa6-270">Azure Cosmos DB se ha creado para rendimiento rápido y predecible, alta disponibilidad, escalado elástico y distribución global.</span><span class="sxs-lookup"><span data-stu-id="07fa6-270">Azure Cosmos DB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="07fa6-271">A pesar de ser una base de datos NoSQL, los desarrolladores pueden usar funciones de consulta SQL enriquecidas y conocidas en los datos JSON.</span><span class="sxs-lookup"><span data-stu-id="07fa6-271">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="07fa6-272">Todos los recursos de Azure Cosmos DB se almacenan como documentos JSON.</span><span class="sxs-lookup"><span data-stu-id="07fa6-272">All resources in Azure Cosmos DB are stored as JSON documents.</span></span> <span data-ttu-id="07fa6-273">Los recursos se administran como _elementos_, que son documentos que contienen metadatos, y _fuentes_, que son colecciones de elementos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-273">Resources are managed as _items_, which are documents containing metadata, and _feeds_, which are collections of items.</span></span> <span data-ttu-id="07fa6-274">En la figura 8-2 se muestra la relación entre los diferentes recursos de Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="07fa6-274">Figure 8-2 shows the relationship between different Azure Cosmos DB resources.</span></span>

![La relación jerárquica entre los recursos de Azure Cosmos DB, una base de datos JSON NoSQL](./media/image8-2.png)

<span data-ttu-id="07fa6-276">**Figura 8-2.**</span><span class="sxs-lookup"><span data-stu-id="07fa6-276">**Figure 8-2.**</span></span> <span data-ttu-id="07fa6-277">Organización de recursos de Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="07fa6-277">Azure Cosmos DB resource organization.</span></span>

<span data-ttu-id="07fa6-278">El lenguaje de consulta de Azure Cosmos DB es una interfaz sencilla, pero eficaz, para consultar documentos JSON.</span><span class="sxs-lookup"><span data-stu-id="07fa6-278">The Azure Cosmos DB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="07fa6-279">El lenguaje admite un subconjunto de la gramática SQL ANSI y agrega integración profunda de matrices de objetos JavaScript, construcción de objetos e invocación de funciones.</span><span class="sxs-lookup"><span data-stu-id="07fa6-279">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="07fa6-280">**Referencias: Azure Cosmos DB**</span><span class="sxs-lookup"><span data-stu-id="07fa6-280">**References – Azure Cosmos DB**</span></span>

- <span data-ttu-id="07fa6-281">Introducción a Azure Cosmos DB<https://docs.microsoft.com/azure/cosmos-db/introduction></span><span class="sxs-lookup"><span data-stu-id="07fa6-281">Azure Cosmos DB Introduction <https://docs.microsoft.com/azure/cosmos-db/introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="07fa6-282">Otras opciones de persistencia</span><span class="sxs-lookup"><span data-stu-id="07fa6-282">Other persistence options</span></span>

<span data-ttu-id="07fa6-283">Además de las opciones de almacenamiento relacionales y NoSQL, en las aplicaciones ASP.NET Core se puede usar Azure Storage para almacenar una variedad de formatos de datos y archivos de forma escalable y basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="07fa6-283">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="07fa6-284">Azure Storage es escalable de forma masiva, para que pueda empezar a almacenar pequeñas cantidades de datos y escalar verticalmente hasta almacenar cientos o terabytes si así lo requiere la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07fa6-284">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="07fa6-285">Azure Storage admite cuatro tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="07fa6-285">Azure Storage supports four kinds of data:</span></span>

- <span data-ttu-id="07fa6-286">Blob Storage para almacenamiento de texto binario no estructurado, que también se denomina almacenamiento de objetos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-286">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

- <span data-ttu-id="07fa6-287">Table Storage para conjuntos de datos estructurados, accesible a través de claves de fila.</span><span class="sxs-lookup"><span data-stu-id="07fa6-287">Table Storage for structured datasets, accessible via row keys.</span></span>

- <span data-ttu-id="07fa6-288">Queue Storage para la mensajería confiable basada en colas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-288">Queue Storage for reliable queue-based messaging.</span></span>

- <span data-ttu-id="07fa6-289">File Storage para el acceso a archivos compartido entre máquinas virtuales de Azure y aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="07fa6-289">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="07fa6-290">**Referencias: Azure Storage**</span><span class="sxs-lookup"><span data-stu-id="07fa6-290">**References – Azure Storage**</span></span>

- <span data-ttu-id="07fa6-291">Introducción a Azure Storage<https://docs.microsoft.com/azure/storage/common/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="07fa6-291">Azure Storage Introduction <https://docs.microsoft.com/azure/storage/common/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="07fa6-292">Almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="07fa6-292">Caching</span></span>

<span data-ttu-id="07fa6-293">En las aplicaciones web, cada solicitud web se debe completar en el menor tiempo posible.</span><span class="sxs-lookup"><span data-stu-id="07fa6-293">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="07fa6-294">Una manera de conseguirlo consiste en limitar el número de llamadas externas que el servidor debe realizar para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="07fa6-294">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="07fa6-295">El almacenamiento en caché implica almacenar una copia de los datos en el servidor (u otro almacén de datos que sea más fácil de consultar que el origen de los datos).</span><span class="sxs-lookup"><span data-stu-id="07fa6-295">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="07fa6-296">Las aplicaciones web y especialmente las aplicaciones web tradicionales que no son de SPA, necesitan generar la interfaz de usuario completa con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="07fa6-296">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="07fa6-297">Con frecuencia, esto implica realizar muchas de las mismas consultas de base de datos varias veces de una solicitud de usuario a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="07fa6-297">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="07fa6-298">En la mayoría de los casos, estos datos apenas cambian, de modo que no hay motivos para solicitarlos constantemente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-298">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="07fa6-299">ASP.NET Core admite el almacenamiento de respuestas en caché, para almacenar en caché páginas completas y el almacenamiento de datos en caché, que admite un comportamiento de almacenamiento en caché más granular.</span><span class="sxs-lookup"><span data-stu-id="07fa6-299">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="07fa6-300">Al implementar el almacenamiento en caché, es importante tener en cuenta la separación de intereses.</span><span class="sxs-lookup"><span data-stu-id="07fa6-300">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="07fa6-301">Evite implementar la lógica de almacenamiento en caché en la lógica de acceso a datos o en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="07fa6-301">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="07fa6-302">En su lugar, encapsule el almacenamiento en caché en sus propias clases y use la configuración para administrar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="07fa6-302">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="07fa6-303">Esto sigue los principios de Abierto o cerrado y Responsabilidad única, y facilitará la administración de cómo usar el almacenamiento en caché en la aplicación cuando crezca.</span><span class="sxs-lookup"><span data-stu-id="07fa6-303">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="07fa6-304">Almacenamiento en caché de respuestas de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07fa6-304">ASP.NET Core response caching</span></span>

<span data-ttu-id="07fa6-305">ASP.NET Core admite dos niveles de almacenamiento en caché de respuestas.</span><span class="sxs-lookup"><span data-stu-id="07fa6-305">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="07fa6-306">El primer nivel no almacena en caché nada en el servidor, pero agrega encabezados HTTP que indican a los clientes y servidores proxy que almacenen las respuestas en caché.</span><span class="sxs-lookup"><span data-stu-id="07fa6-306">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="07fa6-307">Esto se implementa mediante la adición del atributo ResponseCache a controladores o acciones individuales:</span><span class="sxs-lookup"><span data-stu-id="07fa6-307">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
[ResponseCache(Duration = 60)]
public IActionResult Contact()
{
    ViewData["Message"] = "Your contact page.";
    return View();
}
```

<span data-ttu-id="07fa6-308">Como resultado del ejemplo anterior, el encabezado siguiente se agrega a la respuesta, indicando a los clientes que almacenen el resultado en caché hasta 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-308">The previous example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.</span></span>

<span data-ttu-id="07fa6-309">Cache-Control: public,max-age=60</span><span class="sxs-lookup"><span data-stu-id="07fa6-309">Cache-Control: public,max-age=60</span></span>

<span data-ttu-id="07fa6-310">Con el fin de agregar almacenamiento en caché en memoria del lado servidor a la aplicación, debe hacer referencia al paquete NuGet Microsoft.AspNetCore.ResponseCaching y, después, agregar el software intermedio de almacenamiento de las respuestas en caché.</span><span class="sxs-lookup"><span data-stu-id="07fa6-310">In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware.</span></span> <span data-ttu-id="07fa6-311">Este software intermedio se configura en Startup, tanto en ConfigureServices y Configure:</span><span class="sxs-lookup"><span data-stu-id="07fa6-311">This middleware is configured in both ConfigureServices and Configure in Startup:</span></span>

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

<span data-ttu-id="07fa6-312">El software intermedio de almacenamiento de las respuestas en caché almacenará automáticamente las respuestas en caché en función de un conjunto de condiciones que se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-312">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="07fa6-313">De forma predeterminada, solo se almacenan en caché las respuestas 200 (OK) solicitadas a través de métodos GET o HEAD.</span><span class="sxs-lookup"><span data-stu-id="07fa6-313">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="07fa6-314">Además, las solicitudes deben tener una respuesta con un encabezado público Cache-Control: y no pueden incluir encabezados Authorization o Set-Cookie.</span><span class="sxs-lookup"><span data-stu-id="07fa6-314">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="07fa6-315">Vea una [lista completa de las condiciones de almacenamiento en caché que usa el software intermedio de almacenamiento en caché de las respuestas](/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="07fa6-315">See a [complete list of the caching conditions used by the response caching middleware](/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="07fa6-316">Almacenamiento de datos en caché</span><span class="sxs-lookup"><span data-stu-id="07fa6-316">Data caching</span></span>

<span data-ttu-id="07fa6-317">En lugar (o además de) almacenar en caché las respuestas web completas, se pueden almacenar en caché los resultados de consultas de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="07fa6-317">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="07fa6-318">Para ello, se puede usar el almacenamiento en caché en memoria en el servidor web o [una caché distribuida](/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="07fa6-318">For this, you can use in memory caching on the web server, or use [a distributed cache](/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="07fa6-319">En esta sección se muestra cómo implementar el almacenamiento en caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="07fa6-319">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="07fa6-320">La compatibilidad para el almacenamiento en caché en memoria (o caché distribuida) se agrega en ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="07fa6-320">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="07fa6-321">Asegúrese de agregar también el paquete NuGet Microsoft.Extensions.Caching.Memory.</span><span class="sxs-lookup"><span data-stu-id="07fa6-321">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="07fa6-322">Una vez agregado el servicio, se solicita IMemoryCache a través de la inserción de dependencias siempre que haya que obtener acceso a la caché.</span><span class="sxs-lookup"><span data-stu-id="07fa6-322">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="07fa6-323">En este ejemplo, el CachedCatalogService usa el patrón de diseño de Proxy (o Decorador), proporcionando una implementación alternativa de ICatalogService que controla el acceso a la implementación de CatalogService subyacente (o le agrega comportamiento).</span><span class="sxs-lookup"><span data-stu-id="07fa6-323">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
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
        string cacheKey = $"items-{pageIndex}-{itemsPage}-{brandID}-{typeId}";
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

<span data-ttu-id="07fa6-324">Para configurar la aplicación para usar la versión en caché del servicio, pero seguir permitiendo que el servicio obtenga la instancia de CatalogService que necesita en su constructor, se debe agregar lo siguiente en ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="07fa6-324">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="07fa6-325">Después de agregarlo, las llamadas de base de datos para recuperar los datos del catálogo solo se realizarán una vez por minuto, en lugar de en cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="07fa6-325">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="07fa6-326">Según el tráfico al sitio, esto puede tener un impacto significativo en el número de consultas realizadas a la base de datos y el tiempo medio de carga de la página principal que depende actualmente de las tres consultas expuestas por este servicio.</span><span class="sxs-lookup"><span data-stu-id="07fa6-326">Depending on the traffic to the site, this can have a significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="07fa6-327">Un problema que surge cuando se implementa el almacenamiento en caché es el de los _datos obsoletos_, es decir, datos que han cambiado en el origen, pero de los que permanece en caché una versión obsoleta.</span><span class="sxs-lookup"><span data-stu-id="07fa6-327">An issue that arises when caching is implemented is _stale data_ – that is, data that has changed at the source but an out-of-date version remains in the cache.</span></span> <span data-ttu-id="07fa6-328">Una manera sencilla de mitigar este problema consiste en usar duraciones de caché pequeñas, ya que para una aplicación ocupada la ventaja adicional de extender la longitud de los datos en caché es limitada.</span><span class="sxs-lookup"><span data-stu-id="07fa6-328">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="07fa6-329">Por ejemplo, considere una página que realiza una única consulta de base de datos y se solicita 10 veces por segundo.</span><span class="sxs-lookup"><span data-stu-id="07fa6-329">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="07fa6-330">Si esta página se almacena en caché durante un minuto, el número de consultas de base de datos realizadas por minuto descenderá 600 a 1, una reducción del 99,8 %.</span><span class="sxs-lookup"><span data-stu-id="07fa6-330">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="07fa6-331">Si en su lugar, la duración de la caché fuera de una hora, la reducción general sería de 99,997 %, pero ahora la probabilidad y la antigüedad posible de los datos obsoletos aumentan considerablemente.</span><span class="sxs-lookup"><span data-stu-id="07fa6-331">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="07fa6-332">Otro enfoque consiste en quitar proactivamente las entradas de caché cuando se actualizan los datos que contienen.</span><span class="sxs-lookup"><span data-stu-id="07fa6-332">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="07fa6-333">Cualquier entrada individual se puede quitar si se conoce su clave:</span><span class="sxs-lookup"><span data-stu-id="07fa6-333">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="07fa6-334">Si la aplicación expone funcionalidad para actualizar las entradas que almacena en caché, puede quitar las entradas de caché correspondientes en el código que realiza las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="07fa6-334">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="07fa6-335">En ocasiones puede haber muchas otras entradas que dependen de un conjunto de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-335">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="07fa6-336">En ese caso, puede ser útil crear dependencias entre las entradas de caché, mediante el uso de un CancellationChangeToken.</span><span class="sxs-lookup"><span data-stu-id="07fa6-336">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="07fa6-337">Con un CancellationChangeToken se pueden expirar varias entradas de caché a la vez si se cancela el token.</span><span class="sxs-lookup"><span data-stu-id="07fa6-337">With a CancellationChangeToken, you can expire multiple cache entries at once by canceling the token.</span></span>

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

<span data-ttu-id="07fa6-338">El almacenamiento en caché puede mejorar considerablemente el rendimiento de las páginas web que solicitan repetidamente los mismos valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-338">Caching can dramatically improve the performance of web pages that repeatedly request the same values from the database.</span></span> <span data-ttu-id="07fa6-339">Asegúrese de medir el acceso de datos y el rendimiento de la página antes de aplicar el almacenamiento en caché y aplíquelo solo donde vea una necesidad de mejora.</span><span class="sxs-lookup"><span data-stu-id="07fa6-339">Be sure to measure data access and page performance before applying caching, and only apply caching where you see a need for improvement.</span></span> <span data-ttu-id="07fa6-340">El almacenamiento en caché consume recursos de memoria de servidor web y aumenta la complejidad de la aplicación, por lo que es importante que no optimice de forma prematura con esta técnica.</span><span class="sxs-lookup"><span data-stu-id="07fa6-340">Caching consumes web server memory resources and increases the complexity of the application, so it's important you don't prematurely optimize using this technique.</span></span>

## <a name="getting-data-to-no-locblazor-no-locwebassembly-apps"></a><span data-ttu-id="07fa6-341">Obtención de datos para aplicaciones de Blazor WebAssembly</span><span class="sxs-lookup"><span data-stu-id="07fa6-341">Getting data to Blazor WebAssembly apps</span></span>

<span data-ttu-id="07fa6-342">Si va a compilar aplicaciones que usan Blazor Server, puede usar Entity Framework y otras tecnologías de acceso directo a datos como se han analizado hasta ahora en este capítulo.</span><span class="sxs-lookup"><span data-stu-id="07fa6-342">If you're building apps that use Blazor Server, you can use Entity Framework and other direct data access technologies as they've been discussed thus far in this chapter.</span></span> <span data-ttu-id="07fa6-343">Pero al compilar aplicaciones de Blazor WebAssembly, como otros marcos de SPA, necesitará una estrategia diferente para acceder a los datos.</span><span class="sxs-lookup"><span data-stu-id="07fa6-343">However, when building Blazor WebAssembly apps, like other SPA frameworks, you will need a different strategy for data access.</span></span> <span data-ttu-id="07fa6-344">Normalmente, estas aplicaciones acceden a los datos e interactúan con el servidor a través de puntos de conexión de API web.</span><span class="sxs-lookup"><span data-stu-id="07fa6-344">Typically, these applications access data and interact with the server through web API endpoints.</span></span>

<span data-ttu-id="07fa6-345">Si los datos o las operaciones que se realizan son confidenciales, asegúrese de revisar la sección sobre seguridad del [capítulo anterior](develop-asp-net-core-mvc-apps.md) y de proteger las API frente al acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="07fa6-345">If the data or operations being performed are sensitive, be sure to review the section on security in the [previous chapter](develop-asp-net-core-mvc-apps.md) and protect your APIs against unauthorized access.</span></span>

<span data-ttu-id="07fa6-346">Encontrará un ejemplo de una aplicación de Blazor WebAssembly en la [aplicación de referencia eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb) en el proyecto BlazorAdmin.</span><span class="sxs-lookup"><span data-stu-id="07fa6-346">You'll find an example of a Blazor WebAssembly app in the [eShopOnWeb reference application](https://github.com/dotnet-architecture/eShopOnWeb), in the BlazorAdmin project.</span></span> <span data-ttu-id="07fa6-347">Este proyecto se hospeda dentro del proyecto web eShopOnWeb y permite a los usuarios del grupo de administradores administrar los elementos del almacén.</span><span class="sxs-lookup"><span data-stu-id="07fa6-347">This project is hosted within the eShopOnWeb Web project, and allows users in the Administrators group to manage the items in the store.</span></span> <span data-ttu-id="07fa6-348">Puede ver una captura de pantalla de la aplicación en la figura 8-3.</span><span class="sxs-lookup"><span data-stu-id="07fa6-348">You can see a screenshot of the application in Figure 8-3.</span></span>

![Captura de pantalla del administrador del catálogo de eShopOnWeb](./media/image8-3.jpg)

<span data-ttu-id="07fa6-350">**Figura 8-3.**</span><span class="sxs-lookup"><span data-stu-id="07fa6-350">**Figure 8-3.**</span></span> <span data-ttu-id="07fa6-351">Captura de pantalla de administrador del catálogo de eShopOnWeb.</span><span class="sxs-lookup"><span data-stu-id="07fa6-351">eShopOnWeb Catalog Admin Screenshot.</span></span>

<span data-ttu-id="07fa6-352">A la hora de obtener datos de las API web dentro de una aplicación de Blazor WebAssembly, simplemente use una instancia de `HttpClient` como haría en cualquier aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="07fa6-352">When fetching data from web APIs within a Blazor WebAssembly app, you just use an instance of `HttpClient` as you would in any .NET application.</span></span> <span data-ttu-id="07fa6-353">Los pasos básicos a seguir son crear la solicitud de envío (si es necesario, normalmente para las solicitudes POST o PUT), esperar a que se realice la solicitud, comprobar el código de estado y deserializar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="07fa6-353">The basic steps involved are to create the request to send (if required, usually for POST or PUT requests), await the request itself, verify the status code, and deserialize the response.</span></span> <span data-ttu-id="07fa6-354">Si va a hacer muchas solicitudes a un determinado conjunto de API, es aconsejable encapsular las API y configurar la dirección base de `HttpClient` de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="07fa6-354">If you're going to make many requests to a given set of APIs, it's a good idea to encapsulate your APIs and configure the `HttpClient` base address centrally.</span></span> <span data-ttu-id="07fa6-355">De este modo, si necesita ajustar cualquiera de estas configuraciones en varios entornos, puede realizar los cambios en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="07fa6-355">This way, if you need to adjust any of these settings between environments, you can make the changes in just one place.</span></span> <span data-ttu-id="07fa6-356">Debe agregar compatibilidad con este servicio en `Program.Main`:</span><span class="sxs-lookup"><span data-stu-id="07fa6-356">You should add support for this service in your `Program.Main`:</span></span>

```csharp
builder.Services.AddScoped(sp =>
    new HttpClient
    {
        BaseAddress = new Uri(builder.HostEnvironment.BaseAddress)
    });
```

<span data-ttu-id="07fa6-357">Si necesita acceder a los servicios de forma segura, acceda a un token seguro y configurar `HttpClient` para pasar este token como un encabezado de autenticación con cada solicitud:</span><span class="sxs-lookup"><span data-stu-id="07fa6-357">If you need to access services securely, you should access a secure token and configure the `HttpClient` to pass this token as an Authentication header with every request:</span></span>

```csharp
_httpClient.DefaultRequestHeaders.Authorization =
    new AuthenticationHeaderValue("Bearer", token);
```

<span data-ttu-id="07fa6-358">Esto se puede hacer desde cualquier componente que tenga `HttpClient` insertado, siempre que `HttpClient` no se haya agregado a los servicios de la aplicación con una duración `Transient`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-358">This can be done from any component that has the `HttpClient` injected into it, provided that `HttpClient` wasn't added to the application's services with a `Transient` lifetime.</span></span> <span data-ttu-id="07fa6-359">Todas las referencias a `HttpClient` en la aplicación hacen referencia a la misma instancia, por lo que los cambios en un componente se aplican en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07fa6-359">Every reference to `HttpClient` in the application references the same instance, so changes to it in one component flow through the entire application.</span></span> <span data-ttu-id="07fa6-360">Un buen lugar para realizar esta comprobación de autenticación (y después, la especificación del token) es en un componente compartido, como la navegación principal del sitio.</span><span class="sxs-lookup"><span data-stu-id="07fa6-360">A good place to perform this authentication check (followed by specifying the token) is in a shared component like the main navigation for the site.</span></span> <span data-ttu-id="07fa6-361">Obtenga más información sobre este enfoque en el proyecto `BlazorAdmin` en la [aplicación de referencia eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).</span><span class="sxs-lookup"><span data-stu-id="07fa6-361">Learn more about this approach in the `BlazorAdmin` project in the [eShopOnWeb reference application](https://github.com/dotnet-architecture/eShopOnWeb).</span></span>

<span data-ttu-id="07fa6-362">Uno de los beneficios de Blazor WebAssembly frente a las SPA tradicionales de JavaScript es que no es necesario conservar sincronizadas las copias de los objetos de transferencia de datos (DTO).</span><span class="sxs-lookup"><span data-stu-id="07fa6-362">One benefit of Blazor WebAssembly over traditional JavaScript SPAs is that you don't need to keep to copies of your data transfer objects(DTOs) synchronized.</span></span> <span data-ttu-id="07fa6-363">Sus proyectos de Blazor WebAssembly y de API web pueden compartir el mismo objeto de transferencia de datos en un proyecto común compartido.</span><span class="sxs-lookup"><span data-stu-id="07fa6-363">Your Blazor WebAssembly project and your web API project can both share the same DTOs in a common shared project.</span></span> <span data-ttu-id="07fa6-364">Esto elimina parte de la fricción que conlleva el desarrollo de aplicaciones de página única.</span><span class="sxs-lookup"><span data-stu-id="07fa6-364">This eliminates some of the friction involved in developing SPAs.</span></span>

<span data-ttu-id="07fa6-365">Para obtener datos rápidamente de un punto de conexión de API, puede usar el método auxiliar integrado `GetFromJsonAsync`.</span><span class="sxs-lookup"><span data-stu-id="07fa6-365">To quickly get data from an API endpoint, you can use the built-in helper method, `GetFromJsonAsync`.</span></span> <span data-ttu-id="07fa6-366">Hay métodos similares para POST, PUT, etc. A continuación se muestra cómo obtener una clase CatalogItem desde un punto de conexión de API mediante un elemento `HttpClient` configurado en una aplicación de Blazor WebAssembly:</span><span class="sxs-lookup"><span data-stu-id="07fa6-366">There are similar methods for POST, PUT, etc. The following shows how to get a CatalogItem from an API endpoint using a configured `HttpClient` in a Blazor WebAssembly app:</span></span>

```csharp
var item = await _httpClient.GetFromJsonAsync<CatalogItem>($"catalog-items/{id}");
```

<span data-ttu-id="07fa6-367">Una vez que tenga los datos que necesita, normalmente hará un seguimiento de los cambios de forma local.</span><span class="sxs-lookup"><span data-stu-id="07fa6-367">Once you have the data you need, you'll typically track changes locally.</span></span> <span data-ttu-id="07fa6-368">Para realizar actualizaciones en el almacén de datos de back-end, llamará a API web adicionales.</span><span class="sxs-lookup"><span data-stu-id="07fa6-368">When you want to make updates to the backend data store, you'll call additional web APIs for this purpose.</span></span>

<span data-ttu-id="07fa6-369">**Referencias: datos de Blazor**</span><span class="sxs-lookup"><span data-stu-id="07fa6-369">**References – Blazor Data**</span></span>

- <span data-ttu-id="07fa6-370">Llamada a una API web desde Blazor de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07fa6-370">Call a web API from ASP.NET Core Blazor</span></span>
  <https://docs.microsoft.com/aspnet/core/blazor/call-web-api>

>[!div class="step-by-step"]
><span data-ttu-id="07fa6-371">[Anterior](develop-asp-net-core-mvc-apps.md)
>[Siguiente](test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="07fa6-371">[Previous](develop-asp-net-core-mvc-apps.md)
[Next](test-asp-net-core-mvc-apps.md)</span></span>
