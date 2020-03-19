---
title: Seguimiento de estado
description: Explore una forma de implementar la supervisión de estado.
ms.date: 03/02/2020
ms.openlocfilehash: d3d2bc72cf29b3d1ac93191e7ff2bd827c9ee68d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401548"
---
# <a name="health-monitoring"></a><span data-ttu-id="dea19-103">Seguimiento de estado</span><span class="sxs-lookup"><span data-stu-id="dea19-103">Health monitoring</span></span>

<span data-ttu-id="dea19-104">El seguimiento de estado puede permitir información prácticamente en tiempo real sobre el estado de los contenedores y los microservicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="dea19-105">El seguimiento de estado es fundamental para varios aspectos del funcionamiento de los microservicios y es especialmente importante cuando los orquestadores realizan actualizaciones de aplicación parcial en fases, tal como se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="dea19-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="dea19-106">Las aplicaciones basadas en microservicios suelen usar latidos o comprobaciones de estado para que sus monitores de rendimiento, programadores y orquestadores puedan realizar el seguimiento de gran cantidad de servicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="dea19-107">Si los servicios no pueden enviar algún tipo de señal "estoy activo", ya sea a petición o siguiendo una programación, la aplicación podría correr riesgos al implementar las actualizaciones, o podría simplemente detectar los errores demasiado tarde y no poder detener errores en cascada que pueden dar lugar a interrupciones importantes.</span><span class="sxs-lookup"><span data-stu-id="dea19-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might just detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="dea19-108">En el modelo típico, los servicios envían informes sobre su estado. Esa información se agrega para proporcionar una visión general del estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dea19-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="dea19-109">Si se utiliza un orquestador, se puede proporcionar información de estado al clúster del orquestador a fin de que el clúster pueda actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="dea19-109">If you're using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="dea19-110">Si se invierte en informes de estado de alta calidad personalizados para la aplicación, se pueden detectar y corregir mucho más fácilmente los problemas de la aplicación que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="dea19-110">If you invest in high-quality health reporting that's customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implement-health-checks-in-aspnet-core-services"></a><span data-ttu-id="dea19-111">Implementación de comprobaciones de estado en servicios de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dea19-111">Implement health checks in ASP.NET Core services</span></span>

<span data-ttu-id="dea19-112">Al desarrollar una aplicación web o microservicio de ASP.NET Core, puede usar la característica de comprobaciones de estado integrada que se lanzó en ASP.NET Core 2.2 ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)).</span><span class="sxs-lookup"><span data-stu-id="dea19-112">When developing an ASP.NET Core microservice or web application, you can use the built-in health checks feature that was released in ASP .NET Core 2.2 ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)).</span></span> <span data-ttu-id="dea19-113">Al igual que muchas características de ASP.NET Core, las comprobaciones de estado incluyen un conjunto de servicios y un middleware.</span><span class="sxs-lookup"><span data-stu-id="dea19-113">Like many ASP.NET Core features, health checks come with a set of services and a middleware.</span></span>

<span data-ttu-id="dea19-114">Los servicios de comprobación de estado y middleware son fáciles de usar y proporcionan características que permiten validar el funcionamiento correcto de cualquier recurso externo necesario para la aplicación (por ejemplo, una base de datos de SQL Server o API remota).</span><span class="sxs-lookup"><span data-stu-id="dea19-114">Health check services and middleware are easy to use and provide capabilities that let you validate if any external resource needed for your application (like a SQL Server database or a remote API) is working properly.</span></span> <span data-ttu-id="dea19-115">Cuando se utiliza esta característica, también se puede decidir lo que significa que el estado del recurso sea correcto, tal y como se explica más adelante.</span><span class="sxs-lookup"><span data-stu-id="dea19-115">When you use this feature, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="dea19-116">Para usar esta característica con eficacia, primero debe configurar servicios en sus microservicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-116">To use this feature effectively, you need to first configure services in your microservices.</span></span> <span data-ttu-id="dea19-117">En segundo lugar, necesita una aplicación front-end que realice consultas para los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="dea19-117">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="dea19-118">La aplicación front-end podría ser una aplicación de informes personalizada, o podría ser un orquestador que reaccione en consecuencia a los estados.</span><span class="sxs-lookup"><span data-stu-id="dea19-118">That front-end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="dea19-119">Uso de la característica HealthChecks en los microservicios ASP.NET de back-end</span><span class="sxs-lookup"><span data-stu-id="dea19-119">Use the HealthChecks feature in your back-end ASP.NET microservices</span></span>

