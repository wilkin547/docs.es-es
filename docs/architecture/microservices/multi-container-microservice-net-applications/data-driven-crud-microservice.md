---
title: Creación de un microservicio CRUD sencillo controlado por datos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga más información sobre la creación de un microservicio CRUD sencillo (controlado por datos) en el contexto de una aplicación de microservicios.
ms.date: 01/07/2019
ms.openlocfilehash: 74d9022ffa70ade6ae6e7d405403524dfbc2145a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039914"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="43b7a-103">Creación de un microservicio CRUD sencillo controlado por datos</span><span class="sxs-lookup"><span data-stu-id="43b7a-103">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="43b7a-104">En esta sección se describe cómo crear un microservicio sencillo que lleve a cabo operaciones de creación, lectura, actualización y eliminación (CRUD) en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="43b7a-104">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="43b7a-105">Diseño de un microservicio CRUD sencillo</span><span class="sxs-lookup"><span data-stu-id="43b7a-105">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="43b7a-106">Desde un punto de vista de diseño, este tipo de microservicio en contenedor es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="43b7a-106">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="43b7a-107">Quizás el problema para resolver es sencillo o la implementación es solo una prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="43b7a-107">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![Un microservicio CRUD sencillo es un modelo de diseño interno.](./media/image4.png)

<span data-ttu-id="43b7a-109">**Figura 6-4**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-109">**Figure 6-4**.</span></span> <span data-ttu-id="43b7a-110">Diseño interno de microservicios CRUD sencillos</span><span class="sxs-lookup"><span data-stu-id="43b7a-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="43b7a-111">Un ejemplo de este tipo de servicio sencillo controlado por datos es el microservicio de catálogo de la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="43b7a-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="43b7a-112">Este tipo de servicio implementa toda su funcionalidad en un solo proyecto de API Web de ASP.NET Core que incluye las clases para su modelo de datos, su lógica de negocios y su código de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="43b7a-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="43b7a-113">También almacena los datos relacionados en una base de datos que ejecuta SQL Server (como otro contenedor para fines de desarrollo y pruebas), pero también podría ser cualquier host de SQL Server normal, como se muestra en la Figura 6-5.</span><span class="sxs-lookup"><span data-stu-id="43b7a-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 6-5.</span></span>

![El microservicio Catalog lógico incluye su base de datos Catalog, que puede estar o no en el mismo host de Docker.](./media/image5.png)

<span data-ttu-id="43b7a-116">**Figura 6-5**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-116">**Figure 6-5**.</span></span> <span data-ttu-id="43b7a-117">Diseño de un microservicio CRUD sencillo controlado por datos</span><span class="sxs-lookup"><span data-stu-id="43b7a-117">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="43b7a-118">Para desarrollar este tipo de servicio, solo necesita [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) y una ORP o API de acceso a datos, como [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="43b7a-118">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="43b7a-119">También puede generar automáticamente metadatos [Swagger](https://swagger.io/) a través de [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), para proporcionar una descripción de lo que ofrece el servicio, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="43b7a-119">You could also generate [Swagger](https://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="43b7a-120">Tenga en cuenta que ejecutar un servidor de base de datos como SQL Server en un contenedor de Docker es muy útil para entornos de desarrollo, porque puede poner en marcha todas sus dependencias sin tener que proporcionar una base de datos local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="43b7a-120">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="43b7a-121">Esto resulta muy útil para ejecutar pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="43b7a-121">This is very convenient when running integration tests.</span></span> <span data-ttu-id="43b7a-122">Pero no se recomienda ejecutar un servidor de base de datos en un contenedor para entornos de producción, ya que normalmente no se obtiene alta disponibilidad con ese método.</span><span class="sxs-lookup"><span data-stu-id="43b7a-122">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="43b7a-123">En un entorno de producción de Azure, le recomendamos que utilice la base de datos SQL de Azure o cualquier otra tecnología de base de datos que pueda proporcionar alta disponibilidad y alta escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="43b7a-123">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="43b7a-124">Por ejemplo, para un enfoque NoSQL, es posible que elija CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="43b7a-124">For example, for a NoSQL approach, you might choose CosmosDB.</span></span>

<span data-ttu-id="43b7a-125">Por último, al editar los archivos de metadatos de Dockerfile y docker-compose.yml, puede configurar cómo se creará la imagen de este contenedor, es decir, la imagen base que se usará y la configuración de diseño, como los nombres internos y externos y los puertos TCP.</span><span class="sxs-lookup"><span data-stu-id="43b7a-125">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span>

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="43b7a-126">Implementación de un microservicio CRUD sencillo con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="43b7a-126">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="43b7a-127">Para implementar un microservicio CRUD sencillo con .NET Core y Visual Studio, primero debe crear un proyecto de API web de ASP.NET Core sencillo (que se ejecute en .NET Core para que pueda ejecutarse en un host de Linux Docker), como se muestra en la Figura 6-6.</span><span class="sxs-lookup"><span data-stu-id="43b7a-127">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 6-6.</span></span>

