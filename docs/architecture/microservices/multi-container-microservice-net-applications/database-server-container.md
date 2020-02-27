---
title: Uso de un servidor de bases de datos que se ejecuta como contenedor
description: Sirve para comprender la importancia de usar un servidor de base de datos que se ejecuta como contenedor solamente para el desarrollo. Nunca se debe usar para la producción.
ms.date: 01/30/2020
ms.openlocfilehash: 816ac196636f78a368a9f20e8eedcc6a22567fa7
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502286"
---
# <a name="use-a-database-server-running-as-a-container"></a>Uso de un servidor de bases de datos que se ejecuta como contenedor

Puede tener las bases de datos (SQL Server, PostgreSQL, MySQL, etc.) en servidores independientes regulares, en clústeres locales o en los servicios PaaS en la nube como Azure SQL DB. Sin embargo, en los entornos de desarrollo y prueba, el hecho de que las bases de datos se ejecuten como contenedores resulta práctico, ya que no tiene ninguna dependencia externa y solo con ejecutar el comando `docker-compose up` ya se inicia toda la aplicación. Tener esas bases de datos como contenedores también es muy útil para las pruebas de integración, porque la base de datos se inicia en el contenedor y siempre se rellena con los mismos datos de ejemplo, por lo que las pruebas pueden ser más predecibles.

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server que se ejecuta como un contenedor con una base de datos relacionada con un microservicio

En eShopOnContainers, hay un contenedor denominado `sqldata`, como se define en el archivo [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml), que ejecuta una instancia de SQL Server para Linux con las bases de datos de SQL para todos los microservicios que la necesiten.

Un punto clave de los microservicios es que cada uno posee sus datos relacionados, de manera que debería tener su propia base de datos. Sin embargo, las bases de datos pueden encontrarse en cualquier lugar. En este caso, todas están en el mismo contenedor para mantener los requisitos de memoria de Docker tan bajos como sea posible. Tenga en cuenta que esta es una solución suficientemente aceptable para el desarrollo y tal vez para las pruebas, pero no para la producción.

El contenedor de SQL Server de la aplicación de ejemplo se configura con el siguiente código YAML en el archivo docker-compose.yml, que se ejecuta al ejecutar `docker-compose up`. Tenga en cuenta que el código YAML ha recopilado información de configuración del archivo genérico docker-compose.yml y del archivo docker-compose.override.yml. (Normalmente separaría la configuración del entorno de la información base o estática relacionada con la imagen de SQL Server).

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

De forma similar, en lugar de usar `docker-compose`, el siguiente comando `docker run` puede ejecutar ese contenedor:

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

Pero, si va a implementar una aplicación de varios contenedores, como eShopOnContainers, resulta más conveniente usar el comando `docker-compose up` para que implemente todos los contenedores necesarios para la aplicación.

Cuando se inicia este contenedor de SQL Server por primera vez, el contenedor inicializa SQL Server con la contraseña que usted proporcione. Una vez que SQL Server se ejecuta como un contenedor, puede actualizar la base de datos mediante la conexión a través de cualquier conexión de SQL normal, como en SQL Server Management Studio, Visual Studio o código C\#.

La aplicación eShopOnContainers inicializa cada base de datos de microservicio con datos de ejemplo que propaga al inicio, tal como se describe en la sección siguiente.

El hecho de que SQL Server se ejecute como un contenedor no solo es útil para una demo, donde puede que no tenga acceso a una instancia de SQL Server, sino que también es perfecto para entornos de desarrollo y prueba, de manera que puede realizar fácilmente pruebas de integración a partir de una imagen limpia de SQL Server y datos conocidos propagando nuevos datos de ejemplo.

### <a name="additional-resources"></a>Recursos adicionales

- **Ejecución de imágenes de Docker de SQL Server en Linux, Mac o Windows** \
    <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- **Conexión y consulta de SQL Server en Linux con sqlcmd** \
    <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a>Propagación con datos de prueba al iniciar la aplicación web

Para agregar datos a la base de datos cuando se inicia la aplicación, puede agregar código parecido al siguiente al método `Main` de la clase `Program` del proyecto de API web:

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

