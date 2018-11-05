---
title: Creación de un microservicio CRUD sencillo controlado por datos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Creación de un microservicio CRUD sencillo controlado por datos
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: bba0b93ee7e68ae0320460c6a45ab252ac34c326
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873507"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="90ca0-103">Creación de un microservicio CRUD sencillo controlado por datos</span><span class="sxs-lookup"><span data-stu-id="90ca0-103">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="90ca0-104">En esta sección se describe cómo crear un microservicio sencillo que lleve a cabo operaciones de creación, lectura, actualización y eliminación (CRUD) en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="90ca0-104">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="90ca0-105">Diseño de un microservicio CRUD sencillo</span><span class="sxs-lookup"><span data-stu-id="90ca0-105">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="90ca0-106">Desde un punto de vista de diseño, este tipo de microservicio en contenedor es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="90ca0-106">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="90ca0-107">Quizás el problema para resolver es sencillo o la implementación es solo una prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="90ca0-107">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="90ca0-108">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-108">**Figure 8-4**.</span></span> <span data-ttu-id="90ca0-109">Diseño interno de microservicios CRUD sencillos</span><span class="sxs-lookup"><span data-stu-id="90ca0-109">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="90ca0-110">Un ejemplo de este tipo de servicio sencillo controlado por datos es el microservicio de catálogo de la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="90ca0-110">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="90ca0-111">Este tipo de servicio implementa toda su funcionalidad en un solo proyecto de API Web de ASP.NET Core que incluye las clases para su modelo de datos, su lógica de negocios y su código de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="90ca0-111">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="90ca0-112">También almacena los datos relacionados en una base de datos que ejecuta SQL Server (como otro contenedor para fines de desarrollo y pruebas), pero también podría ser cualquier host de SQL Server normal, como se muestra en la Figura 8-5.</span><span class="sxs-lookup"><span data-stu-id="90ca0-112">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="90ca0-113">**Figura 8-5**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-113">**Figure 8-5**.</span></span> <span data-ttu-id="90ca0-114">Diseño de un microservicio CRUD sencillo controlado por datos</span><span class="sxs-lookup"><span data-stu-id="90ca0-114">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="90ca0-115">Para desarrollar este tipo de servicio, solo necesita [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) y una ORP o API de acceso a datos, como [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="90ca0-115">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="90ca0-116">También puede generar automáticamente metadatos [Swagger](https://swagger.io/) a través de [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), para proporcionar una descripción de lo que ofrece el servicio, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="90ca0-116">You could also generate [Swagger](https://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="90ca0-117">Tenga en cuenta que ejecutar un servidor de base de datos como SQL Server en un contenedor de Docker es muy útil para entornos de desarrollo, porque puede poner en marcha todas sus dependencias sin tener que proporcionar una base de datos local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="90ca0-117">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="90ca0-118">Esto resulta muy útil para ejecutar pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="90ca0-118">This is very convenient when running integration tests.</span></span> <span data-ttu-id="90ca0-119">Pero no se recomienda ejecutar un servidor de base de datos en un contenedor para entornos de producción, ya que normalmente no se obtiene alta disponibilidad con ese método.</span><span class="sxs-lookup"><span data-stu-id="90ca0-119">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="90ca0-120">En un entorno de producción de Azure, le recomendamos que utilice la base de datos SQL de Azure o cualquier otra tecnología de base de datos que pueda proporcionar alta disponibilidad y alta escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="90ca0-120">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="90ca0-121">Por ejemplo, para un método NoSQL, puede elegir DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="90ca0-121">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="90ca0-122">Por último, al editar los archivos de metadatos de Dockerfile y docker-compose.yml, puede configurar cómo se creará la imagen de este contenedor, es decir, la imagen base que se usará y la configuración de diseño, como los nombres internos y externos y los puertos TCP.</span><span class="sxs-lookup"><span data-stu-id="90ca0-122">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="90ca0-123">Implementación de un microservicio CRUD sencillo con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="90ca0-123">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="90ca0-124">Para implementar un microservicio CRUD sencillo con .NET Core y Visual Studio, primero debe crear un proyecto de API Web de ASP.NET Core sencillo (que se ejecute en .NET Core para que pueda ejecutarse en un host de Linux Docker), como se muestra en la Figura 8-6.</span><span class="sxs-lookup"><span data-stu-id="90ca0-124">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="90ca0-125">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="90ca0-125">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="90ca0-126">**Figura 8-6**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-126">**Figure 8-6**.</span></span> <span data-ttu-id="90ca0-127">Creación de un proyecto de API Web de ASP.NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="90ca0-127">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="90ca0-128">Después de crear el proyecto, puede implementar los controladores MVC como lo haría en cualquier otro proyecto de API Web, mediante la API de Entity Framework u otra API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-128">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="90ca0-129">En un nuevo proyecto de API Web, puede ver que la única dependencia que tiene de ese microservicio es el mismo ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="90ca0-129">In a new Web API project, you can see that the only dependency you have in that microservice is on ASP.NET Core itself.</span></span> <span data-ttu-id="90ca0-130">Internamente, dentro de la dependencia `Microsoft.AspNetCore.All`, hace referencia a Entity Framework y a muchos otros paquetes de Nuget de .NET Core, tal como se muestra en la Figura 8-7.</span><span class="sxs-lookup"><span data-stu-id="90ca0-130">Internally, within the `Microsoft.AspNetCore.All` dependency, it is referencing Entity Framework and many other .NET Core Nuget packages, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="90ca0-131">**Figura 8-7**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-131">**Figure 8-7**.</span></span> <span data-ttu-id="90ca0-132">Dependencias en un microservicio API Web de CRUD sencillo</span><span class="sxs-lookup"><span data-stu-id="90ca0-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="90ca0-133">Implementación de servicios API Web de CRUD con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="90ca0-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="90ca0-134">Entity Framework (EF) Core es una versión ligera, extensible y multiplataforma de la popular tecnología de acceso a datos Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="90ca0-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="90ca0-135">EF Core es un asignador relacional de objetos (ORM) que permite a los desarrolladores de .NET trabajar con una base de datos mediante objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="90ca0-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="90ca0-136">El microservicio de catálogo usa EF y el proveedor de SQL Server porque su base de datos se está ejecutando en un contenedor con la imagen de SQL Server para Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="90ca0-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="90ca0-137">Pero la base de datos podría implementarse en cualquier SQL Server, como en una base de datos SQL de Azure o Windows local.</span><span class="sxs-lookup"><span data-stu-id="90ca0-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="90ca0-138">Lo único que debe cambiar es la cadena de conexión en el microservicio ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>