![Para crear un proyecto de API web de ASP.NET Core, seleccione primero una aplicación web de ASP.NET Core y, después, seleccione el tipo de API.](./media/image6.png)

<span data-ttu-id="43b7a-129">**Figura 6-6**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-129">**Figure 6-6**.</span></span> <span data-ttu-id="43b7a-130">Creación de un proyecto de API Web de ASP.NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="43b7a-130">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="43b7a-131">Después de crear el proyecto, puede implementar los controladores MVC como lo haría en cualquier otro proyecto de API Web, mediante la API de Entity Framework u otra API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-131">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="43b7a-132">En un nuevo proyecto de API Web, puede ver que la única dependencia que tiene de ese microservicio es el mismo ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="43b7a-132">In a new Web API project, you can see that the only dependency you have in that microservice is on ASP.NET Core itself.</span></span> <span data-ttu-id="43b7a-133">Internamente, dentro de la dependencia *Microsoft.AspNetCore.All*, hace referencia a Entity Framework y a muchos otros paquetes NuGet de .NET Core, como se muestra en la Figura 6-7.</span><span class="sxs-lookup"><span data-stu-id="43b7a-133">Internally, within the *Microsoft.AspNetCore.All* dependency, it is referencing Entity Framework and many other .NET Core NuGet packages, as shown in Figure 6-7.</span></span>

![El proyecto de API incluye referencias al paquete NuGet Microsoft.AspNetCore.App, que incluye referencias a todos los paquetes esenciales.](./media/image8.png)

<span data-ttu-id="43b7a-136">**Figura 6-7**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-136">**Figure 6-7**.</span></span> <span data-ttu-id="43b7a-137">Dependencias en un microservicio API Web de CRUD sencillo</span><span class="sxs-lookup"><span data-stu-id="43b7a-137">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="43b7a-138">Implementación de servicios API Web de CRUD con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="43b7a-138">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="43b7a-139">Entity Framework (EF) Core es una versión ligera, extensible y multiplataforma de la popular tecnología de acceso a datos Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="43b7a-139">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="43b7a-140">EF Core es un asignador relacional de objetos (ORM) que permite a los desarrolladores de .NET trabajar con una base de datos mediante objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="43b7a-140">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="43b7a-141">El microservicio de catálogo usa EF y el proveedor de SQL Server porque su base de datos se está ejecutando en un contenedor con la imagen de SQL Server para Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="43b7a-141">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="43b7a-142">Pero la base de datos podría implementarse en cualquier SQL Server, como en una base de datos SQL de Azure o Windows local.</span><span class="sxs-lookup"><span data-stu-id="43b7a-142">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="43b7a-143">Lo único que debe cambiar es la cadena de conexión en el microservicio ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-143">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="the-data-model"></a><span data-ttu-id="43b7a-144">El modelo de datos</span><span class="sxs-lookup"><span data-stu-id="43b7a-144">The data model</span></span>

<span data-ttu-id="43b7a-145">Con EF Core, el acceso a datos se realiza utilizando un modelo.</span><span class="sxs-lookup"><span data-stu-id="43b7a-145">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="43b7a-146">Un modelo se compone de clases de entidad (modelo de dominio) y un contexto derivado (DbContext) que representa una sesión con la base de datos, lo que permite consultar y guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="43b7a-146">A model is made up of (domain model) entity classes and a derived context (DbContext) that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="43b7a-147">Puede generar un modelo a partir de una base de datos existente, codificar manualmente un modelo para que coincida con la base de datos, o bien usar migraciones de EF para crear una base de datos a partir del modelo, mediante el enfoque Code First (que facilita que la base de datos evolucione a medida que el modelo cambia en el tiempo).</span><span class="sxs-lookup"><span data-stu-id="43b7a-147">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model, using the code-first approach (that makes it easy to evolve the database as your model changes over time).</span></span> <span data-ttu-id="43b7a-148">Para el microservicio de catálogo, usamos el último enfoque.</span><span class="sxs-lookup"><span data-stu-id="43b7a-148">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="43b7a-149">Puede ver un ejemplo de la clase de entidad CatalogItem en el ejemplo de código siguiente, que es una clase de entidad de objeto CLR estándar ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).</span><span class="sxs-lookup"><span data-stu-id="43b7a-149">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

