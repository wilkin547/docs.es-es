---
title: Creación de un microservicio CRUD sencillo controlado por datos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Creación de un microservicio CRUD sencillo controlado por datos
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 85694cbfe8c30b8430200f0ffbd01379f11b3f9d
ms.sourcegitcommit: c03eef711abe961a85db2b4d0715257d1524aef6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Creación de un microservicio CRUD sencillo controlado por datos

En esta sección se describe cómo crear un microservicio sencillo que lleve a cabo operaciones de creación, lectura, actualización y eliminación (CRUD) en un origen de datos.

## <a name="designing-a-simple-crud-microservice"></a>Diseño de un microservicio CRUD sencillo

Desde un punto de vista de diseño, este tipo de microservicio en contenedor es muy sencillo. Quizás el problema para resolver es sencillo o la implementación es solo una prueba de concepto.

![](./media/image4.png)

**Figura 8-4**. Diseño interno de microservicios CRUD sencillos

Un ejemplo de este tipo de servicio sencillo controlado por datos es el microservicio de catálogo de la aplicación de ejemplo eShopOnContainers. Este tipo de servicio implementa toda su funcionalidad en un solo proyecto de API Web de ASP.NET Core que incluye las clases para su modelo de datos, su lógica de negocios y su código de acceso a datos. También almacena los datos relacionados en una base de datos que ejecuta SQL Server (como otro contenedor para fines de desarrollo y pruebas), pero también podría ser cualquier host de SQL Server normal, como se muestra en la Figura 8-5.

![](./media/image5.png)

**Figura 8-5**. Diseño de un microservicio CRUD sencillo controlado por datos

Para desarrollar este tipo de servicio, solo necesita [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) y una ORP o API de acceso a datos, como [Entity Framework Core](https://docs.microsoft.com/ef/core/index). También puede generar automáticamente metadatos [Swagger](https://swagger.io/) a través de [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), para proporcionar una descripción de lo que ofrece el servicio, tal como se describe en la sección siguiente.

Tenga en cuenta que ejecutar un servidor de base de datos como SQL Server en un contenedor de Docker es muy útil para entornos de desarrollo, porque puede poner en marcha todas sus dependencias sin tener que proporcionar una base de datos local o en la nube. Esto resulta muy útil para ejecutar pruebas de integración. Pero no se recomienda ejecutar un servidor de base de datos en un contenedor para entornos de producción, ya que normalmente no se obtiene alta disponibilidad con ese método. En un entorno de producción de Azure, le recomendamos que utilice la base de datos SQL de Azure o cualquier otra tecnología de base de datos que pueda proporcionar alta disponibilidad y alta escalabilidad. Por ejemplo, para un método NoSQL, puede elegir DocumentDB.

Por último, al editar los archivos de metadatos de Dockerfile y docker-compose.yml, puede configurar cómo se creará la imagen de este contenedor, es decir, la imagen base que se usará y la configuración de diseño, como los nombres internos y externos y los puertos TCP. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementación de un microservicio CRUD sencillo con ASP.NET Core

Para implementar un microservicio CRUD sencillo con .NET Core y Visual Studio, primero debe crear un proyecto de API Web de ASP.NET Core sencillo (que se ejecute en .NET Core para que pueda ejecutarse en un host de Linux Docker), como se muestra en la Figura 8-6.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**Figura 8-6**. Creación de un proyecto de API Web de ASP.NET Core en Visual Studio

Después de crear el proyecto, puede implementar los controladores MVC como lo haría en cualquier otro proyecto de API Web, mediante la API de Entity Framework u otra API. En un nuevo proyecto de API Web, puede ver que la única dependencia que tiene de ese microservicio es el mismo ASP.NET Core. Internamente, dentro de la dependencia `Microsoft.AspNetCore.All`, hace referencia a Entity Framework y a muchos otros paquetes de Nuget de .NET Core, tal como se muestra en la Figura 8-7.

![](./media/image8.PNG)

**Figura 8-7**. Dependencias en un microservicio API Web de CRUD sencillo

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementación de servicios API Web de CRUD con Entity Framework Core

Entity Framework (EF) Core es una versión ligera, extensible y multiplataforma de la popular tecnología de acceso a datos Entity Framework. EF Core es un asignador relacional de objetos (ORM) que permite a los desarrolladores de .NET trabajar con una base de datos mediante objetos .NET.

El microservicio de catálogo usa EF y el proveedor de SQL Server porque su base de datos se está ejecutando en un contenedor con la imagen de SQL Server para Linux Docker. Pero la base de datos podría implementarse en cualquier SQL Server, como en una base de datos SQL de Azure o Windows local. Lo único que debe cambiar es la cadena de conexión en el microservicio ASP.NET Web API.


#### <a name="the-data-model"></a>El modelo de datos

Con EF Core, el acceso a datos se realiza utilizando un modelo. Un modelo se compone de clases de entidad y un contexto derivado que representa una sesión con la base de datos, lo que permite consultar y guardar los datos. Puede generar un modelo a partir de una base de datos existente, codificar manualmente un modelo para que coincida con la base de datos o usar migraciones de EF para crear una base de datos a partir de su modelo (y que evolucione a medida que el modelo cambia). Para el microservicio de catálogo, usamos el último enfoque. Puede ver un ejemplo de la clase de entidad CatalogItem en el ejemplo de código siguiente, que es una clase de entidad de objeto CLR estándar ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).

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

