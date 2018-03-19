---
title: Seguimiento de estado
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Seguimiento de estado
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76821e27613335609527b867a6b94dac551f6235
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2018
---
# <a name="health-monitoring"></a>Seguimiento de estado

El seguimiento de estado puede permitir información prácticamente en tiempo real sobre el estado de los contenedores y los microservicios. El seguimiento de estado es fundamental para varios aspectos del funcionamiento de los microservicios y es especialmente importante cuando los orquestadores realizan actualizaciones de aplicación parcial en fases, tal como se describe más adelante.

Las aplicaciones basadas en microservicios suelen usar latidos o comprobaciones de estado para que sus monitores de rendimiento, programadores y orquestadores puedan realizar el seguimiento de gran cantidad de servicios. Si los servicios no pueden enviar algún tipo de señal "estoy activo", ya sea a petición o siguiendo una programación, la aplicación podría correr riesgos al implementar las actualizaciones, o podría simplemente detectar los errores demasiado tarde y no poder detener errores en cascada que pueden dar lugar a interrupciones importantes.

En el modelo típico, los servicios envían informes sobre su estado. Esa información se agrega para proporcionar una visión general del estado de la aplicación. Si se utiliza un orquestador, se puede proporcionar información de estado al clúster del orquestador a fin de que el clúster pueda actuar en consecuencia. Si se invierte en informes de estado de alta calidad personalizados para la aplicación, se pueden detectar y corregir mucho más fácilmente los problemas de la aplicación que se está ejecutando.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>Implementación de comprobaciones de estado en servicios de ASP.NET Core

