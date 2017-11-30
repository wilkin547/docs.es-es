---
title: Trabajar con datos en aplicaciones de ASP.NET Core
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | trabajar con datos en asp"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: bcb8f7bbfa83db9c86cd1278a89750b9f02061d9
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a>Trabajar con datos en aplicaciones ASP.NET Core

> "Los datos es algo muy valioso y duran más de los sistemas por sí mismos."

Tim Berners-Lee

## <a name="summary"></a>Resumen

Acceso a datos es una parte importante de la mayoría de las aplicaciones de software. ASP.NET Core admite una variedad de opciones de acceso a datos, incluido Entity Framework Core (y también Entity Framework 6) y pueden funcionar con cualquier acceso de datos de .NET framework. La elección de los cuales de acceso a datos framework se utilizará depende de las necesidades de la aplicación. La abstracción de estas opciones de los proyectos ApplicationCore e interfaz de usuario y encapsular los detalles de implementación de infraestructura, ayuda a producir software de acoplamiento flexible, comprobable.

## <a name="entity-framework-core-for-relational-databases"></a>Entity Framework Core (para bases de datos relacionales)

Si va a escribir una nueva aplicación de ASP.NET Core que necesita para trabajar con datos relacionales, Entity Framework Core (EF núcleos) es la manera recomendada para la aplicación tener acceso a sus datos. Núcleo EF es un asignador relacional de objetos (O/RM) que permite a los desarrolladores de .NET conservar los objetos a y desde un origen de datos. Elimina la necesidad para la mayoría de los desarrolladores normalmente tendría que escribir el código de acceso de datos. Al igual que ASP.NET Core, Core EF ha vuelto a escribir desde el principio hasta aplicaciones multiplataforma modular de soporte técnico. Agregar a la aplicación como un paquete de NuGet, configurarlo en Inicio y solicitar a través de la inyección de dependencia siempre que lo necesite.

Para usar EF núcleo con una base de datos de SQL Server, ejecute el siguiente comando CLI de dotnet:

dotnet Agregar paquete Microsoft.EntityFrameworkCore.SqlServer

Para agregar compatibilidad para un origen de datos InMemory, para las pruebas:

dotnet Agregar paquete Microsoft.EntityFrameworkCore.InMemory

### <a name="the-dbcontext"></a>DbContext

Para trabajar con EF Core, necesita una subclase de DbContext. Esta clase contiene propiedades que representan las colecciones de las entidades de con que la aplicación funcionará. El ejemplo de eShopOnWeb incluye una CatalogContext con colecciones de elementos, las marcas y los tipos:

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

Su DbContext debe tener un constructor que acepta DbContextOptions y pasar este argumento para el constructor DbContext base. Tenga en cuenta que si tiene solo un DbContext en la aplicación, puede pasar una instancia de DbContextOptions, pero si tiene más de un debe usar el genérico DbContextOptions<T> tipo, que se pasa en el tipo de DbContext como el parámetro genérico.

### <a name="configuring-ef-core"></a>Configuración básica EF

En la aplicación ASP.NET Core, configurará normalmente EF principales en el método ConfigureServices. Núcleo EF usa un DbContextOptionsBuilder, que admite varios métodos de extensión útil para optimizar su configuración. Para configurar CatalogContext para utilizar una base de datos de SQL Server con una cadena de conexión definida en la configuración, debe agregar el código siguiente en ConfigureServices:

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

Para usar la base de datos en memoria:

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

Una vez instalado el núcleo de EF, crea un tipo de elemento secundario de DbContext y configurado en ConfigureServices, está listo para usar EF Core. Puede solicitar una instancia de su tipo de DbContext en cualquier servicio que lo necesite y empezar a trabajar con las entidades persistentes con LINQ como si fueran simplemente en una colección. Núcleo EF realiza el trabajo de la traducción de las expresiones de LINQ a consultas SQL para almacenar y recuperar los datos.

Puede ver las consultas que se está ejecutando el núcleo de EF configurando un registrador y garantizar el nivel se establece en al menos información, tal como se muestra en la figura 8-1.

![](./media/image8-1.png)

Consultas de registro principal de EF figura 8-1 en la consola

### <a name="fetching-and-storing-data"></a>Capturar y almacenar los datos

Para recuperar datos de EF Core, tener acceso a la propiedad adecuada y usar LINQ para filtrar el resultado. También puede usar LINQ para realizar la proyección, transformar el resultado de un tipo a otro. En el ejemplo siguiente se recuperaría CatalogBrands, ordenados por nombre, filtrados por su propiedad Enabled y proyectan en un tipo SelectListItem:

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

