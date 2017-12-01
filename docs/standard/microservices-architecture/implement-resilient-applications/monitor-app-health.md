---
title: "Supervisión de estado"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Supervisión de estado"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a>Supervisión de estado

Supervisión de estado puede permitir que la información de casi en tiempo real sobre el estado de los contenedores y microservicios. Supervisión de estado es crítica para varios aspectos del funcionamiento microservicios y es especialmente importante cuando orchestrators realice actualizaciones de aplicación parcial en fases, tal como se describe más adelante.

Aplicaciones basadas en Microservicios utilizan a menudo latidos o comprobaciones de mantenimiento para que sus monitores de rendimiento, los programadores y orchestrators realizar un seguimiento de la cantidad de servicios. Si los servicios no pueden enviar a algún tipo de señal "Soy activo", a petición o según una programación, la aplicación podría enfrentan riesgos al implementar las actualizaciones, o podría simplemente detectar errores demasiado tarde y no poder detener errores en cascada que pueden terminar en interrupciones importantes.

En el modelo típico, servicios envían informes sobre su estado y se agrega esa información para proporcionar una visión general del estado de mantenimiento de la aplicación. Si usas organizador, puede proporcionar información de estado al clúster de su orchestrator, para que el clúster puede actuar en consecuencia. Si invierte en informes sobre el estado de alta calidad que se personaliza para la aplicación, puede detectar y corregir problemas de la aplicación en ejecución mucho más fácilmente.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>Implementación de mantenimiento comprueba en servicios principales de ASP.NET

Al desarrollar una aplicación de ASP.NET Core microservicio o web, puede usar una biblioteca denominada comprobaciones de estado desde el equipo de ASP.NET. (A partir de mayo de 2017, una versión preliminar está disponible en GitHub).

Esta biblioteca es fácil de usar y proporciona características que permiten que validar que cualquier recurso externo específico necesario para la aplicación (por ejemplo, una base de datos de SQL Server o remota (API)) funciona correctamente. Cuando se utiliza esta biblioteca, también puede decidir lo que significa que el recurso es correcto, tal y como se explica más adelante.

Para poder usar esta biblioteca, debe usar primero la biblioteca en su microservicios. En segundo lugar, necesita una aplicación front-end que realiza consultas para los informes de mantenimiento. Aplicación front-end podría ser una aplicación informes personalizada, o podría ser organizador sí que puede actuar en consecuencia para los Estados de mantenimiento.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Usa la biblioteca de comprobaciones de estado en el back-end ASP.NET microservicios

Puede ver cómo se utiliza la biblioteca de comprobaciones de estado en la aplicación de ejemplo eShopOnContainers. Para empezar, debe definir qué constituye un estado correcto para cada microservicio. En la aplicación de ejemplo, el microservicios están correcto si la API de microservicio es accesible a través de HTTP y si su base de datos de SQL Server relacionada también está disponible.

En el futuro, podrá instalar la biblioteca de comprobaciones de estado como un paquete de NuGet. Pero cuando se redactó este documento, debe descargar y compile el código como parte de la solución. Clonar el código disponible en https://github.com/aspnet/HealthChecks y copie las siguientes carpetas en la solución.

  - src/comunes
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

También puede usar comprobaciones adicionales como los de Azure (Microsoft.Extensions.HealthChecks.AzureStorage), pero dado que esta versión de eShopOnContainers no tiene ninguna dependencia en Azure, no es necesario. Las comprobaciones de estado ASP.NET, no es necesario porque eShopOnContainers se basa en ASP.NET Core.

Figura 10-6 muestra la biblioteca de comprobaciones de estado en Visual Studio, listo para su uso como un bloque de creación por cualquier microservicios.

![](./media/image6.png)

**Figura 6-10**. Código de origen de biblioteca de comprobaciones de estado de núcleo ASP.NET en una solución de Visual Studio

Como se mencionó anteriormente, lo primero que hay que hacer en cada proyecto de microservicio es agregar una referencia a las tres bibliotecas de comprobaciones de estado. A continuación, agregue las acciones de comprobación de mantenimiento que desea realizar en ese microservicio. Estas acciones son básicamente las dependencias en otros microservicios (HttpUrlCheck) o las bases de datos (actualmente SqlCheck\* para bases de datos de SQL Server). Para agregar la acción dentro de la clase de inicio de cada microservicio ASP.NET o una aplicación web ASP.NET.

