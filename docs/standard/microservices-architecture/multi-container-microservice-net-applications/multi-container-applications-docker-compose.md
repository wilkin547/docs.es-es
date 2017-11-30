---
title: "Defina su aplicación de múltiples contenedor con docker compose.yml"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Defina su aplicación de múltiples contenedor con docker compose.yml"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="cc9b3-104">Defina su aplicación de múltiples contenedor con docker compose.yml</span><span class="sxs-lookup"><span data-stu-id="cc9b3-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="cc9b3-105">En esta guía, la [docker compose.yml](https://docs.docker.com/compose/compose-file/) archivo se introdujo en la sección [paso 4. Definir los servicios en docker compose.yml al compilar una aplicación de Docker de contenedor varios](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="cc9b3-106">Sin embargo, hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="cc9b3-107">Por ejemplo, puede describir explícitamente cómo desea implementar la aplicación de contenedor múltiples en el archivo compose.yml docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="cc9b3-108">Si lo desea, también puede describir cómo se van a generar las imágenes del Docker personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="cc9b3-109">(Las imágenes de Docker personalizado también pueden generarse con la CLI de Docker.)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="cc9b3-110">Básicamente, defina cada uno de los contenedores que desea implementar además de ciertas características de cada implementación de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="cc9b3-111">Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada el [docker redactar una](https://docs.docker.com/compose/overview/) comando de CLI, o bien puede implementarlo transparente desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="cc9b3-112">En caso contrario, se debe utilizar la CLI de Docker para implementar los contenedores en varios pasos mediante el comando docker run desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="cc9b3-113">Por lo tanto, cada servicio definido en docker compose.yml debe especificar exactamente una imagen o de compilación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="cc9b3-114">Otras claves son opcionales y son análogas a su homólogos de la línea de comandos de ejecución de docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="cc9b3-115">El siguiente código YAML es la definición de un archivo de posibles global pero solo docker-compose.yml para el ejemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="cc9b3-116">No es el archivo real docker-compose desde eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="cc9b3-117">En su lugar, es una versión simplificada y consolidada en un único archivo, no es la mejor manera de trabajar con docker-crear archivos, como se explicará más adelante.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="cc9b3-118">La clave raíz de este archivo es servicios.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-118">The root key in this file is services.</span></span> <span data-ttu-id="cc9b3-119">Bajo esa clave se definen los servicios que desea implementar y ejecutar cuando se ejecuta el docker crear comandos o cuando se implementa desde Visual Studio mediante el uso de este archivo compose.yml docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="cc9b3-120">En este caso, el archivo de docker compose.yml tiene varios servicios definidos, como se describe en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="cc9b3-121">webmvc contenedor que incluye la aplicación de MVC de ASP.NET Core consumiendo el microservicios del servidor C\#</span><span class="sxs-lookup"><span data-stu-id="cc9b3-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="cc9b3-122">Catalog.API contenedor que incluye el núcleo de catálogo ASP.NET Web API microservicio</span><span class="sxs-lookup"><span data-stu-id="cc9b3-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="cc9b3-123">Ordering.API contenedor que incluye el microservicio de ordenación de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="cc9b3-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="cc9b3-124">SQL.Data contenedor que se ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios</span><span class="sxs-lookup"><span data-stu-id="cc9b3-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="cc9b3-125">Basket.API contenedor con el núcleo de la cesta de compras ASP.NET Web API microservicio</span><span class="sxs-lookup"><span data-stu-id="cc9b3-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="cc9b3-126">Basket.Data contenedor que se ejecuta el servicio de caché REDIS, con la base de datos de la cesta de compra como una memoria caché REDIS</span><span class="sxs-lookup"><span data-stu-id="cc9b3-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="cc9b3-127">Un contenedor de la API del servicio Web simple</span><span class="sxs-lookup"><span data-stu-id="cc9b3-127">A simple Web Service API container</span></span>

<span data-ttu-id="cc9b3-128">Centrarse en un único contenedor, el contenedor de catalog.api-microservicio tiene una definición sencilla:</span><span class="sxs-lookup"><span data-stu-id="cc9b3-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="cc9b3-129">Este servicio en contenedores tiene la siguiente configuración básica:</span><span class="sxs-lookup"><span data-stu-id="cc9b3-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="cc9b3-130">Se basa en la imagen eshop/catalog.api personalizado.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="cc9b3-131">Por simplicidad, no hay ninguna compilación: configuración en el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="cc9b3-132">Esto significa que la imagen debe ha compilado previamente (con la compilación de docker) o se han descargado (con el comando de extracción de docker) de cualquier registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="cc9b3-133">Define una variable de entorno denominada ConnectionString con la cadena de conexión para usarse por Entity Framework para tener acceso a la instancia de SQL Server que contiene el modelo de datos de catálogo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="cc9b3-134">En este caso, el mismo contenedor de SQL Server contiene varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="cc9b3-135">Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="cc9b3-136">Sin embargo, también puede implementar un contenedor de SQL Server para cada base de datos de microservicio.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="cc9b3-137">El nombre de SQL Server es sql.data, que es el mismo nombre que se utiliza para el contenedor que se ejecuta la instancia de SQL Server para Linux.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="cc9b3-138">Esto resulta útil; poder usar esta resolución de nombres (interna en el host Docker) se resuelve la dirección de red, por lo que no necesita conocer la dirección IP interna de los contenedores que obtiene acceso desde otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="cc9b3-139">Dado que la cadena de conexión se define una variable de entorno, puede establecer esa variable mediante un mecanismo diferente y en un momento diferente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="cc9b3-140">Por ejemplo, podría establecer una cadena de conexión diferentes cuando se implementa en producción en los hosts finales, o si lo hace desde sus canalizaciones de CI/CD en VSTS o el sistema de DevOps preferido.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="cc9b3-141">Expone el puerto 80 para el acceso interno al servicio catalog.api dentro del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="cc9b3-142">El host es actualmente una VM Linux porque se basa en una imagen de Docker para Linux, pero puede configurar el contenedor para que se ejecute en una imagen de Windows en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="cc9b3-143">Reenvía el puerto 80 en el contenedor al puerto 5101 en el equipo de host Docker (la VM de Linux) expuesto.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="cc9b3-144">El servicio web vincula al servicio sql.data (la instancia de SQL Server para ejecutar en un contenedor de base de datos de Linux).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="cc9b3-145">Cuando se especifica esta dependencia, el contenedor catalog.api no se iniciará hasta que ya ha iniciado el contenedor de sql.data; Esto es importante porque debe tener la base de datos de SQL Server hasta catalog.api y se ejecuta en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="cc9b3-146">Sin embargo, este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que las comprobaciones de Docker sólo en el nivel de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="cc9b3-147">A veces el servicio (en este caso de SQL Server) todavía no estén listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en su microservicios de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="cc9b3-148">De este modo, si un contenedor de dependencia no está listo para poco tiempo, la aplicación se seguirá resistente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="cc9b3-149">Está configurado para permitir el acceso a los servidores externos: el archivo extra\_hosts establecer permiten obtener acceso a servidores externos o equipos situados fuera del host Docker (es decir, fuera de la VM de Linux que es un desarrollo Docker predeterminado de host), como una instancia de SQL local Instancia del servidor en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="cc9b3-150">También hay otras opciones de docker compose.yml más avanzadas que se exponen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="cc9b3-151">Usando docker-crear archivos en varios entornos de destino</span><span class="sxs-lookup"><span data-stu-id="cc9b3-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="cc9b3-152">Los archivos de docker compose.yml son archivos de definición y pueden utilizarse en varias infraestructuras que entienden ese formato.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="cc9b3-153">La herramienta más sencilla es el docker-crear comando, pero otras herramientas como orchestrators (por ejemplo, Docker Swarm) también comprenden ese archivo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="cc9b3-154">Por consiguiente, al usar el comando puede tener como destino los siguientes escenarios principales de redacción de docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="cc9b3-155">Entornos de desarrollo</span><span class="sxs-lookup"><span data-stu-id="cc9b3-155">Development environments</span></span>

<span data-ttu-id="cc9b3-156">Al desarrollar aplicaciones, es importante ser capaz de ejecutar una aplicación en un entorno de desarrollo aislado.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="cc9b3-157">Puede usar el comando CLI para crear dicho entorno o usar Visual Studio que usa docker redactar tras los bastidores de redacción de docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="cc9b3-158">El archivo compose.yml docker permite configurar y documentar todas las dependencias de su aplicación servicio (otros servicios, caché, las bases de datos, las colas, etcetera).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="cc9b3-159">Mediante el comando de CLI de docker redactar, puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (redactar docker seguridad).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="cc9b3-160">Los archivos de docker compose.yml son interpretados por el motor de Docker de archivos de configuración pero también actúan como archivos de documentación adecuada sobre la composición de la aplicación contenedora múltiples.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="cc9b3-161">Entornos de prueba</span><span class="sxs-lookup"><span data-stu-id="cc9b3-161">Testing environments</span></span>

<span data-ttu-id="cc9b3-162">Una parte importante de cualquier implementación continua (CD) o el proceso de integración continua (CI) son las pruebas unitarias y pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="cc9b3-163">Estas pruebas automatizadas requieren un entorno aislado, por lo que no afectan a los usuarios o cualquier otro cambio en los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="cc9b3-164">Con Docker Compose pueden crear y destruir ese entorno aislado muy fácilmente en algunos comandos desde el símbolo del sistema o secuencias de comandos, como los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc9b3-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="cc9b3-165">Implementaciones de producción</span><span class="sxs-lookup"><span data-stu-id="cc9b3-165">Production deployments</span></span>

<span data-ttu-id="cc9b3-166">También puede utilizar redactar para implementar en un motor de Docker remoto.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="cc9b3-167">Un caso típico consiste en implementar en una única instancia de host de Docker (como una máquina virtual de producción o servidor proporcionado con [máquina Docker](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="cc9b3-168">Pero también podría ser toda una [Docker Swarm](https://docs.docker.com/swarm/overview/) el clúster, porque en clústeres también son compatibles con los archivos de compose.yml de docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="cc9b3-169">Si está utilizando cualquier orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), tendrá que agregar valores de configuración de instalación y los metadatos como los de docker compose.yml, pero en el formato requerido por el orquestador del otro.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="cc9b3-170">En cualquier caso, componer de docker es un formato conveniente de herramienta y los metadatos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orchestrator que usa.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="cc9b3-171">Utilizando varias redactar docker archivos para controlar varios entornos</span><span class="sxs-lookup"><span data-stu-id="cc9b3-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="cc9b3-172">Cuando se destinan a entornos diferentes, debe usar varias crear archivos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="cc9b3-173">Esto le permite crear varias variantes de configuración en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="cc9b3-174">Reemplazar el archivo de base de docker-compose</span><span class="sxs-lookup"><span data-stu-id="cc9b3-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="cc9b3-175">Puede usar un archivo de docker-compose.yml único como en los ejemplos simplificados que se muestra en las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="cc9b3-176">Sin embargo, no se recomienda para la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="cc9b3-177">De forma predeterminada, redactar lee dos archivos, un compose.yml de docker y un archivo de docker-compose.override.yml opcional.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="cc9b3-178">Como se muestra en la figura 8-11, cuando se usa Visual Studio y habilitar la compatibilidad de Docker, Visual Studio crea también los archivos más algunos archivos adicionales usados para la depuración.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="cc9b3-179">**Figura 8-11**.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-179">**Figure 8-11**.</span></span> <span data-ttu-id="cc9b3-180">docker-crear archivos en Visual Studio de 2017</span><span class="sxs-lookup"><span data-stu-id="cc9b3-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="cc9b3-181">Puede editar los archivos de docker-compose con cualquier editor, como código de Visual Studio o fundamentales y ejecutar la aplicación con el docker-crear una copia de seguridad comando.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="cc9b3-182">Por convención, el archivo de docker compose.yml contiene la configuración base y otras opciones estáticas.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="cc9b3-183">Esto significa que no debe cambiar la configuración del servicio según el entorno de implementación de destino.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="cc9b3-184">El archivo compose.override.yml de docker, como su nombre sugiere, contiene valores de configuración que invalidación la configuración básica, como la configuración de los que depende del entorno de implementación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="cc9b3-185">También puede tener varios archivos de invalidación con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="cc9b3-186">Los archivos de invalidación suelen contengan información adicional necesaria para la aplicación pero específico en un entorno o en una implementación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="cc9b3-187">Varios entornos de destino</span><span class="sxs-lookup"><span data-stu-id="cc9b3-187">Targeting multiple environments</span></span>

<span data-ttu-id="cc9b3-188">Un caso de uso típico es cuando se definen varias crear archivos por lo que puede tener como destino varios entornos, como la producción, prueba, desarrollo o elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="cc9b3-189">Para admitir estas diferencias, puede dividir la configuración de redacción en varios archivos, como se muestra en la figura 8-12.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="cc9b3-190">**Figura 8-12**.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-190">**Figure 8-12**.</span></span> <span data-ttu-id="cc9b3-191">Docker-crear varios archivos al reemplazar los valores en el archivo de base de compose.yml de docker</span><span class="sxs-lookup"><span data-stu-id="cc9b3-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="cc9b3-192">Iniciar con el archivo de base de compose.yml de docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="cc9b3-193">Este archivo de base debe contener los valores de configuración base o estático que no cambian en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="cc9b3-194">Por ejemplo, el eShopOnContainers tiene el siguiente archivo de docker compose.yml que el archivo de base.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

<span data-ttu-id="cc9b3-195">No deberían cambiar los valores en el archivo de base de docker-compose.yml debido a los entornos de implementación de destino diferente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="cc9b3-196">Por ejemplo, si coloca el foco en la definición del servicio webmvc, puede ver cómo esa información es el mismo con independencia de qué entorno quiere que podría ser el destino.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="cc9b3-197">Tiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cc9b3-197">You have the following information:</span></span>

-   <span data-ttu-id="cc9b3-198">El nombre del servicio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="cc9b3-199">Imagen personalizada del contenedor: compras/webmvc.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="cc9b3-200">El comando para generar la imagen personalizada de Docker, que indica qué Dockerfile a usar.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="cc9b3-201">Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que hayan iniciado los otros contenedores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="cc9b3-202">Puede tener una configuración adicional, pero lo importante es que en el archivo de base de compose.yml de docker, simplemente desea establecer la información que es común a través de entornos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="cc9b3-203">A continuación, en el docker compose.override.yml o archivos similares para producción o ensayo, debería colocar configuración específica para cada entorno.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="cc9b3-204">Por lo general, la compose.override.yml de docker se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="cc9b3-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="cc9b3-205">En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define las variables de entorno con redirigir las direcciones URL y especifica las cadenas de conexión para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="cc9b3-206">Esta configuración es simplemente para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="cc9b3-207">Al ejecutar docker redactar una (o iniciarlo desde Visual Studio), el comando lee las invalidaciones automáticamente como si se estaban combinando ambos archivos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="cc9b3-208">Suponga que desea que otro archivo de composición para el entorno de producción, con valores de configuración diferente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="cc9b3-209">Puede crear otro archivo de reemplazo, similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-209">You can create another override file, like the following.</span></span> <span data-ttu-id="cc9b3-210">(Este archivo podría estar almacenado en un repositorio de Git diferentes o administrado y protegido por un equipo diferente.)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="cc9b3-211">Cómo implementar con un archivo de invalidación específica</span><span class="sxs-lookup"><span data-stu-id="cc9b3-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="cc9b3-212">Para usar varios archivos de invalidación, o un archivo de reemplazo con un nombre diferente, puede usar la opción -f con los comandos de docker crear y especificar los archivos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="cc9b3-213">Crear archivos de combinaciones en el orden en que se especifican en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="cc9b3-214">En el ejemplo siguiente se muestra cómo implementar con archivos de invalidación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="cc9b3-215">Usar variables de entorno en docker-crear archivos</span><span class="sxs-lookup"><span data-stu-id="cc9b3-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="cc9b3-216">Es conveniente, especialmente en entornos de producción, para poder obtener la información de configuración de variables de entorno, tal y como hemos mostrado en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="cc9b3-217">Hace referencia a una variable de entorno en los archivos de docker-compose mediante la sintaxis \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="cc9b3-218">La siguiente línea de un archivo de docker compose.prod.yml muestra cómo hacer referencia al valor de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="cc9b3-219">Las variables de entorno se crean e inicializan de maneras diferentes, dependiendo de su entorno de host (Linux, Windows, clúster de la nube, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="cc9b3-220">Sin embargo, un método cómodo es usar un archivo .env.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="cc9b3-221">Los archivos docker-compose admiten declarar variables de entorno de forma predeterminada en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="cc9b3-222">Estos valores para las variables de entorno son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="cc9b3-223">Pero se pueden invalidar los valores que se haya definido en cada uno de los entornos (sistema operativo del host o variables de entorno del clúster).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="cc9b3-224">Coloque este archivo .env en la carpeta donde la redacción de docker se ejecuta el comando de.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="cc9b3-225">En el ejemplo siguiente se muestra un archivo .env como el [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) archivo para la aplicación eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="cc9b3-226">Crear docker espera que cada línea de un archivo .env para tener el formato &lt;variable&gt;=&lt;valor&gt;.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="cc9b3-227">Tenga en cuenta que los valores establecidos en el entorno en tiempo de ejecución siempre reemplazan los valores definidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="cc9b3-228">De forma similar, los valores que se pasan a través de los argumentos de línea de comandos invalidan los valores predeterminados establecidos en el archivo .env.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="cc9b3-229">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cc9b3-229">Additional resources</span></span>

-   <span data-ttu-id="cc9b3-230">**Información general de Docker crear**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="cc9b3-231">**Varios archivos de redactar**
    [*https://docs.docker.com/compose/extends/\#archivos componer de varios*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="cc9b3-232">Compilar con optimización para imágenes de Docker de núcleo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cc9b3-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="cc9b3-233">Si está explorando Docker y .NET Core en orígenes de Internet, encontrará Dockerfiles que muestran la sencillez de creación de una imagen de Docker mediante la copia de su origen en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="cc9b3-234">Estos ejemplos sugieren que con una configuración simple, puede tener una imagen de Docker con el entorno de empaquetar con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="cc9b3-235">En el ejemplo siguiente se muestra un sencillo Dockerfile en esta misma línea.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="cc9b3-236">Funcionará un Dockerfile similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="cc9b3-237">Sin embargo, puede optimizar considerablemente sus imágenes, especialmente las imágenes de producción.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="cc9b3-238">En el contenedor y el modelo de microservicios, que está iniciando constantemente contenedores.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="cc9b3-239">La manera habitual de utilizar contenedores no reinicia un contenedor inactivo, porque el contenedor es descartable.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="cc9b3-240">Orchestrators (por ejemplo, Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) basta con crean instancias nuevas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="cc9b3-241">Esto significa que se debe optimizar por precompilar la aplicación cuando se crea para que el proceso de creación de instancias es más rápido.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="cc9b3-242">Cuando se inicia el contenedor, estará preparado para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="cc9b3-243">No se deben restaurar y compilar en tiempo de ejecución, mediante dotnet restauración y dotnet generación comandos de la CLI de dotnet, como se ve en todas las entradas de blog sobre .NET Core y Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="cc9b3-244">El equipo de .NET ha estado realizando trabajo importante para hacer que un marco optimizado para el contenedor de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="cc9b3-245">No solo es .NET Core un marco de trabajo ligera con una pequeña superficie de memoria; el equipo se ha centrado en el rendimiento de inicio y genera algunas imágenes de Docker optimizados, como la [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen disponible en [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), en comparación con la normal [ Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) imágenes.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="cc9b3-246">El [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen proporciona configuración automática de aspnetcore\_las direcciones URL para el puerto 80 y la caché de pre-ngend de ensamblados; estas dos opciones como resultado de inicio más rápido.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="cc9b3-247">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cc9b3-247">Additional resources</span></span>

-   <span data-ttu-id="cc9b3-248">**Compilar con optimización para imágenes de Docker con ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="cc9b3-249">Compilar la aplicación desde un contenedor de compilación (CI)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="cc9b3-250">Otra ventaja de Docker es que puede compilar su aplicación desde un contenedor preconfigurada, tal como se muestra en la figura 8-13, por lo que no es necesario crear una máquina de compilación o la máquina virtual para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="cc9b3-251">Puede usar o probar que el contenedor de compilación mediante la ejecución en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="cc9b3-252">Pero lo que es aún más interesante es que puede usar el mismo contenedor de compilación de la canalización de CI (integración continua).</span><span class="sxs-lookup"><span data-stu-id="cc9b3-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="cc9b3-253">**Figura 8-13**.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-253">**Figure 8-13**.</span></span> <span data-ttu-id="cc9b3-254">Creación de bits de .NET desde un contenedor de componentes</span><span class="sxs-lookup"><span data-stu-id="cc9b3-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="cc9b3-255">En este escenario, proporcionamos el [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) imagen, que puede usar para compilar y generar aplicaciones de la principal de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="cc9b3-256">La salida se coloca en una imagen basada en la [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen, que es una imagen optimizada en tiempo de ejecución, como se indicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="cc9b3-257">La imagen de compilación aspnetcore contiene todo lo que necesita para compilar una aplicación de ASP.NET Core, incluidos .NET Core, el SDK de ASP.NET, npm, Bower, Gulp, etcetera.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="cc9b3-258">Necesitamos estas dependencias en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-258">We need these dependencies at build time.</span></span> <span data-ttu-id="cc9b3-259">Pero no queremos llevar junto con la aplicación en tiempo de ejecución, porque haría que la imagen sea demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="cc9b3-260">En la aplicación eShopOnContainers, puede compilar la aplicación desde un contenedor simplemente ejecutando la siguiente docker-crear comando.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="cc9b3-261">Figura 8-14 muestra este comando que se ejecuta en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="cc9b3-262">**Figura 8-14.**</span><span class="sxs-lookup"><span data-stu-id="cc9b3-262">**Figure 8-14.**</span></span> <span data-ttu-id="cc9b3-263">Compilar la aplicación .NET de un contenedor</span><span class="sxs-lookup"><span data-stu-id="cc9b3-263">Building your .NET application from a container</span></span>

<span data-ttu-id="cc9b3-264">Como puede ver, el contenedor que se ejecuta es la compilación de ci\_1 contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="cc9b3-265">Esto se basa en la imagen de compilación aspnetcore para que puede compilar y generar toda la aplicación desde dentro de ese contenedor en lugar de desde su PC.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="cc9b3-266">Es decir ¿por qué en realidad es generar y compilar los proyectos de .NET Core en Linux, porque ese contenedor se está ejecutando en el host de Linux Docker de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="cc9b3-267">El [docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) de archivos de imagen (parte de eShopOnContainers) contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="cc9b3-268">Puede ver que inicia un contenedor de compilación mediante la [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) imagen.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* <span data-ttu-id="cc9b3-269">A partir de **.NET Core 2.0**, `dotnet restore` comando se ejecuta automáticamente cuando el `dotnet publish` se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="cc9b3-270">Una vez que el contenedor de compilación está en funcionamiento, se ejecuta la restauración de dotnet .NET SDK y dotnet publicar comandos en todos los proyectos de la solución con el fin de compilar los bits. NET.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="cc9b3-271">En este caso, puesto que eShopOnContainers también tiene un SPA basado en TypeScript y Angular para el código de cliente, también necesita comprobar las dependencias de JavaScript con npm, pero esa acción no está relacionado con los bits. NET.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="cc9b3-272">El dotnet publicar compilaciones de comando y publica la salida compilada dentro de la carpeta de cada proyecto a la... carpeta /obj/Docker/Publish, tal como se muestra en la figura 8-15.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="cc9b3-273">**Figura 8-15.**</span><span class="sxs-lookup"><span data-stu-id="cc9b3-273">**Figure 8-15.**</span></span> <span data-ttu-id="cc9b3-274">Comando de publicar los archivos binarios generados por el dotnet.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="cc9b3-275">Crear las imágenes de Docker desde la CLI</span><span class="sxs-lookup"><span data-stu-id="cc9b3-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="cc9b3-276">Una vez que la salida de la aplicación se publica en las carpetas relacionadas (dentro de cada proyecto), el siguiente paso es compilar las imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="cc9b3-277">Para ello, utilice la compilación docker-compose y docker-crear comandos, tal como se muestra en la figura 8-16.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="cc9b3-278">**Figura 8-16.**</span><span class="sxs-lookup"><span data-stu-id="cc9b3-278">**Figure 8-16.**</span></span> <span data-ttu-id="cc9b3-279">Creación de imágenes de Docker y los contenedores en ejecución</span><span class="sxs-lookup"><span data-stu-id="cc9b3-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="cc9b3-280">En la figura 8-17, puede ver cómo la docker-compose crear la ejecución del comando.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="cc9b3-281">**Figura 8-17**.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-281">**Figure 8-17**.</span></span> <span data-ttu-id="cc9b3-282">Creación de las imágenes de Docker con el docker-crear el comando de compilación</span><span class="sxs-lookup"><span data-stu-id="cc9b3-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="cc9b3-283">La diferencia entre el docker-compose compilar y redactar docker de comandos es que docker crear compilaciones e inicia las imágenes.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="cc9b3-284">Cuando se utiliza Visual Studio, todos estos pasos se realizan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="cc9b3-285">Visual Studio compila la aplicación. NET, crea las imágenes de Docker e implementa los contenedores en el host Docker.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="cc9b3-286">Visual Studio ofrece características adicionales, como la capacidad para depurar los contenedores que se ejecutan en Docker, directamente desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="cc9b3-287">Aquí el takeway general es que es capaz de crear la aplicación de la misma forma en la canalización de CI/CD debe compilarse: desde un contenedor en lugar de desde un equipo local.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="cc9b3-288">Si tiene las imágenes creadas, a continuación, simplemente debe ejecutar las imágenes de Docker con el docker-crear comando.</span><span class="sxs-lookup"><span data-stu-id="cc9b3-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="cc9b3-289">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cc9b3-289">Additional resources</span></span>

-   <span data-ttu-id="cc9b3-290">**Creación de bits de un contenedor: configurar la solución eShopOnContainers en un entorno de Windows CLI (dotnet CLI, CLI de Docker y el código de VS)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="cc9b3-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cc9b3-291">[Anterior] (datos-controlada por-crud-microservice.md) [siguiente] (container.md de servidor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
