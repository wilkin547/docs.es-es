---
title: Uso de un servidor de bases de datos que se ejecuta como contenedor
description: Sirve para comprender la importancia de usar un servidor de base de datos que se ejecuta como contenedor solamente para el desarrollo. Nunca se debe usar para la producción.
ms.date: 01/30/2020
ms.openlocfilehash: 0cbc933003aac10970814378c27e88b5cb0ddbe5
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628532"
---
# <a name="use-a-database-server-running-as-a-container"></a><span data-ttu-id="d621b-104">Uso de un servidor de bases de datos que se ejecuta como contenedor</span><span class="sxs-lookup"><span data-stu-id="d621b-104">Use a database server running as a container</span></span>

<span data-ttu-id="d621b-105">Puede tener las bases de datos (SQL Server, PostgreSQL, MySQL, etc.) en servidores independientes regulares, en clústeres locales o en los servicios PaaS en la nube como Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="d621b-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="d621b-106">Sin embargo, en los entornos de desarrollo y prueba, el hecho de que las bases de datos se ejecuten como contenedores resulta práctico, ya que no tiene ninguna dependencia externa y solo con ejecutar el comando `docker-compose up` ya se inicia toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d621b-106">However, for development and test environments, having your databases running as containers is convenient, because you don't have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="d621b-107">Tener esas bases de datos como contenedores también es muy útil para las pruebas de integración, porque la base de datos se inicia en el contenedor y siempre se rellena con los mismos datos de ejemplo, por lo que las pruebas pueden ser más predecibles.</span><span class="sxs-lookup"><span data-stu-id="d621b-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="d621b-108">SQL Server que se ejecuta como un contenedor con una base de datos relacionada con un microservicio</span><span class="sxs-lookup"><span data-stu-id="d621b-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="d621b-109">En eShopOnContainers, hay un contenedor denominado `sqldata`, como se define en el archivo [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml), que ejecuta una instancia de SQL Server para Linux con las bases de datos de SQL para todos los microservicios que la necesiten.</span><span class="sxs-lookup"><span data-stu-id="d621b-109">In eShopOnContainers, there's a container named `sqldata`, as defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file, that runs a SQL Server for Linux instance with the SQL databases for all microservices that need one.</span></span>

<span data-ttu-id="d621b-110">Un punto clave de los microservicios es que cada uno posee sus datos relacionados, de manera que debería tener su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="d621b-110">A key point in microservices is that each microservice owns its related data, so it should have its own database.</span></span> <span data-ttu-id="d621b-111">Sin embargo, las bases de datos pueden encontrarse en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="d621b-111">However, the databases can be anywhere.</span></span> <span data-ttu-id="d621b-112">En este caso, todas están en el mismo contenedor para mantener los requisitos de memoria de Docker tan bajos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="d621b-112">In this case, they are all in the same container to keep Docker memory requirements as low as possible.</span></span> <span data-ttu-id="d621b-113">Tenga en cuenta que esta es una solución suficientemente aceptable para el desarrollo y tal vez para las pruebas, pero no para la producción.</span><span class="sxs-lookup"><span data-stu-id="d621b-113">Keep in mind that this is a good-enough solution for development and, perhaps, testing but not for production.</span></span>

