---
title: Seguimiento de estado
description: Explore una forma de implementar la supervisión de estado.
ms.date: 03/02/2020
ms.openlocfilehash: 3e3e8ec41de1469f0c397d8d80d224dd2f7a2bd2
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267898"
---
# <a name="health-monitoring"></a>Seguimiento de estado

El seguimiento de estado puede permitir información prácticamente en tiempo real sobre el estado de los contenedores y los microservicios. El seguimiento de estado es fundamental para varios aspectos del funcionamiento de los microservicios y es especialmente importante cuando los orquestadores realizan actualizaciones de aplicación parcial en fases, tal como se describe más adelante.

Las aplicaciones basadas en microservicios suelen usar latidos o comprobaciones de estado para que sus monitores de rendimiento, programadores y orquestadores puedan realizar el seguimiento de gran cantidad de servicios. Si los servicios no pueden enviar algún tipo de señal "estoy activo", ya sea a petición o siguiendo una programación, la aplicación podría correr riesgos al implementar las actualizaciones, o podría simplemente detectar los errores demasiado tarde y no poder detener errores en cascada que pueden dar lugar a interrupciones importantes.

En el modelo típico, los servicios envían informes sobre su estado. Esa información se agrega para proporcionar una visión general del estado de la aplicación. Si se utiliza un orquestador, se puede proporcionar información de estado al clúster del orquestador a fin de que el clúster pueda actuar en consecuencia. Si se invierte en informes de estado de alta calidad personalizados para la aplicación, se pueden detectar y corregir mucho más fácilmente los problemas de la aplicación que se está ejecutando.

## <a name="implement-health-checks-in-aspnet-core-services"></a>Implementación de comprobaciones de estado en servicios de ASP.NET Core

Al desarrollar una aplicación web o microservicio de ASP.NET Core, puede usar la característica de comprobaciones de estado integrada que se lanzó en ASP.NET Core 2.2 ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)). Al igual que muchas características de ASP.NET Core, las comprobaciones de estado incluyen un conjunto de servicios y un middleware.

Los servicios de comprobación de estado y middleware son fáciles de usar y proporcionan características que permiten validar el funcionamiento correcto de cualquier recurso externo necesario para la aplicación (por ejemplo, una base de datos de SQL Server o API remota). Cuando se utiliza esta característica, también se puede decidir lo que significa que el estado del recurso sea correcto, tal y como se explica más adelante.

Para usar esta característica con eficacia, primero debe configurar servicios en sus microservicios. En segundo lugar, necesita una aplicación front-end que realice consultas para los informes de estado. La aplicación front-end podría ser una aplicación de informes personalizada, o podría ser un orquestador que reaccione en consecuencia a los estados.

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a>Uso de la característica HealthChecks en los microservicios ASP.NET de back-end

En esta sección, aprenderá a implementar la característica HealthChecks en una aplicación de API web de ASP.NET Core 3.1 de ejemplo al usar el paquete [Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks). La implementación de esta característica en un microservicio a gran escala como eShopOnContainers se explica en la siguiente sección.

Para empezar, debe definir qué constituye un estado correcto en cada microservicio. En la aplicación de ejemplo, definiremos que el estado del microservicio es correcto si se puede acceder a su API a través de HTTP y si su base de datos de SQL Server relacionada también está disponible.

En .NET Core 3.1, con las API integradas, puede configurar los servicios, añadir una comprobación de estado para el microservicio y su base de datos de SQL Server dependiente de esta forma:

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

En el código anterior, el método `services.AddHealthChecks()` configura una comprobación HTTP básica que devuelve un código de estado **200** con "Correcto".  Además, el método de extensión `AddCheck()` configura una `SqlConnectionHealthCheck` personalizada que comprueba el estado de la base de datos SQL Database relacionado.

El método `AddCheck()` agrega una nueva comprobación de estado con un nombre especificado y la implementación de tipo `IHealthCheck`. Puede agregar varias comprobaciones de estado mediante el método AddCheck, por lo que un microservicio no proporcionará un estado "correcto" hasta que el estado de todas sus comprobaciones sea correcto.

`SqlConnectionHealthCheck` es una clase personalizada que implementa `IHealthCheck`, que toma una cadena de conexión como parámetro del constructor y ejecuta una consulta sencilla que se va a comprobar si la conexión a la base de datos SQL es correcta. Devuelve `HealthCheckResult.Healthy()` si la consulta se ejecutó correctamente y un `FailureStatus` con la excepción real si hay errores.

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

