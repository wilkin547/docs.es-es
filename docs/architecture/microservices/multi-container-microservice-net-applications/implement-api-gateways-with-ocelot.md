---
title: Implementación de puertas de enlace de API con Ocelot
description: Obtenga información sobre cómo implementar puertas de enlace de API con Ocelot y cómo usar Ocelot en un entorno basado en contenedores.
ms.date: 03/02/2020
ms.openlocfilehash: 3611ffa7a163ff632ca854fafb910fcd3e228306
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358991"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="73648-103">Implementación de puertas de enlace de API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-103">Implement API Gateways with Ocelot</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73648-104">Actualmente, la aplicación de microservicios de referencia [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) usa características proporcionadas por [Envoy](https://www.envoyproxy.io/) para implementar la puerta de enlace de API en lugar de [Ocelot](https://github.com/ThreeMammals/Ocelot), al que ya se ha hecho referencia anteriormente.</span><span class="sxs-lookup"><span data-stu-id="73648-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is currently using features provided by [Envoy](https://www.envoyproxy.io/) to implement the API Gateway instead of the earlier referenced [Ocelot](https://github.com/ThreeMammals/Ocelot).</span></span>
> <span data-ttu-id="73648-105">El motivo de esta decisión de diseño es la compatibilidad integrada de Envoy con el protocolo WebSocket, necesaria para las nuevas comunicaciones entre servicios de gRPC implementadas en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73648-105">We made this design choice because of Envoy's built-in support for the WebSocket protocol, required by the new gRPC inter-service communications implemented in eShopOnContainers.</span></span>
> <span data-ttu-id="73648-106">Sin embargo, hemos conservado esta sección en la guía para que pueda considerar Ocelot como una puerta de enlace de API sencilla, compatible, ligera y adecuada para escenarios de nivel de producción.</span><span class="sxs-lookup"><span data-stu-id="73648-106">However, we've retained this section in the guide so you can consider Ocelot as a simple, capable, and lightweight API Gateway suitable for production-grade scenarios.</span></span>
> <span data-ttu-id="73648-107">Además, la versión más reciente de Ocelot contiene un cambio importante en su esquema JSON.</span><span class="sxs-lookup"><span data-stu-id="73648-107">Also, latest Ocelot version contains a breaking change on its json schema.</span></span> <span data-ttu-id="73648-108">Considere el uso de Ocelot < v16.0.0 o use los valores Routes clave en lugar de ReRoutes.</span><span class="sxs-lookup"><span data-stu-id="73648-108">Consider using Ocelot < v16.0.0, or use the key Routes instead of ReRoutes.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="73648-109">Arquitectura y diseño de las puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="73648-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="73648-110">En el diagrama de arquitectura siguiente se muestra cómo se implementaron las puertas de enlace de API con Ocelot en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73648-110">The following architecture diagram shows how API Gateways were implemented with Ocelot in eShopOnContainers.</span></span>

![Diagrama que muestra la arquitectura de eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

<span data-ttu-id="73648-112">**Figura 6-28**.</span><span class="sxs-lookup"><span data-stu-id="73648-112">**Figure 6-28**.</span></span> <span data-ttu-id="73648-113">Arquitectura de eShopOnContainers con puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="73648-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="73648-114">En ese diagrama se muestra cómo se implementa toda la aplicación en un único host de Docker o equipo de desarrollo con "Docker para Windows" o "Docker para Mac".</span><span class="sxs-lookup"><span data-stu-id="73648-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with "Docker for Windows" or "Docker for Mac".</span></span> <span data-ttu-id="73648-115">Pero la implementación en cualquier orquestador sería similar, aunque cualquiera de los contenedores del diagrama se podría escalar horizontalmente en el orquestador.</span><span class="sxs-lookup"><span data-stu-id="73648-115">However, deploying into any orchestrator would be similar, but any container in the diagram could be scaled out in the orchestrator.</span></span>

<span data-ttu-id="73648-116">Además, los recursos de infraestructura como bases de datos, caché y agentes de mensajes se deberían descargar del orquestador e implementarse en sistemas de alta disponibilidad para la infraestructura, como Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus o cualquier solución de agrupación en clústeres de alta disponibilidad local.</span><span class="sxs-lookup"><span data-stu-id="73648-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="73648-117">Como también se puede observar en el diagrama, tener varias puertas de enlace de API permite que varios equipos de desarrollo sean autónomos (en este caso, las características de Marketing frente a las de Shopping) al desarrollar e implementar sus microservicios además de sus propias puertas de enlace de API relacionadas.</span><span class="sxs-lookup"><span data-stu-id="73648-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="73648-118">Si tuviera una sola puerta de enlace de API monolítica, sería un único punto para actualizar por varios equipos de desarrollo, que podrían acoplar todos los microservicios con un único elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73648-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="73648-119">Ampliando mucho más el diseño, en ocasiones una puerta de enlace de API específica también se puede limitar a un microservicio empresarial individual en función de la arquitectura elegida.</span><span class="sxs-lookup"><span data-stu-id="73648-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="73648-120">El tener los límites de la puerta de enlace de API dictados por el negocio o el dominio ayuda a lograr un mejor diseño.</span><span class="sxs-lookup"><span data-stu-id="73648-120">Having the API Gateway's boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="73648-121">Por ejemplo, la especificidad del nivel de puerta de enlace de API puede ser especialmente útil para aplicaciones de interfaz de usuario compuesta más avanzadas que se basan en microservicios, dado que el concepto de una puerta de enlace de API específica es similar a un servicio de composición de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="73648-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="73648-122">Nos adentramos en más detalles en la sección anterior, [Creación de interfaz de usuario compuesta basada en microservicios](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="73648-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="73648-123">Como punto clave, para muchas aplicaciones de tamaño medio y grande, el uso de una puerta de enlace de API personalizada suele ser un enfoque adecuado, pero no como un único agregador monolítico ni una única puerta de enlace de API personalizada central, a menos que esa puerta de enlace de API permita varias áreas de configuración independientes para que los diferentes equipos de desarrollo creen microservicios autónomos.</span><span class="sxs-lookup"><span data-stu-id="73648-123">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a><span data-ttu-id="73648-124">Microservicios y contenedores de ejemplo para redistribuir entre las puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="73648-124">Sample microservices/containers to reroute through the API Gateways</span></span>

<span data-ttu-id="73648-125">Como ejemplo, eShopOnContainers tiene aproximadamente seis tipos de microservicio internos que se tienen que publicar entre las puertas de enlace de API, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Captura de pantalla de la carpeta Services con sus subcarpetas.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

<span data-ttu-id="73648-127">**Figura 6-29**.</span><span class="sxs-lookup"><span data-stu-id="73648-127">**Figure 6-29**.</span></span> <span data-ttu-id="73648-128">Carpetas de microservicio en la solución eShopOnContainers en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73648-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="73648-129">En cuanto al servicio Identity, en el diseño se excluye del enrutamiento de puerta de enlace de API, porque es el único interés transversal del sistema, aunque con Ocelot también es posible incluirlo como parte de las listas de reenrutamiento.</span><span class="sxs-lookup"><span data-stu-id="73648-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="73648-130">Todos estos servicios se implementan actualmente como servicios de API web de ASP.NET Core, como se desprende del código.</span><span class="sxs-lookup"><span data-stu-id="73648-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="73648-131">Vamos a centrarnos en uno de los microservicios, por ejemplo, el código del microservicio Catalog.</span><span class="sxs-lookup"><span data-stu-id="73648-131">Let's focus on one of the microservices like the Catalog microservice code.</span></span>

![Captura de pantalla del Explorador de soluciones que muestra el contenido del proyecto Catalog.API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

<span data-ttu-id="73648-133">**Figura 6-30**.</span><span class="sxs-lookup"><span data-stu-id="73648-133">**Figure 6-30**.</span></span> <span data-ttu-id="73648-134">Microservicio de API web de ejemplo (microservicio Catalog)</span><span class="sxs-lookup"><span data-stu-id="73648-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="73648-135">Puede ver que el microservicio Catalog es un proyecto de API web de ASP.NET Core típico con varios controladores y métodos, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="73648-136">La solicitud HTTP terminará ejecutando ese tipo de código de C# que accede a la base de datos de microservicios además de cualquier otra acción requerida.</span><span class="sxs-lookup"><span data-stu-id="73648-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="73648-137">En lo que respecta a la dirección URL del microservicio, cuando los contenedores se implementan en el equipo de desarrollo local (el host de Docker local), el contenedor de cada microservicio siempre tiene un puerto interno (normalmente el puerto 80) especificado en su Dockerfile, como en este caso:</span><span class="sxs-lookup"><span data-stu-id="73648-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice's container always has an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="73648-138">El puerto 80 que se muestra en el código es interno dentro del host de Docker, por lo que las aplicaciones cliente no pueden acceder a él.</span><span class="sxs-lookup"><span data-stu-id="73648-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="73648-139">Las aplicaciones cliente solo pueden acceder a los puertos externos (si existen) publicados al implementar con `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="73648-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="73648-140">Esos puertos externos no se deben publicar al implementar en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="73648-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="73648-141">Por esto precisamente se va a usar la puerta de enlace de API, para evitar la comunicación directa entre las aplicaciones cliente y los microservicios.</span><span class="sxs-lookup"><span data-stu-id="73648-141">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="73648-142">Pero durante el desarrollo, le interesa acceder directamente al contenedor o microservicio, y ejecutarlo a través de Swagger.</span><span class="sxs-lookup"><span data-stu-id="73648-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="73648-143">Por eso en eShopOnContainers se siguen especificando los puertos externos, aunque la puerta de enlace de API o las aplicaciones cliente no los vayan a usar.</span><span class="sxs-lookup"><span data-stu-id="73648-143">That's why in eShopOnContainers, the external ports are still specified even when they won't be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="73648-144">Este es un ejemplo del archivo `docker-compose.override.yml` del microservicio Catalog:</span><span class="sxs-lookup"><span data-stu-id="73648-144">Here's an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="73648-145">Puede ver cómo en la configuración de docker-compose.override.yml el puerto interno del contenedor Catalog es el puerto 80, pero el puerto para el acceso externo es 5101.</span><span class="sxs-lookup"><span data-stu-id="73648-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="73648-146">Pero la aplicación no debería usar este puerto si emplea una puerta de enlace de API, solo para depurar, ejecutar y probar el microservicio Catalog.</span><span class="sxs-lookup"><span data-stu-id="73648-146">But this port shouldn't be used by the application when using an API Gateway, only to debug, run, and test just the Catalog microservice.</span></span>

<span data-ttu-id="73648-147">Normalmente no se implementa con docker-compose en un entorno de producción, ya que el entorno de implementación de producción correcto para los microservicios es un orquestador como Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="73648-147">Normally, you won't be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="73648-148">Cuando se implementa en esos entornos, se usan otros archivos de configuración en los que no se publica directamente ningún puerto externo para los microservicios, pero siempre se usa el proxy inverso de la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-148">When deploying to those environments you use different configuration files where you won't publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="73648-149">Ejecute el microservicio Catalog en el host de Docker local.</span><span class="sxs-lookup"><span data-stu-id="73648-149">Run the catalog microservice in your local Docker host.</span></span> <span data-ttu-id="73648-150">Ejecute la solución eShopOnContainers completa desde Visual Studio (ejecuta todos los servicios de los archivos docker-compose) o inicie el microservicio Catalog con el comando docker-compose siguiente en CMD o PowerShell desde la carpeta donde están `docker-compose.yml` y `docker-compose.override.yml`.</span><span class="sxs-lookup"><span data-stu-id="73648-150">Either run the full eShopOnContainers solution from Visual Studio (it runs all the services in the docker-compose files), or start the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and `docker-compose.override.yml` are placed.</span></span>

```console
docker-compose run --service-ports catalog-api
```

<span data-ttu-id="73648-151">Este comando solo ejecuta el contenedor del servicio catalog-api, además de las dependencias que se especifican en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73648-151">This command only runs the catalog-api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="73648-152">En este caso, el contenedor de SQL Server y el contenedor de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="73648-152">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="73648-153">Después, puede acceder directamente al microservicio Catalog y ver sus métodos a través de la interfaz de usuario de Swagger, que accede directamente a través de ese puerto "externo", en este caso `http://localhost:5101/swagger`:</span><span class="sxs-lookup"><span data-stu-id="73648-153">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that "external" port, in this case `http://localhost:5101/swagger`:</span></span>

![Captura de pantalla de la interfaz de usuario de Swagger que muestra la API REST Catalog.API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

<span data-ttu-id="73648-155">**Figura 6-31**.</span><span class="sxs-lookup"><span data-stu-id="73648-155">**Figure 6-31**.</span></span> <span data-ttu-id="73648-156">Probar el microservicio Catalog con su interfaz de usuario de Swagger</span><span class="sxs-lookup"><span data-stu-id="73648-156">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="73648-157">En este momento, podría establecer un punto de interrupción en el código de C# en Visual Studio, probar el microservicio con los métodos expuestos en la interfaz de usuario de Swagger y, por último, limpiar todo con el comando `docker-compose down`.</span><span class="sxs-lookup"><span data-stu-id="73648-157">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="73648-158">Pero la comunicación de acceso directo al microservicio, en este caso a través del puerto externo 5101, es precisamente lo que se quiere evitar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73648-158">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="73648-159">Y se puede evitar si se establece el nivel adicional de direccionamiento indirecto de la puerta de enlace de API (en este caso, Ocelot).</span><span class="sxs-lookup"><span data-stu-id="73648-159">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="73648-160">De ese modo, la aplicación cliente no accede directamente al microservicio.</span><span class="sxs-lookup"><span data-stu-id="73648-160">That way, the client app won't directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="73648-161">Implementación de las puertas de enlace de API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-161">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="73648-162">Ocelot es básicamente un conjunto de software intermedio que se puede aplicar en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="73648-162">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="73648-163">Ocelot está diseñado para trabajar solamente con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73648-163">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="73648-164">La versión más reciente del paquete tiene como destino `.NETCoreApp 3.1` y, por tanto, no es adecuada en aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73648-164">The latest version of the package targets `.NETCoreApp 3.1` and hence it is not suitable for .NET Framework applications.</span></span>

<span data-ttu-id="73648-165">Ocelot y sus dependencias se instalan en el proyecto de ASP.NET Core con el [paquete NuGet de Ocelot](https://www.nuget.org/packages/Ocelot/), desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="73648-165">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="73648-166">En eShopOnContainers, la implementación de la puerta de enlace de API es un proyecto ASP.NET Core WebHost simple, y el middleware de Ocelot controla todas las características de la puerta de enlace de API, como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="73648-166">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middleware handles all the API Gateway features, as shown in the following image:</span></span>

![Captura de pantalla del Explorador de soluciones que muestra el proyecto de puerta de enlace de API de Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

<span data-ttu-id="73648-168">**Figura 6-32**.</span><span class="sxs-lookup"><span data-stu-id="73648-168">**Figure 6-32**.</span></span> <span data-ttu-id="73648-169">El proyecto base de OcelotApiGw en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73648-169">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="73648-170">Este proyecto ASP.NET Core WebHost se compila básicamente con dos archivos sencillos: `Program.cs` y `Startup.cs`.</span><span class="sxs-lookup"><span data-stu-id="73648-170">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="73648-171">El archivo Program.cs solo tiene que crear y configurar el típico BuildWebHost de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73648-171">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="73648-172">Aquí, lo importante para Ocelot es el archivo `configuration.json` que se debe proporcionar al generador a través del método `AddJsonFile()`.</span><span class="sxs-lookup"><span data-stu-id="73648-172">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="73648-173">Ese archivo `configuration.json` es donde se especifican todas las redistribuciones de la puerta de enlace de API, es decir, los puntos de conexión externos con puertos específicos y los puntos de conexión internos correlacionados, que normalmente usan otros puertos.</span><span class="sxs-lookup"><span data-stu-id="73648-173">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="73648-174">En la configuración hay dos secciones.</span><span class="sxs-lookup"><span data-stu-id="73648-174">There are two sections to the configuration.</span></span> <span data-ttu-id="73648-175">Una matriz de ReRoutes y un elemento GlobalConfiguration.</span><span class="sxs-lookup"><span data-stu-id="73648-175">An array of ReRoutes and a GlobalConfiguration.</span></span> <span data-ttu-id="73648-176">Los objetos ReRoutes indican a Ocelot cómo tratar una solicitud ascendente.</span><span class="sxs-lookup"><span data-stu-id="73648-176">The ReRoutes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="73648-177">GlobalConfiguration permite invalidaciones de los valores específicos de ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73648-177">The Global configuration allows overrides of ReRoute specific settings.</span></span> <span data-ttu-id="73648-178">Es útil si no quiere administrar una gran cantidad de valores específicos de ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73648-178">It's useful if you don't want to manage lots of ReRoute specific settings.</span></span>

<span data-ttu-id="73648-179">Este es un ejemplo simplificado del [archivo de configuración de ReRoute](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) de una de las puertas de enlace de API de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73648-179">Here's a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="73648-180">La funcionalidad principal de una puerta de enlace de API de Ocelot consiste en aceptar solicitudes HTTP entrantes y reenviarlas a un servicio de nivel inferior, actualmente como otra solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="73648-180">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="73648-181">Ocelot describe el enrutamiento de una solicitud a otra como un elemento ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73648-181">Ocelot's describes the routing of one request to another as a ReRoute.</span></span>

<span data-ttu-id="73648-182">Por ejemplo, vamos a centrarnos en uno de los elementos ReRoute del archivo configuration.json anterior, la configuración del microservicio Basket.</span><span class="sxs-lookup"><span data-stu-id="73648-182">For instance, let's focus on one of the ReRoutes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="73648-183">DownstreamPathTemplate, Scheme y DownstreamHostAndPorts forman la dirección URL de microservicio interna a la que se va a reenviar esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="73648-183">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="73648-184">El puerto es el puerto interno que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="73648-184">The port is the internal port used by the service.</span></span> <span data-ttu-id="73648-185">Al usar contenedores, el puerto se especifica en su Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="73648-185">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="73648-186">`Host` es un nombre de servicio que depende de la resolución de nombres de servicio que se use.</span><span class="sxs-lookup"><span data-stu-id="73648-186">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="73648-187">Cuando se usa docker-compose, los nombres de los servicios los proporciona el host de Docker, que usa los nombres de servicio proporcionados en los archivos docker-compose.</span><span class="sxs-lookup"><span data-stu-id="73648-187">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="73648-188">Si se usa un orquestador como Kubernetes o Service Fabric, ese nombre se debe resolver mediante DNS o la resolución de nombres proporcionada por cada orquestador.</span><span class="sxs-lookup"><span data-stu-id="73648-188">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="73648-189">DownstreamHostAndPorts es una matriz que contiene el host y el puerto de los servicios de nivel inferior a los que se quieren reenviar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="73648-189">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="73648-190">Normalmente esto solo contendrá una entrada, pero a veces es posible que quiera equilibrar la carga de las solicitudes a los servicios de nivel inferior y Ocelot permite agregar más de una entrada y después seleccionar un equilibrador de carga.</span><span class="sxs-lookup"><span data-stu-id="73648-190">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="73648-191">Pero si se usa Azure y un orquestador, probablemente una idea mejor sea equilibrar la carga con la infraestructura de nube y de orquestador.</span><span class="sxs-lookup"><span data-stu-id="73648-191">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="73648-192">UpstreamPathTemplate es la dirección URL que Ocelot usará para identificar qué DownstreamPathTemplate se va a usar para una solicitud determinada desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="73648-192">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="73648-193">Por último, se usa UpstreamHttpMethod para que Ocelot pueda distinguir entre diferentes solicitudes (GET, POST, PUT) a la misma dirección URL.</span><span class="sxs-lookup"><span data-stu-id="73648-193">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="73648-194">En este momento, podría tener una única puerta de enlace de API de Ocelot (ASP.NET Core WebHost) con uno o [varios archivos configuration.json combinados](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files), o bien almacenar la [configuración en un almacén de Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="73648-194">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="73648-195">Pero como se mencionó en las secciones de arquitectura y diseño, si realmente quiere tener microservicios autónomos, podría ser mejor dividir esa única puerta de enlace de API monolítica en varias puertas de enlace de API o BFF (back-end para front-end).</span><span class="sxs-lookup"><span data-stu-id="73648-195">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="73648-196">Para ello, vamos a ver cómo se implementa ese enfoque con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="73648-196">For that purpose, let's see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="73648-197">Uso de una sola imagen de contenedor de Docker para ejecutar varios tipos de contenedor de puerta de enlace de API y BFF</span><span class="sxs-lookup"><span data-stu-id="73648-197">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="73648-198">En eShopOnContainers, se usa una sola imagen de contenedor de Docker con la puerta de enlace de API de Ocelot pero, después, en tiempo de ejecución, se crean otros contenedores o servicios para cada tipo de puerta de enlace de API o BFF al proporcionar otro archivo configuration.json mediante un volumen de Docker para acceder a una carpeta distinta del equipo para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="73648-198">In eShopOnContainers, we're using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![Diagrama de una sola imagen de Docker de puerta de enlace de Ocelot para todas las puertas de enlace de API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

<span data-ttu-id="73648-200">**Figura 6-33**.</span><span class="sxs-lookup"><span data-stu-id="73648-200">**Figure 6-33**.</span></span> <span data-ttu-id="73648-201">Volver a usar una única imagen de Docker de Ocelot entre varios tipos de puerta de enlace de API</span><span class="sxs-lookup"><span data-stu-id="73648-201">Reusing a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="73648-202">En eShopOnContainers, la "imagen de Docker de puerta de enlace de API genérica" se crea con el proyecto denominado "OcelotApiGw" y el nombre de imagen "eshop/ocelotapigw" que se especifica en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73648-202">In eShopOnContainers, the "Generic Ocelot API Gateway Docker Image" is created with the project named 'OcelotApiGw' and the image name "eshop/ocelotapigw" that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="73648-203">Después, al implementar en Docker, habrá cuatro contenedores de puerta de enlace de API que se crean a partir de esa misma imagen de Docker, como se muestra en el extracto siguiente del archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73648-203">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="73648-204">Además, como se puede ver en el archivo docker-compose.override.yml siguiente, la única diferencia entre esos contenedores de puerta de enlace de API es el archivo de configuración de Ocelot, que es diferente para cada contenedor de servicios y que se especifica en tiempo de ejecución a través de un volumen de Docker.</span><span class="sxs-lookup"><span data-stu-id="73648-204">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="73648-205">Debido al código anterior, y como se muestra en el Explorador de Visual Studio a continuación, el único archivo necesario para definir cada puerta de enlace de API empresarial específica o BFF es simplemente un archivo configuration.json, dado que las cuatro puertas de enlace de API se basan en la misma imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="73648-205">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![Captura de pantalla que muestra todas las puertas de enlace de API con los archivos configuration.json.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

<span data-ttu-id="73648-207">**Figura 6-34**.</span><span class="sxs-lookup"><span data-stu-id="73648-207">**Figure 6-34**.</span></span> <span data-ttu-id="73648-208">El único archivo necesario para definir cada puerta de enlace de API y BFF con Ocelot es un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="73648-208">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="73648-209">Al dividir la puerta de enlace de API en varias, cada equipo de desarrollo centrado en otros subconjuntos de microservicios puede administrar sus propias puertas de enlace de API mediante archivos de configuración de Ocelot independientes.</span><span class="sxs-lookup"><span data-stu-id="73648-209">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="73648-210">Además, al mismo tiempo pueden reutilizar la misma imagen de Docker de Ocelot.</span><span class="sxs-lookup"><span data-stu-id="73648-210">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="73648-211">Ahora, si ejecuta eShopOnContainers con las puertas de enlace de API (incluidas de forma predeterminada en VS al abrir la solución eShopOnContainers-ServicesAndWebApps.sln o al ejecutar "docker-compose up"), se ejecutan las rutas de ejemplo siguientes.</span><span class="sxs-lookup"><span data-stu-id="73648-211">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running "docker-compose up"), the following sample routes will be performed.</span></span>

<span data-ttu-id="73648-212">Por ejemplo, cuando se visita la dirección URL de nivel superior `http://localhost:5202/api/v1/c/catalog/items/2/` que proporciona la puerta de enlace de API webshoppingapigw, se obtiene el mismo resultado de la dirección URL de nivel inferior interna `http://catalog-api/api/v1/2` dentro del host de Docker, como se muestra en el explorador siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-212">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog-api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Captura de pantalla de un explorador que muestra una respuesta que pasa a través de la puerta de enlace de API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

<span data-ttu-id="73648-214">**Figura 6-35**.</span><span class="sxs-lookup"><span data-stu-id="73648-214">**Figure 6-35**.</span></span> <span data-ttu-id="73648-215">Acceso a un microservicio a través de una dirección URL proporcionada por la puerta de enlace de API</span><span class="sxs-lookup"><span data-stu-id="73648-215">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="73648-216">Por motivos de pruebas o depuración, si quiere acceder directamente al contenedor de Docker Catalog (solo en el entorno de desarrollo) sin pasar por la puerta de enlace de API, ya que "catalog-api" es una resolución DNS interna para el host de Docker (la detección de servicios la controlan los nombres de servicio de docker-compose), la única manera de tener acceso directo al contenedor es a través del puerto externo publicado en el archivo docker-compose.override.yml, que solo se proporciona para pruebas de desarrollo, como `http://localhost:5101/api/v1/Catalog/items/1` en el explorador siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-216">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog-api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Captura de pantalla de un explorador que muestra una respuesta directa a Catalog.API.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

<span data-ttu-id="73648-218">**Figura 6-36**.</span><span class="sxs-lookup"><span data-stu-id="73648-218">**Figure 6-36**.</span></span> <span data-ttu-id="73648-219">Acceso directo a un microservicio con fines de prueba</span><span class="sxs-lookup"><span data-stu-id="73648-219">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="73648-220">Pero la aplicación está configurada para que acceda a todos los microservicios a través de las puertas de enlace de API, no a través de "accesos directos" de puerto directo.</span><span class="sxs-lookup"><span data-stu-id="73648-220">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port "shortcuts".</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="73648-221">El patrón de agregación de puertas de enlace en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73648-221">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="73648-222">Como se mencionó anteriormente, una manera flexible de implementar la agregación de solicitudes consiste en usar servicios personalizados, mediante código.</span><span class="sxs-lookup"><span data-stu-id="73648-222">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="73648-223">También se podría implementar la agregación de solicitudes con la [característica de agregación de solicitudes en Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), pero es posible que no sea tan flexible como se necesita.</span><span class="sxs-lookup"><span data-stu-id="73648-223">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="73648-224">Por tanto, el método seleccionado para implementar la agregación en eShopOnContainers es mediante un servicio de API web de ASP.NET Core explícito para cada agregador.</span><span class="sxs-lookup"><span data-stu-id="73648-224">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API service for each aggregator.</span></span>

<span data-ttu-id="73648-225">Según ese enfoque, el diagrama de composición de las puertas de enlace de API es en realidad más amplio si se tienen en cuenta los servicios de agregador que no se mostraron en el diagrama de arquitectura global simplificado anterior.</span><span class="sxs-lookup"><span data-stu-id="73648-225">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="73648-226">En el diagrama siguiente, también se puede ver cómo funcionan los servicios de agregador con sus puertas de enlace de API relacionadas.</span><span class="sxs-lookup"><span data-stu-id="73648-226">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![Diagrama de arquitectura de eShopOnContainers que muestra los servicios de agregador.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

<span data-ttu-id="73648-228">**Figura 6-37**.</span><span class="sxs-lookup"><span data-stu-id="73648-228">**Figure 6-37**.</span></span> <span data-ttu-id="73648-229">Arquitectura de eShopOnContainers con los servicios de agregador</span><span class="sxs-lookup"><span data-stu-id="73648-229">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="73648-230">Al ampliar más el área empresarial "Shopping" de la imagen siguiente, se puede ver que al usar los servicios agregadores de las puertas de enlace de API se reduce el intercambio de mensajes entre las aplicaciones cliente y los microservicios.</span><span class="sxs-lookup"><span data-stu-id="73648-230">Zooming in further, on the "Shopping" business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![Diagrama que muestra un detalle de la arquitectura de eShopOnContainers.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

<span data-ttu-id="73648-232">**Figura 6-38**.</span><span class="sxs-lookup"><span data-stu-id="73648-232">**Figure 6-38**.</span></span> <span data-ttu-id="73648-233">Visión ampliada de los servicios de agregador</span><span class="sxs-lookup"><span data-stu-id="73648-233">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="73648-234">Se puede observar la complejidad del diagrama cuando se muestran las posibles solicitudes procedentes de las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-234">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get complex.</span></span> <span data-ttu-id="73648-235">Aunque se puede ver cómo se simplificarían las flechas de color azul, desde la perspectiva de las aplicaciones cliente, al usar el patrón de agregadores mediante la reducción del intercambio de mensajes y la latencia de la comunicación, en última instancia se mejora de forma significativa la experiencia del usuario, especialmente para las aplicaciones remotas (aplicaciones móviles y SPA).</span><span class="sxs-lookup"><span data-stu-id="73648-235">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="73648-236">El caso del área empresarial "Marketing" y los microservicios es un caso de uso simple, por lo que no hay necesidad de usar agregadores, aunque se podría, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="73648-236">In the case of the "Marketing" business area and microservices, it is a simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="73648-237">Autenticación y autorización en las puertas de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-237">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="73648-238">En una puerta de enlace de API de Ocelot se puede ubicar el servicio de autenticación, como un servicio de API web de ASP.NET Core con [IdentityServer](https://identityserver.io/) para proporcionar el token de autenticación, fuera o dentro de la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-238">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="73648-239">Dado que en eShopOnContainers se usan varias puertas de enlace de API con límites basados en BFF y áreas de negocio, el servicio Identity/Auth se excluye de las puertas de enlace de API, como se resalta en color amarillo en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-239">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![Diagrama que muestra el microservicio Identity debajo de la puerta de enlace de API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

<span data-ttu-id="73648-241">**Figura 6-39**.</span><span class="sxs-lookup"><span data-stu-id="73648-241">**Figure 6-39**.</span></span> <span data-ttu-id="73648-242">Posición del servicio Identity en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73648-242">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="73648-243">Pero Ocelot también admite que el microservicio Identity/Auth se sitúe dentro de los límites de la puerta de enlace de API, como se muestra en este otro diagrama.</span><span class="sxs-lookup"><span data-stu-id="73648-243">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Diagrama que muestra la autenticación en una puerta de enlace de API de Ocelot.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

<span data-ttu-id="73648-245">**Figura 6-40**.</span><span class="sxs-lookup"><span data-stu-id="73648-245">**Figure 6-40**.</span></span> <span data-ttu-id="73648-246">Autenticación en Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-246">Authentication in Ocelot</span></span>

<span data-ttu-id="73648-247">Tal y como se muestra en el diagrama anterior, cuando el microservicio Identity está por debajo de la puerta de enlace de API (AG): 1) La puerta de enlace de API solicita un token de autenticación del microservicio Identity; 2) el microservicio Identity devuelve las solicitudes de token a la puerta de enlace de API; 3-4) solicitudes de los microservicios a la puerta de enlace de API mediante el token de autenticación.</span><span class="sxs-lookup"><span data-stu-id="73648-247">As the previous diagram shows, when the Identity microservice is beneath the API gateway (AG): 1) AG requests an auth token from identity microservice, 2) The identity microservice returns token to AG, 3-4) AG requests from microservices using the auth token.</span></span> <span data-ttu-id="73648-248">Como en la aplicación eShopOnContainers se ha dividido la puerta de enlace de API en varios BFF (back-end para front-end) y puertas de enlace de API de áreas de negocio, otra opción habría sido crear una puerta de enlace de API adicional para los intereses transversales.</span><span class="sxs-lookup"><span data-stu-id="73648-248">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would have been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="73648-249">Esa opción sería razonable en una arquitectura basada en microservicios más compleja con varios microservicios de intereses transversales.</span><span class="sxs-lookup"><span data-stu-id="73648-249">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="73648-250">Como en eShopOnContainers solo hay un interés transversal, se ha decidido controlar solamente el servicio de seguridad fuera del territorio de la puerta de enlace de API, por motivos de simplicidad.</span><span class="sxs-lookup"><span data-stu-id="73648-250">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity's sake.</span></span>

<span data-ttu-id="73648-251">En cualquier caso, si la aplicación está protegida en el nivel de puerta de enlace de API, el módulo de autenticación de la puerta de enlace de API de Ocelot se visita en primer lugar cuando se intenta usar cualquier microservicio protegido.</span><span class="sxs-lookup"><span data-stu-id="73648-251">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="73648-252">Eso redirige la solicitud HTTP para visitar el microservicio Identity o de autenticación a fin de obtener el token de acceso para poder visitar los servicios protegidos con el token de acceso.</span><span class="sxs-lookup"><span data-stu-id="73648-252">That redirects the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="73648-253">La forma de proteger con autenticación cualquier servicio en el nivel de la puerta de enlace de API consiste en establecer AuthenticationProviderKey en su configuración relacionada en el archivo configuration.json.</span><span class="sxs-lookup"><span data-stu-id="73648-253">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="73648-254">Cuando se ejecuta Ocelot, consulta los elementos ReRoutes AuthenticationOptions.AuthenticationProviderKey y comprueba que hay que un proveedor de autenticación registrado con la clave especificada.</span><span class="sxs-lookup"><span data-stu-id="73648-254">When Ocelot runs, it will look at the ReRoutes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="73648-255">Si no lo hay, Ocelot no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="73648-255">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="73648-256">Si lo hay, la redistribución usará ese proveedor cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="73648-256">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="73648-257">Como el WebHost de Ocelot está configurado con `authenticationProviderKey = "IdentityApiKey"`, eso requerirá la autenticación cada vez que el servicio tenga alguna solicitud sin ningún token de autenticación.</span><span class="sxs-lookup"><span data-stu-id="73648-257">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="73648-258">Después, también tendrá que establecer la autorización con el atributo [Authorize] en cualquier recurso al que se vaya a acceder como los microservicios, como en el siguiente controlador del microservicio Basket.</span><span class="sxs-lookup"><span data-stu-id="73648-258">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="73648-259">ValidAudiences como "basket" se ponen en correlación con el público definido en cada microservicio con `AddJwtBearer()` en el método ConfigureServices() de la clase Startup, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-259">The ValidAudiences such as "basket" are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="73648-260">Si intenta acceder a cualquier microservicio protegido, como Basket, con una dirección URL de ReRoute basada en la puerta de enlace de API como `http://localhost:5202/api/v1/b/basket/1`, obtiene un error "401 No autorizado", a menos que proporcione un token válido.</span><span class="sxs-lookup"><span data-stu-id="73648-260">If you try to access any secured microservice, like the Basket microservice with a ReRoute URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you'll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="73648-261">Por otro lado, si una dirección URL de ReRoute está autenticada, Ocelot invoca a cualquier esquema descendente con el que esté asociada (la dirección URL de microservicio interna).</span><span class="sxs-lookup"><span data-stu-id="73648-261">On the other hand, if a ReRoute URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="73648-262">**Autorización en el nivel de ReRoutes de Ocelot.**</span><span class="sxs-lookup"><span data-stu-id="73648-262">**Authorization at Ocelot's ReRoutes tier.**</span></span>  <span data-ttu-id="73648-263">Ocelot admite la autorización basada en notificaciones que se evalúa después de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="73648-263">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="73648-264">La autorización se establece en un nivel de ruta mediante la adición de las líneas siguientes a la configuración de redistribución.</span><span class="sxs-lookup"><span data-stu-id="73648-264">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="73648-265">En ese ejemplo, cuando se llama al software intermedio de autorización, Ocelot comprobará si el usuario tiene el tipo de notificación "UserType" en el token y si el valor de esa notificación es "employee".</span><span class="sxs-lookup"><span data-stu-id="73648-265">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="73648-266">Si no es así, el usuario no tiene autorización y la respuesta es el error "403 Prohibido".</span><span class="sxs-lookup"><span data-stu-id="73648-266">If it isn't, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="73648-267">Uso de entrada de Kubernetes con las puertas de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-267">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="73648-268">Al usar Kubernetes (como en un clúster de Azure Kubernetes Service) normalmente todas las solicitudes HTTP se unifican a través de la [capa de entrada de Kubernetes](https://kubernetes.io/docs/concepts/services-networking/ingress/) basada en *Nginx*.</span><span class="sxs-lookup"><span data-stu-id="73648-268">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="73648-269">En Kubernetes, si no se usa ningún enfoque de entrada, los servicios y pods tienen direcciones IP que solo son enrutables por la red de clústeres.</span><span class="sxs-lookup"><span data-stu-id="73648-269">In Kubernetes, if you don't use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="73648-270">Pero si usa un enfoque de entrada, tendrá una capa intermedia entre Internet y los servicios (incluidas las puertas de enlace de API), que actúa como un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="73648-270">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="73648-271">Como definición, una entrada es una colección de reglas que permiten que las conexiones entrantes lleguen a los servicios de clúster.</span><span class="sxs-lookup"><span data-stu-id="73648-271">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="73648-272">Normalmente, una entrada se configura para proporcionar a los servicios direcciones URL accesibles de forma externa, tráfico con equilibrio de carga, terminación SSL y mucho más.</span><span class="sxs-lookup"><span data-stu-id="73648-272">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="73648-273">Los usuarios solicitan la entrada mediante la publicación del recurso de entrada en el servidor de API.</span><span class="sxs-lookup"><span data-stu-id="73648-273">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="73648-274">En eShopOnContainers, al desarrollar de forma local y usar solamente el equipo de desarrollo como el host de Docker, no se usa ninguna entrada, solo las diferentes puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-274">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="73648-275">Pero cuando el destino es un entorno de "producción" basado en Kubernetes, en eShopOnContainers se usa una entrada delante de las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-275">However, when targeting a "production" environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="73648-276">De este modo, los clientes pueden seguir llamando a la misma dirección URL base, pero las solicitudes se enrutan a varias puertas de enlace de API o BFF.</span><span class="sxs-lookup"><span data-stu-id="73648-276">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="73648-277">Las puertas de enlace de API actúan de front-end o fachadas en las que solo se exponen los servicios, pero no las aplicaciones web que suelen estar fuera de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="73648-277">API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="73648-278">Además, es posible que las puertas de enlace de API oculten ciertos microservicios internos.</span><span class="sxs-lookup"><span data-stu-id="73648-278">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="73648-279">Pero la entrada simplemente redirige las solicitudes HTTP pero no intenta ocultar ningún microservicio ni aplicación web.</span><span class="sxs-lookup"><span data-stu-id="73648-279">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="73648-280">Tener un nivel Nginx de entrada en Kubernetes delante de las aplicaciones web además de las distintas puertas de enlace de API de Ocelot o BFF es la arquitectura ideal, como se muestra en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="73648-280">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Diagrama que muestra cómo encaja un nivel de entrada en el entorno de AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

<span data-ttu-id="73648-282">**Figura 6-41**.</span><span class="sxs-lookup"><span data-stu-id="73648-282">**Figure 6-41**.</span></span> <span data-ttu-id="73648-283">El nivel de entrada en eShopOnContainers cuando se implementa en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="73648-283">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="73648-284">Una entrada de Kubernetes actúa como un proxy inverso para todo el tráfico a la aplicación, incluidas las aplicaciones web, que normalmente están fuera del ámbito de la puerta de enlace de la API.</span><span class="sxs-lookup"><span data-stu-id="73648-284">A Kubernetes Ingress acts as a reverse proxy for all traffic to the app, including the web applications, that are usually out of the Api gateway scope.</span></span> <span data-ttu-id="73648-285">Al implementar eShopOnContainers en Kubernetes, solo expone algunos servicios o puntos de conexión a través de la _entrada_, básicamente la lista siguiente de postfijos en las direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="73648-285">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="73648-286">`/` para la aplicación web SPA cliente</span><span class="sxs-lookup"><span data-stu-id="73648-286">`/` for the client SPA web application</span></span>
- <span data-ttu-id="73648-287">`/webmvc` para la aplicación web MVC cliente</span><span class="sxs-lookup"><span data-stu-id="73648-287">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="73648-288">`/webstatus` para la aplicación web cliente en la que se muestra el estado o las comprobaciones de estado</span><span class="sxs-lookup"><span data-stu-id="73648-288">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="73648-289">`/webshoppingapigw` para el BFF web y los procesos empresariales de compra</span><span class="sxs-lookup"><span data-stu-id="73648-289">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="73648-290">`/webmarketingapigw` para el BFF web y los procesos empresariales de marketing</span><span class="sxs-lookup"><span data-stu-id="73648-290">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="73648-291">`/mobileshoppingapigw` para el BFF para dispositivos móviles y los procesos empresariales de compra</span><span class="sxs-lookup"><span data-stu-id="73648-291">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="73648-292">`/mobilemarketingapigw` para el BFF para dispositivos móviles y los procesos empresariales de marketing</span><span class="sxs-lookup"><span data-stu-id="73648-292">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="73648-293">Al implementar en Kubernetes, cada puerta de enlace de API de Ocelot usa un archivo "configuration.json" diferente para cada _pod_ en el que se ejecutan las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-293">When deploying to Kubernetes, each Ocelot API Gateway is using a different "configuration.json" file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="73648-294">Esos archivos "configuration.json" se proporcionan mediante el montaje (originalmente con el script deploy.ps1) de un volumen creado en función de un _mapa de configuración_ de Kubernetes denominado "ocelot".</span><span class="sxs-lookup"><span data-stu-id="73648-294">Those "configuration.json" files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot'.</span></span> <span data-ttu-id="73648-295">Cada contenedor monta su archivo de configuración relacionado en la carpeta denominada `/app/configuration` del contenedor.</span><span class="sxs-lookup"><span data-stu-id="73648-295">Each container mounts its related configuration file in the container's folder named `/app/configuration`.</span></span>

<span data-ttu-id="73648-296">En los archivos de código fuente de eShopOnContainers, los archivos "configuration.json" originales se encuentran en la carpeta `k8s/ocelot/`.</span><span class="sxs-lookup"><span data-stu-id="73648-296">In the source code files of eShopOnContainers, the original "configuration.json" files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="73648-297">Hay un archivo para cada BFF o puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="73648-297">There's one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="73648-298">Características transversales adicionales en una puerta de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="73648-298">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="73648-299">Cuando se usa una puerta de enlace de API de Ocelot hay otras características importantes para investigar y utilizar, como se describe en los vínculos siguientes.</span><span class="sxs-lookup"><span data-stu-id="73648-299">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="73648-300">**Detección de servicios en el lado cliente mediante la integración de Ocelot con Consul o Eureka** </span><span class="sxs-lookup"><span data-stu-id="73648-300">**Service discovery in the client side integrating Ocelot with Consul or Eureka** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="73648-301">**Almacenamiento en caché en el nivel de puerta de enlace de API** </span><span class="sxs-lookup"><span data-stu-id="73648-301">**Caching at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="73648-302">**Registro en el nivel de puerta de enlace de API)**  </span><span class="sxs-lookup"><span data-stu-id="73648-302">**Logging at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="73648-303">**Calidad de servicio (reintentos e interruptores) en el nivel de puerta de enlace de API** </span><span class="sxs-lookup"><span data-stu-id="73648-303">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="73648-304">**Limitación de velocidad** </span><span class="sxs-lookup"><span data-stu-id="73648-304">**Rate limiting** </span></span>\
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="73648-305">[Anterior](background-tasks-with-ihostedservice.md)
> [Siguiente](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="73648-305">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