<span data-ttu-id="dea19-120">En esta sección, aprenderá a implementar la característica HealthChecks en una aplicación de API web de ASP.NET Core 3.1 de ejemplo al usar el paquete [Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="dea19-120">In this section, you'll learn how to implement the HealthChecks feature in a sample ASP.NET Core 3.1 Web API application when using the [Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks) package.</span></span> <span data-ttu-id="dea19-121">La implementación de esta característica en un microservicio a gran escala como eShopOnContainers se explica en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="dea19-121">The Implementation of this feature in a large-scale microservices like the eShopOnContainers is explained in the next section.</span></span>

<span data-ttu-id="dea19-122">Para empezar, debe definir qué constituye un estado correcto en cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="dea19-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="dea19-123">En la aplicación de ejemplo, definiremos que el estado del microservicio es correcto si se puede acceder a su API a través de HTTP y si su base de datos de SQL Server relacionada también está disponible.</span><span class="sxs-lookup"><span data-stu-id="dea19-123">In the sample application, we define the microservice is healthy if its API is accessible via HTTP and its related SQL Server database is also available.</span></span>

<span data-ttu-id="dea19-124">En .NET Core 3.1, con las API integradas, puede configurar los servicios, añadir una comprobación de estado para el microservicio y su base de datos de SQL Server dependiente de esta forma:</span><span class="sxs-lookup"><span data-stu-id="dea19-124">In .NET Core 3.1, with the built-in APIs, you can configure the services, add a Health Check for the microservice and its dependent SQL Server database in this way:</span></span>

```csharp
// Startup.cs from .NET Core 3.1 Web API sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
        // Add a health check for a SQL Server database
        .AddCheck(
            "OrderingDB-check",
            new SqlConnectionHealthCheck(Configuration["ConnectionString"]),
            HealthStatus.Unhealthy,
            new string[] { "orderingdb" });
}
```

<span data-ttu-id="dea19-125">En el código anterior, el método `services.AddHealthChecks()` configura una comprobación HTTP básica que devuelve un código de estado **200** con “Correcto”.</span><span class="sxs-lookup"><span data-stu-id="dea19-125">In the previous code, the `services.AddHealthChecks()` method configures a basic HTTP check that returns a status code **200** with “Healthy”.</span></span>  <span data-ttu-id="dea19-126">Además, el método de extensión `AddCheck()` configura una `SqlConnectionHealthCheck` personalizada que comprueba el estado de la base de datos SQL Database relacionado.</span><span class="sxs-lookup"><span data-stu-id="dea19-126">Further, the `AddCheck()` extension method configures a custom `SqlConnectionHealthCheck` that checks the related SQL Database’s health.</span></span>

<span data-ttu-id="dea19-127">El método `AddCheck()` agrega una nueva comprobación de estado con un nombre especificado y la implementación de tipo `IHealthCheck`.</span><span class="sxs-lookup"><span data-stu-id="dea19-127">The `AddCheck()` method adds a new health check with a specified name and the implementation of type `IHealthCheck`.</span></span> <span data-ttu-id="dea19-128">Puede agregar varias comprobaciones de estado mediante el método AddCheck, por lo que un microservicio no proporcionará un estado "correcto" hasta que el estado de todas sus comprobaciones sea correcto.</span><span class="sxs-lookup"><span data-stu-id="dea19-128">You can add multiple Health Checks using AddCheck method, so a microservice won't provide a “healthy” status until all its checks are healthy.</span></span>

<span data-ttu-id="dea19-129">`SqlConnectionHealthCheck` es una clase personalizada que implementa `IHealthCheck`, que toma una cadena de conexión como parámetro del constructor y ejecuta una consulta sencilla que se va a comprobar si la conexión a la base de datos SQL es correcta.</span><span class="sxs-lookup"><span data-stu-id="dea19-129">`SqlConnectionHealthCheck` is a custom class that implements `IHealthCheck`, which takes a connection string as a constructor parameter and executes a simple query to check if the connection to the SQL database is successful.</span></span> <span data-ttu-id="dea19-130">Devuelve `HealthCheckResult.Healthy()` si la consulta se ejecutó correctamente y un `FailureStatus` con la excepción real si hay errores.</span><span class="sxs-lookup"><span data-stu-id="dea19-130">It returns `HealthCheckResult.Healthy()` if the query was executed successfully and a `FailureStatus` with the actual exception when it fails.</span></span>

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

<span data-ttu-id="dea19-131">Tenga en cuenta que en el código anterior, `Select 1` es la consulta usada para comprobar el estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dea19-131">Note that in the previous code, `Select 1` is the query used to check the Health of the database.</span></span> <span data-ttu-id="dea19-132">Para supervisar la disponibilidad de los microservicios, orquestadores como Kubernetes realizan periódicamente comprobaciones de estado mediante el envío de solicitudes para probar los microservicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-132">To monitor the availability of your microservices, orchestrators like Kubernetes periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="dea19-133">Es importante mantener la eficacia de sus consultas de base de datos para que estas operaciones sean rápidas y no den lugar a una mayor utilización de recursos.</span><span class="sxs-lookup"><span data-stu-id="dea19-133">It's important to keep your database queries efficient so that these operations are quick and don’t result in a higher utilization of resources.</span></span>

<span data-ttu-id="dea19-134">Por último, agregue un middleware que responda a la dirección URL `/hc`:</span><span class="sxs-lookup"><span data-stu-id="dea19-134">Finally, add a middleware that responds to the url path `/hc`:</span></span>

```csharp
// Startup.cs from .NET Core 3.1 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
        endpoints.MapHealthChecks("/hc");
        //...
    });
    //…
}
```

<span data-ttu-id="dea19-135">Cuando se invoca, el punto de conexión `<yourmicroservice>/hc` ejecuta todas las comprobaciones de estado que están configuradas en el método `AddHealthChecks()` de la clase Startup y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="dea19-135">When the endpoint `<yourmicroservice>/hc` is invoked, it runs all the health checks that are configured in the `AddHealthChecks()` method in the Startup class and shows the result.</span></span>

### <a name="healthchecks-implementation-in-eshoponcontainers"></a><span data-ttu-id="dea19-136">Implementación de HealthChecks en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="dea19-136">HealthChecks implementation in eShopOnContainers</span></span>

<span data-ttu-id="dea19-137">Los microservicios de eShopOnContainers se basan en varios servicios para realizar su tarea.</span><span class="sxs-lookup"><span data-stu-id="dea19-137">Microservices in eShopOnContainers rely on multiple services to perform its task.</span></span> <span data-ttu-id="dea19-138">Por ejemplo, el microservicio `Catalog.API` de eShopOnContainers depende de muchos servicios, como Azure Blob Storage, SQL Server y RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="dea19-138">For example, the `Catalog.API` microservice from eShopOnContainers depends on many services, such as Azure Blob Storage, SQL Server, and RabbitMQ.</span></span> <span data-ttu-id="dea19-139">Por lo tanto, tiene varias comprobaciones de estado agregadas mediante el método `AddCheck()`.</span><span class="sxs-lookup"><span data-stu-id="dea19-139">Therefore, it has several health checks added using the `AddCheck()` method.</span></span> <span data-ttu-id="dea19-140">En todos los servicios dependientes, se debería agregar una implementación `IHealthCheck` que defina su estado de mantenimiento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dea19-140">For every dependent service, a custom `IHealthCheck` implementation that defines its respective health status would need to be added.</span></span>

<span data-ttu-id="dea19-141">El proyecto de código abierto [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) resuelve este problema mediante implementaciones de comprobación de estado personalizadas para cada uno de estos servicios empresariales basados en .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="dea19-141">The open-source project [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) solves this problem by providing custom health check implementations for each of these enterprise services, that are built on top of .NET Core 3.1.</span></span> <span data-ttu-id="dea19-142">Cada comprobación de estado está disponible como paquete NuGet individual que se puede agregar fácilmente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="dea19-142">Each health check is available as an individual NuGet package that can be easily added to the project.</span></span> <span data-ttu-id="dea19-143">eShopOnContainers los usa mayoritariamente en todos sus microservicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-143">eShopOnContainers uses them extensively in all its microservices.</span></span>

<span data-ttu-id="dea19-144">Por ejemplo, en el microservicio `Catalog.API`, se agregaron los siguientes paquetes NuGet:</span><span class="sxs-lookup"><span data-stu-id="dea19-144">For instance, in the `Catalog.API` microservice, the following NuGet packages were added:</span></span>

![Captura de pantalla de los paquetes de NuGet AspNetCore.Diagnostics.HealthChecks.](./media/monitor-app-health/aspnet-core-diagnostics-health-checks.png)

<span data-ttu-id="dea19-146">**Figura 8-7**.</span><span class="sxs-lookup"><span data-stu-id="dea19-146">**Figure 8-7**.</span></span> <span data-ttu-id="dea19-147">Comprobaciones de estado personalizadas implementadas en Catalog.API mediante AspNetCore.Diagnostics.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="dea19-147">Custom Health Checks implemented in Catalog.API using AspNetCore.Diagnostics.HealthChecks</span></span>

<span data-ttu-id="dea19-148">En el siguiente código, las implementaciones de comprobación de estado se agregan para cada servicio dependiente y, a continuación, se configura el middleware:</span><span class="sxs-lookup"><span data-stu-id="dea19-148">In the following code, the health check implementations are added for each dependent service and then the middleware is configured:</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

<span data-ttu-id="dea19-149">Por último, agregue el middleware HealthCheck que se va a escuchar al punto de conexión "/hc":</span><span class="sxs-lookup"><span data-stu-id="dea19-149">Finally, add the HealthCheck middleware to listen to “/hc” endpoint:</span></span>

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
}
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="dea19-150">Consulta de los microservicios para informar de su estado</span><span class="sxs-lookup"><span data-stu-id="dea19-150">Query your microservices to report about their health status</span></span>

