---
title: Acceso y administración de datos
description: Obtenga información sobre cómo obtener acceso a los datos y controlarlos en formularios Web Forms de ASP.NET y Blazor .
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 09/08/2020
ms.openlocfilehash: 84e12f9890351fa46cd7ed0ee31db449f3c55e59
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515857"
---
# <a name="work-with-data"></a><span data-ttu-id="96bd2-103">Trabajar con datos</span><span class="sxs-lookup"><span data-stu-id="96bd2-103">Work with data</span></span>

<span data-ttu-id="96bd2-104">El acceso a datos es la red troncal de una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="96bd2-104">Data access is the backbone of an ASP.NET Web Forms app.</span></span> <span data-ttu-id="96bd2-105">Si va a crear formularios para la web, ¿qué ocurre con los datos?</span><span class="sxs-lookup"><span data-stu-id="96bd2-105">If you're building forms for the web, what happens to that data?</span></span> <span data-ttu-id="96bd2-106">Con los formularios Web Forms, había varias técnicas de acceso a datos que podría usar para interactuar con una base de datos:</span><span class="sxs-lookup"><span data-stu-id="96bd2-106">With Web Forms, there were multiple data access techniques you could use to interact with a database:</span></span>

- <span data-ttu-id="96bd2-107">Orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="96bd2-107">Data Sources</span></span>
- <span data-ttu-id="96bd2-108">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="96bd2-108">ADO.NET</span></span>
- <span data-ttu-id="96bd2-109">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="96bd2-109">Entity Framework</span></span>

<span data-ttu-id="96bd2-110">Los orígenes de datos eran controles que podía colocar en una página de formularios Web Forms y configurarlos como otros controles.</span><span class="sxs-lookup"><span data-stu-id="96bd2-110">Data Sources were controls that you could place on a Web Forms page and configure like other controls.</span></span> <span data-ttu-id="96bd2-111">Visual Studio proporciona un conjunto descriptivo de cuadros de diálogo para configurar y enlazar los controles a las páginas de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="96bd2-111">Visual Studio provided a friendly set of dialogs to configure and bind the controls to your Web Forms pages.</span></span> <span data-ttu-id="96bd2-112">Los desarrolladores que disfrutan de un enfoque de "código bajo" o "sin código" prefieren esta técnica cuando se lanzaron por primera vez los formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="96bd2-112">Developers who enjoy a "low code" or "no code" approach preferred this technique when Web Forms was first released.</span></span>

![Orígenes de datos](media/data/datasources.png)

<span data-ttu-id="96bd2-114">ADO.NET es el enfoque de bajo nivel para interactuar con una base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-114">ADO.NET is the low-level approach to interacting with a database.</span></span> <span data-ttu-id="96bd2-115">Las aplicaciones pueden crear una conexión a la base de datos con comandos, conjuntos de registros y conjuntos de datos para interactuar.</span><span class="sxs-lookup"><span data-stu-id="96bd2-115">Your apps could create a connection to the database with Commands, Recordsets, and Datasets for interacting.</span></span> <span data-ttu-id="96bd2-116">Los resultados se pueden enlazar a los campos de la pantalla sin mucho código.</span><span class="sxs-lookup"><span data-stu-id="96bd2-116">The results could then be bound to fields on screen without much code.</span></span> <span data-ttu-id="96bd2-117">El inconveniente de este enfoque era que cada conjunto de objetos ADO.NET ( `Connection` , `Command` y `Recordset` ) se enlazó a las bibliotecas proporcionadas por un proveedor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-117">The drawback of this approach was that each set of ADO.NET objects (`Connection`, `Command`, and `Recordset`) was bound to libraries provided by a database vendor.</span></span> <span data-ttu-id="96bd2-118">El uso de estos componentes hace que el código sea rígido y difícil de migrar a una base de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="96bd2-118">Use of these components made the code rigid and difficult to migrate to a different database.</span></span>

## <a name="entity-framework"></a><span data-ttu-id="96bd2-119">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="96bd2-119">Entity Framework</span></span>

