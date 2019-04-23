---
title: Implementación de puertas de enlace de API con Ocelot
description: Obtenga información sobre cómo implementar puertas de enlace de API con Ocelot y cómo usar Ocelot en un entorno basado en contenedores.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 5d4f2a3b2551f8da83359b26578d45559721f7df
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613725"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="f121f-103">Implementación de puertas de enlace de API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-103">Implement API Gateways with Ocelot</span></span>

<span data-ttu-id="f121f-104">En la aplicación de microservicio de referencia [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) se usa [Ocelot](https://github.com/ThreeMammals/Ocelot), una puerta de enlace de API simple y ligera que se puede implementar en cualquier lugar junto con los microservicios y contenedores, como en cualquiera de los entornos siguientes que se usan en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f121f-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is using [Ocelot](https://github.com/ThreeMammals/Ocelot), a simple and lightweight API Gateway that you can deploy anywhere along with your microservices/containers, such as in any of the following environments used by eShopOnContainers.</span></span>

- <span data-ttu-id="f121f-105">Host de Docker, en el equipo PC de desarrollo local, en el entorno local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="f121f-105">Docker host, in your local dev PC, on-premises or in the cloud.</span></span>
- <span data-ttu-id="f121f-106">Clúster de Kubernetes, de forma local o en la nube administrada como Azure Kubernetes Service (AKS).</span><span class="sxs-lookup"><span data-stu-id="f121f-106">Kubernetes cluster, on-premises or in managed cloud such as Azure Kubernetes Service (AKS).</span></span>
- <span data-ttu-id="f121f-107">Clúster de Service Fabric local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="f121f-107">Service Fabric cluster, on-premises or in the cloud.</span></span>
- <span data-ttu-id="f121f-108">Malla de Service Fabric, como PaaS o sin servidor en Azure.</span><span class="sxs-lookup"><span data-stu-id="f121f-108">Service Fabric mesh, as PaaS/Serverless in Azure.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="f121f-109">Arquitectura y diseño de las puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="f121f-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="f121f-110">En el diagrama de arquitectura siguiente se muestra cómo se implementan las puertas de enlace de API con Ocelot en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f121f-110">The following architecture diagram shows how API Gateways are implemented with Ocelot in eShopOnContainers.</span></span>

![Diagrama de arquitectura de eShopOnContainers en el que se muestran aplicaciones cliente, microservicios y las puertas de enlace de API intermedias](./media/image28.png)

<span data-ttu-id="f121f-112">**Figura 6-28**.</span><span class="sxs-lookup"><span data-stu-id="f121f-112">**Figure 6-28**.</span></span> <span data-ttu-id="f121f-113">Arquitectura de eShopOnContainers con puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="f121f-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="f121f-114">En ese diagrama se muestra cómo se implementa toda la aplicación en un único host de Docker o PC de desarrollo con "Docker para Windows" o "Docker para Mac".</span><span class="sxs-lookup"><span data-stu-id="f121f-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with “Docker for Windows” or “Docker for Mac”.</span></span> <span data-ttu-id="f121f-115">Pero la implementación en cualquier orquestador sería bastante similar y cualquiera de los contenedores del diagrama se podría escalar horizontalmente en el orquestador.</span><span class="sxs-lookup"><span data-stu-id="f121f-115">However, deploying into any orchestrator would be pretty similar but any container in the diagram could be scaled-out in the orchestrator.</span></span>

<span data-ttu-id="f121f-116">Además, los recursos de infraestructura como bases de datos, caché y agentes de mensajes se deberían descargar del orquestador e implementarse en sistemas de alta disponibilidad para la infraestructura, como Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus o cualquier solución de agrupación en clústeres de alta disponibilidad local.</span><span class="sxs-lookup"><span data-stu-id="f121f-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="f121f-117">Como también se puede observar en el diagrama, tener varias puertas de enlace de API permite que varios equipos de desarrollo sean autónomos (en este caso, las características de Marketing frente a las de Shopping) al desarrollar e implementar sus microservicios además de sus propias puertas de enlace de API relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f121f-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="f121f-118">Si tuviera una sola puerta de enlace de API monolítica, sería un único punto para actualizar por varios equipos de desarrollo, que podrían acoplar todos los microservicios con un único elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f121f-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="f121f-119">Ampliando mucho más el diseño, en ocasiones una puerta de enlace de API específica también se puede limitar a un microservicio empresarial individual en función de la arquitectura elegida.</span><span class="sxs-lookup"><span data-stu-id="f121f-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="f121f-120">El tener los límites de la puerta de enlace de API dictados por el negocio o el dominio le ayudará a lograr un mejor diseño.</span><span class="sxs-lookup"><span data-stu-id="f121f-120">Having the API Gateway’s boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="f121f-121">Por ejemplo, la especificidad del nivel de puerta de enlace de API puede ser especialmente útil para aplicaciones de interfaz de usuario compuesta más avanzadas que se basan en microservicios, dado que el concepto de una puerta de enlace de API específica es similar a un servicio de composición de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f121f-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="f121f-122">Nos adentramos en más detalles en la sección anterior, [Creación de interfaz de usuario compuesta basada en microservicios](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="f121f-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="f121f-123">Como punto clave, para muchas aplicaciones de tamaño medio y grande, el uso de una puerta de enlace de API personalizada suele ser un enfoque adecuado, pero no como un único agregador monolítico ni una única puerta de enlace de API personalizada central, a menos que esa puerta de enlace de API permita varias áreas de configuración independientes para que los diferentes equipos de desarrollo creen microservicios autónomos.</span><span class="sxs-lookup"><span data-stu-id="f121f-123">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-re-route-through-the-api-gateways"></a><span data-ttu-id="f121f-124">Microservicios y contenedores de ejemplo para redistribuir entre las puertas de enlace de API</span><span class="sxs-lookup"><span data-stu-id="f121f-124">Sample microservices/containers to re-route through the API Gateways</span></span>

<span data-ttu-id="f121f-125">Como ejemplo, eShopOnContainers tiene aproximadamente seis tipos de microservicio internos que se tienen que publicar entre las puertas de enlace de API, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Solo los microservicios Basket, Catalog, Location, Marketing, Ordering y Payment se publican a través de la puerta de enlace de API.](./media/image29.png)

<span data-ttu-id="f121f-127">**Figura 6-29**.</span><span class="sxs-lookup"><span data-stu-id="f121f-127">**Figure 6-29**.</span></span> <span data-ttu-id="f121f-128">Carpetas de microservicio en la solución eShopOnContainers en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f121f-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="f121f-129">En cuanto al servicio Identity, en el diseño se excluye del enrutamiento de puerta de enlace de API, porque es el único interés transversal del sistema, aunque con Ocelot también es posible incluirlo como parte de las listas de reenrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f121f-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="f121f-130">Todos estos servicios se implementan actualmente como servicios de API web de ASP.NET Core, como se desprende del código.</span><span class="sxs-lookup"><span data-stu-id="f121f-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="f121f-131">Centrémonos en uno de los microservicios, como el código del microservicio Catalog.</span><span class="sxs-lookup"><span data-stu-id="f121f-131">Let’s focus on one of the microservices like the Catalog microservice code.</span></span>

![Vista del Explorador de soluciones del proyecto Catalog.API.](./media/image30.png)

<span data-ttu-id="f121f-133">**Figura 6-30**.</span><span class="sxs-lookup"><span data-stu-id="f121f-133">**Figure 6-30**.</span></span> <span data-ttu-id="f121f-134">Microservicio de API web de ejemplo (microservicio Catalog)</span><span class="sxs-lookup"><span data-stu-id="f121f-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="f121f-135">Puede ver que el microservicio Catalog es un proyecto de API web de ASP.NET Core típico con varios controladores y métodos, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

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

<span data-ttu-id="f121f-136">La solicitud HTTP terminará ejecutando ese tipo de código de C# que accede a la base de datos de microservicios además de cualquier otra acción requerida.</span><span class="sxs-lookup"><span data-stu-id="f121f-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="f121f-137">En lo que respecta a la dirección URL del microservicio, cuando los contenedores se implementan en el equipo de desarrollo local (el host de Docker local), el contenedor de cada microservicio siempre tiene un puerto interno (normalmente el puerto 80) que se especifica en su Dockerfile, como se muestra en el Dockerfile siguiente:</span><span class="sxs-lookup"><span data-stu-id="f121f-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice’s container has always an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0.5 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="f121f-138">El puerto 80 que se muestra en el código es interno dentro del host de Docker, por lo que las aplicaciones cliente no pueden acceder a él.</span><span class="sxs-lookup"><span data-stu-id="f121f-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="f121f-139">Las aplicaciones cliente solo pueden acceder a los puertos externos (si existen) publicados al implementar con `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="f121f-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="f121f-140">Esos puertos externos no se deben publicar al implementar en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="f121f-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="f121f-141">Por esto precisamente se va a usar la puerta de enlace de API, para evitar la comunicación directa entre las aplicaciones cliente y los microservicios.</span><span class="sxs-lookup"><span data-stu-id="f121f-141">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="f121f-142">Pero durante el desarrollo, le interesa acceder directamente al contenedor o microservicio, y ejecutarlo a través de Swagger.</span><span class="sxs-lookup"><span data-stu-id="f121f-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="f121f-143">Por eso en eShopOnContainers se siguen especificando los puertos externos, aunque la puerta de enlace de API o las aplicaciones cliente no los vayan a usar.</span><span class="sxs-lookup"><span data-stu-id="f121f-143">That’s why in eShopOnContainers, the external ports are still specified even when they won’t be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="f121f-144">Este es un ejemplo del archivo `docker-compose.override.yml` para el microservicio Catalog:</span><span class="sxs-lookup"><span data-stu-id="f121f-144">Here’s an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog.api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="f121f-145">Puede ver cómo en la configuración de docker-compose.override.yml el puerto interno del contenedor Catalog es el puerto 80, pero el puerto para el acceso externo es 5101.</span><span class="sxs-lookup"><span data-stu-id="f121f-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="f121f-146">Pero la aplicación no debería usar este puerto cuando se utiliza una puerta de enlace de API, solo para depurar, ejecutar y probar el microservicio Catalog.</span><span class="sxs-lookup"><span data-stu-id="f121f-146">But this port shouldn’t be used by the application when using an API Gateway, only to debug, run and test just the Catalog microservice.</span></span>

<span data-ttu-id="f121f-147">Normalmente, no se puede implementar con docker-compose en un entorno de producción porque el entorno de implementación de producción correcto para los microservicios es un orquestador como Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="f121f-147">Normally, you won’t be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="f121f-148">Cuando se implementa en esos entornos, se usan otros archivos de configuración en los que no se publica directamente ningún puerto externo para los microservicios, pero siempre se usa al proxy inverso de la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-148">When deploying to those environments you use different configuration files where you won’t publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="f121f-149">Ejecute el microservicio Catalog en el host de Docker local ya sea mediante la ejecución de la solución eShopOnContainers completa desde Visual Studio (ejecutará todos los servicios de los archivos docker-compose) o iniciando el microservicio con el comando docker-compose siguiente en CMD o PowerShell desde la carpeta donde están `docker-compose.yml` y docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="f121f-149">Run the catalog microservice in your local Docker host either by running the full eShopOnContainers solution from Visual Studio (it’ll run all the services in the docker-compose files) or just starting the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and docker-compose.override.yml are placed.</span></span>

```console
docker-compose run --service-ports catalog.api
```

<span data-ttu-id="f121f-150">Este comando solo ejecuta el contenedor del servicio catalog.api además de las dependencias que se especifican en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f121f-150">This command only runs the catalog.api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="f121f-151">En este caso, el contenedor de SQL Server y el contenedor de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="f121f-151">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="f121f-152">Después, puede acceder directamente al microservicio Catalog y ver sus métodos a través de la interfaz de usuario de Swagger, a la que se accede directamente a través de ese puerto "externo", en este caso `http://localhost:5101/swagger`:</span><span class="sxs-lookup"><span data-stu-id="f121f-152">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that “external” port, in this case `http://localhost:5101/swagger`:</span></span>

![Vista del explorador de la edad de la interfaz de usuario de Swagger para la API REST Catalog.API.](./media/image31.png)

<span data-ttu-id="f121f-154">**Figura 6-31**.</span><span class="sxs-lookup"><span data-stu-id="f121f-154">**Figure 6-31**.</span></span> <span data-ttu-id="f121f-155">Probar el microservicio Catalog con su interfaz de usuario de Swagger</span><span class="sxs-lookup"><span data-stu-id="f121f-155">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="f121f-156">En este momento, podría establecer un punto de interrupción en el código de C# en Visual Studio, probar el microservicio con los métodos expuestos en la interfaz de usuario de Swagger y, por último, limpiar todo con el comando `docker-compose down`.</span><span class="sxs-lookup"><span data-stu-id="f121f-156">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="f121f-157">Pero la comunicación de acceso directo al microservicio, en este caso a través del puerto externo 5101, es precisamente lo que se quiere evitar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f121f-157">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="f121f-158">Y se puede evitar si se establece el nivel adicional de direccionamiento indirecto de la puerta de enlace de API (en este caso, Ocelot).</span><span class="sxs-lookup"><span data-stu-id="f121f-158">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="f121f-159">De ese modo, la aplicación cliente no accederá directamente al microservicio.</span><span class="sxs-lookup"><span data-stu-id="f121f-159">That way, the client app won’t directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="f121f-160">Implementación de las puertas de enlace de API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-160">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="f121f-161">Ocelot es básicamente un conjunto de software intermedio que se puede aplicar en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="f121f-161">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="f121f-162">Ocelot está diseñado para trabajar solamente con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f121f-162">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="f121f-163">Está destinado a .NET Standard 2.0, por lo que se puede usar en cualquier lugar donde se admita .NET Standard 2.0, incluido el runtime de .NET Core 2.0 y el de .NET Framework 4.6.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="f121f-163">It targets netstandard2.0 so it can be used anywhere .NET Standard 2.0 is supported, including .NET Core 2.0 runtime and .NET Framework 4.6.1 runtime and up.</span></span>

<span data-ttu-id="f121f-164">Ocelot y sus dependencias se instalan en el proyecto de ASP.NET Core con el [paquete NuGet de Ocelot](https://www.nuget.org/packages/Ocelot/), desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f121f-164">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="f121f-165">En eShopOnContainers, su implementación de puerta de enlace de API es un proyecto ASP.NET Core WebHost simple, y el software intermedio de Ocelot controla todas las características de la puerta de enlace de API, como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="f121f-165">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middlewares handle all the API Gateway features, as shown in the following image:</span></span>

![Vista del Explorador de soluciones del proyecto de puerta de enlace de API Ocelot.](./media/image32.png)

<span data-ttu-id="f121f-167">**Figura 6-32**.</span><span class="sxs-lookup"><span data-stu-id="f121f-167">**Figure 6-32**.</span></span> <span data-ttu-id="f121f-168">El proyecto base de OcelotApiGw en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f121f-168">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="f121f-169">Este proyecto ASP.NET Core WebHost se compila básicamente con dos archivos sencillos: `Program.cs` y `Startup.cs`.</span><span class="sxs-lookup"><span data-stu-id="f121f-169">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="f121f-170">El archivo Program.cs solo tiene que crear y configurar el típico BuildWebHost de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f121f-170">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

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

<span data-ttu-id="f121f-171">Aquí, lo importante para Ocelot es el archivo `configuration.json` que se debe proporcionar al generador a través del método `AddJsonFile()`.</span><span class="sxs-lookup"><span data-stu-id="f121f-171">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="f121f-172">Ese archivo `configuration.json` es donde se especifican todas las redistribuciones de la puerta de enlace de API, es decir, los puntos de conexión externos con puertos específicos y los puntos de conexión internos correlacionados, que normalmente usan otros puertos.</span><span class="sxs-lookup"><span data-stu-id="f121f-172">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="f121f-173">En la configuración hay dos secciones.</span><span class="sxs-lookup"><span data-stu-id="f121f-173">There are two sections to the configuration.</span></span> <span data-ttu-id="f121f-174">Una matriz de redistribuciones y GlobalConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f121f-174">An array of Re-Routes and a GlobalConfiguration.</span></span> <span data-ttu-id="f121f-175">Las redistribuciones son los objetos que indican a Ocelot cómo procesar una solicitud de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="f121f-175">The Re-Routes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="f121f-176">La configuración Global permite reemplazos de la configuración específica de redistribución.</span><span class="sxs-lookup"><span data-stu-id="f121f-176">The Global configuration allows overrides of Re-Route specific settings.</span></span> <span data-ttu-id="f121f-177">Es útil si no quiere administrar una gran cantidad de configuración específica de redistribución.</span><span class="sxs-lookup"><span data-stu-id="f121f-177">It’s useful if you don’t want to manage lots of Re-Route specific settings.</span></span>

<span data-ttu-id="f121f-178">Este es un ejemplo simplificado del [archivo de configuración de redistribución](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) de una de las puertas de enlace de API de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f121f-178">Here’s a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog.api",
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
          "Host": "basket.api",
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

<span data-ttu-id="f121f-179">La funcionalidad principal de una puerta de enlace de API de Ocelot consiste en aceptar solicitudes HTTP entrantes y reenviarlas a un servicio de nivel inferior, actualmente como otra solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="f121f-179">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="f121f-180">Ocelot describe el enrutamiento de una solicitud a otra como una redistribución.</span><span class="sxs-lookup"><span data-stu-id="f121f-180">Ocelot’s describes the routing of one request to another as a Re-Route.</span></span>

<span data-ttu-id="f121f-181">Por ejemplo, vamos a centrarnos en una de las redistribuciones del archivo configuration.json anterior, la configuración para el microservicio Basket.</span><span class="sxs-lookup"><span data-stu-id="f121f-181">For instance, let’s focus on one of the Re-Routes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
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

<span data-ttu-id="f121f-182">DownstreamPathTemplate, Scheme y DownstreamHostAndPorts forman la dirección URL de microservicio interna a la que se va a reenviar esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="f121f-182">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="f121f-183">El puerto es el puerto interno que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="f121f-183">The port is the internal port used by the service.</span></span> <span data-ttu-id="f121f-184">Al usar contenedores, el puerto se especifica en su Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f121f-184">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="f121f-185">`Host` es un nombre de servicio que depende de la resolución de nombres de servicio que se use.</span><span class="sxs-lookup"><span data-stu-id="f121f-185">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="f121f-186">Cuando se usa docker-compose, los nombres de los servicios los proporciona el host de Docker, que usa los nombres de servicio proporcionados en los archivos docker-compose.</span><span class="sxs-lookup"><span data-stu-id="f121f-186">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="f121f-187">Si se usa un orquestador como Kubernetes o Service Fabric, ese nombre se debe resolver mediante DNS o la resolución de nombres proporcionada por cada orquestador.</span><span class="sxs-lookup"><span data-stu-id="f121f-187">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="f121f-188">DownstreamHostAndPorts es una matriz que contiene el host y el puerto de los servicios de nivel inferior a los que se quieren reenviar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="f121f-188">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="f121f-189">Normalmente esto solo contendrá una entrada, pero a veces es posible que quiera equilibrar la carga de las solicitudes a los servicios de nivel inferior y Ocelot permite agregar más de una entrada y después seleccionar un equilibrador de carga.</span><span class="sxs-lookup"><span data-stu-id="f121f-189">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="f121f-190">Pero si se usa Azure y un orquestador, probablemente una idea mejor sea equilibrar la carga con la infraestructura de nube y de orquestador.</span><span class="sxs-lookup"><span data-stu-id="f121f-190">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="f121f-191">UpstreamPathTemplate es la dirección URL que Ocelot usará para identificar qué DownstreamPathTemplate se va a usar para una solicitud determinada desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="f121f-191">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="f121f-192">Por último, se usa UpstreamHttpMethod para que Ocelot pueda distinguir entre diferentes solicitudes (GET, POST, PUT) a la misma dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f121f-192">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="f121f-193">En este momento, podría tener una única puerta de enlace de API de Ocelot (ASP.NET Core WebHost) con uno o [varios archivos configuration.json combinados](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files), o bien almacenar la [configuración en un almacén de Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="f121f-193">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="f121f-194">Pero como se mencionó en las secciones de arquitectura y diseño, si realmente quiere tener microservicios autónomos, podría ser mejor dividir esa única puerta de enlace de API monolítica en varias puertas de enlace de API o BFF (back-end para front-end).</span><span class="sxs-lookup"><span data-stu-id="f121f-194">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="f121f-195">Para ello, vamos a ver cómo se implementa este enfoque con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="f121f-195">For that purpose, let’s see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="f121f-196">Uso de una sola imagen de contenedor de Docker para ejecutar varios tipos de contenedor de puerta de enlace de API y BFF</span><span class="sxs-lookup"><span data-stu-id="f121f-196">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="f121f-197">En eShopOnContainers, se usa una sola imagen de contenedor de Docker con la puerta de enlace de API de Ocelot pero después, en tiempo de ejecución, se crean otros contenedores y servicios para cada tipo de puerta de enlace de API o BFF proporcionando otro archivo configuration.json, mediante un volumen de Docker para acceder a una carpeta distinta del equipo para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="f121f-197">In eShopOnContainers we’re using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![En el caso de la puerta de enlace API de Ocelot, para las cuatro puertas de enlace de la API se usa una sola imagen de Docker.](./media/image33.png)

<span data-ttu-id="f121f-199">**Figura 6-33**.</span><span class="sxs-lookup"><span data-stu-id="f121f-199">**Figure 6-33**.</span></span> <span data-ttu-id="f121f-200">Volver a usar una única imagen de Docker de Ocelot entre varios tipos de puerta de enlace de API</span><span class="sxs-lookup"><span data-stu-id="f121f-200">Re-using a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="f121f-201">En eShopOnContainers, la "imagen de Docker de puerta de enlace de API genérica" se crea con el proyecto "OcelotApiGw" y el nombre de imagen "eshop/ocelotapigw" que se especifica en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f121f-201">In eShopOnContainers, the “Generic Ocelot API Gateway Docker Image” is created with the project named 'OcelotApiGw' and the image name “eshop/ocelotapigw” that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="f121f-202">Después, al implementar en Docker, habrá cuatro contenedores de puerta de enlace de API que se crean a partir de esa misma imagen de Docker, como se muestra en el extracto siguiente del archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f121f-202">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

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

<span data-ttu-id="f121f-203">Además, como se puede ver en el archivo docker-compose.override.yml siguiente, la única diferencia entre esos contenedores de puerta de enlace de API es el archivo de configuración de Ocelot, que es diferente para cada contenedor de servicios y que se especifica en tiempo de ejecución a través de un volumen de Docker.</span><span class="sxs-lookup"><span data-stu-id="f121f-203">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="f121f-204">Debido al código anterior, y como se muestra en el Explorador de Visual Studio a continuación, el único archivo necesario para definir cada puerta de enlace de API empresarial específica o BFF es simplemente un archivo configuration.json, dado que las cuatro puertas de enlace de API se basan en la misma imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="f121f-204">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![La única diferencia entre las puertas de enlace de API es un archivo configuration.json en cada una de ellas.](./media/image34.png)

<span data-ttu-id="f121f-206">**Figura 6-34**.</span><span class="sxs-lookup"><span data-stu-id="f121f-206">**Figure 6-34**.</span></span> <span data-ttu-id="f121f-207">El único archivo necesario para definir cada puerta de enlace de API y BFF con Ocelot es un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f121f-207">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="f121f-208">Al dividir la puerta de enlace de API en varias, cada equipo de desarrollo centrado en otros subconjuntos de microservicios puede administrar sus propias puertas de enlace de API mediante archivos de configuración de Ocelot independientes.</span><span class="sxs-lookup"><span data-stu-id="f121f-208">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="f121f-209">Además, al mismo tiempo pueden reutilizar la misma imagen de Docker de Ocelot.</span><span class="sxs-lookup"><span data-stu-id="f121f-209">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="f121f-210">Ahora, si ejecuta eShopOnContainers con las puertas de enlace de API (incluidas de forma predeterminada en Visual Studio al abrir la solución eShopOnContainers ServicesAndWebApps.sln o al ejecutar "docker-compose up"), se ejecutarán las rutas de ejemplo siguientes.</span><span class="sxs-lookup"><span data-stu-id="f121f-210">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running “docker-compose up”), the following sample routes will be performed.</span></span>

<span data-ttu-id="f121f-211">Por ejemplo, cuando se visita la dirección URL de nivel superior `http://localhost:5202/api/v1/c/catalog/items/2/` que proporciona la puerta de enlace de API webshoppingapigw, se obtiene el mismo resultado de la dirección URL de nivel inferior interna `http://catalog.api/api/v1/2` dentro del host de Docker, como se muestra en el explorador siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-211">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog.api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Vista del explorador de una respuesta de Catalog.api que pasa por la puerta de enlace de API.](./media/image35.png)

<span data-ttu-id="f121f-213">**Figura 6-35**.</span><span class="sxs-lookup"><span data-stu-id="f121f-213">**Figure 6-35**.</span></span> <span data-ttu-id="f121f-214">Acceso a un microservicio a través de una dirección URL proporcionada por la puerta de enlace de API</span><span class="sxs-lookup"><span data-stu-id="f121f-214">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="f121f-215">Por motivos de pruebas o depuración, si quiere acceder directamente al contenedor de Docker Catalog (solo en el entorno de desarrollo) sin pasar por la puerta de enlace de API, ya que "catalog.api" es una resolución DNS interna para el host de Docker (la detección de servicios la controlan los nombres de servicio de docker-compose), la única manera de tener acceso directo al contenedor es a través del puerto externo publicado en el archivo docker-compose.override.yml, que solo se proporciona para pruebas de desarrollo, como `http://localhost:5101/api/v1/Catalog/items/1` en el explorador siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-215">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog.api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Vista del explorador de una respuesta de Catalog.api que va directamente a Catalog.api, idéntica a la que pasa a través de la puerta de enlace de API.](./media/image36.png)

<span data-ttu-id="f121f-217">**Figura 6-36**.</span><span class="sxs-lookup"><span data-stu-id="f121f-217">**Figure 6-36**.</span></span> <span data-ttu-id="f121f-218">Acceso directo a un microservicio con fines de prueba</span><span class="sxs-lookup"><span data-stu-id="f121f-218">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="f121f-219">Pero la aplicación está configurada para que acceda a todos los microservicios a través de las puertas de enlace de API, no a través de "atajos" de puerto directos.</span><span class="sxs-lookup"><span data-stu-id="f121f-219">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port “shortcuts”.</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="f121f-220">El patrón de agregación de puertas de enlace en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f121f-220">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="f121f-221">Como se mencionó anteriormente, una manera flexible de implementar la agregación de solicitudes consiste en usar servicios personalizados, mediante código.</span><span class="sxs-lookup"><span data-stu-id="f121f-221">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="f121f-222">También se podría implementar la agregación de solicitudes con la [característica de agregación de solicitudes en Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), pero es posible que no sea tan flexible como se necesita.</span><span class="sxs-lookup"><span data-stu-id="f121f-222">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="f121f-223">Por tanto, el método seleccionado para implementar la agregación en eShopOnContainers es mediante un servicio de API web de ASP.NET Core explícito para cada agregador.</span><span class="sxs-lookup"><span data-stu-id="f121f-223">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API services for each aggregator.</span></span>

<span data-ttu-id="f121f-224">Según ese enfoque, el diagrama de composición de las puertas de enlace de API es en realidad más amplio si se tienen en cuenta los servicios de agregador que no se mostraron en el diagrama de arquitectura global simplificado anterior.</span><span class="sxs-lookup"><span data-stu-id="f121f-224">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="f121f-225">En el diagrama siguiente, también se puede ver cómo funcionan los servicios de agregador con sus puertas de enlace de API relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f121f-225">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![Arquitectura de eShopOnContainers, en la que se muestran los servicios de agregador.](./media/image37.png)

<span data-ttu-id="f121f-227">**Figura 6-37**.</span><span class="sxs-lookup"><span data-stu-id="f121f-227">**Figure 6-37**.</span></span> <span data-ttu-id="f121f-228">Arquitectura de eShopOnContainers con los servicios de agregador</span><span class="sxs-lookup"><span data-stu-id="f121f-228">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="f121f-229">Al ampliar más el área empresarial "Shopping" de la imagen siguiente, se puede ver que al usar los servicios agregadores de las puertas de enlace de API se reduce el intercambio de mensajes entre las aplicaciones cliente y los microservicios.</span><span class="sxs-lookup"><span data-stu-id="f121f-229">Zooming in further, on the “Shopping” business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![Ampliación de la arquitectura de eShopOnContainers, en la que se muestran los servicios de agregador, y en la que se "construye" una respuesta que "combina" la respuesta de varios microservicios para reducir el intercambio de mensajes con el cliente final.](./media/image38.png)

<span data-ttu-id="f121f-231">**Figura 6-38**.</span><span class="sxs-lookup"><span data-stu-id="f121f-231">**Figure 6-38**.</span></span> <span data-ttu-id="f121f-232">Visión ampliada de los servicios de agregador</span><span class="sxs-lookup"><span data-stu-id="f121f-232">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="f121f-233">Se puede observar la complejidad del diagrama cuando se muestran las posibles solicitudes procedentes de las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-233">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get pretty complex.</span></span> <span data-ttu-id="f121f-234">Aunque se puede ver cómo se simplificarían las flechas de color azul, desde la perspectiva de las aplicaciones cliente, al usar el patrón de agregadores mediante la reducción del intercambio de mensajes y la latencia de la comunicación, en última instancia se mejora de forma significativa la experiencia del usuario, especialmente para las aplicaciones remotas (aplicaciones móviles y SPA).</span><span class="sxs-lookup"><span data-stu-id="f121f-234">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="f121f-235">El caso del área empresarial "Marketing" y los microservicios es un caso de uso muy simple, por lo que no hubo necesidad de usar agregadores, pero podría ser posible, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="f121f-235">In the case of the “Marketing” business area and microservices, it is a very simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="f121f-236">Autenticación y autorización en las puertas de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-236">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="f121f-237">En una puerta de enlace de API de Ocelot se puede ubicar el servicio de autenticación, como un servicio de API web de ASP.NET Core con [IdentityServer](https://identityserver.io/) para proporcionar el token de autenticación, fuera o dentro de la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-237">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="f121f-238">Dado que en eShopOnContainers se usan varias puertas de enlace de API con límites basados en BFF y áreas de negocio, el servicio Identity/Auth se excluye de las puertas de enlace de API, como se resalta en color amarillo en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-238">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![Diagrama de arquitectura de eShopOnContainers en el que se muestra el microservicio Identity debajo de la puerta de enlace de API.](./media/image39.png)

<span data-ttu-id="f121f-240">**Figura 6-39**.</span><span class="sxs-lookup"><span data-stu-id="f121f-240">**Figure 6-39**.</span></span> <span data-ttu-id="f121f-241">Posición del servicio Identity en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f121f-241">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="f121f-242">Pero Ocelot también admite que el microservicio Identity/Auth se sitúe dentro de los límites de la puerta de enlace de API, como se muestra en este otro diagrama.</span><span class="sxs-lookup"><span data-stu-id="f121f-242">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Autenticación con el microservicio Identity debajo de la puerta de enlace de API (AG): 1) AG solicita un token de autenticación del microservicio Identity, 2) el microservicio devuelve el token a AG, 3-4) solicitudes de AG de los microservicios mediante el token de autenticación.](./media/image40.png)

<span data-ttu-id="f121f-244">**Figura 6-40**.</span><span class="sxs-lookup"><span data-stu-id="f121f-244">**Figure 6-40**.</span></span> <span data-ttu-id="f121f-245">Autenticación en Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-245">Authentication in Ocelot</span></span>

<span data-ttu-id="f121f-246">Como en la aplicación eShopOnContainers se ha dividido la puerta de enlace de API en varios BFF (back-end para front-end) y puertas de enlace de API de áreas de negocio, otra opción habría sido crear una puerta de enlace de API adicional para los intereses transversales.</span><span class="sxs-lookup"><span data-stu-id="f121f-246">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would had been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="f121f-247">Esa opción sería razonable en una arquitectura basada en microservicios más compleja con varios microservicios de intereses transversales.</span><span class="sxs-lookup"><span data-stu-id="f121f-247">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="f121f-248">Como en eShopOnContainers solo hay un interés transversal, se decidió controlar solamente el servicio de seguridad fuera del territorio de la puerta de enlace de API, por motivos de simplicidad.</span><span class="sxs-lookup"><span data-stu-id="f121f-248">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity’s sake.</span></span>

<span data-ttu-id="f121f-249">En cualquier caso, si la aplicación está protegida en el nivel de puerta de enlace de API, el módulo de autenticación de la puerta de enlace de API de Ocelot se visita en primer lugar cuando se intenta usar cualquier microservicio protegido.</span><span class="sxs-lookup"><span data-stu-id="f121f-249">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="f121f-250">Eso redirige la solicitud HTTP al microservicio Identity o de autenticación para obtener el token de acceso para que los servicios protegidos se puedan visitar con el token de acceso.</span><span class="sxs-lookup"><span data-stu-id="f121f-250">That re-directs the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="f121f-251">La forma de proteger con autenticación cualquier servicio en el nivel de la puerta de enlace de API consiste en establecer AuthenticationProviderKey en su configuración relacionada en el archivo configuration.json.</span><span class="sxs-lookup"><span data-stu-id="f121f-251">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
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

<span data-ttu-id="f121f-252">Cuando se ejecuta Ocelot, consultará la redistribución AuthenticationOptions.AuthenticationProviderKey y comprobará que hay que un proveedor de autenticación registrado con la clave especificada.</span><span class="sxs-lookup"><span data-stu-id="f121f-252">When Ocelot runs, it will look at the Re-Routes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="f121f-253">Si no lo hay, Ocelot no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="f121f-253">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="f121f-254">Si lo hay, la redistribución usará ese proveedor cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="f121f-254">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="f121f-255">Como el WebHost de Ocelot está configurado con `authenticationProviderKey = "IdentityApiKey"`, eso requerirá la autenticación cada vez que el servicio tenga alguna solicitud sin ningún token de autenticación.</span><span class="sxs-lookup"><span data-stu-id="f121f-255">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

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

<span data-ttu-id="f121f-256">Después, también tendrá que establecer la autorización con el atributo [Authorize] en cualquier recurso al que se vaya a acceder como los microservicios, como en el siguiente controlador del microservicio Basket.</span><span class="sxs-lookup"><span data-stu-id="f121f-256">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

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

<span data-ttu-id="f121f-257">ValidAudiences como "basket" se ponen en correlación con el público definido en cada microservicio con `AddJwtBearer()` en el método ConfigureServices() de la clase Startup, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-257">The ValidAudiences such as “basket” are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

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

<span data-ttu-id="f121f-258">Si intenta acceder a cualquier microservicio protegido (como Basket) con una dirección URL de redistribución basada en la puerta de enlace de API como `http://localhost:5202/api/v1/b/basket/1`, obtendrá un error "401 No autorizado" a menos que proporcione un token válido.</span><span class="sxs-lookup"><span data-stu-id="f121f-258">If you try to access any secured microservice, like the Basket microservice with a Re-Route URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you’ll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="f121f-259">Por otro lado, si una dirección URL de redistribución está autenticada, Ocelot invocará cualquier esquema de nivel inferior con el que esté asociada (la dirección URL de microservicio interna).</span><span class="sxs-lookup"><span data-stu-id="f121f-259">On the other hand, if a Re-Route URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="f121f-260">**Autorización en el nivel de redistribuciones de Ocelot.**</span><span class="sxs-lookup"><span data-stu-id="f121f-260">**Authorization at Ocelot’s ReRoutes tier.**</span></span>  <span data-ttu-id="f121f-261">Ocelot admite la autorización basada en notificaciones que se evalúa después de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f121f-261">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="f121f-262">La autorización se establece en un nivel de ruta mediante la adición de las líneas siguientes a la configuración de redistribución.</span><span class="sxs-lookup"><span data-stu-id="f121f-262">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="f121f-263">En ese ejemplo, cuando se llama al software intermedio de autorización, Ocelot comprobará si el usuario tiene el tipo de notificación "UserType" en el token y si el valor de esa notificación es "employee".</span><span class="sxs-lookup"><span data-stu-id="f121f-263">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="f121f-264">En caso contrario, el usuario no tendrá autorización y la respuesta será el error "403 Prohibido".</span><span class="sxs-lookup"><span data-stu-id="f121f-264">If it isn’t, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="f121f-265">Uso de entrada de Kubernetes con las puertas de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-265">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="f121f-266">Al usar Kubernetes (como en un clúster de Azure Kubernetes Service) normalmente todas las solicitudes HTTP se unifican a través de la [capa de entrada de Kubernetes](https://kubernetes.io/docs/concepts/services-networking/ingress/) basada en *Nginx*.</span><span class="sxs-lookup"><span data-stu-id="f121f-266">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="f121f-267">En Kubernetes, si no se usa ningún enfoque de entrada, los servicios y pods tienen direcciones IP que solo son enrutables por la red de clústeres.</span><span class="sxs-lookup"><span data-stu-id="f121f-267">In Kubernetes, if you don’t use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="f121f-268">Pero si usa un enfoque de entrada, tendrá una capa intermedia entre Internet y los servicios (incluidas las puertas de enlace de API), que actúa como un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f121f-268">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="f121f-269">Como definición, una entrada es una colección de reglas que permiten que las conexiones entrantes lleguen a los servicios de clúster.</span><span class="sxs-lookup"><span data-stu-id="f121f-269">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="f121f-270">Normalmente, una entrada se configura para proporcionar a los servicios direcciones URL accesibles de forma externa, tráfico con equilibrio de carga, terminación SSL y mucho más.</span><span class="sxs-lookup"><span data-stu-id="f121f-270">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="f121f-271">Los usuarios solicitan la entrada mediante la publicación del recurso de entrada en el servidor de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-271">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="f121f-272">En eShopOnContainers, al desarrollar de forma local y usar solamente el equipo de desarrollo como el host de Docker, no se usa ninguna entrada, solo las diferentes puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-272">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="f121f-273">Pero cuando el destino es un entorno de "producción" basado en Kubernetes, en eShopOnContainers se usa una entrada delante de las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-273">However, when targeting a “production” environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="f121f-274">De este modo, los clientes pueden seguir llamando a la misma dirección URL base, pero las solicitudes se enrutan a varias puertas de enlace de API o BFF.</span><span class="sxs-lookup"><span data-stu-id="f121f-274">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="f121f-275">Tenga en cuenta que las puertas de enlace de API actúan de front-end o fachadas en las que solo se exponen los servicios, pero no las aplicaciones web que suelen estar fuera de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="f121f-275">Note that API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="f121f-276">Además, es posible que las puertas de enlace de API oculten ciertos microservicios internos.</span><span class="sxs-lookup"><span data-stu-id="f121f-276">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="f121f-277">Pero la entrada simplemente redirige las solicitudes HTTP pero no intenta ocultar ningún microservicio ni aplicación web.</span><span class="sxs-lookup"><span data-stu-id="f121f-277">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="f121f-278">Tener un nivel Nginx de entrada en Kubernetes delante de las aplicaciones web además de las distintas puertas de enlace de API de Ocelot o BFF es la arquitectura ideal, como se muestra en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="f121f-278">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Una entrada de Kubernetes actúa como un proxy inverso para todo el tráfico a la aplicación, incluidas las aplicaciones web, que normalmente están fuera del ámbito de la puerta de enlace de la API.](./media/image41.png)

<span data-ttu-id="f121f-280">**Figura 6-41**.</span><span class="sxs-lookup"><span data-stu-id="f121f-280">**Figure 6-41**.</span></span> <span data-ttu-id="f121f-281">El nivel de entrada en eShopOnContainers cuando se implementa en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f121f-281">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="f121f-282">Al implementar eShopOnContainers en Kubernetes, solo expone algunos servicios o puntos de conexión a través de la _entrada_, básicamente la lista siguiente de postfijos en las direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="f121f-282">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="f121f-283">`/` para la aplicación web SPA cliente</span><span class="sxs-lookup"><span data-stu-id="f121f-283">`/` for the client SPA web application</span></span>
- <span data-ttu-id="f121f-284">`/webmvc` para la aplicación web MVC cliente</span><span class="sxs-lookup"><span data-stu-id="f121f-284">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="f121f-285">`/webstatus` para la aplicación web cliente en la que se muestra el estado o las comprobaciones de estado</span><span class="sxs-lookup"><span data-stu-id="f121f-285">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="f121f-286">`/webshoppingapigw` para el BFF web y los procesos empresariales de compra</span><span class="sxs-lookup"><span data-stu-id="f121f-286">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="f121f-287">`/webmarketingapigw` para el BFF web y los procesos empresariales de marketing</span><span class="sxs-lookup"><span data-stu-id="f121f-287">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="f121f-288">`/mobileshoppingapigw` para el BFF para dispositivos móviles y los procesos empresariales de compra</span><span class="sxs-lookup"><span data-stu-id="f121f-288">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="f121f-289">`/mobilemarketingapigw` para el BFF para dispositivos móviles y los procesos empresariales de marketing</span><span class="sxs-lookup"><span data-stu-id="f121f-289">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="f121f-290">Al implementar en Kubernetes, cada puerta de enlace de API Ocelot usa un archivo "configuration.json" diferente para cada _pod_ en el que se ejecutan las puertas de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-290">When deploying to Kubernetes, each Ocelot API Gateway is using a different “configuration.json” file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="f121f-291">Dichos archivos "configuration.json" se proporcionan mediante el montaje (originalmente con el script deploy.ps1) de un volumen creado en función de un _mapa de configuración_ de Kubernetes denominado "ocelot".</span><span class="sxs-lookup"><span data-stu-id="f121f-291">Those “configuration.json” files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot’.</span></span> <span data-ttu-id="f121f-292">Cada contenedor monta su archivo de configuración relacionado en la carpeta `/app/configuration` del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f121f-292">Each container mounts its related configuration file in the container’s folder named `/app/configuration`.</span></span>

<span data-ttu-id="f121f-293">En los archivos de código fuente de eShopOnContainers, los archivos "configuration.json" originales se encuentran en la carpeta `k8s/ocelot/`.</span><span class="sxs-lookup"><span data-stu-id="f121f-293">In the source code files of eShopOnContainers, the original “configuration.json” files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="f121f-294">Hay un archivo para cada BFF o puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="f121f-294">There’s one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="f121f-295">Características transversales adicionales en una puerta de enlace de API de Ocelot</span><span class="sxs-lookup"><span data-stu-id="f121f-295">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="f121f-296">Cuando se usa una puerta de enlace de API de Ocelot hay otras características importantes para investigar y utilizar, como se describe en los vínculos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f121f-296">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="f121f-297">**Service discovery in the client side integrating Ocelot with Consul or Eureka** \ (Detección de servicios en el lado cliente mediante la integración de Ocelot con Consul o Eureka)</span><span class="sxs-lookup"><span data-stu-id="f121f-297">**Service discovery in the client side integrating Ocelot with Consul or Eureka** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="f121f-298">**Caching at the API Gateway tier** \ (Almacenamiento en caché en el nivel de puerta de enlace de API)</span><span class="sxs-lookup"><span data-stu-id="f121f-298">**Caching at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="f121f-299">**Logging at the API Gateway tier** \ (Registro en el nivel de puerta de enlace de API)</span><span class="sxs-lookup"><span data-stu-id="f121f-299">**Logging at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="f121f-300">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** \ (Calidad de servicio (reintentos e interruptores) en el nivel de puerta de enlace de API)</span><span class="sxs-lookup"><span data-stu-id="f121f-300">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="f121f-301">**Rate limiting** \ (Limitación de velocidad)</span><span class="sxs-lookup"><span data-stu-id="f121f-301">**Rate limiting** \\</span></span>
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="f121f-302">[Anterior](background-tasks-with-ihostedservice.md)
> [Siguiente](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="f121f-302">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
