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
# <a name="health-monitoring"></a><span data-ttu-id="91c6b-104">Supervisión de estado</span><span class="sxs-lookup"><span data-stu-id="91c6b-104">Health monitoring</span></span>

<span data-ttu-id="91c6b-105">Supervisión de estado puede permitir que la información de casi en tiempo real sobre el estado de los contenedores y microservicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="91c6b-106">Supervisión de estado es crítica para varios aspectos del funcionamiento microservicios y es especialmente importante cuando orchestrators realice actualizaciones de aplicación parcial en fases, tal como se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="91c6b-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="91c6b-107">Aplicaciones basadas en Microservicios utilizan a menudo latidos o comprobaciones de mantenimiento para que sus monitores de rendimiento, los programadores y orchestrators realizar un seguimiento de la cantidad de servicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="91c6b-108">Si los servicios no pueden enviar a algún tipo de señal "Soy activo", a petición o según una programación, la aplicación podría enfrentan riesgos al implementar las actualizaciones, o podría simplemente detectar errores demasiado tarde y no poder detener errores en cascada que pueden terminar en interrupciones importantes.</span><span class="sxs-lookup"><span data-stu-id="91c6b-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="91c6b-109">En el modelo típico, servicios envían informes sobre su estado y se agrega esa información para proporcionar una visión general del estado de mantenimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91c6b-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="91c6b-110">Si usas organizador, puede proporcionar información de estado al clúster de su orchestrator, para que el clúster puede actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="91c6b-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="91c6b-111">Si invierte en informes sobre el estado de alta calidad que se personaliza para la aplicación, puede detectar y corregir problemas de la aplicación en ejecución mucho más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="91c6b-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="91c6b-112">Implementación de mantenimiento comprueba en servicios principales de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91c6b-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="91c6b-113">Al desarrollar una aplicación de ASP.NET Core microservicio o web, puede usar una biblioteca denominada comprobaciones de estado desde el equipo de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="91c6b-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="91c6b-114">(A partir de mayo de 2017, una versión preliminar está disponible en GitHub).</span><span class="sxs-lookup"><span data-stu-id="91c6b-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="91c6b-115">Esta biblioteca es fácil de usar y proporciona características que permiten que validar que cualquier recurso externo específico necesario para la aplicación (por ejemplo, una base de datos de SQL Server o remota (API)) funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="91c6b-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="91c6b-116">Cuando se utiliza esta biblioteca, también puede decidir lo que significa que el recurso es correcto, tal y como se explica más adelante.</span><span class="sxs-lookup"><span data-stu-id="91c6b-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="91c6b-117">Para poder usar esta biblioteca, debe usar primero la biblioteca en su microservicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="91c6b-118">En segundo lugar, necesita una aplicación front-end que realiza consultas para los informes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="91c6b-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="91c6b-119">Aplicación front-end podría ser una aplicación informes personalizada, o podría ser organizador sí que puede actuar en consecuencia para los Estados de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="91c6b-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="91c6b-120">Usa la biblioteca de comprobaciones de estado en el back-end ASP.NET microservicios</span><span class="sxs-lookup"><span data-stu-id="91c6b-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="91c6b-121">Puede ver cómo se utiliza la biblioteca de comprobaciones de estado en la aplicación de ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="91c6b-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="91c6b-122">Para empezar, debe definir qué constituye un estado correcto para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="91c6b-123">En la aplicación de ejemplo, el microservicios están correcto si la API de microservicio es accesible a través de HTTP y si su base de datos de SQL Server relacionada también está disponible.</span><span class="sxs-lookup"><span data-stu-id="91c6b-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="91c6b-124">En el futuro, podrá instalar la biblioteca de comprobaciones de estado como un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="91c6b-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="91c6b-125">Pero cuando se redactó este documento, debe descargar y compile el código como parte de la solución.</span><span class="sxs-lookup"><span data-stu-id="91c6b-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="91c6b-126">Clonar el código disponible en https://github.com/aspnet/HealthChecks y copie las siguientes carpetas en la solución.</span><span class="sxs-lookup"><span data-stu-id="91c6b-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="91c6b-127">src/comunes</span><span class="sxs-lookup"><span data-stu-id="91c6b-127">src/common</span></span>
  - <span data-ttu-id="91c6b-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="91c6b-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="91c6b-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="91c6b-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="91c6b-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="91c6b-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="91c6b-131">También puede usar comprobaciones adicionales como los de Azure (Microsoft.Extensions.HealthChecks.AzureStorage), pero dado que esta versión de eShopOnContainers no tiene ninguna dependencia en Azure, no es necesario.</span><span class="sxs-lookup"><span data-stu-id="91c6b-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="91c6b-132">Las comprobaciones de estado ASP.NET, no es necesario porque eShopOnContainers se basa en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="91c6b-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="91c6b-133">Figura 10-6 muestra la biblioteca de comprobaciones de estado en Visual Studio, listo para su uso como un bloque de creación por cualquier microservicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="91c6b-134">**Figura 6-10**.</span><span class="sxs-lookup"><span data-stu-id="91c6b-134">**Figure 10-6**.</span></span> <span data-ttu-id="91c6b-135">Código de origen de biblioteca de comprobaciones de estado de núcleo ASP.NET en una solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="91c6b-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="91c6b-136">Como se mencionó anteriormente, lo primero que hay que hacer en cada proyecto de microservicio es agregar una referencia a las tres bibliotecas de comprobaciones de estado.</span><span class="sxs-lookup"><span data-stu-id="91c6b-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="91c6b-137">A continuación, agregue las acciones de comprobación de mantenimiento que desea realizar en ese microservicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="91c6b-138">Estas acciones son básicamente las dependencias en otros microservicios (HttpUrlCheck) o las bases de datos (actualmente SqlCheck\* para bases de datos de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="91c6b-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="91c6b-139">Para agregar la acción dentro de la clase de inicio de cada microservicio ASP.NET o una aplicación web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="91c6b-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="91c6b-140">Cada servicio o aplicación web debe configurarse mediante la adición de todas sus dependencias HTTP o de base de datos como un método de AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="91c6b-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="91c6b-141">Por ejemplo, la aplicación web MVC de eShopOnContainers depende de muchos servicios, por lo tanto, tiene varios métodos de AddCheck que se agregan a las comprobaciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="91c6b-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="91c6b-142">Por ejemplo, en el código siguiente puede ver cómo el catálogo microservicio agrega una dependencia en su base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91c6b-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="91c6b-143">Sin embargo, la aplicación web MVC de eShopOnContainers tiene varias dependencias en el resto de la microservicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="91c6b-144">Por lo tanto, llama a un método AddUrlCheck para cada microservicio, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91c6b-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="91c6b-145">Por lo tanto, un microservicio no proporcionará un estado "correcto" hasta que todas las comprobaciones también son correctos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="91c6b-146">Si la microservicio no tiene una dependencia en un servicio o en SQL Server, solo tiene que debe agregar una comprobación de Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="91c6b-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="91c6b-147">El código siguiente procede de la microservicio basket.api eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="91c6b-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="91c6b-148">(La microservicio cesta usa la caché en Redis, pero la biblioteca aún no incluye un proveedor de comprobación de mantenimiento de Redis.)</span><span class="sxs-lookup"><span data-stu-id="91c6b-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="91c6b-149">Para que un servicio o aplicación web exponer el extremo de la comprobación de mantenimiento, tiene que habilitar la UseHealthChecks (\[*url\_para\_estado\_comprueba*\]) extensión método.</span><span class="sxs-lookup"><span data-stu-id="91c6b-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="91c6b-150">Este método se pasa en el WebHostBuilder nivel en el método main de la clase de programa de la aplicación web o servicio ASP.NET Core, justo después de UseKestrel tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="91c6b-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

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

<span data-ttu-id="91c6b-151">El proceso funciona del siguiente modo: cada microservicio expone el extremo/HC.</span><span class="sxs-lookup"><span data-stu-id="91c6b-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="91c6b-152">Ese punto de conexión se crea en la biblioteca de comprobaciones de estado ASP.NET Core middleware.</span><span class="sxs-lookup"><span data-stu-id="91c6b-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="91c6b-153">Cuando se invoca ese punto de conexión, se ejecuta todas las comprobaciones de mantenimiento que se configuran en el método AddHealthChecks de la clase de inicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="91c6b-154">El método UseHealthChecks espera un puerto o una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="91c6b-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="91c6b-155">Ese puerto o la ruta de acceso es el punto de conexión se utiliza para comprobar el estado de mantenimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="91c6b-156">Por ejemplo, el catálogo de microservicio usa la ruta de acceso/HC.</span><span class="sxs-lookup"><span data-stu-id="91c6b-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="91c6b-157">Almacenamiento en caché las respuestas de comprobación de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="91c6b-157">Caching health check responses</span></span>

<span data-ttu-id="91c6b-158">Puesto que no desea producir una denegación de servicio (DoS) en los servicios, o simplemente no desea afectar el rendimiento del servicio mediante la comprobación de recursos con demasiada frecuencia, puede almacenar en caché la devuelve y configurar una duración de caché para cada comprobación de estado.</span><span class="sxs-lookup"><span data-stu-id="91c6b-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="91c6b-159">De forma predeterminada, la duración de la caché internamente se establece en 5 minutos, pero puede cambiar esa duración de la caché en cada comprobación de estado, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="91c6b-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="91c6b-160">Consultar el microservicios informe sobre su estado de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="91c6b-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="91c6b-161">Cuando haya configurado las comprobaciones de mantenimiento como se describe en este caso, una vez que se ejecuta el microservicio en Docker, puede comprobar directamente desde un explorador si es correcto.</span><span class="sxs-lookup"><span data-stu-id="91c6b-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="91c6b-162">(Esto requiere que se va a publicar el puerto de contenedor fuera del host Docker, por lo que puede tener acceso al contenedor a través de localhost o la dirección IP externa host de Docker). Figura 10-7 muestra una solicitud en un explorador y la respuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="91c6b-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="91c6b-163">**Figura 10-7**.</span><span class="sxs-lookup"><span data-stu-id="91c6b-163">**Figure 10-7**.</span></span> <span data-ttu-id="91c6b-164">Comprobar el estado de mantenimiento de un único servicio desde un explorador</span><span class="sxs-lookup"><span data-stu-id="91c6b-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="91c6b-165">En esa prueba, puede ver que el microservicio catalog.api (que se ejecuta en el puerto 5101) es correcto, devuelve el código de estado HTTP 200 e información de estado en JSON.</span><span class="sxs-lookup"><span data-stu-id="91c6b-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="91c6b-166">También significa que internamente el servicio también comprueba el estado de su dependencia de la base de datos de SQL Server y que la comprobación de mantenimiento se se notificó como correcto.</span><span class="sxs-lookup"><span data-stu-id="91c6b-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="91c6b-167">Usar watchdogs</span><span class="sxs-lookup"><span data-stu-id="91c6b-167">Using watchdogs</span></span>

<span data-ttu-id="91c6b-168">A continuación se proporciona es un servicio independiente que se puede ver el estado y la carga entre los servicios y el estado del informe sobre el microservicios mediante una consulta con la biblioteca de comprobaciones de estado que se presentaron anteriormente.</span><span class="sxs-lookup"><span data-stu-id="91c6b-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="91c6b-169">Esto puede ayudar a evitar errores que no se detectan en función de la vista de un único servicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="91c6b-170">Watchdogs también son un buen lugar para alojar el código que puede realizar acciones correctoras para condiciones sin interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="91c6b-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="91c6b-171">El ejemplo eShopOnContainers contiene una página web que muestra los informes de comprobación de estado de ejemplo, como se muestra en la figura 10-8.</span><span class="sxs-lookup"><span data-stu-id="91c6b-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="91c6b-172">Se trata de la vigilancia más sencilla podría tener, debido a que todo lo que hace es muestra el estado de las aplicaciones web y microservicios en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="91c6b-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="91c6b-173">Normalmente un guardián también realiza acciones cuando detecta Estados no correctos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="91c6b-174">**Figura 8-10**.</span><span class="sxs-lookup"><span data-stu-id="91c6b-174">**Figure 10-8**.</span></span> <span data-ttu-id="91c6b-175">Informe de comprobación de estado de ejemplo en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="91c6b-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="91c6b-176">En resumen, el middleware ASP.NET de la biblioteca de comprobaciones de estado de ASP.NET Core proporciona un punto de conexión de la comprobación de estado único para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="91c6b-177">Esto ejecutará todas las comprobaciones de mantenimiento definidas en él y devolver un estado de mantenimiento general según todas las comprobaciones de esos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="91c6b-178">La biblioteca de comprobaciones de estado es extensible a través de nuevas comprobaciones de mantenimiento de recursos externos futuras.</span><span class="sxs-lookup"><span data-stu-id="91c6b-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="91c6b-179">Por ejemplo, se espera que en el futuro la biblioteca tendrá comprobaciones de mantenimiento de caché en Redis y de otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="91c6b-180">Permite que la biblioteca de informes por varias dependencias de servicio o aplicación de estado y, a continuación, puede realizar acciones basadas en las comprobaciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="91c6b-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="91c6b-181">Comprobaciones de mantenimiento cuando se utiliza orchestrators</span><span class="sxs-lookup"><span data-stu-id="91c6b-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="91c6b-182">Para supervisar la disponibilidad de su microservicios, orchestrators como Docker Swarm, Kubernetes y Service Fabric periódicamente realizan comprobaciones de mantenimiento mediante el envío de solicitudes para probar el microservicios.</span><span class="sxs-lookup"><span data-stu-id="91c6b-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="91c6b-183">Cuando un orchestrator determina que un contenedor de servicios está en mal estado, deja de enrutar las solicitudes a esa instancia.</span><span class="sxs-lookup"><span data-stu-id="91c6b-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="91c6b-184">Normalmente también crea una nueva instancia de ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="91c6b-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="91c6b-185">Por ejemplo, orchestrators mayoría pueden utilizar comprobaciones de estado para administrar implementaciones sin tiempos de inactividad.</span><span class="sxs-lookup"><span data-stu-id="91c6b-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="91c6b-186">Solo cuando el estado de cambia de un servicio o contenedor a correcto será el orchestrator iniciar enrutar el tráfico a las instancias de servicio o el contenedor.</span><span class="sxs-lookup"><span data-stu-id="91c6b-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="91c6b-187">Supervisión de estado es especialmente importante cuando organizador lleva a cabo una actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91c6b-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="91c6b-188">Algunos orchestrators (por ejemplo, Azure Service Fabric) update services en fases, por ejemplo, puede actualizar una quinta parte de la superficie de clúster para cada actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91c6b-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="91c6b-189">El conjunto de nodos que se actualiza al mismo tiempo se conoce como un *dominio de actualización*.</span><span class="sxs-lookup"><span data-stu-id="91c6b-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="91c6b-190">Después de cada dominio de actualización se ha actualizado y está disponible para los usuarios, ese dominio de actualización debe pasar las comprobaciones de mantenimiento antes de la implementación se mueve al siguiente dominio de actualización.</span><span class="sxs-lookup"><span data-stu-id="91c6b-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="91c6b-191">Otro aspecto del estado del servicio está informando de métricas desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="91c6b-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="91c6b-192">Se trata de una característica avanzada del modelo de mantenimiento de algunos orchestrators, como Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="91c6b-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="91c6b-193">Las métricas son importantes cuando se usa un orchestrator porque se usan para equilibrar el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="91c6b-194">Las métricas también pueden ser un indicador del estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="91c6b-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="91c6b-195">Por ejemplo, podría tener una aplicación que tenga muchos microservicios, y cada instancia informa sobre una métrica de solicitudes por segundo (RPS).</span><span class="sxs-lookup"><span data-stu-id="91c6b-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="91c6b-196">Si un servicio está usando más recursos (memoria, procesador, etc.) que otro servicio, el orchestrator puede moverse instancias de servicio del clúster para intentar mantener incluso el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="91c6b-197">Tenga en cuenta que si utilizas Azure Service Fabric, proporciona su propio [modelo de supervisión de estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), que es más avanzado que comprobaciones de estado simple.</span><span class="sxs-lookup"><span data-stu-id="91c6b-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="91c6b-198">Supervisión avanzadas: visualización, análisis y alertas</span><span class="sxs-lookup"><span data-stu-id="91c6b-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="91c6b-199">Visualiza la secuencia de eventos, generación de informes en el rendimiento del servicio y emitir alertas cuando se detecta un problema en la parte final de la supervisión.</span><span class="sxs-lookup"><span data-stu-id="91c6b-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="91c6b-200">Puede usar diferentes soluciones para este aspecto de supervisión.</span><span class="sxs-lookup"><span data-stu-id="91c6b-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="91c6b-201">Puede usar aplicaciones personalizadas simples que muestra el estado de los servicios, como la página personalizada se mostraba cuando se explican [comprobaciones de estado de ASP.NET Core](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="91c6b-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="91c6b-202">O bien, puede utilizar las herramientas más avanzadas como la visión de la aplicación de Azure y Operations Management Suite para generar alertas basadas en el flujo de eventos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="91c6b-203">Por último, si se almacenan todos los flujos de eventos, puede utilizar Microsoft Power BI o una solución de terceros como Kibana o Splunk para visualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="91c6b-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="91c6b-204">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="91c6b-204">Additional resources</span></span>

-   <span data-ttu-id="91c6b-205">**Comprobaciones de estado de ASP.NET Core** (lanzamiento temprano) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="91c6b-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="91c6b-206">**Introducción a la supervisión de estado de Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="91c6b-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="91c6b-207">**Aplicación de Azure Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="91c6b-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="91c6b-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="91c6b-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="91c6b-209">[Anterior] (implementar-circuito-separador-pattern.md) [siguiente] (.. /Secure-NET-microservices-Web-Applications/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="91c6b-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