Tenga en cuenta que en el código anterior, `Select 1` es la consulta usada para comprobar el estado de la base de datos. Para supervisar la disponibilidad de los microservicios, orquestadores como Kubernetes realizan periódicamente comprobaciones de estado mediante el envío de solicitudes para probar los microservicios. Es importante mantener la eficacia de sus consultas de base de datos para que estas operaciones sean rápidas y no den lugar a una mayor utilización de recursos.

Por último, agregue un middleware que responda a la dirección URL `/hc`:

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

Cuando se invoca, el punto de conexión `<yourmicroservice>/hc` ejecuta todas las comprobaciones de estado que están configuradas en el método `AddHealthChecks()` de la clase Startup y muestra el resultado.

### <a name="healthchecks-implementation-in-eshoponcontainers"></a>Implementación de HealthChecks en eShopOnContainers

Los microservicios de eShopOnContainers se basan en varios servicios para realizar su tarea. Por ejemplo, el microservicio `Catalog.API` de eShopOnContainers depende de muchos servicios, como Azure Blob Storage, SQL Server y RabbitMQ. Por lo tanto, tiene varias comprobaciones de estado agregadas mediante el método `AddCheck()`. En todos los servicios dependientes, se debería agregar una implementación `IHealthCheck` que defina su estado de mantenimiento correspondiente.

El proyecto de código abierto [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) resuelve este problema mediante implementaciones de comprobación de estado personalizadas para cada uno de estos servicios empresariales basados en .NET Core 3.1. Cada comprobación de estado está disponible como paquete NuGet individual que se puede agregar fácilmente al proyecto. eShopOnContainers los usa mayoritariamente en todos sus microservicios.

Por ejemplo, en el microservicio `Catalog.API`, se agregaron los siguientes paquetes NuGet:

![Captura de pantalla de los paquetes de NuGet AspNetCore.Diagnostics.HealthChecks.](./media/monitor-app-health/aspnet-core-diagnostics-health-checks.png)

**Figura 8-7**. Comprobaciones de estado personalizadas implementadas en Catalog.API mediante AspNetCore.Diagnostics.HealthChecks

En el siguiente código, las implementaciones de comprobación de estado se agregan para cada servicio dependiente y, a continuación, se configura el middleware:

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

Por último, agregue el middleware HealthCheck que se va a escuchar al punto de conexión "/hc":

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a>Consulta de los microservicios para informar de su estado

Cuando haya configurado las comprobaciones de estado como se describe en este artículo, y una vez que el microservicio se esté ejecutando en Docker, puede comprobar directamente desde un explorador si su estado es correcto. Debe publicar el puerto de contenedor en el host de Docker, para así poder acceder al contenedor a través de la dirección IP del host de Docker externa host local o de `localhost`, como se muestra en la figura 8-8.

![Captura de pantalla de la respuesta JSON devuelta por una comprobación de estado.](./media/monitor-app-health/health-check-json-response.png)

**Figura 8-8**. Comprobación del estado de un único servicio desde un explorador

En esa prueba, puede ver que el estado del microservicio `Catalog.API` (que se ejecuta en el puerto 5101) es correcto. Se devuelve el código de estado HTTP 200 e información de estado en JSON. El servicio también comprobó el estado de su dependencia de la base de datos de SQL Server y RabbitMQ, por lo que el estado se notificó como correcto.

## <a name="use-watchdogs"></a>Uso de guardianes

Un guardián es un servicio independiente que puede observar el estado y la carga en varios servicios, e informar del estado de los microservicios con una consulta con la biblioteca `HealthChecks` vista anteriormente. Esto puede ayudar a evitar errores que no se detectarían si se observase un único servicio. Los guardianes también son un buen lugar para hospedar código que lleve a cabo acciones correctoras para condiciones conocidas sin la intervención del usuario.

El ejemplo de eShopOnContainers contiene una página web que muestra informes de comprobación de estado de ejemplo, como se muestra en la figura 8-9. Se trata del guardián más sencillo que se puede tener, dado que lo único que hace es mostrar el estado de las aplicaciones web y los microservicios en eShopOnContainers. Normalmente, un guardián también realiza acciones cuando detecta estados no correctos.

Afortunadamente, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) también proporciona el paquete NuGet [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) que se puede usar para mostrar los resultados de comprobación de estado de los URI configurados.

