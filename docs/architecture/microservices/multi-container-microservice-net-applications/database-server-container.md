---
title: Uso de un servidor de bases de datos que se ejecuta como un contenedor
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | El uso de un servidor de bases de datos que se ejecuta como un contenedor debería limitarse al desarrollo. Aquí descubrirá por qué.
ms.date: 10/02/2018
ms.openlocfilehash: 3e655e26be2d6132577b0494db39d9c2e8b9aacd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039839"
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="38d20-104">Uso de un servidor de bases de datos que se ejecuta como un contenedor</span><span class="sxs-lookup"><span data-stu-id="38d20-104">Using a database server running as a container</span></span>

<span data-ttu-id="38d20-105">Puede tener las bases de datos (SQL Server, PostgreSQL, MySQL, etc.) en servidores independientes regulares, en clústeres locales o en los servicios PaaS en la nube como Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="38d20-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="38d20-106">Pero en los entornos de desarrollo y prueba, el hecho de que las bases de datos se ejecuten como contenedores es conveniente, ya que no tiene ninguna dependencia externa y solo con ejecutar el comando `docker-compose up` ya se inicia toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38d20-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="38d20-107">Tener esas bases de datos como contenedores también es muy útil para las pruebas de integración, porque la base de datos se inicia en el contenedor y siempre se rellena con los mismos datos de ejemplo, por lo que las pruebas pueden ser más predecibles.</span><span class="sxs-lookup"><span data-stu-id="38d20-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="38d20-108">SQL Server que se ejecuta como un contenedor con una base de datos relacionada con un microservicio</span><span class="sxs-lookup"><span data-stu-id="38d20-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="38d20-109">En eShopOnContainers, hay un contenedor denominado sql.data definido en el archivo [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) que ejecuta SQL Server para Linux con todas las bases de datos de SQL Server necesarias para los microservicios.</span><span class="sxs-lookup"><span data-stu-id="38d20-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="38d20-110">(También puede tener un contenedor de SQL Server para cada base de datos, pero eso requiere más memoria asignada a Docker). Lo importante de los microservicios es que cada microservicio posea sus datos relacionados, es decir, su base de datos SQL relacionada en este caso.</span><span class="sxs-lookup"><span data-stu-id="38d20-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="38d20-111">Pero las bases de datos pueden encontrarse en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="38d20-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="38d20-112">El contenedor de SQL Server de la aplicación de ejemplo se configura con el siguiente código YAML en el archivo docker-compose.yml, que se ejecuta al ejecutar `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="38d20-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="38d20-113">Tenga en cuenta que el código YAML ha recopilado información de configuración del archivo genérico docker-compose.yml y del archivo docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="38d20-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="38d20-114">(Normalmente separaría la configuración del entorno de la información base o estática relacionada con la imagen de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="38d20-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="38d20-115">De forma similar, en lugar de usar `docker-compose`, el siguiente comando `docker run` puede ejecutar ese contenedor:</span><span class="sxs-lookup"><span data-stu-id="38d20-115">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```console
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

<span data-ttu-id="38d20-116">Pero, si va a implementar una aplicación de varios contenedores, como eShopOnContainers, resulta más conveniente usar el comando `docker-compose up` para que implemente todos los contenedores necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38d20-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="38d20-117">Cuando se inicia este contenedor de SQL Server por primera vez, el contenedor inicializa SQL Server con la contraseña que usted proporcione.</span><span class="sxs-lookup"><span data-stu-id="38d20-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="38d20-118">Una vez que SQL Server se ejecuta como un contenedor, puede actualizar la base de datos mediante la conexión a través de cualquier conexión de SQL normal, como en SQL Server Management Studio, Visual Studio o código C\#.</span><span class="sxs-lookup"><span data-stu-id="38d20-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="38d20-119">La aplicación eShopOnContainers inicializa cada base de datos de microservicio con datos de ejemplo que propaga al inicio, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="38d20-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="38d20-120">El hecho de que SQL Server se ejecute como un contenedor no solo es útil para una demo, donde puede que no tenga acceso a una instancia de SQL Server,</span><span class="sxs-lookup"><span data-stu-id="38d20-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="38d20-121">sino que también es perfecto para entornos de desarrollo y prueba, de manera que puede realizar fácilmente pruebas de integración a partir de una imagen limpia de SQL Server y datos conocidos propagando nuevos datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="38d20-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="38d20-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="38d20-122">Additional resources</span></span>