Existe una salvedad importante a la hora de aplicar migraciones e inicializar una base de datos durante el inicio de un contenedor. Dado que es posible que la base de datos no esté disponible por algún motivo, debe controlar los reintentos mientras espera a que el servidor esté disponible. El método de extensión `MigrateDbContext()` controla esta lógica de reintentos, como se muestra en el código siguiente:

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

El código siguiente en la clase CatalogContextSeed personalizada rellena los datos.

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

Al realizar pruebas de integración, resulta útil disponer de una forma de generar datos coherentes con las pruebas de integración. Poder crear cualquier cosa de cero, incluida una instancia de SQL Server que se ejecuta en un contenedor, es muy útil para los entornos de prueba.

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Base de datos de EF Core InMemory frente a SQL Server que se ejecuta como un contenedor

Otra buena opción al realizar pruebas es usar el proveedor de base de datos de Entity Framework InMemory. Puede especificar esa configuración en el método ConfigureServices de la clase Startup en el proyecto de API web:

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

Sin embargo, hay un truco importante. La base de datos en memoria no admite muchas restricciones que son específicas de una base de datos determinada. Por ejemplo, podría agregar un índice único en una columna en el modelo de EF Core y escribir una prueba en la base de datos en memoria para comprobar que no le permite agregar un valor duplicado. Pero cuando usa la base de datos en memoria, no puede controlar los índices únicos en una columna. Por tanto, la base de datos en memoria no se comporta exactamente igual que una base de datos de SQL Server real: no emula restricciones específicas de la base de datos.

Aun así, una base de datos en memoria también es útil para las pruebas y la creación de prototipos. Pero si quiere crear pruebas de integración precisas que tengan en cuenta el comportamiento de la implementación de una base de datos determinada, debe usar una base de datos real como SQL Server. Para ello, ejecutar SQL Server en un contenedor es una gran opción, más precisa que el proveedor de base de datos de EF Core InMemory.

## <a name="using-a-redis-cache-service-running-in-a-container"></a>Uso de un servicio de caché de Redis que se ejecuta en un contenedor

Puede ejecutar Redis en un contenedor, especialmente para desarrollo y pruebas y escenarios de prueba de concepto. Este escenario resulta práctico, porque puede hacer que todas las dependencias se ejecuten en contenedores, no solo para las máquinas de desarrollo locales, sino también para los entornos de pruebas en las canalizaciones de CI/CD.

Sin embargo, al ejecutar Redis en producción, es mejor buscar una solución de alta disponibilidad como Redis Microsoft Azure, que se ejecuta como una PaaS (plataforma como servicio). En el código, solo debe cambiar las cadenas de conexión.

Redis proporciona una imagen de Docker con Redis. Esa imagen está disponible en Docker Hub en esta dirección URL:

<https://hub.docker.com/_/redis/>

Puede ejecutar directamente un contenedor Redis de Docker ejecutando el siguiente comando de CLI de Docker en el símbolo del sistema:

```console
docker run --name some-redis -d redis
```

La imagen de Redis incluye expose:6379 (el puerto que usa Redis), de manera que la vinculación de contenedor estándar hará que esté automáticamente disponible para los contenedores vinculados.

En eShopOnContainers, el microservicio `basket-api` usa una caché de Redis que se ejecuta como contenedor. Ese contenedor `basketdata` se define como parte del archivo de varios contenedores *docker-compose.yml*, como se muestra en el ejemplo siguiente:

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

Este código de docker-compose.yml define un contenedor denominado `basketdata` que se basa en la imagen de Redis y publica el puerto 6379 de forma interna. Esto significa que solo será accesible desde otros contenedores que se ejecuten dentro del host de Docker.

Por último, en el archivo *docker-compose.override.yml*, el microservicio `basket-api` para el ejemplo de eShopOnContainers define la cadena de conexión que se usará para ese contenedor de Redis:

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

Como se mencionó anteriormente, el DNS de la red interna de Docker resuelve el nombre del microservicio `basketdata`.

>[!div class="step-by-step"]
>[Anterior](multi-container-applications-docker-compose.md)
>[Siguiente](integration-event-based-microservice-communications.md)
