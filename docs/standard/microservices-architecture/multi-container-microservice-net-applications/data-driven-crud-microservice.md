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
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Crear un microservicio CRUD simple controladas por datos

Esta sección se describe cómo crear un sencillo que se crea microservicio que lleva a cabo, lectura, actualización y las operaciones de eliminación (CRUD) en un origen de datos.

## <a name="designing-a-simple-crud-microservice"></a>Diseñar un microservicio CRUD simple

Desde un punto de vista de diseño, este tipo de microservicio en contenedores es muy sencillo. Quizás el problema para resolver es simple, o quizás la implementación es sólo una prueba de concepto.

![](./media/image4.png)

**Figura 8-4**. Diseño interno de microservicios CRUD simple

Un ejemplo de este tipo de servicio de la unidad de datos simple es el microservicio de catálogo de la aplicación de ejemplo eShopOnContainers. Este tipo de servicio implementa toda su funcionalidad en un solo proyecto de API Web de ASP.NET Core que incluye las clases para su modelo de datos, su lógica de negocios y su código de acceso a datos. También almacena los datos relacionados en una base de datos en SQL Server en ejecución (como otro contenedor para fines de desarrollo y pruebas), pero también podría ser cualquier host de SQL Server normal, como se muestra en la figura 8-5.

![](./media/image5.png)

**Figura 8-5**. Diseño simple microservicio/CRUD controladas por datos

Cuando está desarrollando este tipo de servicio, solo necesita [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) y una API de acceso a datos o ORM como [Entity Framework Core](https://docs.microsoft.com/ef/core/index). También podría generar [Swagger](http://swagger.io/) automáticamente a través de metadatos [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) para proporcionar una descripción de lo que ofrece el servicio, tal como se describe en la sección siguiente.

Tenga en cuenta que ejecuta un servidor de base de datos como SQL Server dentro de un contenedor de Docker es muy útil para entornos de desarrollo, porque puede hacer que todas las dependencias de las seguridad y se ejecuta sin necesidad de proporcionar una base de datos en la nube o local. Esto resulta muy útil al ejecutando la integración de pruebas. Sin embargo, para entornos de producción, ejecutando un servidor de base de datos en un contenedor no se recomienda, ya que normalmente no se obtiene alta disponibilidad con ese método. En un entorno de producción en Azure, se recomienda que utilice la base de datos de SQL Azure o cualquier otra tecnología de base de datos que puede proporcionar alta disponibilidad y escalabilidad alta. Por ejemplo, para un método NoSQL, puede elegir documentos.

Por último, mediante la edición de los archivos de metadatos de Dockerfile y compose.yml de docker, puede configurar cómo se creará la imagen de este contenedor, la imagen base se utilice, además de diseñar la configuración, como los nombres internos y externos y los puertos TCP. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementar un microservicio CRUD simple con ASP.NET Core

Para implementar un microservicio CRUD simple con .NET Core y Visual Studio, primero debe crear un proyecto de ASP.NET Core Web API simple (ejecutando .NET Core para que pueda ejecutarse en un host Linux Docker), como se muestra en la figura 8-6.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**Figura 8-6**. Crear un proyecto de ASP.NET Core Web API en Visual Studio

Después de crear el proyecto, puede implementar los controladores MVC como lo haría en cualquier otro proyecto de API Web, mediante la API de Entity Framework o de otra API. En el proyecto eShopOnContainers.Catalog.API, puede ver que las dependencias principales de ese microservicio son simplemente ASP.NET Core propio, Entity Framework y Swashbuckle, tal como se muestra en la figura 8-7.

![](./media/image8.PNG)

**Figura 8-7**. Dependencias en un microservicio CRUD Web API simple

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementación de servicios de CRUD Web API con Entity Framework Core

Núcleo de Entity Framework (EF) es una ligera, extensible, y tecnología de acceso de versión entre plataformas de los datos de Entity Framework populares. Núcleo EF es un asignador relacional de objetos (ORM) que permite a los desarrolladores de .NET trabajar con una base de datos mediante objetos. NET.

El catálogo de microservicio usa EF y el proveedor de SQL Server porque su base de datos se está ejecutando en un contenedor con el servidor SQL Server para la imagen de Linux Docker. Sin embargo, la base de datos podría implementarse en cualquier servidor SQL, como Windows local o en la base de datos de SQL Azure. Lo único que debe cambiar es la cadena de conexión en el microservicio de ASP.NET Web API.

#### <a name="add-entity-framework-core-to-your-dependencies"></a>Agregar Entity Framework Core a las dependencias

Puede instalar el paquete de NuGet para el proveedor de base de datos que desea usar, en este caso, SQL Server, desde dentro del IDE de Visual Studio o con la consola de NuGet. Use el siguiente comando:

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>El modelo de datos

Con núcleo de EF, acceso a datos se realiza mediante el uso de un modelo. Un modelo se compone de las clases de entidad y un contexto derivado que representa una sesión con la base de datos, lo que le permite consultar y guardar los datos. Puede generar un modelo de base de datos existente, manualmente un modelo para que coincida con la base de datos de código o usar migraciones de EF para crear una base de datos del modelo (y evolucionan a medida que cambia el modelo con el tiempo). Para el catálogo microservicio, usamos el último enfoque. Puede ver un ejemplo de la clase de entidad CatalogItem en el ejemplo de código siguiente, que es un objeto de CLR Plain Old simple ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) clase de entidad.

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