<span data-ttu-id="dea19-151">Cuando haya configurado las comprobaciones de estado como se describe en este artículo, y una vez que el microservicio se esté ejecutando en Docker, puede comprobar directamente desde un explorador si su estado es correcto.</span><span class="sxs-lookup"><span data-stu-id="dea19-151">When you've configured health checks as described in this article and you have the microservice running in Docker, you can directly check from a browser if it's healthy.</span></span> <span data-ttu-id="dea19-152">Debe publicar el puerto de contenedor en el host de Docker, para así poder acceder al contenedor a través de la dirección IP del host de Docker externa host local o de `localhost`, como se muestra en la figura 8-8.</span><span class="sxs-lookup"><span data-stu-id="dea19-152">You have to publish the container port in the Docker host, so you can access the container through the external Docker host IP or through `localhost`, as shown in figure 8-8.</span></span>

![Captura de pantalla de la respuesta JSON devuelta por una comprobación de estado.](./media/monitor-app-health/health-check-json-response.png)

<span data-ttu-id="dea19-154">**Figura 8-8**.</span><span class="sxs-lookup"><span data-stu-id="dea19-154">**Figure 8-8**.</span></span> <span data-ttu-id="dea19-155">Comprobación del estado de un único servicio desde un explorador</span><span class="sxs-lookup"><span data-stu-id="dea19-155">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="dea19-156">En esa prueba, puede ver que el estado del microservicio `Catalog.API` (que se ejecuta en el puerto 5101) es correcto. Se devuelve el código de estado HTTP 200 e información de estado en JSON.</span><span class="sxs-lookup"><span data-stu-id="dea19-156">In that test, you can see that the `Catalog.API` microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="dea19-157">El servicio también comprobó el estado de su dependencia de la base de datos de SQL Server y RabbitMQ, por lo que el estado se notificó como correcto.</span><span class="sxs-lookup"><span data-stu-id="dea19-157">The service also checked the health of its SQL Server database dependency and RabbitMQ, so the health check reported itself as healthy.</span></span>