Es importante en el ejemplo anterior para agregar la llamada a ToListAsync para ejecutar la consulta inmediatamente. En caso contrario, la instrucción asignará un tipo IQueryable<SelectListItem> a brandItems, que no se ejecutará hasta que se enumere. Hay ventajas y desventajas para devolver resultados de IQueryable de métodos. Permite que la consulta que EF Core construirá para modificarse, pero también pueden generan errores que solo se producen en tiempo de ejecución, si las operaciones se agregan a la consulta que no puede traducir EF Core. Es generalmente más segura pasar los filtros en el método que realiza el acceso a datos, y devuelven una colección en memoria (por ejemplo, una lista de<T>) como resultado.

Núcleo EF realiza un seguimiento de cambios en las entidades que se recupera de la persistencia. Para guardar los cambios en una entidad realiza un seguimiento, llama simplemente al método SaveChanges en DbContext, asegurándose de que es la misma instancia de DbContext que se usó para capturar la entidad. Adición y eliminación de entidades son directamente en la propiedad DbSet adecuada, nuevo con una llamada a SaveChanges para ejecutar los comandos de base de datos. En el ejemplo siguiente se muestra cómo agregar, actualizar y quitar entidades de persistencia.

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

EF Core es compatible con ambos sincrónica y asincrónica de métodos para capturar y guardar. En las aplicaciones web, se recomienda utilizar el patrón de async y await con los métodos asincrónicos, para que los subprocesos de servidor web no se bloquean mientras se espera a que finalicen operaciones de acceso a datos.

### <a name="fetching-related-data"></a>Capturar los datos relacionados

Cuando el núcleo de EF recupera entidades, rellena todas las propiedades que se almacenan directamente a esa entidad en la base de datos. Propiedades de navegación, como las listas de entidades relacionadas, no se llenan y puede tener su valor establecido en null. Esto garantiza que EF Core está no obteniendo más datos que es necesario, que es especialmente importante para las aplicaciones web, que deben procesar las solicitudes rápidamente y se devuelven respuestas de una manera eficaz. Para incluir relaciones con una entidad con *carga diligente*, especifique la propiedad mediante el método de extensión de inclusión en la consulta, como se muestra:

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

Puede incluir varias relaciones, y también pueden incluir relaciones secundarias mediante ThenInclude. Núcleo EF ejecutará una sola consulta para recuperar el conjunto resultante de entidades.

Otra opción para cargar los datos relacionados es usar *carga explícita*. Carga explícita permite cargar datos adicionales en una entidad que ya se han recuperado. Puesto que esto implica una solicitud independiente a la base de datos, no se recomienda para las aplicaciones web, que se deben minimizar el número de la base de datos de ida y vuelta realizados por solicitud.

*Carga diferida* es una característica que se carga automáticamente los datos relacionados tal y como se hace referencia a la aplicación. Actualmente no es compatible con EF Core, pero como con carga explícita normalmente se debe deshabilitar para aplicaciones web.

### <a name="resilient-connections"></a>Conexiones resistentes