Cada servicio o aplicación web debe configurarse mediante la adición de todas sus dependencias HTTP o de base de datos como un método de AddHealthCheck. Por ejemplo, la aplicación web MVC de eShopOnContainers depende de muchos servicios, por lo tanto, tiene varios métodos de AddCheck que se agregan a las comprobaciones de mantenimiento.

Por ejemplo, en el código siguiente puede ver cómo el catálogo microservicio agrega una dependencia en su base de datos de SQL Server.

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

Sin embargo, la aplicación web MVC de eShopOnContainers tiene varias dependencias en el resto de la microservicios. Por lo tanto, llama a un método AddUrlCheck para cada microservicio, tal como se muestra en el ejemplo siguiente:

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

Por lo tanto, un microservicio no proporcionará un estado "correcto" hasta que todas las comprobaciones también son correctos.

Si la microservicio no tiene una dependencia en un servicio o en SQL Server, solo tiene que debe agregar una comprobación de Healthy("Ok"). El código siguiente procede de la microservicio basket.api eShopOnContainers. (La microservicio cesta usa la caché en Redis, pero la biblioteca aún no incluye un proveedor de comprobación de mantenimiento de Redis.)

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Para que un servicio o aplicación web exponer el extremo de la comprobación de mantenimiento, tiene que habilitar la UseHealthChecks (\[*url\_para\_estado\_comprueba*\]) extensión método. Este método se pasa en el WebHostBuilder nivel en el método main de la clase de programa de la aplicación web o servicio ASP.NET Core, justo después de UseKestrel tal como se muestra en el código siguiente.

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

El proceso funciona del siguiente modo: cada microservicio expone el extremo/HC. Ese punto de conexión se crea en la biblioteca de comprobaciones de estado ASP.NET Core middleware. Cuando se invoca ese punto de conexión, se ejecuta todas las comprobaciones de mantenimiento que se configuran en el método AddHealthChecks de la clase de inicio.

El método UseHealthChecks espera un puerto o una ruta de acceso. Ese puerto o la ruta de acceso es el punto de conexión se utiliza para comprobar el estado de mantenimiento del servicio. Por ejemplo, el catálogo de microservicio usa la ruta de acceso/HC.

### <a name="caching-health-check-responses"></a>Almacenamiento en caché las respuestas de comprobación de mantenimiento

Puesto que no desea producir una denegación de servicio (DoS) en los servicios, o simplemente no desea afectar el rendimiento del servicio mediante la comprobación de recursos con demasiada frecuencia, puede almacenar en caché la devuelve y configurar una duración de caché para cada comprobación de estado.

De forma predeterminada, la duración de la caché internamente se establece en 5 minutos, pero puede cambiar esa duración de la caché en cada comprobación de estado, como se muestra en el código siguiente:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>Consultar el microservicios informe sobre su estado de mantenimiento

Cuando haya configurado las comprobaciones de mantenimiento como se describe en este caso, una vez que se ejecuta el microservicio en Docker, puede comprobar directamente desde un explorador si es correcto. (Esto requiere que se va a publicar el puerto de contenedor fuera del host Docker, por lo que puede tener acceso al contenedor a través de localhost o la dirección IP externa host de Docker). Figura 10-7 muestra una solicitud en un explorador y la respuesta correspondiente.

![](./media/image7.png)

**Figura 10-7**. Comprobar el estado de mantenimiento de un único servicio desde un explorador

En esa prueba, puede ver que el microservicio catalog.api (que se ejecuta en el puerto 5101) es correcto, devuelve el código de estado HTTP 200 e información de estado en JSON. También significa que internamente el servicio también comprueba el estado de su dependencia de la base de datos de SQL Server y que la comprobación de mantenimiento se se notificó como correcto.

## <a name="using-watchdogs"></a>Usar watchdogs

A continuación se proporciona es un servicio independiente que se puede ver el estado y la carga entre los servicios y el estado del informe sobre el microservicios mediante una consulta con la biblioteca de comprobaciones de estado que se presentaron anteriormente. Esto puede ayudar a evitar errores que no se detectan en función de la vista de un único servicio. Watchdogs también son un buen lugar para alojar el código que puede realizar acciones correctoras para condiciones sin interacción del usuario.

El ejemplo eShopOnContainers contiene una página web que muestra los informes de comprobación de estado de ejemplo, como se muestra en la figura 10-8. Se trata de la vigilancia más sencilla podría tener, debido a que todo lo que hace es muestra el estado de las aplicaciones web y microservicios en eShopOnContainers. Normalmente un guardián también realiza acciones cuando detecta Estados no correctos.