![Captura de pantalla de la interfaz de usuario de comprobaciones de estado con los estados de mantenimiento de eShopOnContainers.](./media/monitor-app-health/health-check-status-ui.png)

**Figura 8-9**. Informe de comprobación de estado de ejemplo en eShopOnContainers

En resumen, este servicio de vigilancia consulta cada uno de los puntos de conexión "/hc" del microservicio. El middleware ejecutará todas las comprobaciones de estado definidas en él y devolverá un estado general que dependerá de todas esas comprobaciones. HealthChecksUI es fácil de usar con algunas entradas de configuración y dos líneas de código que deben agregarse en el archivo *Startup.cs* del servicio de inspección.

Archivo de configuración de ejemplo para la interfaz de usuario de comprobación de estado:

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

Archivo *Startup.cs* que agrega HealthChecksUI:

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
    app.UseHealthChecksUI(config => config.UIPath = "/hc-ui");
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a>Comprobaciones de estado con orquestadores

Para supervisar la disponibilidad de los microservicios, orquestadores como Kubernetes y Service Fabric realizan periódicamente comprobaciones de estado mediante el envío de solicitudes para probar los microservicios. Cuando un orquestador determina que el estado de un contenedor o servicio no es correcto, deja de enrutar las solicitudes a esa instancia. Normalmente también crea una nueva instancia de ese contenedor.

Por ejemplo, la mayoría de los orquestadores pueden utilizar comprobaciones de estado para administrar implementaciones sin tiempos de inactividad. Solo cuando el estado de un servicio o contenedor cambia a correcto, el orquestador empieza a enrutar el tráfico a las instancias de servicio o contenedor.

El seguimiento de estado es especialmente importante cuando un orquestador lleva a cabo una actualización de la aplicación. Algunos orquestadores (por ejemplo, Azure Service Fabric) actualizan los servicios en fases: por ejemplo, pueden actualizar una quinta parte de la superficie del clúster para cada actualización de la aplicación. El conjunto de nodos que se actualiza al mismo tiempo se conoce como *dominio de actualización*. Después de que cada dominio de actualización se haya actualizado y esté disponible para los usuarios, el dominio de actualización debe pasar las comprobaciones de estado antes de que la implementación se mueva al siguiente dominio de actualización.

Otro aspecto del estado del servicio es informar de las métricas del servicio. Se trata de una característica avanzada del modelo de estado de algunos orquestadores, como Service Fabric. Las métricas son importantes cuando se usa un orquestador porque se usan para equilibrar el uso de recursos. Las métricas también pueden ser un indicador del estado del sistema. Pongamos por ejemplo una aplicación que tenga muchos microservicios, y cada instancia informa sobre una métrica de solicitudes por segundo (RPS). Si un servicio está utilizando más recursos (memoria, procesador, etc.) que otro servicio, el orquestador puede mover las instancias del servicio en el clúster para intentar equilibrar el uso de los recursos.

Tenga en cuenta que Azure Service Fabric proporciona su propio [modelo de seguimiento de estado](/azure/service-fabric/service-fabric-health-introduction), que es más avanzado que las comprobaciones de estado simples.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Supervisión avanzada: visualización, análisis y alertas

La parte final de la supervisión es visualizar la secuencia de eventos, generar informes sobre rendimiento de los servicios y emitir alertas cuando se detecta un problema. Para este aspecto de la supervisión se pueden usar diferentes soluciones.

Se pueden utilizar aplicaciones personalizadas simples que muestren el estado de los servicios, como la página personalizada mostrada al explicar [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks). O bien, podría usar herramientas más avanzadas como [Azure Monitor](https://azure.microsoft.com/services/monitor/) para generar alertas basadas en el flujo de eventos.

Por último, si almacena todos los flujos de eventos, se puede utilizar Microsoft Power BI u otras soluciones como Kibana o Splunk para visualizar los datos.

## <a name="additional-resources"></a>Recursos adicionales

- **HealthChecks and HealthChecks UI for ASP.NET Core (HealthChecks e interfaz de usuario de HealthChecks para ASP.NET Core)**  \
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- **Introduction to Service Fabric health monitoring (Introducción al seguimiento de estado de Service Fabric)**  \
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- **Azure Monitor** \
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
>[Anterior](implement-circuit-breaker-pattern.md)
>[Siguiente](../secure-net-microservices-web-applications/index.md)
