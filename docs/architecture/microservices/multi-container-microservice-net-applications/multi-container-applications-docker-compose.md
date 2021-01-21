---
title: Definir una aplicación de varios contenedores con docker-compose.yml
description: Cómo se especifica la composición de microservicios para una aplicación de varios contenedores con docker-compose.yml.
ms.date: 01/13/2021
ms.openlocfilehash: 224b06c6a10834b42218746964f05b055d947235
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188795"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="aff80-103">Definir una aplicación de varios contenedores con docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="aff80-103">Defining your multi-container application with docker-compose.yml</span></span>

<span data-ttu-id="aff80-104">En esta guía, el archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) se ha introducido en la sección [Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span><span class="sxs-lookup"><span data-stu-id="aff80-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="aff80-105">Pero hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.</span><span class="sxs-lookup"><span data-stu-id="aff80-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="aff80-106">Por ejemplo, puede describir explícitamente cómo quiere implementar la aplicación de varios contenedores en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="aff80-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="aff80-107">Si quiere, también puede describir cómo va a compilar las imágenes de Docker personalizadas</span><span class="sxs-lookup"><span data-stu-id="aff80-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="aff80-108">(las imágenes de Docker personalizadas también se pueden compilar con la CLI de Docker).</span><span class="sxs-lookup"><span data-stu-id="aff80-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="aff80-109">Básicamente define cada uno de los contenedores que quiere implementar, además de ciertas características para cada implementación de contenedor.</span><span class="sxs-lookup"><span data-stu-id="aff80-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="aff80-110">Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada por el comando de la CLI [docker-compose up](https://docs.docker.com/compose/overview/) o bien puede implementarla de forma transparente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aff80-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="aff80-111">En caso contrario, tendría que usar la CLI de Docker para implementar uno a uno los contenedores en varios pasos mediante el comando `docker run` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aff80-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="aff80-112">Por lo tanto, cada servicio definido en el archivo docker-compose.yml debe especificar exactamente una imagen o compilación.</span><span class="sxs-lookup"><span data-stu-id="aff80-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="aff80-113">El resto de las claves son opcionales y son análogas a sus equivalentes de la línea de comandos de `docker run`.</span><span class="sxs-lookup"><span data-stu-id="aff80-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="aff80-114">El siguiente código YAML es la definición de un archivo docker-compose.yml posiblemente global pero único para el ejemplo de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="aff80-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="aff80-115">Este código no es el archivo docker-compose real de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="aff80-115">This code is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="aff80-116">sino que es una versión simplificada y consolidada en un único archivo, lo cual no es la mejor manera de trabajar con archivos docker-compose, como se explicará más adelante.</span><span class="sxs-lookup"><span data-stu-id="aff80-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=[PLACEHOLDER]
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=[PLACEHOLDER]
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=[PLACEHOLDER]
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

<span data-ttu-id="aff80-117">La clave raíz de este archivo es "services" (servicios).</span><span class="sxs-lookup"><span data-stu-id="aff80-117">The root key in this file is services.</span></span> <span data-ttu-id="aff80-118">En esa clave se definen los servicios que se quieren implementar y ejecutar al ejecutar el comando `docker-compose up`, o bien al implementarlos desde Visual Studio mediante este archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="aff80-118">Under that key, you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="aff80-119">En este caso, el archivo docker-compose.yml tiene varios servicios definidos, como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="aff80-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="aff80-120">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="aff80-120">Service name</span></span> | <span data-ttu-id="aff80-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff80-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="aff80-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="aff80-122">webmvc</span></span>       | <span data-ttu-id="aff80-123">Contenedor que incluye la aplicación ASP.NET Core MVC que consume los microservicios de C\# del lado servidor</span><span class="sxs-lookup"><span data-stu-id="aff80-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="aff80-124">catalog-api</span><span class="sxs-lookup"><span data-stu-id="aff80-124">catalog-api</span></span>  | <span data-ttu-id="aff80-125">Contenedor que incluye el microservicio Catalog de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aff80-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="aff80-126">ordering-api</span><span class="sxs-lookup"><span data-stu-id="aff80-126">ordering-api</span></span> | <span data-ttu-id="aff80-127">Contenedor que incluye el microservicio Ordering de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aff80-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="aff80-128">sqldata</span><span class="sxs-lookup"><span data-stu-id="aff80-128">sqldata</span></span>     | <span data-ttu-id="aff80-129">Contenedor que ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios</span><span class="sxs-lookup"><span data-stu-id="aff80-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="aff80-130">basket-api</span><span class="sxs-lookup"><span data-stu-id="aff80-130">basket-api</span></span>   | <span data-ttu-id="aff80-131">Contenedor que incluye el microservicio Basket de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aff80-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="aff80-132">basketdata</span><span class="sxs-lookup"><span data-stu-id="aff80-132">basketdata</span></span>  | <span data-ttu-id="aff80-133">Contenedor que ejecuta el servicio Redis Cache, con la base de datos Basket como caché de Redis</span><span class="sxs-lookup"><span data-stu-id="aff80-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="aff80-134">Contenedor de la API de servicio web simple</span><span class="sxs-lookup"><span data-stu-id="aff80-134">A simple Web Service API container</span></span>

<span data-ttu-id="aff80-135">Si nos centramos en un único contenedor, el microservicio de contenedor catalog-api tiene una definición sencilla:</span><span class="sxs-lookup"><span data-stu-id="aff80-135">Focusing on a single container, the catalog-api container-microservice has a straightforward definition:</span></span>

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=[PLACEHOLDER]
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

<span data-ttu-id="aff80-136">Este servicio de contenedor tiene la siguiente configuración básica:</span><span class="sxs-lookup"><span data-stu-id="aff80-136">This containerized service has the following basic configuration:</span></span>

- <span data-ttu-id="aff80-137">Se basa en la imagen **eshop/catalog-api** personalizada.</span><span class="sxs-lookup"><span data-stu-id="aff80-137">It is based on the custom **eshop/catalog-api** image.</span></span> <span data-ttu-id="aff80-138">Por simplicidad, no hay ninguna compilación: configuración de clave en el archivo.</span><span class="sxs-lookup"><span data-stu-id="aff80-138">For simplicity's sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="aff80-139">Esto significa que la imagen se debe haber compilado previamente (con docker build) o se debe haber descargado (con el comando docker pull) de cualquier registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="aff80-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

- <span data-ttu-id="aff80-140">Define una variable de entorno denominada ConnectionString con la cadena de conexión para que la use Entity Framework para obtener acceso a la instancia de SQL Server que contiene el modelo de datos del catálogo.</span><span class="sxs-lookup"><span data-stu-id="aff80-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="aff80-141">En este caso, el mismo contenedor de SQL Server contiene varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="aff80-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="aff80-142">Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker,</span><span class="sxs-lookup"><span data-stu-id="aff80-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="aff80-143">aunque también podría implementar un contenedor de SQL Server para cada base de datos de microservicio.</span><span class="sxs-lookup"><span data-stu-id="aff80-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

- <span data-ttu-id="aff80-144">El nombre de SQL Server es **sqldata**, que es el mismo nombre que se usa para el contenedor que ejecuta la instancia de SQL Server para Linux.</span><span class="sxs-lookup"><span data-stu-id="aff80-144">The SQL Server name is **sqldata**, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="aff80-145">Esto resulta práctico: poder usar esta resolución de nombres (interna al host de Docker) resolverá la dirección de red, por lo que no necesita saber la dirección IP interna de los contenedores a los que tiene acceso desde otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="aff80-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don't need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="aff80-146">Dado que la cadena de conexión se define mediante una variable de entorno, podría establecer esa variable mediante otro mecanismo y en otro momento.</span><span class="sxs-lookup"><span data-stu-id="aff80-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="aff80-147">Por ejemplo, podría establecer una cadena de conexión diferente al efectuar una implementación en producción en los hosts finales, o haciéndolo desde sus canalizaciones de CI/CD en Azure DevOps Services o en su sistema de DevOps preferido.</span><span class="sxs-lookup"><span data-stu-id="aff80-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

- <span data-ttu-id="aff80-148">Expone el puerto 80 para el acceso interno al servicio **catalog-api** dentro del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="aff80-148">It exposes port 80 for internal access to the **catalog-api** service within the Docker host.</span></span> <span data-ttu-id="aff80-149">Actualmente, el host es una máquina virtual de Linux porque se basa en una imagen de Docker para Linux, aunque podría configurar el contenedor para que se ejecute en una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="aff80-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

- <span data-ttu-id="aff80-150">Reenvía el puerto 80 expuesto del contenedor al puerto 5101 del equipo host de Docker (la máquina virtual de Linux).</span><span class="sxs-lookup"><span data-stu-id="aff80-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

- <span data-ttu-id="aff80-151">Vincula el servicio web al servicio **sqldata** (la base de datos de instancias de SQL Server para Linux que se ejecuta en un contenedor).</span><span class="sxs-lookup"><span data-stu-id="aff80-151">It links the web service to the **sqldata** service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="aff80-152">Al especificar esta dependencia, el contenedor catalog-api no se iniciará hasta que se haya iniciado el contenedor sqldata. Este aspecto es importante porque catalog-api necesita primero que la base de datos de SQL Server esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="aff80-152">When you specify this dependency, the catalog-api container will not start until the sqldata container has already started; this aspect is important because catalog-api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="aff80-153">Pero este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que Docker efectúa comprobaciones únicamente en el nivel de contenedor.</span><span class="sxs-lookup"><span data-stu-id="aff80-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="aff80-154">A veces es posible que el servicio (en este caso SQL Server) aún no esté listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en los microservicios de su cliente.</span><span class="sxs-lookup"><span data-stu-id="aff80-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="aff80-155">De este modo, si un contenedor de dependencia no está listo durante un período de tiempo breve, la aplicación seguirá siendo resistente.</span><span class="sxs-lookup"><span data-stu-id="aff80-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

- <span data-ttu-id="aff80-156">Está configurado para permitir el acceso a los servidores externos: el valor de configuración extra\_hosts le permite obtener acceso a máquinas o servidores externos situados fuera del host de Docker (es decir, fuera de la máquina virtual de Linux predeterminada, que es un host de Docker de desarrollo), como una instancia local de SQL Server en su equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="aff80-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM, which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="aff80-157">También existen otras opciones más avanzadas de los archivos `docker-compose.yml` que se exponen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="aff80-157">There are also other, more advanced `docker-compose.yml` settings that we'll discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="aff80-158">Usar archivos docker-compose para fijar como objetivo varios entornos</span><span class="sxs-lookup"><span data-stu-id="aff80-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="aff80-159">Los archivos `docker-compose.*.yml` son archivos de definición que se pueden usar en varias infraestructuras que comprendan ese formato.</span><span class="sxs-lookup"><span data-stu-id="aff80-159">The `docker-compose.*.yml` files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="aff80-160">La herramienta más sencilla y directa es el comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="aff80-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="aff80-161">Por lo tanto, si usa el comando docker-compose, puede fijar como objetivo los siguientes escenarios principales.</span><span class="sxs-lookup"><span data-stu-id="aff80-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="aff80-162">Entornos de desarrollo</span><span class="sxs-lookup"><span data-stu-id="aff80-162">Development environments</span></span>

<span data-ttu-id="aff80-163">Al desarrollar aplicaciones, es importante poder ejecutar una aplicación en un entorno de desarrollo aislado.</span><span class="sxs-lookup"><span data-stu-id="aff80-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="aff80-164">Puede usar el comando de la CLI docker-compose para crear ese entorno o Visual Studio, que usa docker-compose en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="aff80-164">You can use the docker-compose CLI command to create that environment or Visual Studio, which uses docker-compose under the covers.</span></span>

<span data-ttu-id="aff80-165">El archivo docker-compose.yml le permite configurar y documentar todas las dependencias de servicio de la aplicación (otros servicios, la caché, bases de datos, colas, etc.).</span><span class="sxs-lookup"><span data-stu-id="aff80-165">The docker-compose.yml file allows you to configure and document all your application's service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="aff80-166">Con el comando de la CLI docker-compose puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="aff80-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="aff80-167">Los archivos docker-compose.yml son archivos de configuración interpretados por el motor de Docker, pero también actúan como prácticos archivos de documentación sobre la composición de la aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="aff80-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="aff80-168">Entornos de prueba</span><span class="sxs-lookup"><span data-stu-id="aff80-168">Testing environments</span></span>

<span data-ttu-id="aff80-169">Una parte importante de cualquier proceso de implementación continua (CD) o de integración continua (CI) son las pruebas unitarias y las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="aff80-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="aff80-170">Estas pruebas automatizadas requieren un entorno aislado, por lo que no se ven afectadas por los usuarios ni por ningún otro cambio efectuado en los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aff80-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application's data.</span></span>

<span data-ttu-id="aff80-171">Con Docker Compose puede crear y destruir ese entorno aislado de un modo muy sencillo ejecutando unos scripts o comandos en el símbolo del sistema, como los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aff80-171">With Docker Compose, you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="aff80-172">Implementaciones de producción</span><span class="sxs-lookup"><span data-stu-id="aff80-172">Production deployments</span></span>

<span data-ttu-id="aff80-173">También puede usar Compose para efectuar una implementación en un motor de Docker remoto.</span><span class="sxs-lookup"><span data-stu-id="aff80-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="aff80-174">Un caso típico consiste en efectuar una implementación en una única instancia de host de Docker (como una máquina virtual de producción o un servidor aprovisionado con [Docker Machine](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="aff80-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="aff80-175">Si usa cualquier otro orquestador (Azure Service Fabric, Kubernetes, etc.), es posible que tenga que agregar valores de configuración de instalación y metadatos como los de docker-compose.yml, pero con el formato necesario para el otro orquestador.</span><span class="sxs-lookup"><span data-stu-id="aff80-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="aff80-176">En cualquier caso, docker-compose es una herramienta y un formato de metadatos prácticos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orquestador que está usando.</span><span class="sxs-lookup"><span data-stu-id="aff80-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="aff80-177">Usar varios archivos docker-compose para controlar distintos entornos</span><span class="sxs-lookup"><span data-stu-id="aff80-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="aff80-178">Al fijar como objetivo entornos diferentes, debe usar varios archivos compose.</span><span class="sxs-lookup"><span data-stu-id="aff80-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="aff80-179">Este enfoque permite crear distintas variantes de configuración en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="aff80-179">This approach lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="aff80-180">Invalidar el archivo base docker-compose</span><span class="sxs-lookup"><span data-stu-id="aff80-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="aff80-181">Podría usar un archivo docker-compose.yml como en los ejemplos simplificados que se muestran en las secciones anteriores,</span><span class="sxs-lookup"><span data-stu-id="aff80-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="aff80-182">pero no se recomienda para la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="aff80-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="aff80-183">De forma predeterminada, Compose lee dos archivos, un archivo docker-compose.yml y un archivo docker-compose.override.yml opcional.</span><span class="sxs-lookup"><span data-stu-id="aff80-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="aff80-184">Como se muestra en la figura 6-11, cuando se usa Visual Studio y se habilita la compatibilidad con Docker, Visual Studio también crea un archivo docker-compose.vs.debug.g.yml adicional para depurar la aplicación, como se puede ver en la carpeta obj\\Docker\\ de la carpeta de la solución principal.</span><span class="sxs-lookup"><span data-stu-id="aff80-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![Archivos de un proyecto de Docker Compose.](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

<span data-ttu-id="aff80-186">**Figura 6-11**.</span><span class="sxs-lookup"><span data-stu-id="aff80-186">**Figure 6-11**.</span></span> <span data-ttu-id="aff80-187">Archivos docker-compose en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="aff80-187">docker-compose files in Visual Studio 2019</span></span>

<span data-ttu-id="aff80-188">Estructura de los archivos de un proyecto de **docker-compose**:</span><span class="sxs-lookup"><span data-stu-id="aff80-188">**docker-compose** project file structure:</span></span>

- <span data-ttu-id="aff80-189">*.dockerignore*: se usa para omitir archivos.</span><span class="sxs-lookup"><span data-stu-id="aff80-189">*.dockerignore* - used to ignore files</span></span>
- <span data-ttu-id="aff80-190">*docker-compose.yml*: se usa para crear microservicios.</span><span class="sxs-lookup"><span data-stu-id="aff80-190">*docker-compose.yml* - used to compose microservices</span></span>
- <span data-ttu-id="aff80-191">*docker-compose.override.yml*: se usa para configurar el entorno de microservicios.</span><span class="sxs-lookup"><span data-stu-id="aff80-191">*docker-compose.override.yml* - used to configure microservices environment</span></span>

<span data-ttu-id="aff80-192">Puede editar los archivos docker-compose con cualquier editor, como Visual Studio Code o Sublime, y ejecutar la aplicación con el comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="aff80-192">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="aff80-193">Por convención, el archivo docker-compose.yml contiene la configuración básica y otras opciones estáticas.</span><span class="sxs-lookup"><span data-stu-id="aff80-193">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="aff80-194">Esto significa que la configuración del servicio no debería variar según el entorno de implementación que tenga como objetivo.</span><span class="sxs-lookup"><span data-stu-id="aff80-194">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="aff80-195">El archivo docker-compose.override.yml, como su nombre sugiere, contiene valores de configuración que invalidan la configuración básica, como la configuración que depende del entorno de implementación.</span><span class="sxs-lookup"><span data-stu-id="aff80-195">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="aff80-196">También puede tener varios archivos de invalidación con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="aff80-196">You can have multiple override files with different names also.</span></span> <span data-ttu-id="aff80-197">Los archivos de invalidación suelen contener información adicional necesaria para la aplicación, pero que es específica de un entorno o de una implementación.</span><span class="sxs-lookup"><span data-stu-id="aff80-197">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="aff80-198">Fijar como objetivo varios entornos</span><span class="sxs-lookup"><span data-stu-id="aff80-198">Targeting multiple environments</span></span>

<span data-ttu-id="aff80-199">Un caso de uso típico es cuando se definen varios archivos compose de manera que puede fijar como objetivo varios entornos (por ejemplo, producción, almacenamiento provisional, integración continua o desarrollo).</span><span class="sxs-lookup"><span data-stu-id="aff80-199">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="aff80-200">Para dar cabida a estas diferencias, la configuración de Compose se puede dividir en varios archivos, como se muestra en la figura 6-12.</span><span class="sxs-lookup"><span data-stu-id="aff80-200">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![Diagrama de tres archivos de docker-compose establecidos para invalidar el archivo base.](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

<span data-ttu-id="aff80-202">**Figura 6-12**.</span><span class="sxs-lookup"><span data-stu-id="aff80-202">**Figure 6-12**.</span></span> <span data-ttu-id="aff80-203">Varios archivos docker-compose invalidan los valores del archivo base docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="aff80-203">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="aff80-204">Se pueden combinar varios archivos docker-compose\*.yml para controlar otros entornos.</span><span class="sxs-lookup"><span data-stu-id="aff80-204">You can combine multiple docker-compose\*.yml files to handle different environments.</span></span> <span data-ttu-id="aff80-205">Comienza con el archivo base docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="aff80-205">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="aff80-206">Este archivo base debe contener los valores de configuración básicos o estáticos que no varían según el entorno.</span><span class="sxs-lookup"><span data-stu-id="aff80-206">This base file contains the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="aff80-207">Por ejemplo, la aplicación eShopOnContainers tiene el siguiente archivo docker-compose.yml (simplificado con menos servicios) como archivo base.</span><span class="sxs-lookup"><span data-stu-id="aff80-207">For example, the eShopOnContainers app has the following docker-compose.yml file (simplified with fewer services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="aff80-208">Los valores del archivo base docker-compose.yml no deberían variar porque haya distintos entornos de implementación de destino.</span><span class="sxs-lookup"><span data-stu-id="aff80-208">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="aff80-209">Si se centra en la definición del servicio webmvc, por ejemplo, puede ver que esa información es la misma con independencia del entorno que fije como objetivo.</span><span class="sxs-lookup"><span data-stu-id="aff80-209">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="aff80-210">Dispone de la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="aff80-210">You have the following information:</span></span>

- <span data-ttu-id="aff80-211">El nombre del servicio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="aff80-211">The service name: webmvc.</span></span>

- <span data-ttu-id="aff80-212">La imagen personalizada del contenedor: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="aff80-212">The container's custom image: eshop/webmvc.</span></span>

- <span data-ttu-id="aff80-213">El comando para compilar la imagen personalizada de Docker, que indica qué Dockerfile se debe usar.</span><span class="sxs-lookup"><span data-stu-id="aff80-213">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

- <span data-ttu-id="aff80-214">Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que se hayan iniciado los otros contenedores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="aff80-214">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="aff80-215">Puede tener otra configuración, pero lo importante es que en el archivo base docker-compose.yml solo establezca la información que es común en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="aff80-215">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="aff80-216">Luego, en el archivo docker-compose.override.yml o en archivos similares de producción o almacenamiento provisional, debería colocar la configuración específica para cada entorno.</span><span class="sxs-lookup"><span data-stu-id="aff80-216">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="aff80-217">Por lo general, el archivo docker-compose.override.yml se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="aff80-217">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=[PLACEHOLDER]}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=[PLACEHOLDER]}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=[PLACEHOLDER]
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="aff80-218">En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define variables de entorno con direcciones URL de redireccionamiento y especifica cadenas de conexión para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="aff80-218">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="aff80-219">Esta configuración es solo para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="aff80-219">These settings are all just for the development environment.</span></span>

<span data-ttu-id="aff80-220">Al ejecutar `docker-compose up` (o al iniciarlo en Visual Studio), el comando lee las invalidaciones automáticamente como si se combinaran ambos archivos.</span><span class="sxs-lookup"><span data-stu-id="aff80-220">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="aff80-221">Imagínese que quiere que otro archivo Compose para el entorno de producción, con distintos valores de configuración, puertos o cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="aff80-221">Suppose that you want another Compose file for the production environment, with different configuration values, ports, or connection strings.</span></span> <span data-ttu-id="aff80-222">Puede crear otro archivo de invalidación, como el archivo llamado `docker-compose.prod.yml`, con distintas configuraciones y variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="aff80-222">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span> <span data-ttu-id="aff80-223">Ese archivo podría estar almacenado en otro repositorio de Git o lo podría administrar y proteger un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="aff80-223">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="aff80-224">Cómo efectuar una implementación con un archivo de invalidación específico</span><span class="sxs-lookup"><span data-stu-id="aff80-224">How to deploy with a specific override file</span></span>

<span data-ttu-id="aff80-225">Para usar varios archivos de invalidación, o un archivo de invalidación con otro nombre, puede usar la opción -f con el comando docker-compose y especificar los archivos.</span><span class="sxs-lookup"><span data-stu-id="aff80-225">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="aff80-226">Cree los archivos de combinaciones en el orden en que se especifican en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aff80-226">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="aff80-227">En el ejemplo siguiente se muestra cómo efectuar la implementación con archivos de invalidación.</span><span class="sxs-lookup"><span data-stu-id="aff80-227">The following example shows how to deploy with override files.</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="aff80-228">Usar variables de entorno en los archivos docker-compose</span><span class="sxs-lookup"><span data-stu-id="aff80-228">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="aff80-229">Resulta práctico, sobre todo en los entornos de producción, poder obtener información de configuración de variables de entorno, como hemos mostrado en ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="aff80-229">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="aff80-230">En los archivos docker-compose se puede hacer referencia a una variable de entorno mediante la sintaxis ${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="aff80-230">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="aff80-231">En la siguiente línea de un archivo docker-compose.prod.yml se muestra cómo hacer referencia al valor de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="aff80-231">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="aff80-232">Las variables de entorno se crean y se inicializan de maneras diferentes, en función de su entorno de host (Linux, Windows, clúster en la nube, etc.),</span><span class="sxs-lookup"><span data-stu-id="aff80-232">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="aff80-233">aunque un método práctico consiste en usar un archivo .env.</span><span class="sxs-lookup"><span data-stu-id="aff80-233">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="aff80-234">Los archivos docker-compose admiten la declaración de variables de entorno predeterminadas en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="aff80-234">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="aff80-235">Estos valores de las variables de entorno son los valores predeterminados,</span><span class="sxs-lookup"><span data-stu-id="aff80-235">These values for the environment variables are the default values.</span></span> <span data-ttu-id="aff80-236">pero se pueden invalidar con los valores que haya podido definir en cada uno de sus entornos (sistema operativo host o variables de entorno del clúster).</span><span class="sxs-lookup"><span data-stu-id="aff80-236">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="aff80-237">Este archivo .env se coloca en la carpeta en la que se ejecuta el comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="aff80-237">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="aff80-238">En el siguiente ejemplo se muestra un archivo .env como el archivo [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) para la aplicación eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="aff80-238">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="aff80-239">Docker-compose espera que cada línea de un archivo .env tenga el formato \<variable\>=\<value\>.</span><span class="sxs-lookup"><span data-stu-id="aff80-239">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="aff80-240">Los valores establecidos en el entorno en tiempo de ejecución siempre invalidan los valores definidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="aff80-240">The values set in the run-time environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="aff80-241">De forma similar, los valores que se pasan a través de argumentos de la línea de comandos también invalidan los valores predeterminados establecidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="aff80-241">In a similar way, values passed via command-line arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="aff80-242">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aff80-242">Additional resources</span></span>

- <span data-ttu-id="aff80-243">**Introducción a Docker Compose** </span><span class="sxs-lookup"><span data-stu-id="aff80-243">**Overview of Docker Compose** </span></span>\
    <https://docs.docker.com/compose/overview/>

- <span data-ttu-id="aff80-244">**Varios archivos de Compose** </span><span class="sxs-lookup"><span data-stu-id="aff80-244">**Multiple Compose files** </span></span>\
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="aff80-245">Compilación de imágenes optimizadas de Docker de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aff80-245">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="aff80-246">Si está explorando Docker y .NET en orígenes de Internet, encontrará Dockerfiles que muestran lo fácil que es compilar una imagen de Docker copiando el origen en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="aff80-246">If you are exploring Docker and .NET on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="aff80-247">Estos ejemplos sugieren que, si usa una configuración simple, puede tener una imagen de Docker con el entorno empaquetado con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aff80-247">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="aff80-248">En el ejemplo siguiente se muestra un Dockerfile sencillo en esta misma línea.</span><span class="sxs-lookup"><span data-stu-id="aff80-248">The following example shows a simple Dockerfile in this vein.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="aff80-249">Un Dockerfile como este funcionará,</span><span class="sxs-lookup"><span data-stu-id="aff80-249">A Dockerfile like this will work.</span></span> <span data-ttu-id="aff80-250">pero puede optimizar considerablemente sus imágenes, sobre todo las imágenes de producción.</span><span class="sxs-lookup"><span data-stu-id="aff80-250">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="aff80-251">En el modelo de microservicios y contenedores están iniciando contenedores constantemente.</span><span class="sxs-lookup"><span data-stu-id="aff80-251">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="aff80-252">El método habitual de usar los contenedores no reinicia un contenedor inactivo, porque el contenedor se puede descartar.</span><span class="sxs-lookup"><span data-stu-id="aff80-252">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="aff80-253">Los orquestadores (como Kubernetes y Azure Service Fabric) crean instancias de imágenes.</span><span class="sxs-lookup"><span data-stu-id="aff80-253">Orchestrators (like Kubernetes and Azure Service Fabric) create new instances of images.</span></span> <span data-ttu-id="aff80-254">Esto significa que tendría que efectuar una optimización precompilando la aplicación al crearla para que el proceso de creación de instancias sea más rápido.</span><span class="sxs-lookup"><span data-stu-id="aff80-254">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="aff80-255">Cuando se inicia el contenedor, tendría que estar preparado para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="aff80-255">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="aff80-256">No realice restauraciones ni compilaciones en tiempo de ejecución con los comandos `dotnet restore` y `dotnet build` de la CLI, como puede ver en las entradas de blog sobre .NET y Docker.</span><span class="sxs-lookup"><span data-stu-id="aff80-256">Don't restore and compile at run time using the `dotnet restore` and `dotnet build` CLI commands as you may see in blog posts about .NET and Docker.</span></span>

<span data-ttu-id="aff80-257">El equipo de .NET ha estado trabajando mucho para convertir .NET y ASP.NET Core en un marco optimizado para contenedores.</span><span class="sxs-lookup"><span data-stu-id="aff80-257">The .NET team has been doing important work to make .NET and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="aff80-258">.NET no solo es un marco ligero con una superficie de memoria pequeña; el equipo se ha centrado en imágenes de Docker optimizadas para los tres escenarios principales y las ha publicado en el registro de Docker Hub en *dotnet/* , empezando por la versión 2.1:</span><span class="sxs-lookup"><span data-stu-id="aff80-258">Not only is .NET a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at *dotnet/*, beginning with version 2.1:</span></span>

1. <span data-ttu-id="aff80-259">**Desarrollo**: La prioridad es la capacidad de iterar con rapidez y depurar cambios, donde el tamaño es secundario.</span><span class="sxs-lookup"><span data-stu-id="aff80-259">**Development**: The priority is the ability to quickly iterate and debug changes, and where size is secondary.</span></span>

2. <span data-ttu-id="aff80-260">**Compilación**: la prioridad es compilar la aplicación y la imagen incluye los archivos binarios y otras dependencias para optimizar los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="aff80-260">**Build**: The priority is compiling the application, and the image includes binaries and other dependencies to optimize binaries.</span></span>

3. <span data-ttu-id="aff80-261">**Producción**: El foco es la implementación y el inicio rápido de los contenedores, por lo que estas imágenes se limitan a los archivos binarios y el contenido necesario para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aff80-261">**Production**: The focus is fast deploying and starting of containers, so these images are limited to the binaries and content needed to run the application.</span></span>

<span data-ttu-id="aff80-262">El equipo de .NET proporciona cuatro variantes básicas en [dotnet](https://hub.docker.com/_/microsoft-dotnet/) (en Docker Hub):</span><span class="sxs-lookup"><span data-stu-id="aff80-262">The .NET team provides four basic variants in [dotnet/](https://hub.docker.com/_/microsoft-dotnet/) (at Docker Hub):</span></span>

1. <span data-ttu-id="aff80-263">**sdk**: para los escenarios de desarrollo y compilación</span><span class="sxs-lookup"><span data-stu-id="aff80-263">**sdk**: for development and build scenarios</span></span>
1. <span data-ttu-id="aff80-264">**aspnet**: para los escenarios de producción de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aff80-264">**aspnet**: for ASP.NET production scenarios</span></span>
1. <span data-ttu-id="aff80-265">**runtime**: para los escenarios de producción de .NET</span><span class="sxs-lookup"><span data-stu-id="aff80-265">**runtime**: for .NET production scenarios</span></span>
1. <span data-ttu-id="aff80-266">**runtime-deps**: para los escenarios de producción de [aplicaciones autocontenidas](../../../core/deploying/index.md#publish-self-contained)</span><span class="sxs-lookup"><span data-stu-id="aff80-266">**runtime-deps**: for production scenarios of [self-contained applications](../../../core/deploying/index.md#publish-self-contained)</span></span>

<span data-ttu-id="aff80-267">Para un inicio más rápido, las imágenes en tiempo de ejecución también configuran automáticamente las direcciones URL\_aspnetcore en el puerto 80 y usan Ngen para crear una caché de imágenes nativa de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aff80-267">For faster startup, runtime images also automatically set aspnetcore\_urls to port 80 and use Ngen to create a native image cache of assemblies.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="aff80-268">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aff80-268">Additional resources</span></span>

- <span data-ttu-id="aff80-269">**Compilación de imágenes de Docker optimizadas con ASP.NET Core**
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core></span><span class="sxs-lookup"><span data-stu-id="aff80-269">**Building Optimized Docker Images with ASP.NET Core**
<https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core></span></span>

- <span data-ttu-id="aff80-270">**Compilación de imágenes de Docker para aplicaciones de .NET**
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="aff80-270">**Building Docker Images for .NET Applications**
[https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="aff80-271">[Anterior](data-driven-crud-microservice.md)
> [Siguiente](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="aff80-271">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>