#### <a name="the-data-model"></a><span data-ttu-id="90ca0-139">El modelo de datos</span><span class="sxs-lookup"><span data-stu-id="90ca0-139">The data model</span></span>

<span data-ttu-id="90ca0-140">Con EF Core, el acceso a datos se realiza utilizando un modelo.</span><span class="sxs-lookup"><span data-stu-id="90ca0-140">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="90ca0-141">Un modelo se compone de clases de entidad y un contexto derivado que representa una sesión con la base de datos, lo que permite consultar y guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="90ca0-141">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="90ca0-142">Puede generar un modelo a partir de una base de datos existente, codificar manualmente un modelo para que coincida con la base de datos o usar migraciones de EF para crear una base de datos a partir de su modelo (y que evolucione a medida que el modelo cambia).</span><span class="sxs-lookup"><span data-stu-id="90ca0-142">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="90ca0-143">Para el microservicio de catálogo, usamos el último enfoque.</span><span class="sxs-lookup"><span data-stu-id="90ca0-143">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="90ca0-144">Puede ver un ejemplo de la clase de entidad CatalogItem en el ejemplo de código siguiente, que es una clase de entidad de objeto CLR estándar ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).</span><span class="sxs-lookup"><span data-stu-id="90ca0-144">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

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

<span data-ttu-id="90ca0-145">También necesita un DbContext que represente una sesión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90ca0-145">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="90ca0-146">Para el microservicio de catálogo, la clase CatalogContext se deriva de la clase base DbContext, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90ca0-146">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