<span data-ttu-id="96bd2-120">Entity Framework (EF) es el marco de trabajo de asignación relacional de objetos de código abierto mantenido por .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="96bd2-120">Entity Framework (EF) is the open source object-relational mapping framework maintained by the .NET Foundation.</span></span> <span data-ttu-id="96bd2-121">En la primera versión de .NET Framework, EF permite generar código para las conexiones de base de datos, los esquemas de almacenamiento y las interacciones.</span><span class="sxs-lookup"><span data-stu-id="96bd2-121">Initially released with .NET Framework, EF allows for generating code for the database connections, storage schemas, and interactions.</span></span> <span data-ttu-id="96bd2-122">Con esta abstracción, puede centrarse en las reglas de negocios de la aplicación y permitir que un administrador de bases de datos de confianza administre la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-122">With this abstraction, you can focus on your app's business rules and allow the database to be managed by a trusted database administrator.</span></span> <span data-ttu-id="96bd2-123">En .NET Core, puede usar una versión actualizada de EF denominada EF Core.</span><span class="sxs-lookup"><span data-stu-id="96bd2-123">In .NET Core, you can use an updated version of EF called EF Core.</span></span> <span data-ttu-id="96bd2-124">EF Core ayuda a generar y mantener las interacciones entre el código y la base de datos con una serie de comandos que están disponibles para usted mediante la `dotnet ef` herramienta de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-124">EF Core helps generate and maintain the interactions between your code and the database with a series of commands that are available for you using the `dotnet ef` command-line tool.</span></span> <span data-ttu-id="96bd2-125">Echemos un vistazo a algunos ejemplos para trabajar con una base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-125">Let's take a look at a few samples to get you working with a database.</span></span>

### <a name="ef-code-first"></a><span data-ttu-id="96bd2-126">Code First EF</span><span class="sxs-lookup"><span data-stu-id="96bd2-126">EF Code First</span></span>

<span data-ttu-id="96bd2-127">Una forma rápida de empezar a crear las interacciones de base de datos es comenzar con los objetos de clase con los que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="96bd2-127">A quick way to get started building your database interactions is to start with the class objects you want to work with.</span></span> <span data-ttu-id="96bd2-128">EF proporciona una herramienta que le ayudará a generar el código de base de datos adecuado para las clases.</span><span class="sxs-lookup"><span data-stu-id="96bd2-128">EF provides a tool to help generate the appropriate database code for your classes.</span></span> <span data-ttu-id="96bd2-129">Este enfoque se denomina desarrollo "Code First".</span><span class="sxs-lookup"><span data-stu-id="96bd2-129">This approach is called "Code First" development.</span></span> <span data-ttu-id="96bd2-130">Considere la siguiente `Product` clase para una aplicación de escaparate de ejemplo que deseamos almacenar en una base de datos relacional como Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="96bd2-130">Consider the following `Product` class for a sample storefront app that we want to store in a relational database like Microsoft SQL Server.</span></span>

```csharp
public class Product
{
    public int Id { get; set; }

    [Required]
    public string Name { get; set; }

    [MaxLength(4000)]
    public string Description { get; set; }

    [Range(0, 99999,99)]
    [DataType(DataType.Currency)]
    public decimal Price { get; set; }
}
```

<span data-ttu-id="96bd2-131">El producto tiene una clave principal y tres campos adicionales que se crearían en nuestra base de datos:</span><span class="sxs-lookup"><span data-stu-id="96bd2-131">Product has a primary key and three additional fields that would be created in our database:</span></span>  