## <a name="use-watchdogs"></a><span data-ttu-id="dea19-158">Uso de guardianes</span><span class="sxs-lookup"><span data-stu-id="dea19-158">Use watchdogs</span></span>

<span data-ttu-id="dea19-159">Un guardián es un servicio independiente que puede observar el estado y la carga en varios servicios, e informar del estado de los microservicios con una consulta con la biblioteca `HealthChecks` vista anteriormente.</span><span class="sxs-lookup"><span data-stu-id="dea19-159">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the `HealthChecks` library introduced earlier.</span></span> <span data-ttu-id="dea19-160">Esto puede ayudar a evitar errores que no se detectarían si se observase un único servicio.</span><span class="sxs-lookup"><span data-stu-id="dea19-160">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="dea19-161">Los guardianes también son un buen lugar para hospedar código que lleve a cabo acciones correctoras para condiciones conocidas sin la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="dea19-161">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="dea19-162">El ejemplo de eShopOnContainers contiene una página web que muestra informes de comprobación de estado de ejemplo, como se muestra en la figura 8-9.</span><span class="sxs-lookup"><span data-stu-id="dea19-162">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 8-9.</span></span> <span data-ttu-id="dea19-163">Se trata del guardián más sencillo que se puede tener, dado que lo único que hace es mostrar el estado de las aplicaciones web y los microservicios en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="dea19-163">This is the simplest watchdog you could have since it only shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="dea19-164">Normalmente, un guardián también realiza acciones cuando detecta estados no correctos.</span><span class="sxs-lookup"><span data-stu-id="dea19-164">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

