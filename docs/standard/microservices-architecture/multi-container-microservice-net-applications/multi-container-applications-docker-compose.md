---
title: Definir una aplicación de varios contenedores con docker-compose.yml
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Definir una aplicación de varios contenedores con docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: ded2e5399938be25005776963b0310b6a49d0353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="65b72-103">Definir una aplicación de varios contenedores con docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="65b72-103">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="65b72-104">En esta guía, el archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) se ha introducido en la sección [Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="65b72-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="65b72-105">Pero hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.</span><span class="sxs-lookup"><span data-stu-id="65b72-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="65b72-106">Por ejemplo, puede describir explícitamente cómo quiere implementar la aplicación de varios contenedores en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="65b72-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="65b72-107">Si quiere, también puede describir cómo va a compilar las imágenes de Docker personalizadas</span><span class="sxs-lookup"><span data-stu-id="65b72-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="65b72-108">(las imágenes de Docker personalizadas también se pueden compilar con la CLI de Docker).</span><span class="sxs-lookup"><span data-stu-id="65b72-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="65b72-109">Básicamente define cada uno de los contenedores que quiere implementar, además de ciertas características para cada implementación de contenedor.</span><span class="sxs-lookup"><span data-stu-id="65b72-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="65b72-110">Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada por el comando de la CLI [docker-compose up](https://docs.docker.com/compose/overview/) o bien puede implementarla de forma transparente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="65b72-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="65b72-111">En caso contrario, tendría que usar la CLI de Docker para implementar uno a uno los contenedores en varios pasos usando el comando docker run desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65b72-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="65b72-112">Por lo tanto, cada servicio definido en el archivo docker-compose.yml debe especificar exactamente una imagen o compilación.</span><span class="sxs-lookup"><span data-stu-id="65b72-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="65b72-113">El resto de las claves son opcionales y son análogas a sus equivalentes de la línea de comandos docker run.</span><span class="sxs-lookup"><span data-stu-id="65b72-113">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="65b72-114">El siguiente código YAML es la definición de un archivo docker-compose.yml posiblemente global pero único para el ejemplo de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="65b72-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="65b72-115">Este no es el archivo docker-compose real de eShopOnContainers,</span><span class="sxs-lookup"><span data-stu-id="65b72-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="65b72-116">sino que es una versión simplificada y consolidada en un único archivo, lo cual no es la mejor manera de trabajar con archivos docker-compose, como se explicará más adelante.</span><span class="sxs-lookup"><span data-stu-id="65b72-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

<span data-ttu-id="65b72-117">La clave raíz de este archivo es "services" (servicios).</span><span class="sxs-lookup"><span data-stu-id="65b72-117">The root key in this file is services.</span></span> <span data-ttu-id="65b72-118">En esa clave se definen los servicios que se quieren implementar y ejecutar al ejecutar el comando docker-compose up o al implementarlos en Visual Studio usando este archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="65b72-118">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="65b72-119">En este caso, el archivo docker-compose.yml tiene varios servicios definidos, como se describe en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="65b72-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="65b72-120">webmvc: contenedor que incluye la aplicación MVC de ASP.NET Core que consume los microservicios de C\# del lado servidor</span><span class="sxs-lookup"><span data-stu-id="65b72-120">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="65b72-121">catalog.api: contenedor que incluye el microservicio Catalog de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65b72-121">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="65b72-122">ordering.api: contenedor que incluye el microservicio Ordering de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65b72-122">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="65b72-123">sql.data: contenedor que ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios</span><span class="sxs-lookup"><span data-stu-id="65b72-123">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="65b72-124">basket.api: contenedor que incluye el microservicio Basket de la API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65b72-124">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="65b72-125">basket.data: contenedor que ejecuta el servicio Redis Cache, con la base de datos Basket como memoria caché de Redis</span><span class="sxs-lookup"><span data-stu-id="65b72-125">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="65b72-126">Contenedor de la API de servicio web simple</span><span class="sxs-lookup"><span data-stu-id="65b72-126">A simple Web Service API container</span></span>

<span data-ttu-id="65b72-127">Si nos centramos en un único contenedor, el microservicio de contenedor catalog.api tiene una definición sencilla:</span><span class="sxs-lookup"><span data-stu-id="65b72-127">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

<span data-ttu-id="65b72-128">Este servicio de contenedor tiene la siguiente configuración básica:</span><span class="sxs-lookup"><span data-stu-id="65b72-128">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="65b72-129">Se basa en la imagen eshop/catalog.api personalizada.</span><span class="sxs-lookup"><span data-stu-id="65b72-129">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="65b72-130">Por simplicidad, no hay ninguna compilación: configuración clave en el archivo.</span><span class="sxs-lookup"><span data-stu-id="65b72-130">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="65b72-131">Esto significa que la imagen se debe haber compilado previamente (con docker build) o se debe haber descargado (con el comando docker pull) de cualquier registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-131">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="65b72-132">Define una variable de entorno denominada ConnectionString con la cadena de conexión para que la use Entity Framework para obtener acceso a la instancia de SQL Server que contiene el modelo de datos del catálogo.</span><span class="sxs-lookup"><span data-stu-id="65b72-132">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="65b72-133">En este caso, el mismo contenedor de SQL Server contiene varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="65b72-133">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="65b72-134">Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker,</span><span class="sxs-lookup"><span data-stu-id="65b72-134">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="65b72-135">aunque también podría implementar un contenedor de SQL Server para cada base de datos de microservicio.</span><span class="sxs-lookup"><span data-stu-id="65b72-135">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="65b72-136">El nombre de SQL Server es sql.data, que es el mismo nombre que se usa para el contenedor que ejecuta la instancia de SQL Server para Linux.</span><span class="sxs-lookup"><span data-stu-id="65b72-136">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="65b72-137">Esto resulta práctico: poder usar esta resolución de nombres (interna al host de Docker) resolverá la dirección de red, por lo que no necesita saber la dirección IP interna de los contenedores a los que tiene acceso desde otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="65b72-137">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="65b72-138">Dado que la cadena de conexión se define mediante una variable de entorno, podría establecer esa variable mediante otro mecanismo y en otro momento.</span><span class="sxs-lookup"><span data-stu-id="65b72-138">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="65b72-139">Por ejemplo, podría establecer una cadena de conexión diferente al efectuar una implementación en producción en los hosts finales, o haciéndolo desde sus canalizaciones de CI/CD en VSTS o en su sistema de DevOps preferido.</span><span class="sxs-lookup"><span data-stu-id="65b72-139">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="65b72-140">Expone el puerto 80 para el acceso interno al servicio catalog.api dentro del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-140">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="65b72-141">Actualmente, el host es una máquina virtual de Linux porque se basa en una imagen de Docker para Linux, aunque podría configurar el contenedor para que se ejecute en una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="65b72-141">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="65b72-142">Reenvía el puerto 80 expuesto del contenedor al puerto 5101 del equipo host de Docker (la máquina virtual de Linux).</span><span class="sxs-lookup"><span data-stu-id="65b72-142">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="65b72-143">Vincula el servicio web al servicio sql.data (la base de datos de instancias de SQL Server para Linux que se ejecuta en un contenedor).</span><span class="sxs-lookup"><span data-stu-id="65b72-143">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="65b72-144">Al especificar esta dependencia, el contenedor catalog.api no se iniciará hasta que se haya iniciado el contenedor sql.data. Esto es importante porque catalog.api necesita primero que la base de datos de SQL Server esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="65b72-144">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="65b72-145">Pero este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que Docker efectúa comprobaciones únicamente en el nivel de contenedor.</span><span class="sxs-lookup"><span data-stu-id="65b72-145">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="65b72-146">A veces es posible que el servicio (en este caso SQL Server) aún no esté listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en los microservicios de su cliente.</span><span class="sxs-lookup"><span data-stu-id="65b72-146">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="65b72-147">De este modo, si un contenedor de dependencia no está listo durante un período de tiempo breve, la aplicación seguirá siendo resistente.</span><span class="sxs-lookup"><span data-stu-id="65b72-147">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="65b72-148">Está configurado para permitir el acceso a los servidores externos: el valor de configuración extra\_hosts le permite obtener acceso a máquinas o servidores externos situados fuera del host de Docker (es decir, fuera de la máquina virtual de Linux predeterminada, que es un host de Docker de desarrollo), como una instancia local de SQL Server en su equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="65b72-148">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="65b72-149">También existen otras opciones más avanzadas de los archivos docker-compose.yml que se exponen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="65b72-149">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="65b72-150">Usar archivos docker-compose para fijar como objetivo varios entornos</span><span class="sxs-lookup"><span data-stu-id="65b72-150">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="65b72-151">Los archivos docker-compose.yml son archivos de definición que se pueden usar en varias infraestructuras que comprendan ese formato.</span><span class="sxs-lookup"><span data-stu-id="65b72-151">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="65b72-152">La herramienta más sencilla es el comando docker-compose, pero existen otras herramientas, como los orquestadores (por ejemplo, Docker Swarm), que también comprenden ese archivo.</span><span class="sxs-lookup"><span data-stu-id="65b72-152">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="65b72-153">Por lo tanto, si usa el comando docker-compose, puede fijar como objetivo los siguientes escenarios principales.</span><span class="sxs-lookup"><span data-stu-id="65b72-153">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="65b72-154">Entornos de desarrollo</span><span class="sxs-lookup"><span data-stu-id="65b72-154">Development environments</span></span>

<span data-ttu-id="65b72-155">Al desarrollar aplicaciones, es importante poder ejecutar una aplicación en un entorno de desarrollo aislado.</span><span class="sxs-lookup"><span data-stu-id="65b72-155">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="65b72-156">Puede usar el comando de la CLI docker-compose para crear ese entorno o usar Visual Studio, que usa docker-compose en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="65b72-156">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="65b72-157">El archivo docker-compose.yml le permite configurar y documentar todas las dependencias de servicio de la aplicación (otros servicios, la caché, bases de datos, colas, etc.).</span><span class="sxs-lookup"><span data-stu-id="65b72-157">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="65b72-158">Con el comando de la CLI docker-compose puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="65b72-158">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="65b72-159">Los archivos docker-compose.yml son archivos de configuración interpretados por el motor de Docker, pero también actúan como prácticos archivos de documentación sobre la composición de la aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="65b72-159">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="65b72-160">Entornos de prueba</span><span class="sxs-lookup"><span data-stu-id="65b72-160">Testing environments</span></span>

<span data-ttu-id="65b72-161">Una parte importante de cualquier proceso de implementación continua (CD) o de integración continua (CI) son las pruebas unitarias y las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="65b72-161">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="65b72-162">Estas pruebas automatizadas requieren un entorno aislado, por lo que no se ven afectadas por los usuarios ni por ningún otro cambio efectuado en los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65b72-162">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="65b72-163">Con Docker Compose puede crear y destruir ese entorno aislado de un modo muy sencillo ejecutando unos scripts o comandos en el símbolo del sistema, como los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="65b72-163">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="65b72-164">Implementaciones de producción</span><span class="sxs-lookup"><span data-stu-id="65b72-164">Production deployments</span></span>

<span data-ttu-id="65b72-165">También puede usar Compose para efectuar una implementación en un motor de Docker remoto.</span><span class="sxs-lookup"><span data-stu-id="65b72-165">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="65b72-166">Un caso típico consiste en efectuar una implementación en una única instancia de host de Docker (como una máquina virtual de producción o un servidor aprovisionado con [Docker Machine](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="65b72-166">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="65b72-167">Pero también podría ser todo un clúster de [Docker Swarm](https://docs.docker.com/swarm/overview/), ya que los clústeres también son compatibles con los archivos docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="65b72-167">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="65b72-168">Si usa cualquier otro orquestador (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), puede que tenga que agregar valores de configuración de instalación y metadatos como los de docker-compose.yml, pero con el formato que solicita el otro orquestador.</span><span class="sxs-lookup"><span data-stu-id="65b72-168">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="65b72-169">En cualquier caso, docker-compose es una herramienta y un formato de metadatos prácticos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orquestador que está usando.</span><span class="sxs-lookup"><span data-stu-id="65b72-169">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="65b72-170">Usar varios archivos docker-compose para controlar distintos entornos</span><span class="sxs-lookup"><span data-stu-id="65b72-170">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="65b72-171">Al fijar como objetivo entornos diferentes, debe usar varios archivos compose.</span><span class="sxs-lookup"><span data-stu-id="65b72-171">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="65b72-172">Así puede crear distintas variantes de configuración en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="65b72-172">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="65b72-173">Invalidar el archivo base docker-compose</span><span class="sxs-lookup"><span data-stu-id="65b72-173">Overriding the base docker-compose file</span></span>

<span data-ttu-id="65b72-174">Podría usar un archivo docker-compose.yml como en los ejemplos simplificados que se muestran en las secciones anteriores,</span><span class="sxs-lookup"><span data-stu-id="65b72-174">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="65b72-175">pero no se recomienda para la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="65b72-175">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="65b72-176">De forma predeterminada, Compose lee dos archivos, un archivo docker-compose.yml y un archivo docker-compose.override.yml opcional.</span><span class="sxs-lookup"><span data-stu-id="65b72-176">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="65b72-177">Como se muestra en la figura 8-11, al usar Visual Studio y habilitar la compatibilidad de Docker, Visual Studio también crea otro archivo docker-compose.ci.build.yml para que lo use desde sus canalizaciones de CI/CD, como en VSTS.</span><span class="sxs-lookup"><span data-stu-id="65b72-177">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.ci.build,yml file for you to use from your CI/CD pipelines like in VSTS.</span></span>

![](./media/image12.png)

<span data-ttu-id="65b72-178">**Figura 8-11**.</span><span class="sxs-lookup"><span data-stu-id="65b72-178">**Figure 8-11**.</span></span> <span data-ttu-id="65b72-179">Archivos docker-compose en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="65b72-179">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="65b72-180">Puede editar los archivos docker-compose con cualquier editor, como Visual Studio Code o Sublime, y ejecutar la aplicación con el comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="65b72-180">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="65b72-181">Por convención, el archivo docker-compose.yml contiene la configuración básica y otras opciones estáticas.</span><span class="sxs-lookup"><span data-stu-id="65b72-181">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="65b72-182">Esto significa que la configuración del servicio no debería variar según el entorno de implementación que tenga como objetivo.</span><span class="sxs-lookup"><span data-stu-id="65b72-182">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="65b72-183">El archivo docker-compose.override.yml, como su nombre sugiere, contiene valores de configuración que invalidan la configuración básica, como la configuración que depende del entorno de implementación.</span><span class="sxs-lookup"><span data-stu-id="65b72-183">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="65b72-184">También puede tener varios archivos de invalidación con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="65b72-184">You can have multiple override files with different names also.</span></span> <span data-ttu-id="65b72-185">Los archivos de invalidación suelen contener información adicional necesaria para la aplicación, pero que es específica de un entorno o de una implementación.</span><span class="sxs-lookup"><span data-stu-id="65b72-185">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="65b72-186">Fijar como objetivo varios entornos</span><span class="sxs-lookup"><span data-stu-id="65b72-186">Targeting multiple environments</span></span>

<span data-ttu-id="65b72-187">Un caso de uso típico es cuando se definen varios archivos compose de manera que puede fijar como objetivo varios entornos (por ejemplo, producción, almacenamiento provisional, integración continua o desarrollo).</span><span class="sxs-lookup"><span data-stu-id="65b72-187">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="65b72-188">Para dar cabida a estas diferencias, puede dividir la configuración de Compose en varios archivos, como se muestra en la figura 8-12.</span><span class="sxs-lookup"><span data-stu-id="65b72-188">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="65b72-189">**Figura 8-12**.</span><span class="sxs-lookup"><span data-stu-id="65b72-189">**Figure 8-12**.</span></span> <span data-ttu-id="65b72-190">Varios archivos docker-compose invalidan los valores del archivo base docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="65b72-190">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="65b72-191">Comienza con el archivo base docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="65b72-191">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="65b72-192">Este archivo base debe contener los valores de configuración básicos o estáticos que no varían según el entorno.</span><span class="sxs-lookup"><span data-stu-id="65b72-192">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="65b72-193">Por ejemplo, eShopOnContainers tiene el siguiente archivo docker-compose.yml como archivo base.</span><span class="sxs-lookup"><span data-stu-id="65b72-193">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="65b72-194">Los valores del archivo base docker-compose.yml no deberían variar porque haya distintos entornos de implementación de destino.</span><span class="sxs-lookup"><span data-stu-id="65b72-194">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="65b72-195">Si se centra en la definición del servicio webmvc, por ejemplo, puede ver que esa información es la misma con independencia del entorno que fije como objetivo.</span><span class="sxs-lookup"><span data-stu-id="65b72-195">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="65b72-196">Dispone de la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="65b72-196">You have the following information:</span></span>

-   <span data-ttu-id="65b72-197">El nombre del servicio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="65b72-197">The service name: webmvc.</span></span>

-   <span data-ttu-id="65b72-198">La imagen personalizada del contenedor: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="65b72-198">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="65b72-199">El comando para compilar la imagen personalizada de Docker, que indica qué Dockerfile se debe usar.</span><span class="sxs-lookup"><span data-stu-id="65b72-199">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="65b72-200">Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que se hayan iniciado los otros contenedores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="65b72-200">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="65b72-201">Puede tener otra configuración, pero lo importante es que en el archivo base docker-compose.yml solo establezca la información que es común en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="65b72-201">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="65b72-202">Luego, en el archivo docker-compose.override.yml o en archivos similares de producción o almacenamiento provisional, debería colocar la configuración específica para cada entorno.</span><span class="sxs-lookup"><span data-stu-id="65b72-202">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="65b72-203">Por lo general, el archivo docker-compose.override.yml se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="65b72-203">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
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

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
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

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
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
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="65b72-204">En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define variables de entorno con direcciones URL de redireccionamiento y especifica cadenas de conexión para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="65b72-204">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="65b72-205">Esta configuración es solo para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="65b72-205">These settings are all just for the development environment.</span></span>

<span data-ttu-id="65b72-206">Al ejecutar `docker-compose up` (o al iniciarlo en Visual Studio), el comando lee las invalidaciones automáticamente como si se combinaran ambos archivos.</span><span class="sxs-lookup"><span data-stu-id="65b72-206">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="65b72-207">Imagínese que quiere que otro archivo Compose para el entorno de producción, con distintos valores de configuración, puertos o cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="65b72-207">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="65b72-208">Puede crear otro archivo de invalidación, como el archivo llamado `docker-compose.prod.yml`, con distintas configuraciones y variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="65b72-208">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span>  <span data-ttu-id="65b72-209">Ese archivo podría estar almacenado en otro repositorio de Git o lo podría administrar y proteger un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="65b72-209">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="65b72-210">Cómo efectuar una implementación con un archivo de invalidación específico</span><span class="sxs-lookup"><span data-stu-id="65b72-210">How to deploy with a specific override file</span></span>

<span data-ttu-id="65b72-211">Para usar varios archivos de invalidación, o un archivo de invalidación con otro nombre, puede usar la opción -f con el comando docker-compose y especificar los archivos.</span><span class="sxs-lookup"><span data-stu-id="65b72-211">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="65b72-212">Cree los archivos de combinaciones en el orden en que se especifican en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65b72-212">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="65b72-213">En el ejemplo siguiente se muestra cómo efectuar la implementación con archivos de invalidación.</span><span class="sxs-lookup"><span data-stu-id="65b72-213">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="65b72-214">Usar variables de entorno en los archivos docker-compose</span><span class="sxs-lookup"><span data-stu-id="65b72-214">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="65b72-215">Resulta práctico, sobre todo en los entornos de producción, poder obtener información de configuración de variables de entorno, como hemos mostrado en ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="65b72-215">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="65b72-216">En los archivos docker-compose se hace referencia a una variable de entorno mediante la sintaxis \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="65b72-216">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="65b72-217">En la siguiente línea de un archivo docker-compose.prod.yml se muestra cómo hacer referencia al valor de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="65b72-217">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="65b72-218">Las variables de entorno se crean y se inicializan de maneras diferentes, en función de su entorno de host (Linux, Windows, clúster en la nube, etc.),</span><span class="sxs-lookup"><span data-stu-id="65b72-218">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="65b72-219">aunque un método práctico consiste en usar un archivo .env.</span><span class="sxs-lookup"><span data-stu-id="65b72-219">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="65b72-220">Los archivos docker-compose admiten la declaración de variables de entorno predeterminadas en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="65b72-220">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="65b72-221">Estos valores de las variables de entorno son los valores predeterminados,</span><span class="sxs-lookup"><span data-stu-id="65b72-221">These values for the environment variables are the default values.</span></span> <span data-ttu-id="65b72-222">pero se pueden invalidar con los valores que haya podido definir en cada uno de sus entornos (sistema operativo host o variables de entorno del clúster).</span><span class="sxs-lookup"><span data-stu-id="65b72-222">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="65b72-223">Este archivo .env se coloca en la carpeta en la que se ejecuta el comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="65b72-223">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="65b72-224">En el siguiente ejemplo se muestra un archivo .env como el archivo [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) para la aplicación eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="65b72-224">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="65b72-225">Docker-compose espera que cada línea de los archivos .env tenga el formato &lt;variable&gt;=&lt;valor&gt;.</span><span class="sxs-lookup"><span data-stu-id="65b72-225">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="65b72-226">Tenga en cuenta que los valores establecidos en el entorno en tiempo de ejecución siempre invalidan los valores definidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="65b72-226">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="65b72-227">De forma similar, los valores que se pasan a través de argumentos de comando de la línea de comandos también invalidan los valores predeterminados establecidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="65b72-227">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="65b72-228">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="65b72-228">Additional resources</span></span>

-   <span data-ttu-id="65b72-229">**Overview of Docker Compose (Introducción a Docker Compose)**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="65b72-229">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="65b72-230">**Multiple Compose files (Varios archivos de Compose)**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="65b72-230">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="65b72-231">Compilación de imágenes optimizadas de Docker de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65b72-231">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="65b72-232">Si está explorando Docker y .NET Core en orígenes de Internet, encontrará Dockerfiles que muestran lo fácil que es compilar una imagen de Docker copiando el origen en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="65b72-232">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="65b72-233">Estos ejemplos sugieren que, si usa una configuración simple, puede tener una imagen de Docker con el entorno empaquetado con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65b72-233">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="65b72-234">En el ejemplo siguiente se muestra un Dockerfile sencillo en esta misma línea.</span><span class="sxs-lookup"><span data-stu-id="65b72-234">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="65b72-235">Un Dockerfile como este funcionará,</span><span class="sxs-lookup"><span data-stu-id="65b72-235">A Dockerfile like this will work.</span></span> <span data-ttu-id="65b72-236">pero puede optimizar considerablemente sus imágenes, sobre todo las imágenes de producción.</span><span class="sxs-lookup"><span data-stu-id="65b72-236">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="65b72-237">En el modelo de microservicios y contenedores están iniciando contenedores constantemente.</span><span class="sxs-lookup"><span data-stu-id="65b72-237">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="65b72-238">El método habitual de usar los contenedores no reinicia un contenedor inactivo, porque el contenedor se puede descartar.</span><span class="sxs-lookup"><span data-stu-id="65b72-238">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="65b72-239">Los orquestadores (como Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) tan solo crean instancias nuevas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="65b72-239">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="65b72-240">Esto significa que tendría que efectuar una optimización precompilando la aplicación al crearla para que el proceso de creación de instancias sea más rápido.</span><span class="sxs-lookup"><span data-stu-id="65b72-240">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="65b72-241">Cuando se inicia el contenedor, tendría que estar preparado para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="65b72-241">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="65b72-242">No se debería restaurar y compilar en tiempo de ejecución con los comandos dotnet restore y dotnet build desde la CLI de dotnet, como se puede ver en muchas entradas de blog sobre .NET Core y Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-242">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="65b72-243">El equipo de .NET ha estado trabajando mucho para convertir .NET Core y ASP.NET Core en un marco optimizado para contenedores.</span><span class="sxs-lookup"><span data-stu-id="65b72-243">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="65b72-244">.NET Core no es solo un marco de trabajo ligero con una pequeña superficie de memoria. El equipo se ha centrado en el rendimiento de inicio y ha generado algunas imágenes de Docker optimizadas, como la imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), disponible en [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), en comparación con las imágenes corrientes [Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="65b72-244">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="65b72-245">La imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) proporciona una configuración automática de aspnetcore\_urls en el puerto 80 y la caché pre-ngend de los ensamblados; ambas configuraciones hacen que el inicio sea más rápido.</span><span class="sxs-lookup"><span data-stu-id="65b72-245">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="65b72-246">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="65b72-246">Additional resources</span></span>

-   <span data-ttu-id="65b72-247">**Building Optimized Docker Images with ASP.NET Core (Compilación de imágenes de Docker optimizadas con ASP.NET Core)**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="65b72-247">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="65b72-248">Compilación de la aplicación desde un contenedor de compilación (CI)</span><span class="sxs-lookup"><span data-stu-id="65b72-248">Building the application from a build (CI) container</span></span>

<span data-ttu-id="65b72-249">Otra ventaja de Docker es que se puede compilar una aplicación desde un contenedor preconfigurado, como se muestra en la figura 8-13, por lo que no es necesario crear un equipo de compilación o máquina virtual para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65b72-249">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="65b72-250">Puede usar o probar este contenedor de compilación ejecutándolo en su equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="65b72-250">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="65b72-251">Pero lo que es aún más interesante es que puede usar el mismo contenedor de compilación desde su canalización de CI (integración continua).</span><span class="sxs-lookup"><span data-stu-id="65b72-251">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="65b72-252">**Figura 8-13**.</span><span class="sxs-lookup"><span data-stu-id="65b72-252">**Figure 8-13**.</span></span> <span data-ttu-id="65b72-253">Contenedor de compilación de Docker que compila los archivos binarios de .NET</span><span class="sxs-lookup"><span data-stu-id="65b72-253">Docker build-container compiling your .NET binaries</span></span> 

<span data-ttu-id="65b72-254">En este escenario proporcionamos la imagen [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), que se puede usar para compilar y generar sus propias aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="65b72-254">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="65b72-255">La salida se coloca en una imagen basada en la imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), que es una imagen optimizada en tiempo de ejecución, como se ha indicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="65b72-255">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="65b72-256">La imagen aspnetcore-build contiene todo lo necesario para compilar una aplicación de ASP.NET Core, incluidos .NET Core, el SDK de ASP.NET, npm, Bower, Gulp, etc.</span><span class="sxs-lookup"><span data-stu-id="65b72-256">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="65b72-257">Estas dependencias son necesarias en tiempo de compilación,</span><span class="sxs-lookup"><span data-stu-id="65b72-257">We need these dependencies at build time.</span></span> <span data-ttu-id="65b72-258">pero no queremos transportarlas junto con la aplicación en tiempo de ejecución, porque haría que la imagen fuera demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="65b72-258">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="65b72-259">En la aplicación eShopOnContainers puede compilar la aplicación desde un contenedor ejecutando el siguiente comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="65b72-259">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="65b72-260">En la figura 8-14 se muestra este comando ejecutándose en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65b72-260">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="65b72-261">**Figura 8-14.**</span><span class="sxs-lookup"><span data-stu-id="65b72-261">**Figure 8-14.**</span></span> <span data-ttu-id="65b72-262">Compilación de la aplicación .NET desde un contenedor</span><span class="sxs-lookup"><span data-stu-id="65b72-262">Building your .NET application from a container</span></span>

<span data-ttu-id="65b72-263">Como puede ver, el contenedor que se ejecuta es el contenedor ci-build\_1.</span><span class="sxs-lookup"><span data-stu-id="65b72-263">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="65b72-264">Se basa en la imagen aspnetcore-build para que pueda compilar y generar toda la aplicación desde dentro de ese contenedor en lugar de hacerlo desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="65b72-264">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="65b72-265">Es por este motivo que en realidad crea y compila los proyectos de .NET Core en Linux: ese contenedor se está ejecutando en el host de Linux predeterminado de Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-265">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="65b72-266">El archivo [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) de esa imagen (parte de eShopOnContainers) contiene el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="65b72-266">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="65b72-267">Puede ver que inicia un contenedor de compilación mediante la imagen [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).</span><span class="sxs-lookup"><span data-stu-id="65b72-267">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* <span data-ttu-id="65b72-268">A partir de **.NET Core 2.0**, el comando `dotnet restore` se ejecuta automáticamente cuando se ejecuta el comando `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="65b72-268">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="65b72-269">Una vez que el contenedor de compilación está en funcionamiento, ejecuta los comandos dotnet restore y dotnet publish del SDK de .NET en todos los proyectos de la solución con el objetivo de compilar los bits de .NET.</span><span class="sxs-lookup"><span data-stu-id="65b72-269">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="65b72-270">En este caso, dado que eShopOnContainers también tiene una SPA basada en TypeScript y Angular para el código de cliente, también debe comprobar las dependencias de JavaScript con npm, pero esa acción no está relacionada con los bits de .NET.</span><span class="sxs-lookup"><span data-stu-id="65b72-270">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="65b72-271">El comando dotnet publish compila y publica la salida compilada dentro de la carpeta de cada proyecto en la carpeta …/obj/Docker/publish, como se muestra en la figura 8-15.</span><span class="sxs-lookup"><span data-stu-id="65b72-271">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="65b72-272">**Figura 8-15.**</span><span class="sxs-lookup"><span data-stu-id="65b72-272">**Figure 8-15.**</span></span> <span data-ttu-id="65b72-273">Archivos binarios generados por el comando dotnet publish</span><span class="sxs-lookup"><span data-stu-id="65b72-273">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="65b72-274">Creación de las imágenes de Docker desde la CLI</span><span class="sxs-lookup"><span data-stu-id="65b72-274">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="65b72-275">Una vez que se publica la salida de la aplicación en las carpetas relacionadas (dentro de cada proyecto), el siguiente paso consiste en compilar las imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-275">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="65b72-276">Para ello, use los comandos docker-compose build y docker-compose up, como muestra en la figura 8-16.</span><span class="sxs-lookup"><span data-stu-id="65b72-276">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="65b72-277">**Figura 8-16.**</span><span class="sxs-lookup"><span data-stu-id="65b72-277">**Figure 8-16.**</span></span> <span data-ttu-id="65b72-278">Compilación de imágenes de Docker y ejecución de los contenedores</span><span class="sxs-lookup"><span data-stu-id="65b72-278">Building Docker images and running the containers</span></span>

<span data-ttu-id="65b72-279">En la figura 8-17 puede ver cómo se ejecuta el comando docker-compose build</span><span class="sxs-lookup"><span data-stu-id="65b72-279">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="65b72-280">**Figura 8-17**.</span><span class="sxs-lookup"><span data-stu-id="65b72-280">**Figure 8-17**.</span></span> <span data-ttu-id="65b72-281">Compilación de las imágenes de Docker con el comando docker-compose build</span><span class="sxs-lookup"><span data-stu-id="65b72-281">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="65b72-282">La diferencia entre el comando docker-compose build y el comando docker-compose up es que docker-compose up compila e inicia las imágenes.</span><span class="sxs-lookup"><span data-stu-id="65b72-282">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="65b72-283">Si usa Visual Studio, todos estos pasos se llevan a cabo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="65b72-283">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="65b72-284">Visual Studio compila la aplicación. NET, crea las imágenes de Docker e implementa los contenedores en el host de Docker.</span><span class="sxs-lookup"><span data-stu-id="65b72-284">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="65b72-285">Visual Studio ofrece características adicionales, como la capacidad de depurar los contenedores que se ejecutan en Docker, directamente desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="65b72-285">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="65b72-286">Lo importante aquí es que puede compilar la aplicación de la misma manera que debería compilarla la canalización de CI/CD: desde un contenedor y no desde un equipo local.</span><span class="sxs-lookup"><span data-stu-id="65b72-286">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="65b72-287">Una vez creadas las imágenes, solo tiene que ejecutar las imágenes de Docker con el comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="65b72-287">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="65b72-288">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="65b72-288">Additional resources</span></span>

-   <span data-ttu-id="65b72-289">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code) (Compilar bits desde un contenedor: configurar la solución eShopOnContainers en un entorno de la CLI de Windows [CLI de dotnet, CLI de Docker y código de VS])**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="65b72-289">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="65b72-290">[Anterior] (data-driven-crud-microservice.md) [Siguiente] (database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="65b72-290">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