- <span data-ttu-id="96bd2-132">EF identificará la `Id` propiedad como clave principal por Convención.</span><span class="sxs-lookup"><span data-stu-id="96bd2-132">EF will identify the `Id` property as a primary key by convention.</span></span>
- <span data-ttu-id="96bd2-133">`Name` se almacenará en una columna configurada para el almacenamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="96bd2-133">`Name` will be stored in a column configured for text storage.</span></span> <span data-ttu-id="96bd2-134">El `[Required]` atributo que decora esta propiedad agregará una `not null` restricción para ayudar a exigir este comportamiento declarado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="96bd2-134">The `[Required]` attribute decorating this property will add a `not null` constraint to help enforce this declared behavior of the property.</span></span>
- <span data-ttu-id="96bd2-135">`Description` se almacenará en una columna configurada para el almacenamiento de texto y tendrá una longitud máxima configurada de 4000 caracteres como indica el `[MaxLength]` atributo.</span><span class="sxs-lookup"><span data-stu-id="96bd2-135">`Description` will be stored in a column configured for text storage, and have a maximum length configured of 4000 characters as dictated by the `[MaxLength]` attribute.</span></span> <span data-ttu-id="96bd2-136">El esquema de la base de datos se configurará con una columna denominada `MaxLength` con el tipo de datos `varchar(4000)` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-136">The database schema will be configured with a column named `MaxLength` using data type `varchar(4000)`.</span></span>
- <span data-ttu-id="96bd2-137">La `Price` propiedad se almacenará como moneda.</span><span class="sxs-lookup"><span data-stu-id="96bd2-137">The `Price` property will be stored as currency.</span></span> <span data-ttu-id="96bd2-138">El `[Range]` atributo generará las restricciones adecuadas para evitar el almacenamiento de datos fuera de los valores mínimo y máximo declarados.</span><span class="sxs-lookup"><span data-stu-id="96bd2-138">The `[Range]` attribute will generate appropriate constraints to prevent data storage outside of the minimum and maximum values declared.</span></span>

<span data-ttu-id="96bd2-139">Necesitamos agregar esta `Product` clase a una clase de contexto de base de datos que defina las operaciones de conexión y traducción con nuestra base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-139">We need to add this `Product` class to a database context class that defines the connection and translation operations with our database.</span></span>

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