<span data-ttu-id="d621b-114">El contenedor de SQL Server de la aplicación de ejemplo se configura con el siguiente código YAML en el archivo docker-compose.yml, que se ejecuta al ejecutar `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="d621b-114">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="d621b-115">Tenga en cuenta que el código YAML ha recopilado información de configuración del archivo genérico docker-compose.yml y del archivo docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="d621b-115">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="d621b-116">(Normalmente separaría la configuración del entorno de la información base o estática relacionada con la imagen de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="d621b-116">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="d621b-117">De forma similar, en lugar de usar `docker-compose`, el siguiente comando `docker run` puede ejecutar ese contenedor:</span><span class="sxs-lookup"><span data-stu-id="d621b-117">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

<span data-ttu-id="d621b-118">Pero, si va a implementar una aplicación de varios contenedores, como eShopOnContainers, resulta más conveniente usar el comando `docker-compose up` para que implemente todos los contenedores necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d621b-118">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="d621b-119">Cuando se inicia este contenedor de SQL Server por primera vez, el contenedor inicializa SQL Server con la contraseña que usted proporcione.</span><span class="sxs-lookup"><span data-stu-id="d621b-119">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="d621b-120">Una vez que SQL Server se ejecuta como un contenedor, puede actualizar la base de datos mediante la conexión a través de cualquier conexión de SQL normal, como en SQL Server Management Studio, Visual Studio o código C\#.</span><span class="sxs-lookup"><span data-stu-id="d621b-120">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="d621b-121">La aplicación eShopOnContainers inicializa cada base de datos de microservicio con datos de ejemplo que propaga al inicio, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="d621b-121">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="d621b-122">El hecho de que SQL Server se ejecute como un contenedor no solo es útil para una demo, donde puede que no tenga acceso a una instancia de SQL Server,</span><span class="sxs-lookup"><span data-stu-id="d621b-122">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="d621b-123">sino que también es perfecto para entornos de desarrollo y prueba, de manera que puede realizar fácilmente pruebas de integración a partir de una imagen limpia de SQL Server y datos conocidos propagando nuevos datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d621b-123">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d621b-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d621b-124">Additional resources</span></span>

- <span data-ttu-id="d621b-125">**Ejecución de imágenes de Docker de SQL Server en Linux, Mac o Windows** </span><span class="sxs-lookup"><span data-stu-id="d621b-125">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- <span data-ttu-id="d621b-126">**Conexión y consulta de SQL Server en Linux con sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="d621b-126">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="d621b-127">Propagación con datos de prueba al iniciar la aplicación web</span><span class="sxs-lookup"><span data-stu-id="d621b-127">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="d621b-128">Para agregar datos a la base de datos cuando se inicia la aplicación, puede agregar código parecido al siguiente al método `Main` de la clase `Program` del proyecto de API web:</span><span class="sxs-lookup"><span data-stu-id="d621b-128">To add data to the database when the application starts up, you can add code like the following to the `Main` method in the `Program` class of the Web API project:</span></span>

```csharp
public static int Main(string[] args)
{
    var configuration = GetConfiguration();

    Log.Logger = CreateSerilogLogger(configuration);

    try
    {
        Log.Information("Configuring web host ({ApplicationContext})...", AppName);
        var host = CreateHostBuilder(configuration, args);

        Log.Information("Applying migrations ({ApplicationContext})...", AppName);
        host.MigrateDbContext<CatalogContext>((context, services) =>
        {
            var env = services.GetService<IWebHostEnvironment>();
            var settings = services.GetService<IOptions<CatalogSettings>>();
            var logger = services.GetService<ILogger<CatalogContextSeed>>();

            new CatalogContextSeed()
                .SeedAsync(context, env, settings, logger)
                .Wait();
        })
        .MigrateDbContext<IntegrationEventLogContext>((_, __) => { });

        Log.Information("Starting web host ({ApplicationContext})...", AppName);
        host.Run();

        return 0;
    }
    catch (Exception ex)
    {
        Log.Fatal(ex, "Program terminated unexpectedly ({ApplicationContext})!", AppName);
        return 1;
    }
    finally
    {
        Log.CloseAndFlush();
    }
}
```

<span data-ttu-id="d621b-129">Existe una salvedad importante a la hora de aplicar migraciones e inicializar una base de datos durante el inicio de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d621b-129">There's an important caveat when applying migrations and seeding a database during container startup.</span></span> <span data-ttu-id="d621b-130">Dado que es posible que la base de datos no esté disponible por algún motivo, debe controlar los reintentos mientras espera a que el servidor esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d621b-130">Since the database server might not be available for whatever reason, you must handle retries while waiting for the server to be available.</span></span> <span data-ttu-id="d621b-131">El método de extensión `MigrateDbContext()` controla esta lógica de reintentos, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d621b-131">This retry logic is handled by the `MigrateDbContext()` extension method, as shown in the following code:</span></span>

```cs
public static IWebHost MigrateDbContext<TContext>(
    this IWebHost host,
    Action<TContext,
    IServiceProvider> seeder)
      where TContext : DbContext
{
    var underK8s = host.IsInKubernetes();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        var logger = services.GetRequiredService<ILogger<TContext>>();

        var context = services.GetService<TContext>();

        try
        {
            logger.LogInformation("Migrating database associated with context {DbContextName}", typeof(TContext).Name);

            if (underK8s)
            {
                InvokeSeeder(seeder, context, services);
            }
            else
            {
                var retry = Policy.Handle<SqlException>()
                    .WaitAndRetry(new TimeSpan[]
                    {
                    TimeSpan.FromSeconds(3),
                    TimeSpan.FromSeconds(5),
                    TimeSpan.FromSeconds(8),
                    });

                //if the sql server container is not created on run docker compose this
                //migration can't fail for network related exception. The retry options for DbContext only
                //apply to transient exceptions
                // Note that this is NOT applied when running some orchestrators (let the orchestrator to recreate the failing service)
                retry.Execute(() => InvokeSeeder(seeder, context, services));
            }

            logger.LogInformation("Migrated database associated with context {DbContextName}", typeof(TContext).Name);
        }
        catch (Exception ex)
        {
            logger.LogError(ex, "An error occurred while migrating the database used on context {DbContextName}", typeof(TContext).Name);
            if (underK8s)
            {
                throw;          // Rethrow under k8s because we rely on k8s to re-run the pod
            }
        }
    }

    return host;
}
```

<span data-ttu-id="d621b-132">El código siguiente en la clase CatalogContextSeed personalizada rellena los datos.</span><span class="sxs-lookup"><span data-stu-id="d621b-132">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="d621b-133">Al realizar pruebas de integración, resulta útil disponer de una forma de generar datos coherentes con las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="d621b-133">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="d621b-134">Poder crear cualquier cosa de cero, incluida una instancia de SQL Server que se ejecuta en un contenedor, es muy útil para los entornos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d621b-134">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="d621b-135">Base de datos de EF Core InMemory frente a SQL Server que se ejecuta como un contenedor</span><span class="sxs-lookup"><span data-stu-id="d621b-135">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="d621b-136">Otra buena opción al realizar pruebas es usar el proveedor de base de datos de Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="d621b-136">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="d621b-137">Puede especificar esa configuración en el método ConfigureServices de la clase Startup en el proyecto de API web:</span><span class="sxs-lookup"><span data-stu-id="d621b-137">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }

    // Other Startup code ...
}
```