Recursos externos como bases de datos SQL en ocasiones pueden ser no está disponible. En los casos de falta de disponibilidad temporal, las aplicaciones pueden utilizar lógica de reintento para evitar que se genere una excepción. Esta técnica se conoce normalmente como *resistencia de conexión*. Puede implementar su [propio reintento con retroceso exponencial](https://docs.microsoft.com/azure/architecture/patterns/retry) técnica intentando reintento con un tiempo de espera aumenta exponencialmente, hasta que se ha alcanzado un número máximo de reintentos. Esta técnica adopta el hecho de que los recursos de nube no de vez en cuando estén disponibles durante breves períodos de tiempo, que se produjo un error de algunas solicitudes.

Base de datos de SQL Azure, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna. Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si desea tener conexiones de núcleo de EF resistentes.

Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite resistentes conexiones de SQL que se vuelve a intentar si se produce un error en la conexión.

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

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Estrategias de ejecución y las transacciones explícitas mediante BeginTransaction y varios DbContexts 
  
  Cuando reintentos están habilitados en las conexiones de núcleo de EF, cada operación que se realiza mediante EF principal se convierte en su propia operación reintentable. Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.
  
  Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad, todo dentro de la transacción se revierte si se produce un error. Verá una excepción similar al siguiente si intenta ejecutar esa transacción cuando se utiliza una estrategia de ejecución de EF (directiva de reintentos) e incluye varias SaveChanges desde varios DbContexts en ella.

System.InvalidOperationException: La estrategia de ejecución configurada 'SqlServerRetryingExecutionStrategy' no es compatible con las transacciones iniciadas por el usuario. Utilice la estrategia de ejecución devuelta por 'DbContext.Database.CreateExecutionStrategy()' para ejecutar todas las operaciones en la transacción como una unidad reintentable.

La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa todos los elementos que se debe ejecutar. Si se produce un error transitorio, la estrategia de ejecución invoca al delegado de nuevo. El código siguiente muestra cómo implementar este enfoque:

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

Es el primer DbContext el \_catalogContext y el segundo DbContext está dentro de la \_integrationEventLogService objeto. Por último, la confirmación sería acción realiza varias DbContexts y el uso de una estrategia de ejecución de EF.

> ### <a name="references--entity-framework-core"></a>Referencias: Entity Framework Core
> - **Documentos EF básicos**  
> <https://docs.Microsoft.com/EF/>
> - **EF principal: Datos relacionados**  
> <https://docs.Microsoft.com/EF/Core/Querying/Related-Data>
> - **Evite las entidades de la carga diferida de las aplicaciones de ASPNET**  
> <http://ardalis.com/AVOID-Lazy-Loading-Entities-in-ASP-NET-Applications>

## <a name="ef-core-or-micro-orm"></a>¿Núcleo EF o micro-ORM?

Aunque el núcleo de EF es una excelente opción para administrar la persistencia y en su mayor parte encapsula los detalles de base de datos de los desarrolladores de aplicaciones, no es la única opción. Otra alternativa de código abierto populares es [Dapper](https://github.com/StackExchange/Dapper), un micro-ORM como los denominados. Un micro-ORM es una ligera, menos completa herramienta para la asignación de objetos a las estructuras de datos. En el caso de Dapper, su diseño de objetivos de centran en el rendimiento, en lugar de encapsular totalmente subyacente la consulta se utiliza para recuperar y actualizar datos. Dado que no abstracta SQL del programador, Dapper es "más cercano para el sistema operativo" y permite a los desarrolladores escribir exactamente las consultas que desean usar para un determinado de datos tener acceso a la operación.

Núcleo EF tiene dos características importantes proporciona separarlo de Dapper, pero también se agregue a su sobrecarga de rendimiento. La primera es la traducción de expresiones LINQ a SQL. Las traducciones se almacenan en caché, pero aún así hay una sobrecarga en la realización de la primera vez. El segundo es el seguimiento de cambios en las entidades (de modo que se pueden generar instrucciones de actualización eficaz). Este comportamiento puede estar desactivada para consultas específicas mediante la extensión de AsNotTracking. Núcleo EF también genera consultas SQL que suelen ser muy eficaces y en cualquier caso absolutamente aceptable desde la perspectiva del rendimiento, pero si necesita un preciso control sobre la consulta precisa que se ejecute, se puede pasar en SQL personalizada (o ejecutar un procedimiento almacenado) usan EF Principales, demasiado. En este caso, sigue Dapper supera EF Core, pero solo ligeramente. Presenta Julie Lerman algunos datos de rendimiento en ella pueden artículo de MSDN de 2016 [Dapper, Entity Framework y aplicaciones híbridas](https://msdn.microsoft.com/magazine/mt703432.aspx). Datos de pruebas comparativas de rendimiento adicionales para una amplia variedad de métodos de acceso de datos pueden encontrarse en [el sitio Dapper](https://github.com/StackExchange/Dapper).

Para ver cómo la sintaxis de Dapper varía en función del núcleo de EF, tenga en cuenta estas dos versiones del mismo método para recuperar una lista de elementos:

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

Si tiene que generar gráficos de objetos más complejos con Dapper, debe escribir las consultas asociadas (en lugar de agregar un archivo de inclusión como lo haría en EF Core). Esto se admite a través de una serie de sintaxis, incluida una característica denominada asignación múltiple que le permite asignar filas individuales a varios objetos asignados. Por ejemplo, dada una clase Post con un propietario de la propiedad de tipo de usuario, el código SQL siguiente devuelve todos los datos necesarios:

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

Cada fila devuelta incluye los datos de usuario y Post. Dado que los datos de usuario deben asociarse a los datos de entrada a través de su propiedad de propietario, se utiliza la función siguiente:

```csharp
(post, user) => { post.Owner = user; return post; }
```

La lista de código completa para devolver una colección de entradas con su propiedad de propietario que se rellena con los datos de usuario asociado sería:

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

Dado que ofrece menos encapsulación, Dapper requiere que los programadores podrán obtener más información acerca de cómo se almacenan sus datos, cómo consultar de forma eficaz y escribir más código para capturarlo. Cuando se cambia el modelo, en lugar de simplemente crear una nueva migración (otra característica de EF Core) o actualizar la información de asignación en una posición en un DbContext, deben actualizarse todas las consultas que se ve afectada. Estas consultas tienen no garantías en tiempo de compilación, por lo que pueden dividir en tiempo de ejecución en respuesta a los cambios a la base de datos, lo más difíciles de detectar rápidamente los errores o el modelo. A cambio de estos inconvenientes, Dapper ofrece un rendimiento extremadamente rápido.

Para la mayoría de las aplicaciones y la mayoría de las partes de casi todas las aplicaciones, EF Core ofrece un rendimiento aceptable. Por lo tanto, sus ventajas de productividad para desarrolladores suelen superan a su sobrecarga de rendimiento. Para las consultas que pueden beneficiarse del almacenamiento en caché, solo se puede ejecutar la consulta real sea irrelevante de diferencias de rendimiento de consultas de un pequeño porcentaje de los casos, realizar relativamente pequeño.

## <a name="sql-or-nosql"></a>SQL o NoSQL

Tradicionalmente, las bases de datos relacional como SQL Server han dominado marketplace para el almacenamiento de datos persistentes, pero no son la única solución disponible. Al igual que las bases de datos NoSQL [MongoDB](https://www.mongodb.com/what-is-mongodb) ofrecer un enfoque diferente para almacenar los objetos. En lugar de asignar objetos a las tablas y filas, otra opción es serializar el objeto gráfico completo y almacena el resultado. Las ventajas de este enfoque, al menos inicialmente, están mayor simplicidad y rendimiento. Es ciertamente más simple almacenar un objeto serializado único con una clave que al descomponer el objeto en muchas tablas con relaciones y actualización y las filas que pueden haber cambiado desde la último el objeto se recuperan de la base de datos. Del mismo modo, la obtención y deserializar un objeto único de un almacén basado en clave suele ser mucho más rápida y sencilla que combinaciones complejas o varias consultas de base de datos necesarias para crear completamente el mismo objeto de base de datos relacional. La falta de bloqueos de transacciones o de un esquema fijo también hace que las bases de datos NoSQL muy sensibles al escalar entre varias máquinas, compatibilidad con grandes conjuntos de datos.

Por otro lado, las bases de datos NoSQL (como normalmente se denominan) tienen sus desventajas. Bases de datos relacionales use normalización para exigir la coherencia y evitar la duplicación de datos. Esto reduce el tamaño total de la base de datos y garantiza que las actualizaciones a los datos compartidos están disponibles inmediatamente a lo largo de la base de datos. En una base de datos relacional, una tabla de direcciones puede referencia a una tabla de país con el identificador, tal que si se cambia el nombre de un país, los registros de direcciones se beneficiarían de la actualización sin ellos mismos tener que actualizarse. Sin embargo, en una base de datos NoSQL, dirección y su país asociado pueden serializarse como parte de muchos objetos almacenados. Una actualización en un nombre de país requeriría todos esos objetos actualizarse, en lugar de una sola fila. Bases de datos relacionales también pueden asegurar la integridad relacional aplicando reglas, como claves externas. Normalmente, las bases de datos NoSQL no ofrecen estas restricciones en sus datos.

Otro complejidad NoSQL deben ocuparse de las bases de datos es control de versiones. Cuando cambian las propiedades de un objeto, puede no ser capaz de deserializar en las versiones anteriores que se almacenaron. Por lo tanto, todos los objetos existentes que tengan una versión (anterior) serializada del objeto deben actualizarse para que se ajuste a su esquema de nuevo. Esto no es conceptualmente diferente de una base de datos relacional, que cambia el esquema a veces requieren secuencias de comandos de actualización o asignación de actualizaciones. Sin embargo, el número de entradas que se debe modificar suele ser mucho mayor en el enfoque de NoSQL, porque no hay más de duplicación de datos.

Es posible en las bases de datos NoSQL para almacenar varias versiones de objetos, no admiten bases de datos relacionales de esquema fijo algo normalmente. Sin embargo, en este caso el código de aplicación deberá tener en cuenta la existencia de versiones anteriores de objetos, la adición de complejidad adicional.

Las bases de datos NoSQL normalmente no exigir [ACID](http://en.wikipedia.org/wiki/ACID), lo que significa que tienen ventajas de rendimiento y escalabilidad a través de bases de datos relacionales. Son adecuadas para conjuntos de datos muy grandes y los objetos que no son adecuados para el almacenamiento en las estructuras de tabla normalizada. No hay ninguna razón para una sola aplicación no puede aprovechar las ventajas de ambos relacional y bases de datos NoSQL, con cada uno sea mejor adecuado.

## <a name="azure-documentdb"></a>Documentos de Azure

Documentos de Azure es un servicio de base de datos NoSQL completamente administrado que ofrece el almacenamiento de datos de esquema en la nube. Documentos se crean para rendimiento rápido y predecible, la alta disponibilidad, la escala elástica y la distribución global. A pesar de ser una base de datos NoSQL, los desarrolladores pueden usar enriquecidas y familiar capacidades de consulta SQL sobre datos JSON. Todos los recursos de documentos se almacenan como documentos JSON. Los recursos se administran como *elementos*, que son documentos que contiene los metadatos, y *fuentes*, que son colecciones de elementos. Figura 8-2 muestra la relación entre los diferentes recursos.


![La relación jerárquica entre los recursos en DocumentDB, una base de datos NoSQL JSON](./media/image8-2.png)

**Figura 8-2.** Organización de recursos de DocumentDB.

El lenguaje de consulta de documentos es una interfaz sencilla pero eficaz para consultar los documentos JSON. El lenguaje admite un subconjunto de la gramática de ANSI SQL y agrega integración profunda de objeto JavaScript, matrices, la construcción de objetos y la invocación de función.

**Referencias a documentos**

-   Introduction\ de documentos
    <https://docs.Microsoft.com/Azure/documentdb/documentdb-Introduction>

## <a name="other-persistence-options"></a>Otras opciones de persistencia

Además relacionales y NoSQL opciones de almacenamiento, aplicaciones de ASP.NET Core pueden utilizar el almacenamiento de Azure para almacenar una variedad de formatos de datos y archivos de forma escalable y basada en la nube. Almacenamiento de Azure es escalable de forma masiva, para que pueda empezar a almacenar pequeñas cantidades de datos y la escala hasta almacenar cientos o terabytes si así lo requiere la aplicación. Almacenamiento de Azure admite cuatro tipos de datos:

-   Almacenamiento de blobs para almacenamiento binario, que también se denomina almacenamiento de objetos o texto no estructurado.

-   Almacenamiento de tablas para conjuntos de datos estructurados, accesible a través de las claves de fila.

-   Almacenamiento de cola para la mensajería de confianza basada en cola.

-   Almacenamiento de archivos para el acceso a archivos compartidos entre máquinas virtuales de Azure y aplicaciones locales.

**Referencias: almacenamiento de Azure**

-   Introduction\ de almacenamiento de Azure
    <https://docs.Microsoft.com/Azure/Storage/Storage-Introduction>

## <a name="caching"></a>Almacenamiento en memoria caché

En las aplicaciones web, cada solicitud web se debe completar en el menor tiempo posible. Una manera de conseguirlo es limitar el número de llamadas externas, que el servidor debe realizar para completar la solicitud. Almacenamiento en caché requiere almacenar una copia de datos en el servidor (u otros del almacén de datos que es más fácil consultar el origen de los datos de). Aplicaciones Web y especialmente las aplicaciones web tradicionales no SPA, necesitan generar la interfaz de usuario completo con cada solicitud. Con frecuencia, esto implica realizar muchas de las mismas consultas de base de datos varias veces de solicitud de un usuario a la siguiente. En la mayoría de los casos, estos datos en contadas ocasiones, cambian de modo que no hay motivos para realizar dicha solicitud constantemente desde la base de datos. ASP.NET Core es compatible con las respuestas en caché, para almacenar en caché páginas completas y almacenamiento en caché de datos, que admite el comportamiento de almacenamiento en caché más granular.

Al implementar el almacenamiento en caché, es importante tener en la separación de la cuenta de problemas. No implementa la lógica de almacenamiento en caché en la lógica de acceso a datos o en la interfaz de usuario. En su lugar, encapsular el almacenamiento en caché en sus propias clases y usar la configuración para administrar su comportamiento. Esto sigue los principios de responsabilidad única y abierto o cerrado y le resultará más fácil de administrar cómo usar almacenamiento en caché en la aplicación cuando crece.

### <a name="aspnet-core-response-caching"></a>Las respuestas en caché de ASP.NET Core

ASP.NET Core admite dos niveles de almacenamiento en caché de respuesta. El primer nivel no almacena en caché nada en el servidor, pero agrega encabezados HTTP que indicar a los clientes y servidores proxy a la memoria caché las respuestas. Esto se implementa mediante la adición del atributo ResponseCache a los controladores individuales o acciones:

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

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

El Middleware de almacenamiento en caché de respuesta automáticamente almacenará en memoria caché las respuestas basándose en un conjunto de condiciones que puede personalizar. De forma predeterminada, se almacenan en caché respuestas sólo 200 (Aceptar) solicitadas a través de métodos GET o HEAD. Además, las solicitudes deben tener una respuesta con un valor de Cache-Control: encabezado público y no puede incluir encabezados de autorización o Set-Cookie. Vea una [lista completa de las condiciones de almacenamiento en caché utilizado por la respuesta de almacenamiento en caché middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).

### <a name="data-caching"></a>Almacenamiento en caché de datos

En lugar de (o además de) el almacenamiento en caché las respuestas web completo, puede almacenar en caché los resultados de consultas de datos individuales. Para ello, puede usar en la memoria caché en el servidor web o usar [una memoria caché distribuida](https://docs.microsoft.com/aspnet/core/performance/caching/distributed). En esta sección se muestra cómo implementar en almacenamiento en memoria caché.

Agregar compatibilidad para memoria (o distribuida) almacenamiento en caché en ConfigureServices:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

Asegúrese de agregar el paquete de Microsoft.Extensions.Caching.Memory NuGet así.

Una vez que haya agregado el servicio, solicitar IMemoryCache a través de la inyección de dependencia siempre que necesite obtener acceso a la memoria caché. En este ejemplo, el CachedCatalogService está usando el patrón de diseño de Proxy (o decorador), proporcionando una implementación alternativa de ICatalogService que controla el acceso a (o agrega comportamiento a) la implementación de CatalogService subyacente.

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
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
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
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

Para configurar la aplicación para usar la versión en caché del servicio, pero seguirá permitiendo el servicio para obtener la instancia de CatalogService que necesita en su constructor, debe agregar lo siguiente en ConfigureServices:

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

Teniendo esto en su lugar, las llamadas de base de datos para capturar los datos del catálogo sólo se realizará una vez por minuto, en lugar de en cada solicitud. Según el tráfico al sitio, esto puede tener un impacto muy significativo en el número de consultas realizadas en la base de datos y el tiempo de carga de página promedio de la página principal que actualmente depende de las tres de las consultas expuestas por este servicio.

Es un problema que surge cuando se implementa el almacenamiento en caché *datos obsoletos* : es decir, datos que han cambiado en el origen, pero una versión obsoleta permanecen en la memoria caché. Una manera sencilla para mitigar este problema es utilizar duraciones de caché pequeño, ya que para una aplicación ocupada hay limitado ventaja adicional para extender la longitud de los datos en caché. Por ejemplo, considere la posibilidad de una página que realiza una consulta de base de datos única, y se solicita 10 veces por segundo. Si esta página se almacena en caché durante un minuto, se producirá un error en el número de consultas de base de datos realizadas por minuto para quitar de 600 en 1, una reducción del 99,8%. Si en su lugar, la duración de la caché se ha realizado una hora, la reducción general sería 99,997%, pero ahora la antigüedad de probabilidad y potencial de datos obsoletos son ambos aumentados considerablemente.

Otro enfoque consiste en Quitar proactivamente las entradas de caché cuando se actualizan los datos que contienen. Cualquier entrada individual puede quitarse si se conoce su clave:

```csharp
_cache.Remove(cacheKey);
```

Si la aplicación expone funcionalidad para actualizar las entradas que almacena en caché, puede quitar las entradas de caché correspondiente en el código que realiza las actualizaciones. En ocasiones puede haber varias entradas diferentes que dependen de un determinado conjunto de datos. En ese caso, puede ser útil crear las dependencias existentes entre las entradas de caché, mediante el uso de un CancellationChangeToken. Con un CancellationChangeToken puede expirar varias entradas de caché a la vez si se cancela el token.

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

>[!div class="step-by-step"]
[Anterior] (develop-asp-net-core-mvc-apps.md) [siguiente] (test-asp-net-core-mvc-apps.md)