<span data-ttu-id="96bd2-140">La `MyDbContext` clase proporciona una propiedad que define el acceso y la traducción de la `Product` clase.</span><span class="sxs-lookup"><span data-stu-id="96bd2-140">The `MyDbContext` class provides the one property that defines the access and translation for the `Product` class.</span></span>  <span data-ttu-id="96bd2-141">La aplicación configura esta clase para la interacción con la base de datos mediante las siguientes entradas en el `Startup` método de la clase `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="96bd2-141">Your application configures this class for interaction with the database using the following entries in the `Startup` class's `ConfigureServices` method:</span></span>

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

<span data-ttu-id="96bd2-142">El código anterior se conectará a una base de datos de SQL Server con la cadena de conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="96bd2-142">The preceding code will connect to a SQL Server database with the specified connection string.</span></span> <span data-ttu-id="96bd2-143">Puede colocar la cadena de conexión en el *appsettings.jsen* el archivo, variables de entorno u otras ubicaciones de almacenamiento de configuración y reemplazar esta cadena incrustada de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="96bd2-143">You can place the connection string in your *appsettings.json* file, environment variables, or other configuration storage locations and replace this embedded string appropriately.</span></span>

<span data-ttu-id="96bd2-144">A continuación, puede generar la tabla de base de datos adecuada para esta clase mediante los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="96bd2-144">You can then generate the database table appropriate for this class using the following commands:</span></span>

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

<span data-ttu-id="96bd2-145">El primer comando define los cambios que se realizan en el esquema de la base de datos como una nueva migración de EF denominada `Create Product table` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-145">The first command defines the changes you're making to the database schema as a new EF Migration called `Create Product table`.</span></span>  <span data-ttu-id="96bd2-146">Una migración define cómo aplicar y quitar los nuevos cambios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-146">A Migration defines how to apply and remove your new database changes.</span></span>

<span data-ttu-id="96bd2-147">Una vez aplicado, tiene una `Product` tabla simple en la base de datos y algunas clases nuevas agregadas al proyecto que ayudan a administrar el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-147">Once applied, you have a simple `Product` table in your database and some new classes added to the project that help manage the database schema.</span></span>  <span data-ttu-id="96bd2-148">Puede encontrar estas clases generadas, de forma predeterminada, en una nueva carpeta denominada *migraciones*.</span><span class="sxs-lookup"><span data-stu-id="96bd2-148">You can find these generated classes, by default, in a new folder called *Migrations*.</span></span>  <span data-ttu-id="96bd2-149">Cuando realice cambios en la `Product` clase o agregue más clases relacionadas que le gustaría interactuar con la base de datos, deberá volver a ejecutar los comandos de la línea de comandos con un nuevo nombre de la migración.</span><span class="sxs-lookup"><span data-stu-id="96bd2-149">When you make changes to the `Product` class or add more related classes you would like interacting with your database, you need to run the command-line commands again with a new name of the migration.</span></span>  <span data-ttu-id="96bd2-150">Este comando generará otro conjunto de clases de migración para actualizar el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-150">This command will generate another set of migration classes to update your database schema.</span></span>

### <a name="ef-database-first"></a><span data-ttu-id="96bd2-151">Database First EF</span><span class="sxs-lookup"><span data-stu-id="96bd2-151">EF Database First</span></span>

<span data-ttu-id="96bd2-152">En el caso de las bases de datos existentes, puede generar las clases para EF Core mediante el uso de las herramientas de línea de comandos de .NET.</span><span class="sxs-lookup"><span data-stu-id="96bd2-152">For existing databases, you can generate the classes for EF Core by using the .NET command-line tools.</span></span> <span data-ttu-id="96bd2-153">Para aplicar scaffolding a las clases, use una variación del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="96bd2-153">To scaffold the classes, use a variation of the following command:</span></span>

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

<span data-ttu-id="96bd2-154">El comando anterior se conecta a la base de datos utilizando la cadena de conexión especificada y el `Microsoft.EntityFrameworkCore.SqlServer` proveedor.</span><span class="sxs-lookup"><span data-stu-id="96bd2-154">The preceding command connects to the database using the specified connection string and the `Microsoft.EntityFrameworkCore.SqlServer` provider.</span></span> <span data-ttu-id="96bd2-155">Una vez conectado, se crea una clase de contexto de base de datos denominada `MyDbContext` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-155">Once connected, a database context class named `MyDbContext` is created.</span></span> <span data-ttu-id="96bd2-156">Además, las clases auxiliares se crean para `Product` las `Customer` tablas y que se especificaron con las `-t` Opciones.</span><span class="sxs-lookup"><span data-stu-id="96bd2-156">Additionally, supporting classes are created for the `Product` and `Customer` tables that were specified with the `-t` options.</span></span> <span data-ttu-id="96bd2-157">Hay muchas opciones de configuración para este comando con el fin de generar la jerarquía de clases adecuada para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-157">There are many configuration options for this command to generate the class hierarchy appropriate for your database.</span></span> <span data-ttu-id="96bd2-158">Para obtener una referencia completa, consulte [la documentación del comando](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span><span class="sxs-lookup"><span data-stu-id="96bd2-158">For a complete reference, see [the command's documentation](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span></span>

<span data-ttu-id="96bd2-159">Puede encontrar más información sobre [EF Core](/ef/core/) en el sitio de Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="96bd2-159">More information about [EF Core](/ef/core/) can be found on the Microsoft Docs site.</span></span>

## <a name="interact-with-web-services"></a><span data-ttu-id="96bd2-160">Interacción con servicios Web</span><span class="sxs-lookup"><span data-stu-id="96bd2-160">Interact with web services</span></span>

<span data-ttu-id="96bd2-161">Cuando ASP.NET se lanzó por primera vez, los servicios SOAP eran el mejor método para que los clientes y servidores web intercambien datos.</span><span class="sxs-lookup"><span data-stu-id="96bd2-161">When ASP.NET was first released, SOAP services were the preferred way for web servers and clients to exchange data.</span></span> <span data-ttu-id="96bd2-162">Ha cambiado mucho desde ese momento y las interacciones preferidas con los servicios se han desplazado a interacciones directas del cliente HTTP.</span><span class="sxs-lookup"><span data-stu-id="96bd2-162">Much has changed since that time, and the preferred interactions with services have shifted to direct HTTP client interactions.</span></span> <span data-ttu-id="96bd2-163">Con ASP.NET Core y Blazor , puede registrar la configuración de `HttpClient` en el `Startup` método de la clase `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-163">With ASP.NET Core and Blazor, you can register the configuration of your `HttpClient` in the `Startup` class's `ConfigureServices` method.</span></span> <span data-ttu-id="96bd2-164">Use esa configuración cuando necesite interactuar con el punto de conexión HTTP.</span><span class="sxs-lookup"><span data-stu-id="96bd2-164">Use that configuration when you need to interact with the HTTP endpoint.</span></span> <span data-ttu-id="96bd2-165">Considere el siguiente código de configuración:</span><span class="sxs-lookup"><span data-stu-id="96bd2-165">Consider the following configuration code:</span></span>