<span data-ttu-id="dea19-165">Afortunadamente, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) también proporciona el paquete NuGet [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) que se puede usar para mostrar los resultados de comprobación de estado de los URI configurados.</span><span class="sxs-lookup"><span data-stu-id="dea19-165">Fortunately, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) also provides [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) NuGet package that can be used to display the health check results from the configured URIs.</span></span>

![Captura de pantalla de la interfaz de usuario de comprobaciones de estado con los estados de mantenimiento de eShopOnContainers.](./media/monitor-app-health/health-check-status-ui.png)

<span data-ttu-id="dea19-167">**Figura 8-9**.</span><span class="sxs-lookup"><span data-stu-id="dea19-167">**Figure 8-9**.</span></span> <span data-ttu-id="dea19-168">Informe de comprobación de estado de ejemplo en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="dea19-168">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="dea19-169">En resumen, este servicio de vigilancia consulta cada uno de los puntos de conexión "/hc" del microservicio.</span><span class="sxs-lookup"><span data-stu-id="dea19-169">In summary, this watchdog service queries each microservice’s "/hc" endpoint.</span></span> <span data-ttu-id="dea19-170">El middleware ejecutará todas las comprobaciones de estado definidas en él y devolverá un estado general que dependerá de todas esas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="dea19-170">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span> <span data-ttu-id="dea19-171">La HealthChecksUI es fácil de usar con algunas entradas de configuración y dos líneas de código que deben agregarse en el archivo Startup.cs del servicio de vigilancia.</span><span class="sxs-lookup"><span data-stu-id="dea19-171">The HealthChecksUI is easy to consume with a few configuration entries and two lines of code that needs to be added into the Startup.cs of the watchdog service.</span></span>

<span data-ttu-id="dea19-172">Archivo de configuración de ejemplo para la interfaz de usuario de comprobación de estado:</span><span class="sxs-lookup"><span data-stu-id="dea19-172">Sample configuration file for health check UI:</span></span>

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

<span data-ttu-id="dea19-173">Archivo Startup.cs que agrega HealthChecksUI:</span><span class="sxs-lookup"><span data-stu-id="dea19-173">Startup.cs file that adds HealthChecksUI:</span></span>

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config=> config.UIPath = “/hc-ui”);
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="dea19-174">Comprobaciones de estado con orquestadores</span><span class="sxs-lookup"><span data-stu-id="dea19-174">Health checks when using orchestrators</span></span>