<span data-ttu-id="90ca0-147">Puede tener implementaciones `DbContext` adicionales.</span><span class="sxs-lookup"><span data-stu-id="90ca0-147">You can have additional `DbContext` implementations.</span></span> <span data-ttu-id="90ca0-148">Por ejemplo, en el microservicio Catalog.API de ejemplo, hay un segundo `DbContext` denominado `CatalogContextSeed`, en que rellena automáticamente los datos de ejemplo la primera vez que intenta acceder a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90ca0-148">For example, in the sample Catalog.API microservice, there's a second `DbContext` named `CatalogContextSeed` where it automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="90ca0-149">Este método es útil para los datos de demostración y también para escenarios de pruebas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="90ca0-149">This method is useful for demo data and for automated testing scenarios, as well.</span></span> <span data-ttu-id="90ca0-150">En `DbContext`, usa el método `OnModelCreating` para personalizar las asignaciones de entidades de objeto/base de datos con otros [puntos de extensibilidad de EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-150">Within the `DbContext`, you use the `OnModelCreating` method to customize object/database entity mappings with and other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="90ca0-151">Consulta de los datos desde controladores de API web</span><span class="sxs-lookup"><span data-stu-id="90ca0-151">Querying data from Web API controllers</span></span>

<span data-ttu-id="90ca0-152">Normalmente las instancias de sus clases de entidad se recuperan de la base de datos mediante Language Integrated Query (LINQ), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90ca0-152">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context, 
                             IOptionsSnapshot<CatalogSettings> settings,
                             ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
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

##### <a name="saving-data"></a><span data-ttu-id="90ca0-153">Guardado de datos</span><span class="sxs-lookup"><span data-stu-id="90ca0-153">Saving data</span></span>

<span data-ttu-id="90ca0-154">Los datos se crean, se eliminan y se modifican en la base de datos mediante instancias de las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="90ca0-154">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="90ca0-155">Puede agregar código similar al siguiente ejemplo codificado de forma rígida (datos simulados, en este caso) a sus controladores de la API web.</span><span class="sxs-lookup"><span data-stu-id="90ca0-155">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="90ca0-156">Inserción de dependencias en los controladores de ASP.NET Core y API web</span><span class="sxs-lookup"><span data-stu-id="90ca0-156">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="90ca0-157">En ASP.NET Core, puede usar la inserción de dependencias desde el principio.</span><span class="sxs-lookup"><span data-stu-id="90ca0-157">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="90ca0-158">No es necesario que configure un contenedor de inversión de control (IoC) de terceros, aunque, si lo desea, puede conectar su contenedor de IoC preferido a la infraestructura de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="90ca0-158">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="90ca0-159">En este caso, puede insertar directamente el DBContext de EF requerido o los repositorios adicionales a través del constructor del controlador.</span><span class="sxs-lookup"><span data-stu-id="90ca0-159">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="90ca0-160">En el ejemplo anterior de la clase `CatalogController`, vamos a insertar un objeto del tipo `CatalogContext` junto con otros objetos a través del constructor `CatalogController()`.</span><span class="sxs-lookup"><span data-stu-id="90ca0-160">In the example above of the `CatalogController` class, we are injecting an object of `CatalogContext` type plus other objects through the `CatalogController()` constructor.</span></span>

<span data-ttu-id="90ca0-161">Una opción importante que hay que configurar en el proyecto de Web API es el registro de la clase DbContext en el contenedor de IoC del servicio.</span><span class="sxs-lookup"><span data-stu-id="90ca0-161">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="90ca0-162">Normalmente se hace en la clase `Startup`, mediante una llamada al método `services.AddDbContext<DbContext>()` dentro del método `ConfigureServices()`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90ca0-162">You typically do so in the `Startup` class by calling the `services.AddDbContext<DbContext>()` method inside the `ConfigureServices()` method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
                   typeof(Startup).
                    GetTypeInfo().
                     Assembly.
                      GetName().Name);

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

### <a name="additional-resources"></a><span data-ttu-id="90ca0-163">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="90ca0-163">Additional resources</span></span>

-   <span data-ttu-id="90ca0-164">**Consulta de datos**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="90ca0-164">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="90ca0-165">**Guardado de datos**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="90ca0-165">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="90ca0-166">Variables de entorno y cadena de conexión de la base de datos utilizadas por contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="90ca0-166">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="90ca0-167">Puede usar la configuración de ASP.NET Core y agregar una propiedad ConnectionString al archivo settings.json, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90ca0-167">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```csharp
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

<span data-ttu-id="90ca0-168">El archivo settings.json puede tener valores predeterminados para la propiedad ConnectionString o para cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="90ca0-168">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="90ca0-169">Pero estas propiedades se reemplazarán por los valores de las variables de entorno que se especifican en el archivo docker-compose.override.yml, al usar Docker.</span><span class="sxs-lookup"><span data-stu-id="90ca0-169">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file, when using Docker.</span></span>

