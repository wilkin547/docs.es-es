---
title: Crear un microservicio CRUD simple controladas por datos
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Crear un microservicio CRUD simple controladas por datos
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="16559-104">Crear un microservicio CRUD simple controladas por datos</span><span class="sxs-lookup"><span data-stu-id="16559-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="16559-105">Esta sección se describe cómo crear un sencillo que se crea microservicio que lleva a cabo, lectura, actualización y las operaciones de eliminación (CRUD) en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="16559-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="16559-106">Diseñar un microservicio CRUD simple</span><span class="sxs-lookup"><span data-stu-id="16559-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="16559-107">Desde un punto de vista de diseño, este tipo de microservicio en contenedores es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="16559-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="16559-108">Quizás el problema para resolver es simple, o quizás la implementación es sólo una prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="16559-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="16559-109">**Figura 8-4**.</span><span class="sxs-lookup"><span data-stu-id="16559-109">**Figure 8-4**.</span></span> <span data-ttu-id="16559-110">Diseño interno de microservicios CRUD simple</span><span class="sxs-lookup"><span data-stu-id="16559-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="16559-111">Un ejemplo de este tipo de servicio de la unidad de datos simple es el microservicio de catálogo de la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="16559-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="16559-112">Este tipo de servicio implementa toda su funcionalidad en un solo proyecto de API Web de ASP.NET Core que incluye las clases para su modelo de datos, su lógica de negocios y su código de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="16559-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="16559-113">También almacena los datos relacionados en una base de datos en SQL Server en ejecución (como otro contenedor para fines de desarrollo y pruebas), pero también podría ser cualquier host de SQL Server normal, como se muestra en la figura 8-5.</span><span class="sxs-lookup"><span data-stu-id="16559-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="16559-114">**Figura 8-5**.</span><span class="sxs-lookup"><span data-stu-id="16559-114">**Figure 8-5**.</span></span> <span data-ttu-id="16559-115">Diseño simple microservicio/CRUD controladas por datos</span><span class="sxs-lookup"><span data-stu-id="16559-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="16559-116">Cuando está desarrollando este tipo de servicio, solo necesita [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) y una API de acceso a datos o ORM como [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="16559-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="16559-117">También podría generar [Swagger](http://swagger.io/) automáticamente a través de metadatos [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) para proporcionar una descripción de lo que ofrece el servicio, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="16559-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="16559-118">Tenga en cuenta que ejecuta un servidor de base de datos como SQL Server dentro de un contenedor de Docker es muy útil para entornos de desarrollo, porque puede hacer que todas las dependencias de las seguridad y se ejecuta sin necesidad de proporcionar una base de datos en la nube o local.</span><span class="sxs-lookup"><span data-stu-id="16559-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="16559-119">Esto resulta muy útil al ejecutando la integración de pruebas.</span><span class="sxs-lookup"><span data-stu-id="16559-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="16559-120">Sin embargo, para entornos de producción, ejecutando un servidor de base de datos en un contenedor no se recomienda, ya que normalmente no se obtiene alta disponibilidad con ese método.</span><span class="sxs-lookup"><span data-stu-id="16559-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="16559-121">En un entorno de producción en Azure, se recomienda que utilice la base de datos de SQL Azure o cualquier otra tecnología de base de datos que puede proporcionar alta disponibilidad y escalabilidad alta.</span><span class="sxs-lookup"><span data-stu-id="16559-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="16559-122">Por ejemplo, para un método NoSQL, puede elegir documentos.</span><span class="sxs-lookup"><span data-stu-id="16559-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="16559-123">Por último, mediante la edición de los archivos de metadatos de Dockerfile y compose.yml de docker, puede configurar cómo se creará la imagen de este contenedor, la imagen base se utilice, además de diseñar la configuración, como los nombres internos y externos y los puertos TCP.</span><span class="sxs-lookup"><span data-stu-id="16559-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="16559-124">Implementar un microservicio CRUD simple con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="16559-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="16559-125">Para implementar un microservicio CRUD simple con .NET Core y Visual Studio, primero debe crear un proyecto de ASP.NET Core Web API simple (ejecutando .NET Core para que pueda ejecutarse en un host Linux Docker), como se muestra en la figura 8-6.</span><span class="sxs-lookup"><span data-stu-id="16559-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="16559-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="16559-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="16559-127">**Figura 8-6**.</span><span class="sxs-lookup"><span data-stu-id="16559-127">**Figure 8-6**.</span></span> <span data-ttu-id="16559-128">Crear un proyecto de ASP.NET Core Web API en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="16559-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="16559-129">Después de crear el proyecto, puede implementar los controladores MVC como lo haría en cualquier otro proyecto de API Web, mediante la API de Entity Framework o de otra API.</span><span class="sxs-lookup"><span data-stu-id="16559-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="16559-130">En el proyecto eShopOnContainers.Catalog.API, puede ver que las dependencias principales de ese microservicio son simplemente ASP.NET Core propio, Entity Framework y Swashbuckle, tal como se muestra en la figura 8-7.</span><span class="sxs-lookup"><span data-stu-id="16559-130">In the eShopOnContainers.Catalog.API project, you can see that the main dependencies for that microservice are just ASP.NET Core itself, Entity Framework, and Swashbuckle, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="16559-131">**Figura 8-7**.</span><span class="sxs-lookup"><span data-stu-id="16559-131">**Figure 8-7**.</span></span> <span data-ttu-id="16559-132">Dependencias en un microservicio CRUD Web API simple</span><span class="sxs-lookup"><span data-stu-id="16559-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="16559-133">Implementación de servicios de CRUD Web API con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="16559-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="16559-134">Núcleo de Entity Framework (EF) es una ligera, extensible, y tecnología de acceso de versión entre plataformas de los datos de Entity Framework populares.</span><span class="sxs-lookup"><span data-stu-id="16559-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="16559-135">Núcleo EF es un asignador relacional de objetos (ORM) que permite a los desarrolladores de .NET trabajar con una base de datos mediante objetos. NET.</span><span class="sxs-lookup"><span data-stu-id="16559-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="16559-136">El catálogo de microservicio usa EF y el proveedor de SQL Server porque su base de datos se está ejecutando en un contenedor con el servidor SQL Server para la imagen de Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="16559-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="16559-137">Sin embargo, la base de datos podría implementarse en cualquier servidor SQL, como Windows local o en la base de datos de SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="16559-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="16559-138">Lo único que debe cambiar es la cadena de conexión en el microservicio de ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="16559-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="add-entity-framework-core-to-your-dependencies"></a><span data-ttu-id="16559-139">Agregar Entity Framework Core a las dependencias</span><span class="sxs-lookup"><span data-stu-id="16559-139">Add Entity Framework Core to your dependencies</span></span>

<span data-ttu-id="16559-140">Puede instalar el paquete de NuGet para el proveedor de base de datos que desea usar, en este caso, SQL Server, desde dentro del IDE de Visual Studio o con la consola de NuGet.</span><span class="sxs-lookup"><span data-stu-id="16559-140">You can install the NuGet package for the database provider you want to use, in this case SQL Server, from within the Visual Studio IDE or with the NuGet console.</span></span> <span data-ttu-id="16559-141">Use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="16559-141">Use the following command:</span></span>

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a><span data-ttu-id="16559-142">El modelo de datos</span><span class="sxs-lookup"><span data-stu-id="16559-142">The data model</span></span>

<span data-ttu-id="16559-143">Con núcleo de EF, acceso a datos se realiza mediante el uso de un modelo.</span><span class="sxs-lookup"><span data-stu-id="16559-143">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="16559-144">Un modelo se compone de las clases de entidad y un contexto derivado que representa una sesión con la base de datos, lo que le permite consultar y guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="16559-144">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="16559-145">Puede generar un modelo de base de datos existente, manualmente un modelo para que coincida con la base de datos de código o usar migraciones de EF para crear una base de datos del modelo (y evolucionan a medida que cambia el modelo con el tiempo).</span><span class="sxs-lookup"><span data-stu-id="16559-145">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="16559-146">Para el catálogo microservicio, usamos el último enfoque.</span><span class="sxs-lookup"><span data-stu-id="16559-146">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="16559-147">Puede ver un ejemplo de la clase de entidad CatalogItem en el ejemplo de código siguiente, que es un objeto de CLR Plain Old simple ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) clase de entidad.</span><span class="sxs-lookup"><span data-stu-id="16559-147">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