- <span data-ttu-id="38d20-123">**Ejecución de imágenes de Docker de SQL Server en Linux, Mac o Windows** </span><span class="sxs-lookup"><span data-stu-id="38d20-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- <span data-ttu-id="38d20-124">**Conexión y consulta de SQL Server en Linux con sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="38d20-124">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="38d20-125">Propagación con datos de prueba al iniciar la aplicación web</span><span class="sxs-lookup"><span data-stu-id="38d20-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="38d20-126">Para agregar datos a la base de datos cuando se inicia la aplicación, puede agregar código similar al siguiente al método Configure en la clase Startup del proyecto de API web:</span><span class="sxs-lookup"><span data-stu-id="38d20-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="38d20-127">El código siguiente en la clase CatalogContextSeed personalizada rellena los datos.</span><span class="sxs-lookup"><span data-stu-id="38d20-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="38d20-128">Al realizar pruebas de integración, resulta útil disponer de una forma de generar datos coherentes con las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="38d20-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="38d20-129">Poder crear cualquier cosa de cero, incluida una instancia de SQL Server que se ejecuta en un contenedor, es muy útil para los entornos de prueba.</span><span class="sxs-lookup"><span data-stu-id="38d20-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="38d20-130">Base de datos de EF Core InMemory frente a SQL Server que se ejecuta como un contenedor</span><span class="sxs-lookup"><span data-stu-id="38d20-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="38d20-131">Otra buena opción al realizar pruebas es usar el proveedor de base de datos de Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="38d20-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="38d20-132">Puede especificar esa configuración en el método ConfigureServices de la clase Startup en el proyecto de API web:</span><span class="sxs-lookup"><span data-stu-id="38d20-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="38d20-133">Sin embargo, hay un truco importante.</span><span class="sxs-lookup"><span data-stu-id="38d20-133">There is an important catch, though.</span></span> <span data-ttu-id="38d20-134">La base de datos en memoria no admite muchas restricciones que son específicas de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="38d20-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="38d20-135">Por ejemplo, podría agregar un índice único en una columna en el modelo de EF Core y escribir una prueba en la base de datos en memoria para comprobar que no le permite agregar un valor duplicado.</span><span class="sxs-lookup"><span data-stu-id="38d20-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="38d20-136">Pero cuando usa la base de datos en memoria, no puede controlar los índices únicos en una columna.</span><span class="sxs-lookup"><span data-stu-id="38d20-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="38d20-137">Por tanto, la base de datos en memoria no se comporta exactamente igual que una base de datos de SQL Server real: no emula restricciones específicas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="38d20-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="38d20-138">Aun así, una base de datos en memoria también es útil para las pruebas y la creación de prototipos.</span><span class="sxs-lookup"><span data-stu-id="38d20-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="38d20-139">Pero si quiere crear pruebas de integración precisas que tengan en cuenta el comportamiento de la implementación de una base de datos determinada, debe usar una base de datos real como SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38d20-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="38d20-140">Para ello, ejecutar SQL Server en un contenedor es una gran opción, más precisa que el proveedor de base de datos de EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="38d20-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="38d20-141">Uso de un servicio de caché de Redis que se ejecuta en un contenedor</span><span class="sxs-lookup"><span data-stu-id="38d20-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="38d20-142">Puede ejecutar Redis en un contenedor, especialmente para desarrollo y pruebas y escenarios de prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="38d20-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="38d20-143">Este escenario resulta práctico, porque puede hacer que todas las dependencias se ejecuten en contenedores, no solo para las máquinas de desarrollo locales, sino también para los entornos de pruebas en las canalizaciones de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="38d20-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="38d20-144">Sin embargo, al ejecutar Redis en producción, es mejor buscar una solución de alta disponibilidad como Redis Microsoft Azure, que se ejecuta como una PaaS (plataforma como servicio).</span><span class="sxs-lookup"><span data-stu-id="38d20-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="38d20-145">En el código, solo debe cambiar las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="38d20-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="38d20-146">Redis proporciona una imagen de Docker con Redis.</span><span class="sxs-lookup"><span data-stu-id="38d20-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="38d20-147">Esa imagen está disponible en Docker Hub en esta dirección URL:</span><span class="sxs-lookup"><span data-stu-id="38d20-147">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/\_/redis/>

<span data-ttu-id="38d20-148">Puede ejecutar directamente un contenedor Redis de Docker ejecutando el siguiente comando de CLI de Docker en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="38d20-148">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
  docker run --name some-redis -d redis
```

<span data-ttu-id="38d20-149">La imagen de Redis incluye expose:6379 (el puerto que usa Redis), de manera que la vinculación de contenedor estándar hará que esté automáticamente disponible para los contenedores vinculados.</span><span class="sxs-lookup"><span data-stu-id="38d20-149">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="38d20-150">En eShopOnContainers, el microservicio basket.api usa una caché de Redis que se ejecuta como un contenedor.</span><span class="sxs-lookup"><span data-stu-id="38d20-150">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="38d20-151">Ese contenedor basket.data se define como parte del archivo de varios contenedores docker-compose.yml, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38d20-151">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="38d20-152">Este código en el archivo docker-compose.yml define un contenedor denominado basket.data basado en la imagen de Redis que publica el puerto 6379 internamente, lo que significa que estará accesible solo desde los otros contenedores que se ejecutan dentro del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="38d20-152">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="38d20-153">Por último, en el archivo docker-compose.override.yml, el microservicio basket.api para el ejemplo de eShopOnContainers define la cadena de conexión que se usará para ese contenedor de Redis:</span><span class="sxs-lookup"><span data-stu-id="38d20-153">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="38d20-154">Como se mencionó antes, el DNS de la red interna de Docker resuelve el nombre del microservicio "basket.data".</span><span class="sxs-lookup"><span data-stu-id="38d20-154">As mentioned before, the name of the microservice "basket.data" is resolved by docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="38d20-155">[Anterior](multi-container-applications-docker-compose.md)
>[Siguiente](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="38d20-155">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