<span data-ttu-id="d621b-138">Sin embargo, hay un truco importante.</span><span class="sxs-lookup"><span data-stu-id="d621b-138">There is an important catch, though.</span></span> <span data-ttu-id="d621b-139">La base de datos en memoria no admite muchas restricciones que son específicas de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="d621b-139">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="d621b-140">Por ejemplo, podría agregar un índice único en una columna en el modelo de EF Core y escribir una prueba en la base de datos en memoria para comprobar que no le permite agregar un valor duplicado.</span><span class="sxs-lookup"><span data-stu-id="d621b-140">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="d621b-141">Pero cuando usa la base de datos en memoria, no puede controlar los índices únicos en una columna.</span><span class="sxs-lookup"><span data-stu-id="d621b-141">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="d621b-142">Por tanto, la base de datos en memoria no se comporta exactamente igual que una base de datos de SQL Server real: no emula restricciones específicas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d621b-142">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="d621b-143">Aun así, una base de datos en memoria también es útil para las pruebas y la creación de prototipos.</span><span class="sxs-lookup"><span data-stu-id="d621b-143">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="d621b-144">Pero si quiere crear pruebas de integración precisas que tengan en cuenta el comportamiento de la implementación de una base de datos determinada, debe usar una base de datos real como SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d621b-144">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="d621b-145">Para ello, ejecutar SQL Server en un contenedor es una gran opción, más precisa que el proveedor de base de datos de EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="d621b-145">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