También necesita un DbContext que represente una sesión con la base de datos. Para el microservicio de catálogo, la clase CatalogContext se deriva de la clase base DbContext, tal como se muestra en el ejemplo siguiente:

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

Puede tener implementaciones `DbContext` adicionales. Por ejemplo, en el microservicio Catalog.API de ejemplo, hay un segundo `DbContext` denominado `CatalogContextSeed`, en que rellena automáticamente los datos de ejemplo la primera vez que intenta acceder a la base de datos. Este método es útil para los datos de demostración y también para escenarios de pruebas automatizadas. En `DbContext`, usa el método `OnModelCreating` para personalizar las asignaciones de entidades de objeto/base de datos con otros [puntos de extensibilidad de EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

##### <a name="querying-data-from-web-api-controllers"></a>Consulta de los datos desde controladores de API web

Normalmente las instancias de sus clases de entidad se recuperan de la base de datos mediante Language Integrated Query (LINQ), como se muestra en el ejemplo siguiente:

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

##### <a name="saving-data"></a>Guardado de datos

Los datos se crean, se eliminan y se modifican en la base de datos mediante instancias de las clases de entidad. Puede agregar código similar al siguiente ejemplo codificado de forma rígida (datos simulados, en este caso) a sus controladores de la API web.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Inserción de dependencias en los controladores de ASP.NET Core y API web

En ASP.NET Core, puede usar la inserción de dependencias desde el principio. No es necesario que configure un contenedor de inversión de control (IoC) de terceros, aunque, si lo desea, puede conectar su contenedor de IoC preferido a la infraestructura de ASP.NET Core. En este caso, puede insertar directamente el DBContext de EF requerido o los repositorios adicionales a través del constructor del controlador. En el ejemplo anterior de la clase `CatalogController`, vamos a insertar un objeto del tipo `CatalogContext` junto con otros objetos a través del constructor `CatalogController()`.

Una opción importante que hay que configurar en el proyecto de Web API es el registro de la clase DbContext en el contenedor de IoC del servicio. Normalmente se hace en la clase `Startup`, mediante una llamada al método `services.AddDbContext<DbContext>()` dentro del método `ConfigureServices()`, como se muestra en el ejemplo siguiente:

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

### <a name="additional-resources"></a>Recursos adicionales

-   **Consulta de datos**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **Guardado de datos**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Variables de entorno y cadena de conexión de la base de datos utilizadas por contenedores de Docker

Puede usar la configuración de ASP.NET Core y agregar una propiedad ConnectionString al archivo settings.json, tal como se muestra en el ejemplo siguiente:

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

El archivo settings.json puede tener valores predeterminados para la propiedad ConnectionString o para cualquier otra propiedad. Pero estas propiedades se reemplazarán por los valores de las variables de entorno que se especifican en el archivo docker-compose.override.yml, al usar Docker.

Desde los archivos docker-compose.yml o docker-compose.override.yml, puede inicializar estas variables de entorno para que Docker las configure como variables de entorno del sistema operativo, como se muestra en el siguiente archivo docker-compose.override.yml (la cadena de conexión y otras líneas se encapsulan en este ejemplo, pero no lo harán en su archivo de código).

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

Los archivos docker-compose.yml en el nivel de solución no solo son más flexibles que los archivos de configuración en el nivel de proyecto o de microservicio, sino que también son más seguros si reemplaza las variables declaradas en los archivos docker-compose con valores establecidos en las herramientas de implementación, como las tareas de implementación del Docker de VSTS. 

Por último, puede obtener ese valor desde el código mediante la configuración \["ConnectionString"\], tal y como se muestra en el método ConfigureServices de un ejemplo de código anterior.

Pero, en entornos de producción, puede ser que le interese analizar otras formas de almacenar secretos, como las cadenas de conexión. Por lo general, esto estará administrado por el orquestador que elija, como puede hacer con [la administración de secretos en Docker Swarm](https://docs.docker.com/engine/swarm/secrets/).

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementación del control de versiones en las API web de ASP.NET

A medida que cambian los requisitos empresariales, pueden agregarse nuevas colecciones de recursos, las relaciones entre recursos pueden cambiar y la estructura de los datos en los recursos se puede modificar. Actualizar una API web para controlar requisitos nuevos es un proceso relativamente sencillo, pero debe tener en cuenta los efectos que estos cambios tendrán en las aplicaciones cliente que consumen la API web. Aunque el desarrollador que diseña e implementa una API web tiene control total sobre dicha API, no tiene el mismo grado de control sobre las aplicaciones cliente creadas por organizaciones de terceros que funcionan de forma remota.

El control de versiones permite que una API web indique las características y los recursos que expone. De este modo, una aplicación cliente puede enviar solicitudes a una versión específica de una característica o de un recurso. Existen varios enfoques para implementar el control de versiones:

-   Control de versiones de URI

-   Control de versiones de cadena de consulta

-   Control de versiones de encabezado

El control de versiones de URI y de cadena de consulta son los más fáciles de implementar. El control de versiones de encabezado es una buena opción. Pero el control de versiones de encabezado no es tan explícito y sencillo como el control de versiones de URI. Como el control de versiones de URI es el más sencillo y explícito, es el que utiliza la aplicación de ejemplo eShopOnContainers.

Con el control de versiones de URI, como se muestra en la aplicación de ejemplo eShopOnContainers, cada vez que modifique la API web o cambie el esquema de recursos, agregará un número de versión al URI de cada recurso. Los URI existentes deben continuar funcionando como antes, devolviendo los recursos que conforman el esquema que coincide con la versión solicitada.

Como se muestra en el ejemplo de código siguiente, la versión puede establecerse mediante el atributo de ruta en la API web, lo que hace que la versión se explicite en el URI (versión 1 en este caso).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Este mecanismo de control de versiones es sencillo y depende del servidor que enruta la solicitud al punto de conexión adecuado. Pero para utilizar un control de versiones más sofisticado y adoptar el mejor método al utilizar REST, debe usar hipermedia e implementar [HATEOAS (hipertexto como motor del estado de la aplicación)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Recursos adicionales

-   **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Control de versiones simplificado de ASP.NET Core RESTful Web API)**
    [*https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **Control de versiones de una API web RESTful**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Versioning, Hypermedia, and REST (Control de versiones, hipermedia y REST)**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Generación de metadatos de descripción de Swagger desde la API web de ASP.NET Core 

[Swagger](https://swagger.io/) es un marco de código abierto de uso común, respaldado por una gran variedad de herramientas que le permite diseñar, compilar, documentar y utilizar las API RESTful. Se está convirtiendo en el estándar para el dominio de metadatos de la descripción de API. Debe incluir los metadatos de descripción de Swagger con cualquier tipo de microservicio, tanto si está controlado por datos como si está controlado por dominios de forma más avanzada (como se explica en la sección siguiente).

El núcleo de Swagger es su especificación, que son los metadatos de descripción de la API en un archivo JSON o YAML. La especificación crea el contrato RESTful para la API, donde se detallan todos sus recursos y operaciones en formatos legibles por máquinas y por humanos, para que se puedan desarrollar, descubrir e integrar de forma sencilla.

La especificación es la base de la especificación OpenAPI (OAS) y se desarrolla en una comunidad abierta, transparente y colaborativa para estandarizar la forma en que se definen las interfaces RESTful.

La especificación define la estructura de descubrimiento de un servicio y la forma de entender sus capacidades. Para obtener más información, incluido un editor web y ejemplos de especificaciones de Swagger de empresas como Spotify, Uber, Slack y Microsoft, consulte el sitio web de Swagger (<https://swagger.io/>).

### <a name="why-use-swagger"></a>¿Por qué usar Swagger?

Las razones principales para generar metadatos de Swagger para las API son las siguientes:

**Capacidad de otros productos de utilizar e integrar las API automáticamente** . Swagger es compatible con docenas de productos y [herramientas comerciales](https://swagger.io/commercial-tools/), así como con muchas [bibliotecas y marcos](https://swagger.io/open-source-integrations/). Microsoft tiene productos y herramientas de alto nivel que pueden utilizar automáticamente API basadas en Swagger, como las siguientes:

-   [AutoRest](https://github.com/Azure/AutoRest). Puede generar automáticamente clases de cliente de .NET para llamar a Swagger. Esta herramienta se puede utilizar desde la interfaz de la línea de comandos y también se integra con Visual Studio para que pueda utilizarse fácilmente desde la interfaz gráfica de usuario.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/). También puede [utilizar e integrar la API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) automáticamente en un flujo de trabajo de Microsoft Flow de alto nivel, aunque no tenga conocimientos de programación.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/). Puede utilizar la API automáticamente desde [aplicaciones móviles PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) creadas con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), aunque no tenga conocimientos de programación.

-   [Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). También puede [utilizar e integrar automáticamente su API en una Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), aunque no tenga conocimientos de programación.

**Capacidad de generar documentación de la API automáticamente**. Al crear API RESTful a gran escala, como aplicaciones complejas basadas en microservicios, tiene que controlar muchos de los puntos de conexión con diferentes modelos de datos diferentes que se utilizan en las cargas de solicitud y respuesta. Tener una documentación adecuada y un explorador de API potente, como se consigue con Swagger, es fundamental para que su API tenga éxito y los desarrolladores la adopten.

Microsoft Flow, PowerApps y Azure Logic Apps utilizan los metadatos de Swagger para aprender a usar las API y conectar con ellas.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Cómo se automatiza la generación de metadatos de la API de Swagger con el paquete NuGet de Swashbuckle

Generar metadatos de Swagger manualmente (en un archivo JSON o YAML) puede resultar muy pesado. Pero puede automatizar la detección de API de servicios ASP.NET Web API mediante el uso del [paquete NuGet de Swashbuckle](http://aka.ms/swashbuckledotnetcore) para generar dinámicamente metadatos de la API de Swagger.

Swashbuckle genera automáticamente metadatos de Swagger para sus proyectos de ASP.NET Web API. Admite proyectos de ASP.NET Core Web API, proyectos tradicionales de ASP.NET Web API y cualquier otro tipo, como la aplicación API de Azure, la aplicación móvil de Azure o los microservicios Azure Service Fabric basados en ASP.NET. También admite API web sencillas implementadas en contenedores, como es el caso de la aplicación de referencia.

Swashbuckle combina el explorador de API y Swagger o [swagger-ui](https://github.com/swagger-api/swagger-ui) para proporcionar una experiencia de detección y documentación increíble a los consumidores de la API. Además de su motor generador de metadatos de Swagger, Swashbuckle también contiene una versión insertada de swagger-ui, que se usará automáticamente cuando se haya instalado Swashbuckle.

Esto significa que puede complementar su API con una bonita interfaz de usuario de descubrimiento para ayudar a los desarrolladores a usar su API. Para ello se requiere una cantidad muy pequeña de código y mantenimiento, puesto que se genera automáticamente, lo que le permite centrarse en la creación de la API. El resultado para el explorador de API se parece a la Figura 8-8.

![](./media/image9.png)

**Figura 8-8**. Explorador de API de Swashbuckle basado en metadatos de Swagger: microservicio del catálogo eShopOnContainers

Pero aquí lo más importante no es el explorador de API. Cuando tenga una API web que se pueda describir en metadatos de Swagger, la API podrá usarse sin problemas desde herramientas basadas en Swagger, incluidos los generadores de código de clase proxy de cliente que pueden tener varias plataformas como destino. Por ejemplo, tal y como se ha mencionado, [AutoRest](https://github.com/Azure/AutoRest) genera automáticamente clases de cliente .NET. Pero también están disponibles herramientas como [swagger-codegen](https://github.com/swagger-api/swagger-codegen), que permiten que se genere automáticamente código de bibliotecas de cliente de API, códigos auxiliares de servidor y documentación.

Actualmente, Swashbuckle consta de dos paquetes de NuGet internos que se engloban en el metapaquete de alto nivel [Swashbuckle.Swashbuckle.AspNetCoreSwaggerGen](https://www.nuget.org/packages/Swashbuckle.AspNetCore/) versión 1.0.0 o una versión posterior para las aplicaciones de ASP.NET Core.

Después de instalar estos paquetes de NuGet en su proyecto de API web, debe configurar Swagger en la clase de inicio, como en el código siguiente:

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

Una vez hecho esto, puede iniciar la aplicación y examinar los siguientes puntos de conexión JSON y de interfaz de usuario de Swagger utilizando direcciones URL como estas:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/
```

Anteriormente, vio la interfaz de usuario generada creada por Swashbuckle para una dirección URL como http://&lt;su-url-raíz&gt;/swagger/ui. En la Figura 8-9 también puede ver cómo puede probar cualquier método de API.

![](./media/image10.png)

**Figura 8-9**. Interfaz de usuario de Swashbuckle poniendo a prueba el método de API de catálogo o elementos

En la Figura 8-10 se muestran los metadatos JSON de Swagger generados a partir del microservicio eShopOnContainers (que es lo que las herramientas usan en segundo plano) al solicitar &lt;su-url-raíz&gt;/swagger/v1/swagger.json utilizando [Postman](https://www.getpostman.com/).

![](./media/image11.png)

**Figura 8-10**. Metadatos JSON de Swagger

Es así de sencillo. Y, como se generan automáticamente, los metadatos de Swagger crecerán cuando agregue más funcionalidad a la API.

### <a name="additional-resources"></a>Recursos adicionales

-   **ASP.NET Web API Help Pages using Swagger (Páginas de ayuda de ASP.NET Web API mediante Swagger)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[Anterior] (microservice-application-design.md) [Siguiente] (multi-container-applications-docker-compose.md)