<span data-ttu-id="43b7a-150">También necesita un DbContext que represente una sesión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43b7a-150">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="43b7a-151">Para el microservicio de catálogo, la clase CatalogContext se deriva de la clase base DbContext, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43b7a-151">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    { }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...
}
```

<span data-ttu-id="43b7a-152">Puede tener implementaciones `DbContext` adicionales.</span><span class="sxs-lookup"><span data-stu-id="43b7a-152">You can have additional `DbContext` implementations.</span></span> <span data-ttu-id="43b7a-153">Por ejemplo, en el microservicio Catalog.API de ejemplo, hay un segundo `DbContext` denominado `CatalogContextSeed`, en que rellena automáticamente los datos de ejemplo la primera vez que intenta acceder a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43b7a-153">For example, in the sample Catalog.API microservice, there's a second `DbContext` named `CatalogContextSeed` where it automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="43b7a-154">Este método es útil para los datos de demostración y también para escenarios de pruebas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="43b7a-154">This method is useful for demo data and for automated testing scenarios, as well.</span></span>

<span data-ttu-id="43b7a-155">En `DbContext`, se usa el método `OnModelCreating` para personalizar las asignaciones de entidades de objeto y base de datos, y otros [puntos de extensibilidad de EF](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-155">Within the `DbContext`, you use the `OnModelCreating` method to customize object/database entity mappings and other [EF extensibility points](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="43b7a-156">Consulta de los datos desde controladores de API web</span><span class="sxs-lookup"><span data-stu-id="43b7a-156">Querying data from Web API controllers</span></span>

<span data-ttu-id="43b7a-157">Normalmente las instancias de sus clases de entidad se recuperan de la base de datos mediante Language Integrated Query (LINQ), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43b7a-157">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(
        CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService 
            ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
                                           [FromQuery]int pageIndex = 0)

    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a><span data-ttu-id="43b7a-158">Guardado de datos</span><span class="sxs-lookup"><span data-stu-id="43b7a-158">Saving data</span></span>

<span data-ttu-id="43b7a-159">Los datos se crean, se eliminan y se modifican en la base de datos mediante instancias de las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="43b7a-159">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="43b7a-160">Puede agregar código similar al siguiente ejemplo codificado de forma rígida (datos simulados, en este caso) a sus controladores de la API web.</span><span class="sxs-lookup"><span data-stu-id="43b7a-160">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="43b7a-161">Inserción de dependencias en los controladores de ASP.NET Core y API web</span><span class="sxs-lookup"><span data-stu-id="43b7a-161">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="43b7a-162">En ASP.NET Core, puede usar la inserción de dependencias desde el principio.</span><span class="sxs-lookup"><span data-stu-id="43b7a-162">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="43b7a-163">No es necesario que configure un contenedor de inversión de control (IoC) de terceros, aunque, si lo desea, puede conectar su contenedor de IoC preferido a la infraestructura de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="43b7a-163">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="43b7a-164">En este caso, puede insertar directamente el DBContext de EF requerido o los repositorios adicionales a través del constructor del controlador.</span><span class="sxs-lookup"><span data-stu-id="43b7a-164">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span>

<span data-ttu-id="43b7a-165">En el ejemplo anterior de la clase `CatalogController`, vamos a insertar un objeto del tipo `CatalogContext` junto con otros objetos a través del constructor `CatalogController()`.</span><span class="sxs-lookup"><span data-stu-id="43b7a-165">In the example above of the `CatalogController` class, we are injecting an object of `CatalogContext` type plus other objects through the `CatalogController()` constructor.</span></span>

<span data-ttu-id="43b7a-166">Una opción importante que hay que configurar en el proyecto de Web API es el registro de la clase DbContext en el contenedor de IoC del servicio.</span><span class="sxs-lookup"><span data-stu-id="43b7a-166">An important configuration to set up in the Web API project is the DbContext class registration into the service's IoC container.</span></span> <span data-ttu-id="43b7a-167">Normalmente se hace en la clase `Startup`, mediante una llamada al método `services.AddDbContext<DbContext>()` dentro del método `ConfigureServices()`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43b7a-167">You typically do so in the `Startup` class by calling the `services.AddDbContext<DbContext>()` method inside the `ConfigureServices()` method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.MigrationsAssembly(
                typeof(Startup).GetTypeInfo().Assembly.GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...
}
```

### <a name="additional-resources"></a><span data-ttu-id="43b7a-168">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43b7a-168">Additional resources</span></span>

