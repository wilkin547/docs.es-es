---
title: Uso de un servidor de base de datos que se ejecuta como un contenedor
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Uso de un servidor de base de datos que se ejecuta como un contenedor
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a>Uso de un servidor de base de datos que se ejecuta como un contenedor

Puede tener las bases de datos (SQL Server, PostgreSQL, MySQL, etc.) en los servidores de independientes regular, en clústeres locales o en los servicios de PaaS en la nube como base de datos de SQL Azure. Sin embargo, para entornos de desarrollo y prueba, las bases de datos que se ejecuta como contenedores es tener cómoda, ya que no tiene ninguna dependencia externa y en ejecución simplemente la redacción de docker comando inicia toda la aplicación. Tener esas bases de datos como contenedores también es muy útil para las pruebas de integración, porque la base de datos se inicia en el contenedor y siempre se rellena con los mismos datos, por lo que las pruebas pueden ser más predecibles.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server que se ejecuta como un contenedor con una base de datos relacionados con el microservicio

En eShopOnContainers, hay un contenedor denominado sql.data definido en el [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) archivo que se ejecuta SQL Server para Linux con todas las bases de datos de SQL Server necesarios para la microservicios. (También puede tener un contenedor de SQL Server para cada base de datos, pero que requiere más memoria asignada a Docker). Es importante en microservicios es que cada microservicio es propietaria de sus datos relacionados, por lo tanto, su base de datos SQL relacionada en este caso. Pero las bases de datos pueden ser desde cualquier lugar.

Contenedor de la aplicación de ejemplo se configura con el siguiente código YAML en el archivo compose.yml de docker, que se ejecuta cuando se ejecuta SQL Server docker-crear una. Tenga en cuenta que el código YAML ha recopilado la información de configuración desde el archivo genérico de compose.yml de docker y el archivo compose.override.yml docker. (Normalmente separaría la configuración del entorno de la información de base o estática relacionada con la imagen de SQL Server.)

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

El siguiente comando docker run puede ejecutar dicho contenedor:

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

Sin embargo, si va a implementar una aplicación de contenedor múltiples como eShopOnContainers, resulta más conveniente utilizar el docker-crear comando para que se implemente todos los contenedores necesarios para la aplicación.

Cuando se inicia este contenedor de SQL Server por primera vez, el contenedor inicializa SQL Server con la contraseña proporcionada por usted. Una vez que SQL Server se ejecuta como un contenedor, puede actualizar la base de datos mediante la conexión a través de cualquier conexión de SQL normal, como en SQL Server Management Studio, Visual Studio o C\# código.

La aplicación eShopOnContainers inicializa cada base de datos de microservicio con datos de ejemplo inicializarla con datos en el inicio, tal como se describe en la sección siguiente.

Con SQL Server que se ejecuta como un contenedor no es sólo es útil para obtener una demostración donde puede que no tenga acceso a una instancia de SQL Server. Como se indicó, también es ideal para entornos de desarrollo y pruebas para que pueda ejecutar pruebas de integración a partir de una imagen limpia de SQL Server y datos conocidos propagando nuevos datos de ejemplo fácilmente.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Ejecutar la imagen de Docker de SQL Server en Linux, Mac o Windows**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **Conectarse y consultar SQL Server en Linux con sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>La propagación con datos de prueba al iniciar la aplicación Web

Para agregar datos a la base de datos cuando se inicia la aplicación, puede agregar código similar al siguiente al método configurar en la clase de inicio de proyecto de API Web:

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

Al ejecutar pruebas de integración, resulta útil tener una forma de generar datos coherentes con las pruebas de integración. Posibilidad de crear cualquier cosa, desde cero, incluya una instancia de SQL Server que se ejecuta en un contenedor, es muy útil para entornos de prueba.

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Base de datos EF Core InMemory frente a SQL Server que se ejecuta como un contenedor

Otra buena elección cuando se ejecuten pruebas consiste en utilizar el proveedor de base de datos de Entity Framework InMemory. Puede especificar que la configuración en el método ConfigureServices de la clase de inicio en el proyecto de API Web:

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

Sin embargo, hay un bloque catch importante. La base de datos en memoria no admite varias restricciones que son específicas de una base de datos determinada. Por ejemplo, podría agregar un índice único en una columna en el modelo de EF Core y escribir una prueba en la base de datos en memoria para comprobar que no le permite agregar un valor duplicado. Pero cuando se usa la base de datos en memoria, no puede controlar los índices únicos en una columna. Por lo tanto, la base de datos en memoria no se comportan exactamente igual que una base de datos de SQL Server real: no emula restricciones específicas de la base de datos.

Aun así, una base de datos en memoria también es útil para las pruebas y la creación de prototipos. Pero si desea crear pruebas de integración precisa que tener en cuenta el comportamiento de una implementación específica de la base de datos, debe usar una base de datos real como SQL Server. Para ello, ejecuta SQL Server en un contenedor es una gran elección y más precisa que el proveedor de base de datos de EF Core InMemory.

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Uso de un servicio de caché de Redis ejecuta en un contenedor

Puede ejecutar Redis en un contenedor, especialmente para desarrollo y pruebas y escenarios de prueba de concepto. Este escenario resulta práctico, porque puede hacer que todas las dependencias con contenedores, no solo para los equipos de desarrollo local, pero para los entornos de pruebas en las canalizaciones de CI/CD.

Sin embargo, al ejecutar Redis en producción, es mejor buscar una solución de alta disponibilidad como Redis Microsoft Azure, que se ejecuta como una PaaS (plataforma como servicio). En el código, solo necesita cambiar las cadenas de conexión.

Redis proporciona una imagen de Docker con Redis. Esa imagen está disponible en Docker Hub en esta dirección URL:

<https://hub.docker.com/_/Redis/>

Puede ejecutar directamente un contenedor Docker Redis ejecutando el siguiente comando de CLI de Docker en el símbolo del sistema:

```
  docker run --name some-redis -d redis
```

La imagen de Redis incluye exponen: 6379 (es decir, el puerto usado por Redis), la vinculación de contenedor estándar por lo que le resultará disponibles automáticamente a los contenedores vinculados.

En eShopOnContainers, el microservicio basket.api utiliza una caché de Redis que se ejecuta como un contenedor. Ese contenedor basket.data se define como parte del archivo Multi-contenedor docker-compose.yml, tal como se muestra en el ejemplo siguiente:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Este código en el compose.yml docker define un contenedor denominado basket.data basada en la imagen de redis y publicar el puerto 6379 internamente, lo que significa que estará accesible sólo desde los otros contenedores que se ejecutan dentro del host de Docker.

Por último, en el archivo compose.override.yml de docker, el microservicio basket.api del ejemplo eShopOnContainers define la cadena de conexión que se usará para ese contenedor Redis:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[Anterior] (varios-container-aplicaciones-docker-compose.md) [siguiente] (integración-eventos-según-microservicio-communications.md)