<span data-ttu-id="dea19-175">Para supervisar la disponibilidad de los microservicios, orquestadores como Kubernetes y Service Fabric realizan periódicamente comprobaciones de estado mediante el envío de solicitudes para probar los microservicios.</span><span class="sxs-lookup"><span data-stu-id="dea19-175">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="dea19-176">Cuando un orquestador determina que el estado de un contenedor o servicio no es correcto, deja de enrutar las solicitudes a esa instancia.</span><span class="sxs-lookup"><span data-stu-id="dea19-176">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="dea19-177">Normalmente también crea una nueva instancia de ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="dea19-177">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="dea19-178">Por ejemplo, la mayoría de los orquestadores pueden utilizar comprobaciones de estado para administrar implementaciones sin tiempos de inactividad.</span><span class="sxs-lookup"><span data-stu-id="dea19-178">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="dea19-179">Solo cuando el estado de un servicio o contenedor cambia a correcto, el orquestador empieza a enrutar el tráfico a las instancias de servicio o contenedor.</span><span class="sxs-lookup"><span data-stu-id="dea19-179">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="dea19-180">El seguimiento de estado es especialmente importante cuando un orquestador lleva a cabo una actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dea19-180">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="dea19-181">Algunos orquestadores (por ejemplo, Azure Service Fabric) actualizan los servicios en fases: por ejemplo, pueden actualizar una quinta parte de la superficie del clúster para cada actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dea19-181">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="dea19-182">El conjunto de nodos que se actualiza al mismo tiempo se conoce como *dominio de actualización*.</span><span class="sxs-lookup"><span data-stu-id="dea19-182">The set of nodes that's upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="dea19-183">Después de que cada dominio de actualización se haya actualizado y esté disponible para los usuarios, el dominio de actualización debe pasar las comprobaciones de estado antes de que la implementación se mueva al siguiente dominio de actualización.</span><span class="sxs-lookup"><span data-stu-id="dea19-183">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="dea19-184">Otro aspecto del estado del servicio es informar de las métricas del servicio.</span><span class="sxs-lookup"><span data-stu-id="dea19-184">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="dea19-185">Se trata de una característica avanzada del modelo de estado de algunos orquestadores, como Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="dea19-185">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="dea19-186">Las métricas son importantes cuando se usa un orquestador porque se usan para equilibrar el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="dea19-186">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="dea19-187">Las métricas también pueden ser un indicador del estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="dea19-187">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="dea19-188">Pongamos por ejemplo una aplicación que tenga muchos microservicios, y cada instancia informa sobre una métrica de solicitudes por segundo (RPS).</span><span class="sxs-lookup"><span data-stu-id="dea19-188">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="dea19-189">Si un servicio está utilizando más recursos (memoria, procesador, etc.) que otro servicio, el orquestador puede mover las instancias del servicio en el clúster para intentar equilibrar el uso de los recursos.</span><span class="sxs-lookup"><span data-stu-id="dea19-189">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="dea19-190">Tenga en cuenta que Azure Service Fabric proporciona su propio [modelo de seguimiento de estado](/azure/service-fabric/service-fabric-health-introduction), que es más avanzado que las comprobaciones de estado simples.</span><span class="sxs-lookup"><span data-stu-id="dea19-190">Note that Azure Service Fabric provides its own [Health Monitoring model](/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="dea19-191">Supervisión avanzada: visualización, análisis y alertas</span><span class="sxs-lookup"><span data-stu-id="dea19-191">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="dea19-192">La parte final de la supervisión es visualizar la secuencia de eventos, generar informes sobre rendimiento de los servicios y emitir alertas cuando se detecta un problema.</span><span class="sxs-lookup"><span data-stu-id="dea19-192">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="dea19-193">Para este aspecto de la supervisión se pueden usar diferentes soluciones.</span><span class="sxs-lookup"><span data-stu-id="dea19-193">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="dea19-194">Se pueden utilizar aplicaciones personalizadas simples que muestren el estado de los servicios, como la página personalizada mostrada al explicar [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="dea19-194">You can use simple custom applications showing the state of your services, like the custom page shown when explaining the [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks).</span></span> <span data-ttu-id="dea19-195">O bien, podría usar herramientas más avanzadas como [Azure Monitor](https://azure.microsoft.com/services/monitor/) para generar alertas basadas en el flujo de eventos.</span><span class="sxs-lookup"><span data-stu-id="dea19-195">Or you could use more advanced tools like [Azure Monitor](https://azure.microsoft.com/services/monitor/) to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="dea19-196">Por último, si almacena todos los flujos de eventos, se puede utilizar Microsoft Power BI u otras soluciones como Kibana o Splunk para visualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="dea19-196">Finally, if you're storing all the event streams, you can use Microsoft Power BI or other solutions like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dea19-197">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dea19-197">Additional resources</span></span>

- <span data-ttu-id="dea19-198">**HealthChecks and HealthChecks UI for ASP.NET Core (HealthChecks e interfaz de usuario de HealthChecks para ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="dea19-198">**HealthChecks and HealthChecks UI for ASP.NET Core** </span></span>\
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- <span data-ttu-id="dea19-199">**Introduction to Service Fabric health monitoring (Introducción al seguimiento de estado de Service Fabric)**  </span><span class="sxs-lookup"><span data-stu-id="dea19-199">**Introduction to Service Fabric health monitoring** </span></span>\
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- <span data-ttu-id="dea19-200">**Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="dea19-200">**Azure Monitor** </span></span>\
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
><span data-ttu-id="dea19-201">[Anterior](implement-circuit-breaker-pattern.md)
>[Siguiente](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="dea19-201">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>