- <span data-ttu-id="43b7a-169">**Consulta de datos** </span><span class="sxs-lookup"><span data-stu-id="43b7a-169">**Querying Data** </span></span>\
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- <span data-ttu-id="43b7a-170">**Guardado de datos** </span><span class="sxs-lookup"><span data-stu-id="43b7a-170">**Saving Data** </span></span>\
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="43b7a-171">Variables de entorno y cadena de conexión de la base de datos utilizadas por contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="43b7a-171">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="43b7a-172">Puede usar la configuración de ASP.NET Core y agregar una propiedad ConnectionString al archivo settings.json, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43b7a-172">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

<span data-ttu-id="43b7a-173">El archivo settings.json puede tener valores predeterminados para la propiedad ConnectionString o para cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="43b7a-173">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="43b7a-174">Pero estas propiedades se reemplazarán por los valores de las variables de entorno que se especifican en el archivo docker-compose.override.yml, al usar Docker.</span><span class="sxs-lookup"><span data-stu-id="43b7a-174">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file, when using Docker.</span></span>

<span data-ttu-id="43b7a-175">Desde los archivos docker-compose.yml o docker-compose.override.yml, puede inicializar estas variables de entorno para que Docker las configure como variables de entorno del sistema operativo, como se muestra en el siguiente archivo docker-compose.override.yml (la cadena de conexión y otras líneas se encapsulan en este ejemplo, pero no lo harán en su propio archivo).</span><span class="sxs-lookup"><span data-stu-id="43b7a-175">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

<span data-ttu-id="43b7a-176">Los archivos docker-compose.yml en el nivel de solución no solo son más flexibles que los archivos de configuración en el nivel de proyecto o de microservicio, sino que también son más seguros si reemplaza las variables de entorno declaradas en los archivos docker-compose con valores establecidos en las herramientas de implementación, como las tareas de implementación del Docker de Azure DevOps Services.</span><span class="sxs-lookup"><span data-stu-id="43b7a-176">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure if you override the environment variables declared at the docker-compose files with values set from your deployment tools, like from Azure DevOps Services Docker deployment tasks.</span></span>