## <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="d621b-146">Uso de un servicio de caché de Redis que se ejecuta en un contenedor</span><span class="sxs-lookup"><span data-stu-id="d621b-146">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="d621b-147">Puede ejecutar Redis en un contenedor, especialmente para desarrollo y pruebas y escenarios de prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="d621b-147">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="d621b-148">Este escenario resulta práctico, porque puede hacer que todas las dependencias se ejecuten en contenedores, no solo para las máquinas de desarrollo locales, sino también para los entornos de pruebas en las canalizaciones de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="d621b-148">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="d621b-149">Sin embargo, al ejecutar Redis en producción, es mejor buscar una solución de alta disponibilidad como Redis Microsoft Azure, que se ejecuta como una PaaS (plataforma como servicio).</span><span class="sxs-lookup"><span data-stu-id="d621b-149">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="d621b-150">En el código, solo debe cambiar las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="d621b-150">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="d621b-151">Redis proporciona una imagen de Docker con Redis.</span><span class="sxs-lookup"><span data-stu-id="d621b-151">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="d621b-152">Esa imagen está disponible en Docker Hub en esta dirección URL:</span><span class="sxs-lookup"><span data-stu-id="d621b-152">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/_/redis/>

<span data-ttu-id="d621b-153">Puede ejecutar directamente un contenedor Redis de Docker ejecutando el siguiente comando de CLI de Docker en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d621b-153">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
docker run --name some-redis -d redis
```

<span data-ttu-id="d621b-154">La imagen de Redis incluye expose:6379 (el puerto que usa Redis), de manera que la vinculación de contenedor estándar hará que esté automáticamente disponible para los contenedores vinculados.</span><span class="sxs-lookup"><span data-stu-id="d621b-154">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="d621b-155">En eShopOnContainers, el microservicio `basket-api` usa una caché de Redis que se ejecuta como contenedor.</span><span class="sxs-lookup"><span data-stu-id="d621b-155">In eShopOnContainers, the `basket-api` microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="d621b-156">Ese contenedor `basketdata` se define como parte del archivo de varios contenedores *docker-compose.yml*, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d621b-156">That `basketdata` container is defined as part of the multi-container *docker-compose.yml* file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="d621b-157">Este código de docker-compose.yml define un contenedor denominado `basketdata` que se basa en la imagen de Redis y publica el puerto 6379 de forma interna.</span><span class="sxs-lookup"><span data-stu-id="d621b-157">This code in the docker-compose.yml defines a container named `basketdata` based on the redis image and publishing the port 6379 internally.</span></span> <span data-ttu-id="d621b-158">Esto significa que solo será accesible desde otros contenedores que se ejecuten dentro del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="d621b-158">This means that it will only be accessible from other containers running within the Docker host.</span></span>

<span data-ttu-id="d621b-159">Por último, en el archivo *docker-compose.override.yml*, el microservicio `basket-api` para el ejemplo de eShopOnContainers define la cadena de conexión que se usará para ese contenedor de Redis:</span><span class="sxs-lookup"><span data-stu-id="d621b-159">Finally, in the *docker-compose.override.yml* file, the `basket-api` microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="d621b-160">Como se mencionó anteriormente, el DNS de la red interna de Docker resuelve el nombre del microservicio `basketdata`.</span><span class="sxs-lookup"><span data-stu-id="d621b-160">As mentioned before, the name of the microservice `basketdata` is resolved by Docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d621b-161">[Anterior](multi-container-applications-docker-compose.md)
>[Siguiente](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="d621b-161">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