<span data-ttu-id="16559-148">También necesita un DbContext que representa una sesión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16559-148">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="16559-149">Para el microservicio de catálogo, la clase de CatalogContext se deriva de la clase base de DbContext, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16559-149">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

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

<span data-ttu-id="16559-150">Puede tener código adicional en la implementación de DbContext.</span><span class="sxs-lookup"><span data-stu-id="16559-150">You can have additional code in the DbContext implementation.</span></span> <span data-ttu-id="16559-151">Por ejemplo, en la aplicación de ejemplo, tenemos un método OnModelCreating en la clase CatalogContext que rellena automáticamente los datos de ejemplo en la primera vez que intenta obtener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16559-151">For example, in the sample application, we have an OnModelCreating method in the CatalogContext class that automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="16559-152">Este método es útil para los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="16559-152">This method is useful for demo data.</span></span> <span data-ttu-id="16559-153">También puede usar el método OnModelCreating para personalizar las asignaciones de entidad del objeto y base de datos con muchos otros [puntos de extensibilidad EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="16559-153">You can also use the OnModelCreating method to customize object/database entity mappings with many other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

<span data-ttu-id="16559-154">Puede ver más detalles acerca de OnModelCreating en el [implementar la capa de persistencia de infraestructura con Entity Framework Core](#implementing_infrastructure_persistence) sección más adelante en este libro.</span><span class="sxs-lookup"><span data-stu-id="16559-154">You can see further details about OnModelCreating in the [Implementing the infrastructure-persistence layer with Entity Framework Core](#implementing_infrastructure_persistence) section later in this book.</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="16559-155">Consultar datos de controladores de API Web</span><span class="sxs-lookup"><span data-stu-id="16559-155">Querying data from Web API controllers</span></span>

<span data-ttu-id="16559-156">Instancias de las clases de entidad se recuperan normalmente de la base de datos utilizando Language Integrated Query (LINQ), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16559-156">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

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
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
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

##### <a name="saving-data"></a><span data-ttu-id="16559-157">Guardar datos</span><span class="sxs-lookup"><span data-stu-id="16559-157">Saving data</span></span>

<span data-ttu-id="16559-158">Datos es crear, eliminar y modificar en la base de datos con instancias de las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="16559-158">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="16559-159">Puede agregar código similar al siguiente codificado de forma rígida ejemplo (datos simulados, en este caso) para los controladores de API Web.</span><span class="sxs-lookup"><span data-stu-id="16559-159">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="16559-160">Inserción de dependencias en los controladores de ASP.NET Core y API Web</span><span class="sxs-lookup"><span data-stu-id="16559-160">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="16559-161">En ASP.NET Core puede usar inyección de dependencia (DI) desde el principio.</span><span class="sxs-lookup"><span data-stu-id="16559-161">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="16559-162">No es necesario configurar un contenedor de inversión de Control (IoC) de terceros, aunque se puede conectar el contenedor de IoC preferido en la infraestructura básica de ASP.NET si desea.</span><span class="sxs-lookup"><span data-stu-id="16559-162">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="16559-163">En este caso, significa que puede insertar directamente el necesario DBContext EF o repositorios adicionales a través del constructor de controlador.</span><span class="sxs-lookup"><span data-stu-id="16559-163">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="16559-164">En el ejemplo anterior de la clase CatalogController, nos estamos está insertando un objeto de tipo CatalogContext además de otros objetos mediante el constructor CatalogController.</span><span class="sxs-lookup"><span data-stu-id="16559-164">In the example above of the CatalogController class, we are injecting an object of CatalogContext type plus other objects through the CatalogController constructor.</span></span>

<span data-ttu-id="16559-165">Una configuración importante para configurar en el proyecto de Web API es el registro de la clase DbContext en contenedor de IoC del servicio.</span><span class="sxs-lookup"><span data-stu-id="16559-165">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="16559-166">Normalmente lo hace en la clase de inicio mediante una llamada a los servicios. Método AddDbContext dentro del método ConfigureServices, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16559-166">You typically do so in the Startup class by calling the services.AddDbContext method inside the ConfigureServices method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
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

### <a name="additional-resources"></a><span data-ttu-id="16559-167">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="16559-167">Additional resources</span></span>

-   <span data-ttu-id="16559-168">**Consultar datos**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="16559-168">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="16559-169">**Guardar datos**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="16559-169">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="16559-170">Las variables entorno y la cadena de conexión base de datos utilizadas por contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="16559-170">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="16559-171">Puede usar la configuración básica de ASP.NET y agregar una propiedad ConnectionString al archivo settings.json tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16559-171">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

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

<span data-ttu-id="16559-172">El archivo settings.json puede tener valores predeterminados para la propiedad ConnectionString o para cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="16559-172">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="16559-173">Sin embargo, estas propiedades serán reemplazadas por los valores de variables de entorno que especifican en el archivo compose.override.yml docker.</span><span class="sxs-lookup"><span data-stu-id="16559-173">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file.</span></span>

<span data-ttu-id="16559-174">De los archivos compose.yml de docker o compose.override.yml de docker, puede inicializar estas variables de entorno por lo que Docker configurará ellos como variables de entorno de sistema operativo para usted, como se muestra en el siguiente archivo de docker compose.override.yml (la conexión cadena y otras líneas de ajustan en este ejemplo, pero no se ajusta en su propio archivo).</span><span class="sxs-lookup"><span data-stu-id="16559-174">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

<span data-ttu-id="16559-175">Los archivos de compose.yml de docker en el nivel de solución no sólo son más flexibles que los archivos de configuración en el nivel de proyecto o microservicio, pero también más segura.</span><span class="sxs-lookup"><span data-stu-id="16559-175">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure.</span></span> <span data-ttu-id="16559-176">Tenga en cuenta que las imágenes de Docker que se compilación por microservicio no contienen el compose.yml docker archivos, solo los archivos binarios y los archivos de configuración para cada microservicio, incluido el archivo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="16559-176">Consider that the Docker images that you build per microservice do not contain the docker-compose.yml files, only binary files and configuration files for each microservice, including the Dockerfile.</span></span> <span data-ttu-id="16559-177">Pero no se implementa el archivo de docker compose.yml junto con la aplicación; se utiliza solo durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="16559-177">But the docker-compose.yml file is not deployed along with your application; it is used only at deployment time.</span></span> <span data-ttu-id="16559-178">Por lo tanto, la colocación de los valores de las variables de entorno en esos archivos docker compose.yml (incluso sin cifrar los valores) es más seguro que colocar esos valores en archivos de configuración de .NET normales que se implementan con el código.</span><span class="sxs-lookup"><span data-stu-id="16559-178">Therefore, placing environment variables values in those docker-compose.yml files (even without encrypting the values) is more secure than placing those values in regular .NET configuration files that are deployed with your code.</span></span>

<span data-ttu-id="16559-179">Por último, puede obtener ese valor desde el código mediante la configuración\["ConnectionString"\], tal y como se muestra en el método ConfigureServices de un ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="16559-179">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="16559-180">Sin embargo, para entornos de producción, puede a otras formas de explorador sobre cómo almacenar secretos, como las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="16559-180">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="16559-181">Por lo general que serán administradas por su orchestrator elegido, como se puede hacer con [Docker Swarm administración de secretos](https://docs.docker.com/engine/swarm/secrets/).</span><span class="sxs-lookup"><span data-stu-id="16559-181">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="16559-182">Implementar el control de versiones en las API Web de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="16559-182">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="16559-183">Medida que cambian los requisitos empresariales, se pueden agregar nuevas colecciones de recursos, pueden cambiar las relaciones entre los recursos y podría modificarse la estructura de los datos de recursos.</span><span class="sxs-lookup"><span data-stu-id="16559-183">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="16559-184">Una API Web para controlar los requisitos nuevo la actualización es un proceso relativamente sencillo, pero debe tener en cuenta los efectos que tengan dichos cambios en aplicaciones cliente que consumen la API Web.</span><span class="sxs-lookup"><span data-stu-id="16559-184">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="16559-185">Aunque el desarrollador diseñar e implementar una API Web no tiene control total sobre dicha API, el programador no tiene el mismo grado de control sobre las aplicaciones cliente que podría estar compilado por organizaciones de terceros funciona de forma remota.</span><span class="sxs-lookup"><span data-stu-id="16559-185">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="16559-186">Control de versiones permite a una API Web indicar las características y recursos que expone.</span><span class="sxs-lookup"><span data-stu-id="16559-186">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="16559-187">Una aplicación cliente, a continuación, puede enviar solicitudes a una versión específica de una característica o un recurso.</span><span class="sxs-lookup"><span data-stu-id="16559-187">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="16559-188">Existen varios enfoques para implementar las versiones:</span><span class="sxs-lookup"><span data-stu-id="16559-188">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="16559-189">Control de versiones URI</span><span class="sxs-lookup"><span data-stu-id="16559-189">URI versioning</span></span>

-   <span data-ttu-id="16559-190">Control de versiones de cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="16559-190">Query string versioning</span></span>

-   <span data-ttu-id="16559-191">Control de versiones de encabezado</span><span class="sxs-lookup"><span data-stu-id="16559-191">Header versioning</span></span>

<span data-ttu-id="16559-192">Cadena de consulta y la versión del URI son las más fáciles de implementar.</span><span class="sxs-lookup"><span data-stu-id="16559-192">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="16559-193">Control de versiones de encabezado es un enfoque adecuado.</span><span class="sxs-lookup"><span data-stu-id="16559-193">Header versioning is a good approach.</span></span> <span data-ttu-id="16559-194">Sin embargo, las versiones de encabezado no como explícita y sencilla como control de versiones URI.</span><span class="sxs-lookup"><span data-stu-id="16559-194">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="16559-195">Dado que las versiones de la dirección URL son la más sencilla y más explícito, la aplicación de ejemplo eShopOnContainers utiliza las versiones URI.</span><span class="sxs-lookup"><span data-stu-id="16559-195">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="16559-196">Con las versiones de URI, como se muestra en la aplicación de ejemplo eShopOnContainers, cada vez que modifique la API Web o cambia el esquema de recursos, agregará un número de versión para el URI para cada recurso.</span><span class="sxs-lookup"><span data-stu-id="16559-196">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="16559-197">URI existentes deben continuar funcionando como antes, devuelven los recursos que se ajustan al esquema que coincide con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="16559-197">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="16559-198">Como se muestra en el ejemplo de código siguiente, la versión puede establecerse mediante el atributo de ruta en la API Web, lo que hace que la versión explícito en el URI (v1 en este caso).</span><span class="sxs-lookup"><span data-stu-id="16559-198">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="16559-199">Este mecanismo de control de versiones es sencillo y depende del servidor de enrutamiento de la solicitud al extremo adecuado.</span><span class="sxs-lookup"><span data-stu-id="16559-199">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="16559-200">Sin embargo, para un control de versiones más sofisticada y el mejor método si utiliza REST, debe usar hipermedia e implementar [HATEOAS (hipertexto como el estado del motor de aplicación)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="16559-200">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="16559-201">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="16559-201">Additional resources</span></span>

-   <span data-ttu-id="16559-202">**Scott Hanselman. Control de versiones ASP.NET Core RESTful Web API facilitan**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="16559-202">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="16559-203">**Control de versiones de una API web de REST**</span><span class="sxs-lookup"><span data-stu-id="16559-203">**Versioning a RESTful web API**</span></span>

    [<span data-ttu-id="16559-204">*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*</span><span class="sxs-lookup"><span data-stu-id="16559-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   <span data-ttu-id="16559-205">**Roy Fielding. Control de versiones, hipermedia y REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="16559-205">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="16559-206">Generar metadatos de Swagger descripción de la API de Web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="16559-206">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="16559-207">[Swagger](http://swagger.io/) es un marco de código abierto utilizadas respaldado por un gran ecosistema de herramientas que le ayuda a diseño, la compilación, documento y utilizar las API de REST.</span><span class="sxs-lookup"><span data-stu-id="16559-207">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="16559-208">Se está convirtiendo en el estándar para el dominio de metadatos de descripción de las API.</span><span class="sxs-lookup"><span data-stu-id="16559-208">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="16559-209">Deben incluir metadatos de descripción de Swagger con cualquier tipo de microservicio, controlada por datos microservicios o más avanzados microservicios controlada por el dominio (como se explica en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="16559-209">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="16559-210">El núcleo de Swagger es la especificación de Swagger, que es la API de metadatos de descripción en un archivo JSON o YAML.</span><span class="sxs-lookup"><span data-stu-id="16559-210">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="16559-211">La especificación crea el contrato RESTful de la API, que detalla todas sus recursos y operaciones en ambos humanos y machine readable formato para desarrollar fácilmente, detección e integración.</span><span class="sxs-lookup"><span data-stu-id="16559-211">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="16559-212">La especificación es la base de la OpenAPI especificación (analizador en tiempo real) y se desarrolla en una comunidad abierta, transparente y colaboración para estandarizar la forma en que se definen las interfaces RESTful.</span><span class="sxs-lookup"><span data-stu-id="16559-212">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="16559-213">La especificación define la estructura de cómo se puede detectar un servicio y cómo entienden sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="16559-213">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="16559-214">Para obtener más información, incluido un editor de web y ejemplos de especificaciones de Swagger de empresas como Spotify, la misma, la demora y Microsoft, vea el sitio de Swagger (<http://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="16559-214">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="16559-215">¿Por qué usar Swagger?</span><span class="sxs-lookup"><span data-stu-id="16559-215">Why use Swagger?</span></span>

<span data-ttu-id="16559-216">Las razones principales para generar metadatos de Swagger de las API son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="16559-216">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="16559-217">**Capacidad de otros productos automáticamente consumir e integrar las API**.</span><span class="sxs-lookup"><span data-stu-id="16559-217">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="16559-218">Docenas de productos y [herramientas comercial](http://swagger.io/commercial-tools/) y muchos [bibliotecas y marcos](http://swagger.io/open-source-integrations/) admite Swagger.</span><span class="sxs-lookup"><span data-stu-id="16559-218">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="16559-219">Microsoft tiene productos de alto nivel y herramientas que automáticamente se pueden utilizar la API basadas en Swagger, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="16559-219">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="16559-220">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="16559-220">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="16559-221">Puede generar automáticamente las clases de cliente de .NET para llamar a Swagger.</span><span class="sxs-lookup"><span data-stu-id="16559-221">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="16559-222">Esto</span><span class="sxs-lookup"><span data-stu-id="16559-222">This</span></span>

-   <span data-ttu-id="16559-223">herramienta que puede usarse desde la CLI y también se integra con Visual Studio para facilitar su uso a través de la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="16559-223">tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="16559-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="16559-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="16559-225">También puede automáticamente [utilizar e integrar su API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) en un flujo de trabajo de Microsoft Flow alto nivel, y no tienen ninguna programación destrezas necesarias.</span><span class="sxs-lookup"><span data-stu-id="16559-225">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="16559-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="16559-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="16559-227">Automáticamente se puede utilizar la API de [aplicaciones móviles PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) compiladas con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), sin conocimientos de programación necesarios.</span><span class="sxs-lookup"><span data-stu-id="16559-227">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="16559-228">[Aplicaciones de servicio de aplicaciones de Azure lógicas](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="16559-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="16559-229">También puede automáticamente [utilizar e integrar su API en una aplicación de lógica de servicio de aplicación de Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), sin conocimientos de programación necesarios.</span><span class="sxs-lookup"><span data-stu-id="16559-229">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="16559-230">**Capacidad de generar automáticamente la documentación de la API**.</span><span class="sxs-lookup"><span data-stu-id="16559-230">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="16559-231">Al crear las API RESTful a gran escala, como aplicaciones complejas de microservicio, necesario controlar muchos de los puntos de conexión con los modelos de datos diferentes utilizados en las cargas de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="16559-231">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="16559-232">Tener una documentación adecuada y con un explorador de API sólido, tal y como se obtienen con Swagger, son clave para el éxito de la API y la adopción por los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="16559-232">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="16559-233">Metadatos de swagger están la lógica de aplicaciones de Azure, PowerApps y Microsoft Flow usan para aprender a usar las API y conectarse a ellos.</span><span class="sxs-lookup"><span data-stu-id="16559-233">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="16559-234">Cómo automatizar la generación de metadatos de Swagger de API con el paquete de Swashbuckle NuGet</span><span class="sxs-lookup"><span data-stu-id="16559-234">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="16559-235">Generar metadatos de Swagger manualmente (en un archivo JSON o YAML) puede resultar una tarea tediosa.</span><span class="sxs-lookup"><span data-stu-id="16559-235">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="16559-236">Sin embargo, puede automatizar la detección de API de servicios de API Web de ASP.NET mediante el uso de la [paquete Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) generar dinámicamente los metadatos de Swagger API.</span><span class="sxs-lookup"><span data-stu-id="16559-236">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="16559-237">Swashbuckle genera automáticamente los metadatos de Swagger para los proyectos de ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="16559-237">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="16559-238">Admite proyectos API Web de ASP.NET Core y ASP.NET Web API tradicionales y cualquier otro tipo, como aplicación de API de Azure, aplicación móvil de Azure, microservicios Azure Service Fabric basado en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="16559-238">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="16559-239">También admite simple API Web implementados en los contenedores, como en para la aplicación de referencia.</span><span class="sxs-lookup"><span data-stu-id="16559-239">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="16559-240">Swashbuckle combina el Explorador de API y Swagger o [swagger la interfaz de usuario](https://github.com/swagger-api/swagger-ui) para proporcionar una detección completo y la documentación experimentan para los consumidores de API.</span><span class="sxs-lookup"><span data-stu-id="16559-240">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="16559-241">Además de su motor de generador de metadatos de Swagger, Swashbuckle también contiene una versión incrustada de swagger de interfaz de usuario, que se usará automáticamente una cuando se ha instalado Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="16559-241">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="16559-242">Esto significa que pueden complementar su API con una interfaz de usuario para ayudar a los desarrolladores usar la API de detección "nice".</span><span class="sxs-lookup"><span data-stu-id="16559-242">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="16559-243">Requiere una cantidad muy pequeña de código y mantenimiento dado que se genera automáticamente, lo que le permite centrarse en la creación de la API.</span><span class="sxs-lookup"><span data-stu-id="16559-243">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="16559-244">El resultado para el Explorador de API tiene un aspecto como la figura 8-8.</span><span class="sxs-lookup"><span data-stu-id="16559-244">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="16559-245">**Figura 8-8**.</span><span class="sxs-lookup"><span data-stu-id="16559-245">**Figure 8-8**.</span></span> <span data-ttu-id="16559-246">Explorador de la API de Swashbuckle basándose en los metadatos de Swagger: eShopOnContainers microservicio de catálogo</span><span class="sxs-lookup"><span data-stu-id="16559-246">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="16559-247">El Explorador de API no es lo más importante aquí.</span><span class="sxs-lookup"><span data-stu-id="16559-247">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="16559-248">Una vez que tenga una API Web que se pueden describir en metadatos de Swagger, la API puede usarse sin problemas de herramientas basadas en Swagger, incluidos los generadores de código de clase de proxy de cliente que pueden tener como destino varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="16559-248">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="16559-249">Por ejemplo, tal y como se ha mencionado, [AutoRest](https://github.com/Azure/AutoRest) genera automáticamente las clases de cliente. NET.</span><span class="sxs-lookup"><span data-stu-id="16559-249">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="16559-250">Pero, como herramientas adicionales [swagger codegen](https://github.com/swagger-api/swagger-codegen) también están disponibles, lo que permite la generación de código de cliente de API de bibliotecas, el código auxiliar de servidor y la documentación automáticamente.</span><span class="sxs-lookup"><span data-stu-id="16559-250">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="16559-251">Actualmente, Swashbuckle consta de dos paquetes de NuGet: Swashbuckle.SwaggerGen y Swashbuckle.SwaggerUi.</span><span class="sxs-lookup"><span data-stu-id="16559-251">Currently, Swashbuckle consists of two NuGet packages: Swashbuckle.SwaggerGen and Swashbuckle.SwaggerUi.</span></span> <span data-ttu-id="16559-252">El primero proporciona funcionalidad para generar uno o varios documentos de Swagger directamente desde su implementación de la API y expóngalos como extremos JSON.</span><span class="sxs-lookup"><span data-stu-id="16559-252">The former provides functionality to generate one or more Swagger documents directly from your API implementation and expose them as JSON endpoints.</span></span> <span data-ttu-id="16559-253">El segundo, proporciona una versión incrustada de la herramienta de swagger de interfaz de usuario que se pueden usar su aplicación y gracias a los documentos de Swagger generados para describir su API.</span><span class="sxs-lookup"><span data-stu-id="16559-253">The latter provides an embedded version of the swagger-ui tool that can be served by your application and powered by the generated Swagger documents to describe your API.</span></span> <span data-ttu-id="16559-254">Sin embargo, las versiones más recientes de Swashbuckle ajustan con el metapackage Swashbuckle.AspNetCore.</span><span class="sxs-lookup"><span data-stu-id="16559-254">However, the latest versions of Swashbuckle wrap these with the Swashbuckle.AspNetCore metapackage.</span></span>

<span data-ttu-id="16559-255">Tenga en cuenta que para los proyectos de .NET Core Web API, debe usar [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) versión 1.0.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="16559-255">Note that for .NET Core Web API projects, you need to use [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) version 1.0.0 or later.</span></span>

<span data-ttu-id="16559-256">Después de instalar estos paquetes de NuGet en el proyecto de API Web, debe configurar Swagger en la clase de inicio, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="16559-256">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
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
            .UseSwaggerUi();
    }
}
```

<span data-ttu-id="16559-257">Una vez hecho esto, se puede iniciar la aplicación y examinar los siguientes extremos de Swagger JSON y la interfaz de usuario con las direcciones URL como estas:</span><span class="sxs-lookup"><span data-stu-id="16559-257">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

<span data-ttu-id="16559-258">Anteriormente, vio la interfaz de usuario generado creado por Swashbuckle para una dirección URL como http://&lt;la dirección url raíz &gt; /swagger/interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="16559-258">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="16559-259">En la figura 8-9 también puede ver cómo puede probar cualquier método de API.</span><span class="sxs-lookup"><span data-stu-id="16559-259">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="16559-260">**Figura 8-9**.</span><span class="sxs-lookup"><span data-stu-id="16559-260">**Figure 8-9**.</span></span> <span data-ttu-id="16559-261">UI Swashbuckle probar el método de API de elementos del catálogo</span><span class="sxs-lookup"><span data-stu-id="16559-261">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="16559-262">Figura 8-10 se muestran los metadatos de Swagger JSON generado a partir de la microservicio eShopOnContainers (que es lo que las herramientas usan debajo) al solicitar &lt;la dirección url raíz&gt;/swagger/v1/swagger.json utilizando [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="16559-262">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="16559-263">**Figura 8-10**.</span><span class="sxs-lookup"><span data-stu-id="16559-263">**Figure 8-10**.</span></span> <span data-ttu-id="16559-264">Metadatos de swagger JSON</span><span class="sxs-lookup"><span data-stu-id="16559-264">Swagger JSON metadata</span></span>

<span data-ttu-id="16559-265">Es así de sencillo.</span><span class="sxs-lookup"><span data-stu-id="16559-265">It is that simple.</span></span> <span data-ttu-id="16559-266">Y dado que se genera automáticamente, los metadatos de Swagger crecerá al agregar más funcionalidad a su API.</span><span class="sxs-lookup"><span data-stu-id="16559-266">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="16559-267">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="16559-267">Additional resources</span></span>

-   <span data-ttu-id="16559-268">**ASP.NET Web API páginas de ayuda mediante Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="16559-268">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="16559-269">[Anterior] (microservicio-aplicaciones-design.md) [siguiente] (multi-container-aplicaciones-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="16559-269">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