<span data-ttu-id="43b7a-177">Por último, puede obtener ese valor desde el código mediante la configuración \["ConnectionString"\], tal y como se muestra en el método ConfigureServices de un ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="43b7a-177">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="43b7a-178">Pero, en entornos de producción, puede ser que le interese analizar otras formas de almacenar secretos, como las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="43b7a-178">However, for production environments, you might want to explore additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="43b7a-179">Una manera excelente de administrar los secretos de aplicación consiste en usar [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-179">An excellent way to manage application secrets is using [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="43b7a-180">Azure Key Vault ayuda a almacenar y proteger las claves criptográficas y los secretos que usan la aplicaciones y los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="43b7a-180">Azure Key Vault helps to store and safeguard cryptographic keys and secrets used by your cloud applications and services.</span></span> <span data-ttu-id="43b7a-181">Un secreto es todo aquello sobre lo que quiera mantener un control estricto, como las claves de API, las cadenas de conexión, las contraseñas, etc. Asimismo, un control estricto incluye el registro del uso, el establecimiento de la caducidad y la administración del acceso, *entre otros aspectos*.</span><span class="sxs-lookup"><span data-stu-id="43b7a-181">A secret is anything you want to keep strict control of, like API keys, connection strings, passwords, etc. and strict control includes usage logging, setting expiration, managing access, *among others*.</span></span>

<span data-ttu-id="43b7a-182">Azure Key Vault permite un nivel de control muy detallado del uso de secretos de la aplicación sin necesidad de dejar que nadie los conozca.</span><span class="sxs-lookup"><span data-stu-id="43b7a-182">Azure Key Vault allows a very detailed control level of the application secrets usage without the need to let anyone know them.</span></span> <span data-ttu-id="43b7a-183">Incluso se puede definir que los secretos vayan rotando para mejorar la seguridad sin interrumpir las operaciones ni el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="43b7a-183">The secrets can even be rotated for enhanced security without disrupting development or operations.</span></span>

<span data-ttu-id="43b7a-184">Es necesario registrar las aplicaciones en la instancia de Active Directory de la organización, de modo que puedan usar el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="43b7a-184">Applications have to be registered in the organization's Active Directory, so they can use the Key Vault.</span></span>

<span data-ttu-id="43b7a-185">Puede consultar la *documentación de conceptos de Key Vault* para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="43b7a-185">You can check the *Key Vault Concepts documentation* for more details.</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="43b7a-186">Implementación del control de versiones en las API web de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43b7a-186">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="43b7a-187">A medida que cambian los requisitos empresariales, pueden agregarse nuevas colecciones de recursos, las relaciones entre recursos pueden cambiar y la estructura de los datos en los recursos se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="43b7a-187">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="43b7a-188">Actualizar una API web para controlar requisitos nuevos es un proceso relativamente sencillo, pero debe tener en cuenta los efectos que estos cambios tendrán en las aplicaciones cliente que consumen la API web.</span><span class="sxs-lookup"><span data-stu-id="43b7a-188">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="43b7a-189">Aunque el desarrollador que diseña e implementa una API web tiene control total sobre dicha API, no tiene el mismo grado de control sobre las aplicaciones cliente creadas por organizaciones de terceros que funcionan de forma remota.</span><span class="sxs-lookup"><span data-stu-id="43b7a-189">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="43b7a-190">El control de versiones permite que una API web indique las características y los recursos que expone.</span><span class="sxs-lookup"><span data-stu-id="43b7a-190">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="43b7a-191">De este modo, una aplicación cliente puede enviar solicitudes a una versión específica de una característica o de un recurso.</span><span class="sxs-lookup"><span data-stu-id="43b7a-191">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="43b7a-192">Existen varios enfoques para implementar el control de versiones:</span><span class="sxs-lookup"><span data-stu-id="43b7a-192">There are several approaches to implement versioning:</span></span>

- <span data-ttu-id="43b7a-193">Control de versiones de URI</span><span class="sxs-lookup"><span data-stu-id="43b7a-193">URI versioning</span></span>

- <span data-ttu-id="43b7a-194">Control de versiones de cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="43b7a-194">Query string versioning</span></span>

- <span data-ttu-id="43b7a-195">Control de versiones de encabezado</span><span class="sxs-lookup"><span data-stu-id="43b7a-195">Header versioning</span></span>

<span data-ttu-id="43b7a-196">El control de versiones de URI y de cadena de consulta son los más fáciles de implementar.</span><span class="sxs-lookup"><span data-stu-id="43b7a-196">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="43b7a-197">El control de versiones de encabezado es una buena opción.</span><span class="sxs-lookup"><span data-stu-id="43b7a-197">Header versioning is a good approach.</span></span> <span data-ttu-id="43b7a-198">Pero el control de versiones de encabezado no es tan explícito y sencillo como el control de versiones de URI.</span><span class="sxs-lookup"><span data-stu-id="43b7a-198">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="43b7a-199">Como el control de versiones de URI es el más sencillo y explícito, es el que utiliza la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="43b7a-199">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="43b7a-200">Con el control de versiones de URI, como se muestra en la aplicación de ejemplo eShopOnContainers, cada vez que modifique la API web o cambie el esquema de recursos, agregará un número de versión al URI de cada recurso.</span><span class="sxs-lookup"><span data-stu-id="43b7a-200">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="43b7a-201">Los URI existentes deben continuar funcionando como antes, devolviendo los recursos que conforman el esquema que coincide con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="43b7a-201">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="43b7a-202">Como se muestra en el ejemplo de código siguiente, la versión se puede establecer mediante el atributo Route del controlador de la API web, lo que hace que la versión se explicite en el URI (v1 en este caso).</span><span class="sxs-lookup"><span data-stu-id="43b7a-202">As shown in the following code example, the version can be set by using the Route attribute in the Web API controller, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="43b7a-203">Este mecanismo de control de versiones es sencillo y depende del servidor que enruta la solicitud al punto de conexión adecuado.</span><span class="sxs-lookup"><span data-stu-id="43b7a-203">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="43b7a-204">Pero para utilizar un control de versiones más sofisticado y adoptar el mejor método al utilizar REST, debe usar hipermedia e implementar [HATEOAS (hipertexto como motor del estado de la aplicación)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="43b7a-204">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="43b7a-205">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43b7a-205">Additional resources</span></span>

- <span data-ttu-id="43b7a-206">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy** \ (Control de versiones simplificado de API web RESTful de ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="43b7a-206">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy** \</span></span>
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- <span data-ttu-id="43b7a-207">**Control de versiones de una API web RESTful** </span><span class="sxs-lookup"><span data-stu-id="43b7a-207">**Versioning a RESTful web API** </span></span>\
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- <span data-ttu-id="43b7a-208">**Roy Fielding. Versioning, Hypermedia, and REST** \ (Control de versiones, hipermedios y REST)</span><span class="sxs-lookup"><span data-stu-id="43b7a-208">**Roy Fielding. Versioning, Hypermedia, and REST** \</span></span>
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="43b7a-209">Generación de metadatos de descripción de Swagger desde la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="43b7a-209">Generating Swagger description metadata from your ASP.NET Core Web API</span></span>

<span data-ttu-id="43b7a-210">[Swagger](https://swagger.io/) es un marco de código abierto de uso común, respaldado por una gran variedad de herramientas que le permite diseñar, compilar, documentar y utilizar las API RESTful.</span><span class="sxs-lookup"><span data-stu-id="43b7a-210">[Swagger](https://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="43b7a-211">Se está convirtiendo en el estándar para el dominio de metadatos de la descripción de API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-211">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="43b7a-212">Debe incluir los metadatos de descripción de Swagger con cualquier tipo de microservicio, tanto si está controlado por datos como si está controlado por dominios de forma más avanzada (como se explica en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="43b7a-212">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="43b7a-213">El núcleo de Swagger es su especificación, que son los metadatos de descripción de la API en un archivo JSON o YAML.</span><span class="sxs-lookup"><span data-stu-id="43b7a-213">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="43b7a-214">La especificación crea el contrato RESTful para la API, donde se detallan todos sus recursos y operaciones en formatos legibles por máquinas y por humanos, para que se puedan desarrollar, descubrir e integrar de forma sencilla.</span><span class="sxs-lookup"><span data-stu-id="43b7a-214">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="43b7a-215">La especificación es la base de la especificación OpenAPI (OAS) y se desarrolla en una comunidad abierta, transparente y colaborativa para estandarizar la forma en que se definen las interfaces RESTful.</span><span class="sxs-lookup"><span data-stu-id="43b7a-215">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="43b7a-216">La especificación define la estructura de descubrimiento de un servicio y la forma de entender sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="43b7a-216">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="43b7a-217">Para obtener más información, incluido un editor web y ejemplos de especificaciones de Swagger de empresas como Spotify, Uber, Slack y Microsoft, consulte el sitio web de Swagger (<https://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="43b7a-217">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<https://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="43b7a-218">¿Por qué usar Swagger?</span><span class="sxs-lookup"><span data-stu-id="43b7a-218">Why use Swagger?</span></span>

<span data-ttu-id="43b7a-219">Las razones principales para generar metadatos de Swagger para las API son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="43b7a-219">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="43b7a-220">**Capacidad de otros productos de utilizar e integrar las API automáticamente** .</span><span class="sxs-lookup"><span data-stu-id="43b7a-220">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="43b7a-221">Swagger es compatible con docenas de productos y [herramientas comerciales](https://swagger.io/commercial-tools/), así como con muchas [bibliotecas y marcos](https://swagger.io/open-source-integrations/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-221">Dozens of products and [commercial tools](https://swagger.io/commercial-tools/) and many [libraries and frameworks](https://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="43b7a-222">Microsoft tiene productos y herramientas de alto nivel que pueden utilizar automáticamente API basadas en Swagger, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="43b7a-222">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

- <span data-ttu-id="43b7a-223">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="43b7a-223">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="43b7a-224">Puede generar automáticamente clases de cliente de .NET para llamar a Swagger.</span><span class="sxs-lookup"><span data-stu-id="43b7a-224">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="43b7a-225">Esta herramienta se puede utilizar desde la interfaz de la línea de comandos y también se integra con Visual Studio para que pueda utilizarse fácilmente desde la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="43b7a-225">This tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

- <span data-ttu-id="43b7a-226">[Microsoft Flow](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-226">[Microsoft Flow](https://flow.microsoft.com/).</span></span> <span data-ttu-id="43b7a-227">También puede [utilizar e integrar la API](https://flow.microsoft.com/blog/integrating-custom-api/) automáticamente en un flujo de trabajo de Microsoft Flow de alto nivel, aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="43b7a-227">You can automatically [use and integrate your API](https://flow.microsoft.com/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

- <span data-ttu-id="43b7a-228">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-228">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span></span> <span data-ttu-id="43b7a-229">Puede utilizar la API automáticamente desde [aplicaciones móviles PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) creadas con [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="43b7a-229">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), with no programming skills required.</span></span>

- <span data-ttu-id="43b7a-230">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="43b7a-230">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="43b7a-231">También puede [utilizar e integrar automáticamente su API en una Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="43b7a-231">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="43b7a-232">**Capacidad de generar documentación de la API automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-232">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="43b7a-233">Al crear API RESTful a gran escala, como aplicaciones complejas basadas en microservicios, tiene que controlar muchos de los puntos de conexión con diferentes modelos de datos diferentes que se utilizan en las cargas de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="43b7a-233">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="43b7a-234">Tener una documentación adecuada y un explorador de API potente, como se consigue con Swagger, es fundamental para que su API tenga éxito y los desarrolladores la adopten.</span><span class="sxs-lookup"><span data-stu-id="43b7a-234">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="43b7a-235">Microsoft Flow, PowerApps y Azure Logic Apps usan los metadatos de Swagger para aprender a usar las API y conectarse a ellas.</span><span class="sxs-lookup"><span data-stu-id="43b7a-235">Swagger's metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

<span data-ttu-id="43b7a-236">Hay varias opciones para automatizar la generación de metadatos de Swagger para las aplicaciones de API REST de ASP.NET Core, en forma de páginas de ayuda de API funcionales, basadas en *swagger-ui*.</span><span class="sxs-lookup"><span data-stu-id="43b7a-236">There are several options to automate Swagger metadata generation for ASP.NET Core REST API applications, in the form of functional API help pages, based on *swagger-ui*.</span></span>

<span data-ttu-id="43b7a-237">Probablemente la más conocida sea [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), que actualmente se usa en [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) y que trataremos con más detalle en esta guía, pero también existe la opción de usar [NSwag](https://github.com/RSuter/NSwag), que puede generar clientes de API de Typescript y C\#, así como controladores de C\#, a partir de una especificación de OpenAPI o Swagger, e incluso mediante el análisis del archivo .dll que contiene los controladores, con [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).</span><span class="sxs-lookup"><span data-stu-id="43b7a-237">Probably the best know is [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) which is currently used in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) and we'll cover in some detail in this guide but there's also the option to use [NSwag](https://github.com/RSuter/NSwag), that can generate Typescript and C\# API clients, as well as C\# controllers, from a Swagger or OpenAPI specification and even by scanning the .dll that contains the controllers, using [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="43b7a-238">Cómo se automatiza la generación de metadatos de la API de Swagger con el paquete NuGet de Swashbuckle</span><span class="sxs-lookup"><span data-stu-id="43b7a-238">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="43b7a-239">Generar metadatos de Swagger manualmente (en un archivo JSON o YAML) puede resultar muy pesado.</span><span class="sxs-lookup"><span data-stu-id="43b7a-239">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="43b7a-240">Pero puede automatizar la detección de API de servicios ASP.NET Web API mediante el uso del [paquete NuGet de Swashbuckle](https://aka.ms/swashbuckledotnetcore) para generar dinámicamente metadatos de la API de Swagger.</span><span class="sxs-lookup"><span data-stu-id="43b7a-240">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](https://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="43b7a-241">Swashbuckle genera automáticamente metadatos de Swagger para sus proyectos de ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-241">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="43b7a-242">Admite proyectos de ASP.NET Core Web API, proyectos tradicionales de ASP.NET Web API y cualquier otro tipo, como la aplicación API de Azure, la aplicación móvil de Azure o los microservicios Azure Service Fabric basados en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43b7a-242">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="43b7a-243">También admite API web sencillas implementadas en contenedores, como es el caso de la aplicación de referencia.</span><span class="sxs-lookup"><span data-stu-id="43b7a-243">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="43b7a-244">Swashbuckle combina el explorador de API y Swagger o [swagger-ui](https://github.com/swagger-api/swagger-ui) para proporcionar una experiencia de detección y documentación increíble a los consumidores de la API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-244">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="43b7a-245">Además de su motor generador de metadatos de Swagger, Swashbuckle también contiene una versión insertada de swagger-ui, que se usará automáticamente cuando se haya instalado Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="43b7a-245">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="43b7a-246">Esto significa que puede complementar su API con una bonita interfaz de usuario de descubrimiento para ayudar a los desarrolladores a usar su API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-246">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="43b7a-247">Para ello se requiere una cantidad muy pequeña de código y mantenimiento, puesto que se genera automáticamente, lo que le permite centrarse en la creación de la API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-247">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="43b7a-248">El resultado para el explorador de API se parece a la Figura 6-8.</span><span class="sxs-lookup"><span data-stu-id="43b7a-248">The result for the API Explorer looks like Figure 6-8.</span></span>

![La documentación de API de la interfaz de usuario de Swagger generada por Swashbuckle incluye todas las acciones publicadas.](./media/image9.png)

<span data-ttu-id="43b7a-250">**Figura 6-8**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-250">**Figure 6-8**.</span></span> <span data-ttu-id="43b7a-251">Explorador de API de Swashbuckle basado en metadatos de Swagger: microservicio del catálogo eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="43b7a-251">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="43b7a-252">Pero aquí lo más importante no es el explorador de API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-252">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="43b7a-253">Cuando tenga una API web que se pueda describir en metadatos de Swagger, la API podrá usarse sin problemas desde herramientas basadas en Swagger, incluidos los generadores de código de clase proxy de cliente que pueden tener varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="43b7a-253">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="43b7a-254">Por ejemplo, tal y como se ha mencionado, [AutoRest](https://github.com/Azure/AutoRest) genera automáticamente clases de cliente .NET.</span><span class="sxs-lookup"><span data-stu-id="43b7a-254">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="43b7a-255">Pero también están disponibles herramientas como [swagger-codegen](https://github.com/swagger-api/swagger-codegen), que permiten que se genere automáticamente código de bibliotecas de cliente de API, códigos auxiliares de servidor y documentación.</span><span class="sxs-lookup"><span data-stu-id="43b7a-255">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="43b7a-256">En la actualidad, Swashbuckle consta de cinco paquetes NuGet internos que se engloban en el metapaquete general [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) para las aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="43b7a-256">Currently, Swashbuckle consists of five internal NuGet packages under the high-level meta- package [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) for ASP.NET Core applications.</span></span>

<span data-ttu-id="43b7a-257">Después de instalar estos paquetes NuGet en el proyecto de API web, debe configurar Swagger en la clase de inicio, como en el código siguiente (simplificado):</span><span class="sxs-lookup"><span data-stu-id="43b7a-257">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code (simplified):</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new Swashbuckle.AspNetCore.Swagger.Info
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample",
                TermsOfService = "Terms Of Service"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

<span data-ttu-id="43b7a-258">Una vez hecho esto, puede iniciar la aplicación y examinar los siguientes puntos de conexión JSON y de interfaz de usuario de Swagger utilizando direcciones URL como estas:</span><span class="sxs-lookup"><span data-stu-id="43b7a-258">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```url
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

<span data-ttu-id="43b7a-259">Anteriormente, vio la interfaz de usuario generada creada por Swashbuckle para una dirección URL como `http://<your-root-url>/swagger`.</span><span class="sxs-lookup"><span data-stu-id="43b7a-259">You previously saw the generated UI created by Swashbuckle for a URL like `http://<your-root-url>/swagger`.</span></span> <span data-ttu-id="43b7a-260">En la Figura 6-9 también puede ver cómo se puede probar cualquier método de API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-260">In Figure 6-9 you can also see how you can test any API method.</span></span>

![En los detalles de la API de interfaz de usuario de Swagger se muestra un ejemplo de la respuesta y se puede usar para ejecutar la API real, que es muy útil para la detección por parte de los desarrolladores.](./media/image10.png)

<span data-ttu-id="43b7a-262">**Figura 6-9**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-262">**Figure 6-9**.</span></span> <span data-ttu-id="43b7a-263">Interfaz de usuario de Swashbuckle poniendo a prueba el método de API de catálogo o elementos</span><span class="sxs-lookup"><span data-stu-id="43b7a-263">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="43b7a-264">En la Figura 6-10 se muestran los metadatos JSON de Swagger generados a partir del microservicio eShopOnContainers (que es lo que las herramientas usan en segundo plano) al solicitar `http://<your-root-url>/swagger/v1/swagger.json` mediante [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="43b7a-264">Figure 6-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request `http://<your-root-url>/swagger/v1/swagger.json` using [Postman](https://www.getpostman.com/).</span></span>

![Ejemplo de interfaz de usuario de Postman en la que se muestran metadatos JSON de Swagger](./media/image11.png)

<span data-ttu-id="43b7a-266">**Figura 6-10**.</span><span class="sxs-lookup"><span data-stu-id="43b7a-266">**Figure 6-10**.</span></span> <span data-ttu-id="43b7a-267">Metadatos JSON de Swagger</span><span class="sxs-lookup"><span data-stu-id="43b7a-267">Swagger JSON metadata</span></span>

<span data-ttu-id="43b7a-268">Es así de sencillo.</span><span class="sxs-lookup"><span data-stu-id="43b7a-268">It is that simple.</span></span> <span data-ttu-id="43b7a-269">Y, como se generan automáticamente, los metadatos de Swagger crecerán cuando agregue más funcionalidad a la API.</span><span class="sxs-lookup"><span data-stu-id="43b7a-269">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="43b7a-270">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43b7a-270">Additional resources</span></span>

- <span data-ttu-id="43b7a-271">**Páginas de ayuda de ASP.NET Core Web API con Swagger** </span><span class="sxs-lookup"><span data-stu-id="43b7a-271">**ASP.NET Web API Help Pages using Swagger** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- <span data-ttu-id="43b7a-272">**Introducción a Swashbuckle y ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="43b7a-272">**Get started with Swashbuckle and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- <span data-ttu-id="43b7a-273">**Introducción a NSwag y ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="43b7a-273">**Get started with NSwag and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> <span data-ttu-id="43b7a-274">[Anterior](microservice-application-design.md)
> [Siguiente](multi-container-applications-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="43b7a-274">[Previous](microservice-application-design.md)
[Next](multi-container-applications-docker-compose.md)</span></span>