<span data-ttu-id="90ca0-170">Desde los archivos docker-compose.yml o docker-compose.override.yml, puede inicializar estas variables de entorno para que Docker las configure como variables de entorno del sistema operativo, como se muestra en el siguiente archivo docker-compose.override.yml (la cadena de conexión y otras líneas se encapsulan en este ejemplo, pero no lo harán en su archivo de código).</span><span class="sxs-lookup"><span data-stu-id="90ca0-170">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own code file).</span></span>

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

<span data-ttu-id="90ca0-171">Los archivos docker-compose.yml en el nivel de solución no solo son más flexibles que los archivos de configuración en el nivel de proyecto o de microservicio, sino que también son más seguros si reemplaza las variables de entorno declaradas en los archivos docker-compose con valores establecidos en las herramientas de implementación, como las tareas de implementación del Docker de Azure DevOps Services.</span><span class="sxs-lookup"><span data-stu-id="90ca0-171">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure if you override the environment variables declared at the docker-compose files with values set from your deployment tools, like from Azure DevOps Services Docker deployment tasks.</span></span> 

<span data-ttu-id="90ca0-172">Por último, puede obtener ese valor desde el código mediante la configuración \["ConnectionString"\], tal y como se muestra en el método ConfigureServices de un ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="90ca0-172">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="90ca0-173">Pero, en entornos de producción, puede ser que le interese analizar otras formas de almacenar secretos, como las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="90ca0-173">However, for production environments, you might want to explore additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="90ca0-174">Por lo general, esto estará administrado por el orquestador que elija, como puede hacer con [la administración de secretos en Docker Swarm](https://docs.docker.com/engine/swarm/secrets/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-174">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="90ca0-175">Implementación del control de versiones en las API web de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="90ca0-175">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="90ca0-176">A medida que cambian los requisitos empresariales, pueden agregarse nuevas colecciones de recursos, las relaciones entre recursos pueden cambiar y la estructura de los datos en los recursos se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="90ca0-176">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="90ca0-177">Actualizar una API web para controlar requisitos nuevos es un proceso relativamente sencillo, pero debe tener en cuenta los efectos que estos cambios tendrán en las aplicaciones cliente que consumen la API web.</span><span class="sxs-lookup"><span data-stu-id="90ca0-177">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="90ca0-178">Aunque el desarrollador que diseña e implementa una API web tiene control total sobre dicha API, no tiene el mismo grado de control sobre las aplicaciones cliente creadas por organizaciones de terceros que funcionan de forma remota.</span><span class="sxs-lookup"><span data-stu-id="90ca0-178">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="90ca0-179">El control de versiones permite que una API web indique las características y los recursos que expone.</span><span class="sxs-lookup"><span data-stu-id="90ca0-179">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="90ca0-180">De este modo, una aplicación cliente puede enviar solicitudes a una versión específica de una característica o de un recurso.</span><span class="sxs-lookup"><span data-stu-id="90ca0-180">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="90ca0-181">Existen varios enfoques para implementar el control de versiones:</span><span class="sxs-lookup"><span data-stu-id="90ca0-181">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="90ca0-182">Control de versiones de URI</span><span class="sxs-lookup"><span data-stu-id="90ca0-182">URI versioning</span></span>

-   <span data-ttu-id="90ca0-183">Control de versiones de cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="90ca0-183">Query string versioning</span></span>

-   <span data-ttu-id="90ca0-184">Control de versiones de encabezado</span><span class="sxs-lookup"><span data-stu-id="90ca0-184">Header versioning</span></span>

<span data-ttu-id="90ca0-185">El control de versiones de URI y de cadena de consulta son los más fáciles de implementar.</span><span class="sxs-lookup"><span data-stu-id="90ca0-185">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="90ca0-186">El control de versiones de encabezado es una buena opción.</span><span class="sxs-lookup"><span data-stu-id="90ca0-186">Header versioning is a good approach.</span></span> <span data-ttu-id="90ca0-187">Pero el control de versiones de encabezado no es tan explícito y sencillo como el control de versiones de URI.</span><span class="sxs-lookup"><span data-stu-id="90ca0-187">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="90ca0-188">Como el control de versiones de URI es el más sencillo y explícito, es el que utiliza la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="90ca0-188">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="90ca0-189">Con el control de versiones de URI, como se muestra en la aplicación de ejemplo eShopOnContainers, cada vez que modifique la API web o cambie el esquema de recursos, agregará un número de versión al URI de cada recurso.</span><span class="sxs-lookup"><span data-stu-id="90ca0-189">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="90ca0-190">Los URI existentes deben continuar funcionando como antes, devolviendo los recursos que conforman el esquema que coincide con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="90ca0-190">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="90ca0-191">Como se muestra en el ejemplo de código siguiente, la versión puede establecerse mediante el atributo de ruta en la API web, lo que hace que la versión se explicite en el URI (versión 1 en este caso).</span><span class="sxs-lookup"><span data-stu-id="90ca0-191">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="90ca0-192">Este mecanismo de control de versiones es sencillo y depende del servidor que enruta la solicitud al punto de conexión adecuado.</span><span class="sxs-lookup"><span data-stu-id="90ca0-192">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="90ca0-193">Pero para utilizar un control de versiones más sofisticado y adoptar el mejor método al utilizar REST, debe usar hipermedia e implementar [HATEOAS (hipertexto como motor del estado de la aplicación)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="90ca0-193">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="90ca0-194">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="90ca0-194">Additional resources</span></span>

-   <span data-ttu-id="90ca0-195">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Control de versiones simplificado de ASP.NET Core RESTful Web API)**
    [*https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="90ca0-195">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="90ca0-196">**Control de versiones de una API web RESTful**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="90ca0-196">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="90ca0-197">**Roy Fielding. Versioning, Hypermedia, and REST (Control de versiones, hipermedia y REST)**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="90ca0-197">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="90ca0-198">Generación de metadatos de descripción de Swagger desde la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="90ca0-198">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="90ca0-199">[Swagger](https://swagger.io/) es un marco de código abierto de uso común, respaldado por una gran variedad de herramientas que le permite diseñar, compilar, documentar y utilizar las API RESTful.</span><span class="sxs-lookup"><span data-stu-id="90ca0-199">[Swagger](https://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="90ca0-200">Se está convirtiendo en el estándar para el dominio de metadatos de la descripción de API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-200">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="90ca0-201">Debe incluir los metadatos de descripción de Swagger con cualquier tipo de microservicio, tanto si está controlado por datos como si está controlado por dominios de forma más avanzada (como se explica en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="90ca0-201">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="90ca0-202">El núcleo de Swagger es su especificación, que son los metadatos de descripción de la API en un archivo JSON o YAML.</span><span class="sxs-lookup"><span data-stu-id="90ca0-202">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="90ca0-203">La especificación crea el contrato RESTful para la API, donde se detallan todos sus recursos y operaciones en formatos legibles por máquinas y por humanos, para que se puedan desarrollar, descubrir e integrar de forma sencilla.</span><span class="sxs-lookup"><span data-stu-id="90ca0-203">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="90ca0-204">La especificación es la base de la especificación OpenAPI (OAS) y se desarrolla en una comunidad abierta, transparente y colaborativa para estandarizar la forma en que se definen las interfaces RESTful.</span><span class="sxs-lookup"><span data-stu-id="90ca0-204">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="90ca0-205">La especificación define la estructura de descubrimiento de un servicio y la forma de entender sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="90ca0-205">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="90ca0-206">Para obtener más información, incluido un editor web y ejemplos de especificaciones de Swagger de empresas como Spotify, Uber, Slack y Microsoft, consulte el sitio web de Swagger (<https://swagger.io/>).</span><span class="sxs-lookup"><span data-stu-id="90ca0-206">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<https://swagger.io/>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="90ca0-207">¿Por qué usar Swagger?</span><span class="sxs-lookup"><span data-stu-id="90ca0-207">Why use Swagger?</span></span>

<span data-ttu-id="90ca0-208">Las razones principales para generar metadatos de Swagger para las API son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="90ca0-208">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="90ca0-209">**Capacidad de otros productos de utilizar e integrar las API automáticamente** .</span><span class="sxs-lookup"><span data-stu-id="90ca0-209">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="90ca0-210">Swagger es compatible con docenas de productos y [herramientas comerciales](https://swagger.io/commercial-tools/), así como con muchas [bibliotecas y marcos](https://swagger.io/open-source-integrations/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-210">Dozens of products and [commercial tools](https://swagger.io/commercial-tools/) and many [libraries and frameworks](https://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="90ca0-211">Microsoft tiene productos y herramientas de alto nivel que pueden utilizar automáticamente API basadas en Swagger, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="90ca0-211">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="90ca0-212">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="90ca0-212">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="90ca0-213">Puede generar automáticamente clases de cliente de .NET para llamar a Swagger.</span><span class="sxs-lookup"><span data-stu-id="90ca0-213">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="90ca0-214">Esta herramienta se puede utilizar desde la interfaz de la línea de comandos y también se integra con Visual Studio para que pueda utilizarse fácilmente desde la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="90ca0-214">This tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="90ca0-215">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-215">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="90ca0-216">También puede [utilizar e integrar la API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) automáticamente en un flujo de trabajo de Microsoft Flow de alto nivel, aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="90ca0-216">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="90ca0-217">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-217">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="90ca0-218">Puede utilizar la API automáticamente desde [aplicaciones móviles PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) creadas con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="90ca0-218">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="90ca0-219">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="90ca0-219">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="90ca0-220">También puede [utilizar e integrar automáticamente su API en una Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), aunque no tenga conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="90ca0-220">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="90ca0-221">**Capacidad de generar documentación de la API automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-221">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="90ca0-222">Al crear API RESTful a gran escala, como aplicaciones complejas basadas en microservicios, tiene que controlar muchos de los puntos de conexión con diferentes modelos de datos diferentes que se utilizan en las cargas de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="90ca0-222">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="90ca0-223">Tener una documentación adecuada y un explorador de API potente, como se consigue con Swagger, es fundamental para que su API tenga éxito y los desarrolladores la adopten.</span><span class="sxs-lookup"><span data-stu-id="90ca0-223">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="90ca0-224">Microsoft Flow, PowerApps y Azure Logic Apps utilizan los metadatos de Swagger para aprender a usar las API y conectar con ellas.</span><span class="sxs-lookup"><span data-stu-id="90ca0-224">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="90ca0-225">Cómo se automatiza la generación de metadatos de la API de Swagger con el paquete NuGet de Swashbuckle</span><span class="sxs-lookup"><span data-stu-id="90ca0-225">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="90ca0-226">Generar metadatos de Swagger manualmente (en un archivo JSON o YAML) puede resultar muy pesado.</span><span class="sxs-lookup"><span data-stu-id="90ca0-226">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="90ca0-227">Pero puede automatizar la detección de API de servicios ASP.NET Web API mediante el uso del [paquete NuGet de Swashbuckle](https://aka.ms/swashbuckledotnetcore) para generar dinámicamente metadatos de la API de Swagger.</span><span class="sxs-lookup"><span data-stu-id="90ca0-227">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](https://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="90ca0-228">Swashbuckle genera automáticamente metadatos de Swagger para sus proyectos de ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-228">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="90ca0-229">Admite proyectos de ASP.NET Core Web API, proyectos tradicionales de ASP.NET Web API y cualquier otro tipo, como la aplicación API de Azure, la aplicación móvil de Azure o los microservicios Azure Service Fabric basados en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="90ca0-229">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="90ca0-230">También admite API web sencillas implementadas en contenedores, como es el caso de la aplicación de referencia.</span><span class="sxs-lookup"><span data-stu-id="90ca0-230">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="90ca0-231">Swashbuckle combina el explorador de API y Swagger o [swagger-ui](https://github.com/swagger-api/swagger-ui) para proporcionar una experiencia de detección y documentación increíble a los consumidores de la API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-231">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="90ca0-232">Además de su motor generador de metadatos de Swagger, Swashbuckle también contiene una versión insertada de swagger-ui, que se usará automáticamente cuando se haya instalado Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="90ca0-232">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="90ca0-233">Esto significa que puede complementar su API con una bonita interfaz de usuario de descubrimiento para ayudar a los desarrolladores a usar su API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-233">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="90ca0-234">Para ello se requiere una cantidad muy pequeña de código y mantenimiento, puesto que se genera automáticamente, lo que le permite centrarse en la creación de la API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-234">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="90ca0-235">El resultado para el explorador de API se parece a la Figura 8-8.</span><span class="sxs-lookup"><span data-stu-id="90ca0-235">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="90ca0-236">**Figura 8-8**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-236">**Figure 8-8**.</span></span> <span data-ttu-id="90ca0-237">Explorador de API de Swashbuckle basado en metadatos de Swagger: microservicio del catálogo eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="90ca0-237">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="90ca0-238">Pero aquí lo más importante no es el explorador de API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-238">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="90ca0-239">Cuando tenga una API web que se pueda describir en metadatos de Swagger, la API podrá usarse sin problemas desde herramientas basadas en Swagger, incluidos los generadores de código de clase proxy de cliente que pueden tener varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="90ca0-239">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="90ca0-240">Por ejemplo, tal y como se ha mencionado, [AutoRest](https://github.com/Azure/AutoRest) genera automáticamente clases de cliente .NET.</span><span class="sxs-lookup"><span data-stu-id="90ca0-240">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="90ca0-241">Pero también están disponibles herramientas como [swagger-codegen](https://github.com/swagger-api/swagger-codegen), que permiten que se genere automáticamente código de bibliotecas de cliente de API, códigos auxiliares de servidor y documentación.</span><span class="sxs-lookup"><span data-stu-id="90ca0-241">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="90ca0-242">En la actualidad, Swashbuckle consta de varios paquetes NuGet internos que se engloban en el metapaquete general [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/) versión 1.0.0 o una versión posterior para las aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="90ca0-242">Currently, Swashbuckle consists of several internal NuGet packages under the high-level meta-package [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/) version 1.0.0 or later for ASP.NET Core applications.</span></span>

<span data-ttu-id="90ca0-243">Después de instalar estos paquetes de NuGet en su proyecto de API web, debe configurar Swagger en la clase de inicio, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="90ca0-243">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

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

<span data-ttu-id="90ca0-244">Una vez hecho esto, puede iniciar la aplicación y examinar los siguientes puntos de conexión JSON y de interfaz de usuario de Swagger utilizando direcciones URL como estas:</span><span class="sxs-lookup"><span data-stu-id="90ca0-244">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/
```

<span data-ttu-id="90ca0-245">Anteriormente, vio la interfaz de usuario generada creada por Swashbuckle para una dirección URL como `http://<your-root-url>/swagger/ui`.</span><span class="sxs-lookup"><span data-stu-id="90ca0-245">You previously saw the generated UI created by Swashbuckle for a URL like `http://<your-root-url>/swagger/ui`.</span></span> <span data-ttu-id="90ca0-246">En la Figura 8-9 también puede ver cómo puede probar cualquier método de API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-246">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="90ca0-247">**Figura 8-9**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-247">**Figure 8-9**.</span></span> <span data-ttu-id="90ca0-248">Interfaz de usuario de Swashbuckle poniendo a prueba el método de API de catálogo o elementos</span><span class="sxs-lookup"><span data-stu-id="90ca0-248">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="90ca0-249">En la Figura 8-10 se muestran los metadatos JSON de Swagger generados a partir del microservicio eShopOnContainers (que es lo que las herramientas usan en segundo plano) al solicitar &lt;su-url-raíz&gt;/swagger/v1/swagger.json utilizando [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="90ca0-249">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="90ca0-250">**Figura 8-10**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-250">**Figure 8-10**.</span></span> <span data-ttu-id="90ca0-251">Metadatos JSON de Swagger</span><span class="sxs-lookup"><span data-stu-id="90ca0-251">Swagger JSON metadata</span></span>

<span data-ttu-id="90ca0-252">Es así de sencillo.</span><span class="sxs-lookup"><span data-stu-id="90ca0-252">It is that simple.</span></span> <span data-ttu-id="90ca0-253">Y, como se generan automáticamente, los metadatos de Swagger crecerán cuando agregue más funcionalidad a la API.</span><span class="sxs-lookup"><span data-stu-id="90ca0-253">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="90ca0-254">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="90ca0-254">Additional resources</span></span>

-   <span data-ttu-id="90ca0-255">**ASP.NET Web API Help Pages using Swagger (Páginas de ayuda de ASP.NET Web API mediante Swagger)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="90ca0-255">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="90ca0-256">[Anterior](microservice-application-design.md)
[Siguiente](multi-container-applications-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="90ca0-256">[Previous](microservice-application-design.md)
[Next](multi-container-applications-docker-compose.md)</span></span>