![](./media/image8.png)

**Figura 8-10**. Informe de comprobación de estado de ejemplo en eShopOnContainers

En resumen, el middleware ASP.NET de la biblioteca de comprobaciones de estado de ASP.NET Core proporciona un punto de conexión de la comprobación de estado único para cada microservicio. Esto ejecutará todas las comprobaciones de mantenimiento definidas en él y devolver un estado de mantenimiento general según todas las comprobaciones de esos.

La biblioteca de comprobaciones de estado es extensible a través de nuevas comprobaciones de mantenimiento de recursos externos futuras. Por ejemplo, se espera que en el futuro la biblioteca tendrá comprobaciones de mantenimiento de caché en Redis y de otras bases de datos. Permite que la biblioteca de informes por varias dependencias de servicio o aplicación de estado y, a continuación, puede realizar acciones basadas en las comprobaciones de mantenimiento.

## <a name="health-checks-when-using-orchestrators"></a>Comprobaciones de mantenimiento cuando se utiliza orchestrators

Para supervisar la disponibilidad de su microservicios, orchestrators como Docker Swarm, Kubernetes y Service Fabric periódicamente realizan comprobaciones de mantenimiento mediante el envío de solicitudes para probar el microservicios. Cuando un orchestrator determina que un contenedor de servicios está en mal estado, deja de enrutar las solicitudes a esa instancia. Normalmente también crea una nueva instancia de ese contenedor.

Por ejemplo, orchestrators mayoría pueden utilizar comprobaciones de estado para administrar implementaciones sin tiempos de inactividad. Solo cuando el estado de cambia de un servicio o contenedor a correcto será el orchestrator iniciar enrutar el tráfico a las instancias de servicio o el contenedor.

Supervisión de estado es especialmente importante cuando organizador lleva a cabo una actualización de la aplicación. Algunos orchestrators (por ejemplo, Azure Service Fabric) update services en fases, por ejemplo, puede actualizar una quinta parte de la superficie de clúster para cada actualización de la aplicación. El conjunto de nodos que se actualiza al mismo tiempo se conoce como un *dominio de actualización*. Después de cada dominio de actualización se ha actualizado y está disponible para los usuarios, ese dominio de actualización debe pasar las comprobaciones de mantenimiento antes de la implementación se mueve al siguiente dominio de actualización.

Otro aspecto del estado del servicio está informando de métricas desde el servicio. Se trata de una característica avanzada del modelo de mantenimiento de algunos orchestrators, como Service Fabric. Las métricas son importantes cuando se usa un orchestrator porque se usan para equilibrar el uso de recursos. Las métricas también pueden ser un indicador del estado del sistema. Por ejemplo, podría tener una aplicación que tenga muchos microservicios, y cada instancia informa sobre una métrica de solicitudes por segundo (RPS). Si un servicio está usando más recursos (memoria, procesador, etc.) que otro servicio, el orchestrator puede moverse instancias de servicio del clúster para intentar mantener incluso el uso de recursos.

Tenga en cuenta que si utilizas Azure Service Fabric, proporciona su propio [modelo de supervisión de estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), que es más avanzado que comprobaciones de estado simple.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Supervisión avanzadas: visualización, análisis y alertas

Visualiza la secuencia de eventos, generación de informes en el rendimiento del servicio y emitir alertas cuando se detecta un problema en la parte final de la supervisión. Puede usar diferentes soluciones para este aspecto de supervisión.

Puede usar aplicaciones personalizadas simples que muestra el estado de los servicios, como la página personalizada se mostraba cuando se explican [comprobaciones de estado de ASP.NET Core](https://github.com/aspnet/HealthChecks). O bien, puede utilizar las herramientas más avanzadas como la visión de la aplicación de Azure y Operations Management Suite para generar alertas basadas en el flujo de eventos.

Por último, si se almacenan todos los flujos de eventos, puede utilizar Microsoft Power BI o una solución de terceros como Kibana o Splunk para visualizar los datos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Comprobaciones de estado de ASP.NET Core** (lanzamiento temprano) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Introducción a la supervisión de estado de Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Aplicación de Azure Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[Anterior] (implementar-circuito-separador-pattern.md) [siguiente] (.. /Secure-NET-microservices-Web-Applications/Index.MD)