También necesita un DbContext que representa una sesión con la base de datos. Para el microservicio de catálogo, la clase de CatalogContext se deriva de la clase base de DbContext, tal como se muestra en el ejemplo siguiente:

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

Puede tener código adicional en la implementación de DbContext. Por ejemplo, en la aplicación de ejemplo, tenemos un método OnModelCreating en la clase CatalogContext que rellena automáticamente los datos de ejemplo en la primera vez que intenta obtener acceso a la base de datos. Este método es útil para los datos de demostración. También puede usar el método OnModelCreating para personalizar las asignaciones de entidad del objeto y base de datos con muchos otros [puntos de extensibilidad EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

Puede ver más detalles acerca de OnModelCreating en el [implementar la capa de persistencia de infraestructura con Entity Framework Core](#implementing_infrastructure_persistence) sección más adelante en este libro.

##### <a name="querying-data-from-web-api-controllers"></a>Consultar datos de controladores de API Web

Instancias de las clases de entidad se recuperan normalmente de la base de datos utilizando Language Integrated Query (LINQ), como se muestra en el ejemplo siguiente:

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

##### <a name="saving-data"></a>Guardar datos

Datos es crear, eliminar y modificar en la base de datos con instancias de las clases de entidad. Puede agregar código similar al siguiente codificado de forma rígida ejemplo (datos simulados, en este caso) para los controladores de API Web.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Inserción de dependencias en los controladores de ASP.NET Core y API Web

En ASP.NET Core puede usar inyección de dependencia (DI) desde el principio. No es necesario configurar un contenedor de inversión de Control (IoC) de terceros, aunque se puede conectar el contenedor de IoC preferido en la infraestructura básica de ASP.NET si desea. En este caso, significa que puede insertar directamente el necesario DBContext EF o repositorios adicionales a través del constructor de controlador. En el ejemplo anterior de la clase CatalogController, nos estamos está insertando un objeto de tipo CatalogContext además de otros objetos mediante el constructor CatalogController.

Una configuración importante para configurar en el proyecto de Web API es el registro de la clase DbContext en contenedor de IoC del servicio. Normalmente lo hace en la clase de inicio mediante una llamada a los servicios. Método AddDbContext dentro del método ConfigureServices, tal como se muestra en el ejemplo siguiente:

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

### <a name="additional-resources"></a>Recursos adicionales

-   **Consultar datos**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **Guardar datos**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Las variables entorno y la cadena de conexión base de datos utilizadas por contenedores de Docker

Puede usar la configuración básica de ASP.NET y agregar una propiedad ConnectionString al archivo settings.json tal como se muestra en el ejemplo siguiente:

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

El archivo settings.json puede tener valores predeterminados para la propiedad ConnectionString o para cualquier otra propiedad. Sin embargo, estas propiedades serán reemplazadas por los valores de variables de entorno que especifican en el archivo compose.override.yml docker.

De los archivos compose.yml de docker o compose.override.yml de docker, puede inicializar estas variables de entorno por lo que Docker configurará ellos como variables de entorno de sistema operativo para usted, como se muestra en el siguiente archivo de docker compose.override.yml (la conexión cadena y otras líneas de ajustan en este ejemplo, pero no se ajusta en su propio archivo).

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

Los archivos de compose.yml de docker en el nivel de solución no sólo son más flexibles que los archivos de configuración en el nivel de proyecto o microservicio, pero también más segura. Tenga en cuenta que las imágenes de Docker que se compilación por microservicio no contienen el compose.yml docker archivos, solo los archivos binarios y los archivos de configuración para cada microservicio, incluido el archivo Dockerfile. Pero no se implementa el archivo de docker compose.yml junto con la aplicación; se utiliza solo durante la implementación. Por lo tanto, la colocación de los valores de las variables de entorno en esos archivos docker compose.yml (incluso sin cifrar los valores) es más seguro que colocar esos valores en archivos de configuración de .NET normales que se implementan con el código.

Por último, puede obtener ese valor desde el código mediante la configuración\["ConnectionString"\], tal y como se muestra en el método ConfigureServices de un ejemplo de código anterior.

Sin embargo, para entornos de producción, puede a otras formas de explorador sobre cómo almacenar secretos, como las cadenas de conexión. Por lo general que serán administradas por su orchestrator elegido, como se puede hacer con [Docker Swarm administración de secretos](https://docs.docker.com/engine/swarm/secrets/).

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementar el control de versiones en las API Web de ASP.NET

Medida que cambian los requisitos empresariales, se pueden agregar nuevas colecciones de recursos, pueden cambiar las relaciones entre los recursos y podría modificarse la estructura de los datos de recursos. Una API Web para controlar los requisitos nuevo la actualización es un proceso relativamente sencillo, pero debe tener en cuenta los efectos que tengan dichos cambios en aplicaciones cliente que consumen la API Web. Aunque el desarrollador diseñar e implementar una API Web no tiene control total sobre dicha API, el programador no tiene el mismo grado de control sobre las aplicaciones cliente que podría estar compilado por organizaciones de terceros funciona de forma remota.

Control de versiones permite a una API Web indicar las características y recursos que expone. Una aplicación cliente, a continuación, puede enviar solicitudes a una versión específica de una característica o un recurso. Existen varios enfoques para implementar las versiones:

-   Control de versiones URI

-   Control de versiones de cadena de consulta

-   Control de versiones de encabezado

Cadena de consulta y la versión del URI son las más fáciles de implementar. Control de versiones de encabezado es un enfoque adecuado. Sin embargo, las versiones de encabezado no como explícita y sencilla como control de versiones URI. Dado que las versiones de la dirección URL son la más sencilla y más explícito, la aplicación de ejemplo eShopOnContainers utiliza las versiones URI.

Con las versiones de URI, como se muestra en la aplicación de ejemplo eShopOnContainers, cada vez que modifique la API Web o cambia el esquema de recursos, agregará un número de versión para el URI para cada recurso. URI existentes deben continuar funcionando como antes, devuelven los recursos que se ajustan al esquema que coincide con la versión solicitada.

Como se muestra en el ejemplo de código siguiente, la versión puede establecerse mediante el atributo de ruta en la API Web, lo que hace que la versión explícito en el URI (v1 en este caso).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Este mecanismo de control de versiones es sencillo y depende del servidor de enrutamiento de la solicitud al extremo adecuado. Sin embargo, para un control de versiones más sofisticada y el mejor método si utiliza REST, debe usar hipermedia e implementar [HATEOAS (hipertexto como el estado del motor de aplicación)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Recursos adicionales

-   **Scott Hanselman. Control de versiones ASP.NET Core RESTful Web API facilitan**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **Control de versiones de una API web de REST**

    [*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Control de versiones, hipermedia y REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Generar metadatos de Swagger descripción de la API de Web de ASP.NET Core 

[Swagger](http://swagger.io/) es un marco de código abierto utilizadas respaldado por un gran ecosistema de herramientas que le ayuda a diseño, la compilación, documento y utilizar las API de REST. Se está convirtiendo en el estándar para el dominio de metadatos de descripción de las API. Deben incluir metadatos de descripción de Swagger con cualquier tipo de microservicio, controlada por datos microservicios o más avanzados microservicios controlada por el dominio (como se explica en la sección siguiente).

El núcleo de Swagger es la especificación de Swagger, que es la API de metadatos de descripción en un archivo JSON o YAML. La especificación crea el contrato RESTful de la API, que detalla todas sus recursos y operaciones en ambos humanos y machine readable formato para desarrollar fácilmente, detección e integración.

La especificación es la base de la OpenAPI especificación (analizador en tiempo real) y se desarrolla en una comunidad abierta, transparente y colaboración para estandarizar la forma en que se definen las interfaces RESTful.

La especificación define la estructura de cómo se puede detectar un servicio y cómo entienden sus capacidades. Para obtener más información, incluido un editor de web y ejemplos de especificaciones de Swagger de empresas como Spotify, la misma, la demora y Microsoft, vea el sitio de Swagger (<http://swagger.io>).

### <a name="why-use-swagger"></a>¿Por qué usar Swagger?

Las razones principales para generar metadatos de Swagger de las API son las siguientes:

**Capacidad de otros productos automáticamente consumir e integrar las API**. Docenas de productos y [herramientas comercial](http://swagger.io/commercial-tools/) y muchos [bibliotecas y marcos](http://swagger.io/open-source-integrations/) admite Swagger. Microsoft tiene productos de alto nivel y herramientas que automáticamente se pueden utilizar la API basadas en Swagger, como las siguientes:

-   [AutoRest](https://github.com/Azure/AutoRest). Puede generar automáticamente las clases de cliente de .NET para llamar a Swagger. Esto

-   herramienta que puede usarse desde la CLI y también se integra con Visual Studio para facilitar su uso a través de la interfaz gráfica de usuario.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/). También puede automáticamente [utilizar e integrar su API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) en un flujo de trabajo de Microsoft Flow alto nivel, y no tienen ninguna programación destrezas necesarias.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/). Automáticamente se puede utilizar la API de [aplicaciones móviles PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) compiladas con [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), sin conocimientos de programación necesarios.

-   [Aplicaciones de servicio de aplicaciones de Azure lógicas](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). También puede automáticamente [utilizar e integrar su API en una aplicación de lógica de servicio de aplicación de Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), sin conocimientos de programación necesarios.

**Capacidad de generar automáticamente la documentación de la API**. Al crear las API RESTful a gran escala, como aplicaciones complejas de microservicio, necesario controlar muchos de los puntos de conexión con los modelos de datos diferentes utilizados en las cargas de solicitud y respuesta. Tener una documentación adecuada y con un explorador de API sólido, tal y como se obtienen con Swagger, son clave para el éxito de la API y la adopción por los desarrolladores.

Metadatos de swagger están la lógica de aplicaciones de Azure, PowerApps y Microsoft Flow usan para aprender a usar las API y conectarse a ellos.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Cómo automatizar la generación de metadatos de Swagger de API con el paquete de Swashbuckle NuGet

Generar metadatos de Swagger manualmente (en un archivo JSON o YAML) puede resultar una tarea tediosa. Sin embargo, puede automatizar la detección de API de servicios de API Web de ASP.NET mediante el uso de la [paquete Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) generar dinámicamente los metadatos de Swagger API.

Swashbuckle genera automáticamente los metadatos de Swagger para los proyectos de ASP.NET Web API. Admite proyectos API Web de ASP.NET Core y ASP.NET Web API tradicionales y cualquier otro tipo, como aplicación de API de Azure, aplicación móvil de Azure, microservicios Azure Service Fabric basado en ASP.NET. También admite simple API Web implementados en los contenedores, como en para la aplicación de referencia.

Swashbuckle combina el Explorador de API y Swagger o [swagger la interfaz de usuario](https://github.com/swagger-api/swagger-ui) para proporcionar una detección completo y la documentación experimentan para los consumidores de API. Además de su motor de generador de metadatos de Swagger, Swashbuckle también contiene una versión incrustada de swagger de interfaz de usuario, que se usará automáticamente una cuando se ha instalado Swashbuckle.

Esto significa que pueden complementar su API con una interfaz de usuario para ayudar a los desarrolladores usar la API de detección "nice". Requiere una cantidad muy pequeña de código y mantenimiento dado que se genera automáticamente, lo que le permite centrarse en la creación de la API. El resultado para el Explorador de API tiene un aspecto como la figura 8-8.

![](./media/image9.png)

**Figura 8-8**. Explorador de la API de Swashbuckle basándose en los metadatos de Swagger: eShopOnContainers microservicio de catálogo

El Explorador de API no es lo más importante aquí. Una vez que tenga una API Web que se pueden describir en metadatos de Swagger, la API puede usarse sin problemas de herramientas basadas en Swagger, incluidos los generadores de código de clase de proxy de cliente que pueden tener como destino varias plataformas. Por ejemplo, tal y como se ha mencionado, [AutoRest](https://github.com/Azure/AutoRest) genera automáticamente las clases de cliente. NET. Pero, como herramientas adicionales [swagger codegen](https://github.com/swagger-api/swagger-codegen) también están disponibles, lo que permite la generación de código de cliente de API de bibliotecas, el código auxiliar de servidor y la documentación automáticamente.

Actualmente, Swashbuckle consta de dos paquetes de NuGet: Swashbuckle.SwaggerGen y Swashbuckle.SwaggerUi. El primero proporciona funcionalidad para generar uno o varios documentos de Swagger directamente desde su implementación de la API y expóngalos como extremos JSON. El segundo, proporciona una versión incrustada de la herramienta de swagger de interfaz de usuario que se pueden usar su aplicación y gracias a los documentos de Swagger generados para describir su API. Sin embargo, las versiones más recientes de Swashbuckle ajustan con el metapackage Swashbuckle.AspNetCore.

Tenga en cuenta que para los proyectos de .NET Core Web API, debe usar [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) versión 1.0.0 o una versión posterior.

Después de instalar estos paquetes de NuGet en el proyecto de API Web, debe configurar Swagger en la clase de inicio, como en el código siguiente:

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

Una vez hecho esto, se puede iniciar la aplicación y examinar los siguientes extremos de Swagger JSON y la interfaz de usuario con las direcciones URL como estas:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

Anteriormente, vio la interfaz de usuario generado creado por Swashbuckle para una dirección URL como http://&lt;la dirección url raíz &gt; /swagger/interfaz de usuario. En la figura 8-9 también puede ver cómo puede probar cualquier método de API.

![](./media/image10.png)

**Figura 8-9**. UI Swashbuckle probar el método de API de elementos del catálogo

Figura 8-10 se muestran los metadatos de Swagger JSON generado a partir de la microservicio eShopOnContainers (que es lo que las herramientas usan debajo) al solicitar &lt;la dirección url raíz&gt;/swagger/v1/swagger.json utilizando [Postman](https://www.getpostman.com/).

![](./media/image11.png)

**Figura 8-10**. Metadatos de swagger JSON

Es así de sencillo. Y dado que se genera automáticamente, los metadatos de Swagger crecerá al agregar más funcionalidad a su API.

### <a name="additional-resources"></a>Recursos adicionales

-   **ASP.NET Web API páginas de ayuda mediante Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[Anterior] (microservicio-aplicaciones-design.md) [siguiente] (multi-container-aplicaciones-docker-compose.md)