```csharp
services.AddHttpClient("github", client =>
{
    client.BaseAddress = new Uri("http://api.github.com/");
    // Github API versioning
    client.DefaultRequestHeaders.Add("Accept", "application/vnd.github.v3+json");
    // Github requires a user-agent
    client.DefaultRequestHeaders.Add("User-Agent", "BlazorWebForms-Sample");
});
```

<span data-ttu-id="96bd2-166">Siempre que necesite tener acceso a los datos de GitHub, cree un cliente con el nombre `github` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-166">Whenever you need to access data from GitHub, create a client with a name of `github`.</span></span> <span data-ttu-id="96bd2-167">El cliente está configurado con la dirección base y los encabezados de solicitud se establecen adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="96bd2-167">The client is configured with the base address, and the request headers are set appropriately.</span></span> <span data-ttu-id="96bd2-168">Inserte el `IHttpClientFactory` en los Blazor componentes con la `@inject` Directiva o un `[Inject]` atributo en una propiedad.</span><span class="sxs-lookup"><span data-stu-id="96bd2-168">Inject the `IHttpClientFactory` into your Blazor components with the `@inject` directive or an `[Inject]` attribute on a property.</span></span> <span data-ttu-id="96bd2-169">Cree el cliente con nombre e interactúe con los servicios mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="96bd2-169">Create your named client and interact with services using the following syntax:</span></span>

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = await response.Content.ReadAsStringAsync();
    }
}
```

<span data-ttu-id="96bd2-170">Este método devuelve la cadena que describe la colección de problemas en el repositorio de github *dotnet/docs* .</span><span class="sxs-lookup"><span data-stu-id="96bd2-170">This method returns the string describing the collection of issues in the *dotnet/docs* GitHub repository.</span></span> <span data-ttu-id="96bd2-171">Devuelve contenido en formato JSON y se deserializa en los objetos de problema de GitHub correspondientes.</span><span class="sxs-lookup"><span data-stu-id="96bd2-171">It returns content in JSON format and is deserialized into appropriate GitHub issue objects.</span></span> <span data-ttu-id="96bd2-172">Hay muchas maneras de configurar `HttpClientFactory` para proporcionar objetos preconfigurados `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="96bd2-172">There are many ways that you can configure the `HttpClientFactory` to deliver preconfigured `HttpClient` objects.</span></span> <span data-ttu-id="96bd2-173">Intente configurar varias `HttpClient` instancias con distintos nombres y puntos de conexión para los diversos servicios web con los que trabaja.</span><span class="sxs-lookup"><span data-stu-id="96bd2-173">Try configuring multiple `HttpClient` instances with different names and endpoints for the various web services you work with.</span></span> <span data-ttu-id="96bd2-174">Este enfoque hará que sus interacciones con esos servicios sean más fáciles de trabajar en cada página.</span><span class="sxs-lookup"><span data-stu-id="96bd2-174">This approach will make your interactions with those services easier to work with on each page.</span></span> <span data-ttu-id="96bd2-175">Para obtener más información, lea [la documentación de IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span><span class="sxs-lookup"><span data-stu-id="96bd2-175">For more details, read [the documentation for the IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="96bd2-176">[Anterior](forms-validation.md)
>[Siguiente](middleware.md)</span><span class="sxs-lookup"><span data-stu-id="96bd2-176">[Previous](forms-validation.md)
[Next](middleware.md)</span></span>