Al desarrollar una aplicación web o un microservicio de ASP.NET Core, se puede usar una biblioteca denominada `HealthChecks` del equipo de ASP.NET. Hay una versión temprana disponible en este [repositorio de GitHub](https://github.com/dotnet-architecture/HealthChecks).

Esta biblioteca es fácil de usar y proporciona características que permiten validar el funcionamiento correcto de cualquier recurso externo específico necesario para la aplicación (por ejemplo, una base de datos de SQL Server o API remota). Cuando se utiliza esta biblioteca, también se puede decidir lo que significa que el estado del recurso sea correcto, tal y como se explica más adelante.

Para poder usar esta biblioteca, debe usar primero la biblioteca en su microservicios. En segundo lugar, necesita una aplicación front-end que realice consultas para los informes de estado. La aplicación front-end podría ser una aplicación de informes personalizada, o podría ser un orquestador que reaccione en consecuencia a los estados.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Uso de la biblioteca HealthChecks en los microservicios ASP.NET de back-end

Puede ver cómo se utiliza la biblioteca HealthChecks en la aplicación de ejemplo eShopOnContainers. Para empezar, debe definir qué constituye un estado correcto en cada microservicio. En la aplicación de ejemplo, el estado de los microservicios es correcto si se puede acceder a la API del microservicio a través de HTTP y si su base de datos de SQL Server relacionada también está disponible.

En el futuro, podrá instalar la biblioteca HealthChecks como un paquete NuGet. Pero en el momento de redactar este documento, es necesario descargar y compilar el código como parte de la solución. Clonar el código disponible en https://github.com/dotnet-architecture/HealthChecks y copie las siguientes carpetas en la solución:

  - src/common
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

También puede usar comprobaciones adicionales como las de Azure (Microsoft.Extensions.HealthChecks.AzureStorage), pero dado que esta versión de eShopOnContainers no tiene ninguna dependencia en Azure, no es necesario. Las comprobaciones de estado ASP.NET no son necesarias porque eShopOnContainers se basa en ASP.NET Core.

La figura 10-6 muestra la biblioteca HealthChecks en Visual Studio, lista para que los microservicios la utilicen como un bloque de creación.

![](./media/image6.png)

**Figura 10-6**. Código de origen de la biblioteca HealthChecks de ASP.NET Core en una solución de Visual Studio

Como se mencionó anteriormente, lo primero que hay que hacer en cada proyecto de microservicio es agregar una referencia a las tres bibliotecas de HealthChecks. A continuación, hay que agregar las acciones de comprobación de estado que se quieren realizar en ese microservicio. Estas acciones son básicamente dependencias en otros microservicios (HttpUrlCheck) o bases de datos (actualmente SqlCheck\* para bases de datos de SQL Server). La acción se agrega en la clase Startup de cada microservicio ASP.NET o aplicación web ASP.NET.

Cada servicio o aplicación web debe configurarse mediante la adición de todas sus dependencias HTTP o de base de datos como un método AddHealthCheck. Por ejemplo, la aplicación web MVC de eShopOnContainers depende de muchos servicios, por lo que tiene varios métodos AddCheck agregados a las comprobaciones de estado.

Por ejemplo, en el código siguiente puede ver cómo el microservicio de catálogo agrega una dependencia en su base de datos de SQL Server.

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

Pero la aplicación web MVC de eShopOnContainers tiene varias dependencias en el resto de los microservicios. Por lo tanto, llama a un método AddUrlCheck para cada microservicio, tal como se muestra en el ejemplo siguiente:

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

De este modo, un microservicio no proporcionará un estado "correcto" hasta que todas las comprobaciones también sean correctas.

Si el microservicio no tiene una dependencia en un servicio o en SQL Server, solo debe agregarse una comprobación Healthy("Ok"). El código siguiente procede del microservicio basket.api de eShopOnContainers. (El microservicio de cesta usa Redis Cache, pero la biblioteca aún no incluye un proveedor de comprobación de estado de Redis).

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Para que un servicio o aplicación web expongan el punto de conexión de la comprobación de estado, tiene que habilitar el método de extensión UseHealthChecks (\[*url\_para\_comprobaciones_de\_estado*\]). Este método se pasa en el nivel WebHostBuilder en el método Main de la clase Program de su aplicación web o servicio ASP.NET Core, justo después de UseKestrel, tal como se muestra en el código siguiente.

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

El proceso funciona del siguiente modo: cada microservicio expone el punto de conexión /hc. Ese punto de conexión lo crea el middleware de ASP.NET Core de la biblioteca HealthChecks. Cuando se invoca, el punto de conexión ejecuta todas las comprobaciones de estado que están configuradas en el método AddHealthChecks de la clase Startup.

El método UseHealthChecks espera un puerto o una ruta de acceso. Ese puerto o ruta de acceso es el punto de conexión que se utiliza para comprobar el estado del servicio. Por ejemplo, el microservicio de catálogo usa la ruta de acceso /hc.

### <a name="caching-health-check-responses"></a>Almacenamiento en caché de las respuestas de comprobación de estado

Puesto que no desea que se produzca una denegación de servicio (DoS) en sus servicios, o simplemente no quiere que el rendimiento del servicio se vea afectado por una comprobación de recursos demasiado frecuente, puede almacenar en caché los valores devueltos y configurar una duración de caché para cada comprobación de estado.

De forma predeterminada, la duración de la caché está establecida internamente en 5 minutos, pero se puede cambiar esa duración en cada comprobación de estado, como se muestra en el código siguiente:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>Consulta de los microservicios para informar de su estado

Cuando haya configurado las comprobaciones de estado como se describe aquí, y una vez que el microservicio se esté ejecutando en Docker, puede comprobar directamente desde un explorador si su estado es correcto. (Esto requiere que publique el puerto de contenedor fuera del host de Docker, para así poder acceder al contenedor a través del host local o de la dirección IP del host de Docker externa). La figura 10-7 muestra una solicitud en un explorador y la respuesta correspondiente.

![](./media/image7.png)

**Figura 10-7**. Comprobación del estado de un único servicio desde un explorador

En esa prueba, puede ver que el estado del microservicio catalog.api (que se ejecuta en el puerto 5101) es correcto. Se devuelve el código de estado HTTP 200 e información de estado en JSON. Además, significa que internamente el servicio también comprobó el estado de su dependencia de la base de datos de SQL Server y que su estado se notificó como correcto.

## <a name="using-watchdogs"></a>Uso de guardianes

Un guardián es un servicio independiente que puede observar el estado y la carga en varios servicios, e informar del estado de los microservicios con una consulta con la biblioteca HealthChecks vista anteriormente. Esto puede ayudar a evitar errores que no se detectarían si se observase un único servicio. Los guardianes también son un buen lugar para hospedar código que lleve a cabo acciones correctoras para condiciones conocidas sin la intervención del usuario.

El ejemplo de eShopOnContainers contiene una página web que muestra informes de comprobación de estado de ejemplo, como se muestra en la figura 10-8. Se trata del guardián más sencillo que se puede tener, dado que lo único que hace es mostrar el estado de las aplicaciones web y los microservicios en eShopOnContainers. Normalmente, un guardián también realiza acciones cuando detecta estados no correctos.

![](./media/image8.png)

**Figura 10-8**. Informe de comprobación de estado de ejemplo en eShopOnContainers

En resumen, el middleware ASP.NET de la biblioteca HealthChecks de ASP.NET Core proporciona un punto de conexión para comprobación de estado único para cada microservicio. El middleware ejecutará todas las comprobaciones de estado definidas en él y devolverá un estado general que dependerá de todas esas comprobaciones.

La biblioteca HealthChecks es extensible mediante nuevas comprobaciones de estado de recursos externos futuros. Por ejemplo, se espera que en el futuro la biblioteca tenga comprobaciones de estado de Redis Cache y otras bases de datos. La biblioteca permite obtener informes de estado de varias dependencias de servicios o aplicaciones, que luego se podrán usar para llevar a cabo acciones basadas en las comprobaciones de estado.

## <a name="health-checks-when-using-orchestrators"></a>Comprobaciones de estado con orquestadores

Para supervisar la disponibilidad de los microservicios, los orquestadores como Docker Swarm, Kubernetes y Service Fabric realizan periódicamente comprobaciones de estado mediante el envío de solicitudes para probar los microservicios. Cuando un orquestador determina que el estado de un contenedor o servicio no es correcto, deja de enrutar las solicitudes a esa instancia. Normalmente también crea una nueva instancia de ese contenedor.

Por ejemplo, la mayoría de los orquestadores pueden utilizar comprobaciones de estado para administrar implementaciones sin tiempos de inactividad. Solo cuando el estado de un servicio o contenedor cambia a correcto, el orquestador empieza a enrutar el tráfico a las instancias de servicio o contenedor.

El seguimiento de estado es especialmente importante cuando un orquestador lleva a cabo una actualización de la aplicación. Algunos orquestadores (por ejemplo, Azure Service Fabric) actualizan los servicios en fases: por ejemplo, pueden actualizar una quinta parte de la superficie del clúster para cada actualización de la aplicación. El conjunto de nodos que se actualiza al mismo tiempo se conoce como *dominio de actualización*. Después de que cada dominio de actualización se haya actualizado y esté disponible para los usuarios, el dominio de actualización debe pasar las comprobaciones de estado antes de que la implementación se mueva al siguiente dominio de actualización.

Otro aspecto del estado del servicio es informar de las métricas del servicio. Se trata de una característica avanzada del modelo de estado de algunos orquestadores, como Service Fabric. Las métricas son importantes cuando se usa un orquestador porque se usan para equilibrar el uso de recursos. Las métricas también pueden ser un indicador del estado del sistema. Pongamos por ejemplo una aplicación que tenga muchos microservicios, y cada instancia informa sobre una métrica de solicitudes por segundo (RPS). Si un servicio está utilizando más recursos (memoria, procesador, etc.) que otro servicio, el orquestador puede mover las instancias del servicio en el clúster para intentar equilibrar el uso de los recursos.

Tenga en cuenta que si utiliza Azure Service Fabric, la plataforma proporciona su propio [modelo de seguimiento de estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), que es más avanzado que las comprobaciones de estado simples.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Supervisión avanzada: visualización, análisis y alertas

La parte final de la supervisión es visualizar la secuencia de eventos, generar informes sobre rendimiento de los servicios y emitir alertas cuando se detecta un problema. Para este aspecto de la supervisión se pueden usar diferentes soluciones.

Se pueden utilizar aplicaciones personalizadas simples que muestren el estado de los servicios, como la página personalizada que mostramos al explicar [HealthChecks de ASP.NET Core](https://github.com/aspnet/HealthChecks). O bien se pueden utilizar herramientas más avanzadas como Azure Application Insights y Operations Management Suite para generar alertas basadas en el flujo de eventos.

Por último, si se han almacenado todos los flujos de eventos, se puede utilizar Microsoft Power BI o una solución de terceros como Kibana o Splunk para visualizar los datos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Comprobaciones de estado de ASP.NET Core** (lanzamiento temprano) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Introducción a la supervisión de estado de Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Visión de la aplicación de Azure**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[Anterior] (implement-circuit-breaker-pattern.md) [Siguiente] (../secure-net-microservices-web-applications/index.md)
