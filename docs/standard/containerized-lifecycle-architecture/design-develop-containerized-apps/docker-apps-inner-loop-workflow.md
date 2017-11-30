---
title: Flujo de trabajo de desarrollo de bucle interno para las aplicaciones de Docker
description: "Ciclo de vida de aplicación de Docker en contenedores con herramientas y plataforma de Microsoft"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 30c10b2407ab643e04eb44c00ddf4a89d369a025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="3cf34-104">Flujo de trabajo de desarrollo de bucle interno para las aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="3cf34-105">Antes de desencadenar el flujo de trabajo de bucle exterior que abarca el DevOps todo ciclo, todo comienza en la máquina de cada programador, codificación de la propia aplicación, usando su idioma preferido o plataformas y probándolo localmente (figura 4-14).</span><span class="sxs-lookup"><span data-stu-id="3cf34-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using his preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="3cf34-106">Pero en todos los casos, tendrá un aspecto muy importante en común, independientemente del lenguaje, marco de trabajo o plataformas elija.</span><span class="sxs-lookup"><span data-stu-id="3cf34-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="3cf34-107">En este flujo de trabajo concreto, siempre se desarrollar y probar contenedores de Docker, pero localmente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="3cf34-108">Contexto de desarrollo de bucle interno de la figura 4-14:</span><span class="sxs-lookup"><span data-stu-id="3cf34-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="3cf34-109">El contenedor o la instancia de una imagen de Docker contendrá estos componentes:</span><span class="sxs-lookup"><span data-stu-id="3cf34-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="3cf34-110">Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="3cf34-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="3cf34-111">Archivos agregados por el programador (por ejemplo, archivos binarios de aplicación)</span><span class="sxs-lookup"><span data-stu-id="3cf34-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="3cf34-112">Configuración (por ejemplo, configuración de entorno y las dependencias)</span><span class="sxs-lookup"><span data-stu-id="3cf34-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="3cf34-113">Instrucciones para la que procesa al ejecutar Docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="3cf34-114">Puede configurar el flujo de trabajo de desarrollo de bucle interno que utiliza Docker como el proceso (descrito en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="3cf34-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="3cf34-115">Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluye, porque debe hacer una sola vez.</span><span class="sxs-lookup"><span data-stu-id="3cf34-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="3cf34-116">Creación de una aplicación única dentro de un contenedor de Docker con código de Visual Studio y la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="3cf34-117">Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="3cf34-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="3cf34-118">Figura 4-15 muestra los pasos básicos que suele ser preciso para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.</span><span class="sxs-lookup"><span data-stu-id="3cf34-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="3cf34-119">Figura 4-15: flujo de trabajo de alto nivel para el ciclo de vida de Docker en contenedores aplicaciones mediante la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="3cf34-120">Paso 1: Comenzar a codificar en código de Visual Studio y cree la línea de base inicial de aplicación/servicio</span><span class="sxs-lookup"><span data-stu-id="3cf34-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="3cf34-121">La manera de desarrollar la aplicación es bastante similar a la manera de que hacerlo sin necesidad de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="3cf34-122">La diferencia es que al desarrollar, implementar y pruebe la aplicación o los servicios que se ejecutan dentro de los contenedores de Docker que se coloca en su entorno local (por ejemplo, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="3cf34-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="3cf34-123">**Configuración del entorno local**</span><span class="sxs-lookup"><span data-stu-id="3cf34-123">**Setting up your local environment**</span></span>

<span data-ttu-id="3cf34-124">Con las versiones más recientes de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.</span><span class="sxs-lookup"><span data-stu-id="3cf34-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="3cf34-125">**Obtener más información** para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="3cf34-126">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="3cf34-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="3cf34-127">Además, deberá un editor de código para que realmente puede desarrollar su aplicación mientras usa la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="3cf34-128">Microsoft proporciona el código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [admite muchos idiomas](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, vaya, Java, Ruby, Python y más lenguajes modernos), [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con las extensiones](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="3cf34-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="3cf34-129">Este editor es una excelente elección para los desarrolladores Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="3cf34-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="3cf34-130">En Windows, también puede usar la aplicación completa de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3cf34-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="3cf34-131">**Obtener más información** para obtener instrucciones acerca de cómo instalar Visual Studio para Windows, Mac o Linux, vaya a [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="3cf34-132">También puede trabajar con CLI de Docker y escribir el código con cualquier editor de código, pero si usa código de Visual Studio, permite que los fáciles de autor Dockerfile y docker compose.yml archivos en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3cf34-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="3cf34-133">Además, puede ejecutar tareas de código de Visual Studio desde el IDE, que le solicitará las secuencias de comandos que se pueden ejecutar operaciones elaboradas con CLI de Docker debajo.</span><span class="sxs-lookup"><span data-stu-id="3cf34-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="3cf34-134">Código de Visual Studio proporciona una extensión, que debe instalar.</span><span class="sxs-lookup"><span data-stu-id="3cf34-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="3cf34-135">Para ello, presione Ctrl + Mayús + P, escriba **instalar ext**, y, a continuación, ejecutar las extensiones: comando de la extensión de instalación para que aparezca la lista de extensiones de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="3cf34-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="3cf34-136">A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione el archivo Dockerfile y redactar Dockerfile (yml) extensión de soporte técnico, como se muestra en la figura 4-16.</span><span class="sxs-lookup"><span data-stu-id="3cf34-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="3cf34-137">Figura 4-16: instalar la extensión Docker en el código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3cf34-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="3cf34-138">Paso 2: Crear un archivo DockerFile relacionada con una imagen existente (sistema operativo sin formato o entornos de desarrollo como el principal. NET, Node.js y Ruby)</span><span class="sxs-lookup"><span data-stu-id="3cf34-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="3cf34-139">Necesitará un DockerFile por una imagen personalizada que se crea y por contenedor para implementarse, por lo tanto, si la aplicación está formada por un único servicio personalizado, necesitará un DockerFile único.</span><span class="sxs-lookup"><span data-stu-id="3cf34-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="3cf34-140">Sin embargo, si la aplicación está compuesta de varios servicios (como en una arquitectura microservicios), necesitará un Dockerfile por cada servicio.</span><span class="sxs-lookup"><span data-stu-id="3cf34-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="3cf34-141">El DockerFile se coloca normalmente en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que ese Docker sepa cómo configurar y ejecutar esa aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="3cf34-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="3cf34-142">Puede crear el archivo DockerFile y agregarlo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="3cf34-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="3cf34-143">Puede usar una herramienta de línea de comandos denominada [yo docker](https://github.com/Microsoft/generator-docker), que scaffolds archivos desde el proyecto en el idioma que elija y agrega los archivos de configuración de Docker necesarios.</span><span class="sxs-lookup"><span data-stu-id="3cf34-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="3cf34-144">Básicamente, para ayudar a los desarrolladores de introducción, crea el DockerFile adecuado, docker compose.yml y otras secuencias de comandos asociadas para compilar y ejecutar los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="3cf34-145">Este generador yeoman le pedirá que con unas cuantas preguntas que pedir el host del contenedor de lenguaje y el destino de desarrollo seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3cf34-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![Yo docker](./media/image21.png)

<span data-ttu-id="3cf34-147">Por ejemplo, en la figura 4-17 muestra dos capturas de pantalla de los terminales en Windows y en un equipo Mac, en ambos casos, ejecute yo docker, lo que generará los proyectos de código muestra (actualmente .NET Core, Golang y Node.js como idiomas admitidos) ya está configurados para que funcionen en parte superior de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="3cf34-148">Figura 4-17: yo docker herramienta de comandos en Windows (izquierda) y en un equipo Mac</span><span class="sxs-lookup"><span data-stu-id="3cf34-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="3cf34-149">Figura 4-18 presenta un ejemplo de cómo utilizar yo docker después de tener un proyecto existente de .NET Core en su lugar para ser scaffolding.</span><span class="sxs-lookup"><span data-stu-id="3cf34-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="3cf34-150">Figura 4-18: yo docker con un núcleo de .NET existentes del proyecto en su lugar</span><span class="sxs-lookup"><span data-stu-id="3cf34-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="3cf34-151">Desde el DockerFile, especificar qué imagen de Docker base que vamos a usar (por ejemplo, mediante "de microsoft/dotnet:1.0.0-core").</span><span class="sxs-lookup"><span data-stu-id="3cf34-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="3cf34-152">Normalmente, se compilará la imagen personalizada encima de una imagen base que puede obtener desde cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como un [imagen para .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o un [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="3cf34-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="3cf34-153">***Opción A: usar una imagen de Docker oficial existente***</span><span class="sxs-lookup"><span data-stu-id="3cf34-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="3cf34-154">El uso de un repositorio de una pila de idioma oficial con un número de versión, se garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).</span><span class="sxs-lookup"><span data-stu-id="3cf34-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="3cf34-155">Aquí te mostramos un ejemplo de DockerFile para un contenedor de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="3cf34-155">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="3cf34-156">En este caso, que está usando la versión 1.0.1 de la imagen de Docker de núcleo de ASP.NET oficial para Linux denominada microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="3cf34-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="3cf34-157">Para obtener más información, consulte el [página de la imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) y [página de la imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="3cf34-158">También podría estar utilizando otra imagen comparable como nodo: 4-onbuild para Node.js o muchas otras imágenes preconfiguradas de lenguajes de programación, que están disponibles en [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="3cf34-159">En el DockerFile, también debe indicar a Docker que debe escuchar al puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).</span><span class="sxs-lookup"><span data-stu-id="3cf34-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="3cf34-160">Hay otras líneas de configuración que se puede agregar en el DockerFile según el idioma/framework que está utilizando, por lo que Docker sabe cómo ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cf34-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="3cf34-161">Por ejemplo, necesita la línea de punto de entrada con \["dotnet", "MyCustomMicroservice.dll"\] para ejecutar una aplicación .NET Core, aunque puede tener varias variantes según el enfoque para compilar y ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="3cf34-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="3cf34-162">Si usa el SDK y dotnet CLI para generar y ejecutar la aplicación. NET, sería ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="3cf34-163">La conclusión es que la línea de punto de entrada más líneas adicionales pueden variar en función del lenguaje o plataforma que elija para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cf34-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="3cf34-164">**Obtener más información** para obtener información sobre la creación de imágenes de Docker para las aplicaciones de .NET Core, vaya a <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="3cf34-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="3cf34-165">Para más información acerca de cómo crear sus propias imágenes, vaya a [https://docs.docker.com/engine/ \tutoriales/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="3cf34-166">**Repositorios de imágenes multiplataforma**</span><span class="sxs-lookup"><span data-stu-id="3cf34-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="3cf34-167">Contenedores de Windows se vuelven más frecuentes, un solo repositorio puede contener las variantes de la plataforma, como una imagen de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="3cf34-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="3cf34-168">Esta es una característica nueva que entran en Docker que permite a los proveedores usar un solo repositorio para abarcar varias plataformas, como [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio, que está disponible en el registro de DockerHub.</span><span class="sxs-lookup"><span data-stu-id="3cf34-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="3cf34-169">Tal como la característica se activa, extraer esta imagen de un host de Windows extraerá la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extraerá la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="3cf34-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="3cf34-170">***Opción B: crear la imagen base desde el principio***</span><span class="sxs-lookup"><span data-stu-id="3cf34-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="3cf34-171">Puede crear su propia imagen de base de Docker desde el principio como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="3cf34-172">Se trata de un escenario que probablemente no es mejor para usted si están iniciándose con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="3cf34-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="3cf34-173">Paso 3: Crear imágenes personalizadas Docker incrustar su servicio en él</span><span class="sxs-lookup"><span data-stu-id="3cf34-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="3cf34-174">Para cada servicio personalizado que consta de la aplicación, debe crear una imagen relacionada.</span><span class="sxs-lookup"><span data-stu-id="3cf34-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="3cf34-175">Si la aplicación está formada por un único servicio o una aplicación web, necesitará solo una única imagen.</span><span class="sxs-lookup"><span data-stu-id="3cf34-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf34-176">Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso automatizado de compilación siempre que insertar el código fuente en un repositorio de Git (integración continua) por lo que las imágenes se creará en el entorno global de su código fuente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="3cf34-177">Sin embargo, antes de que se tenga en cuenta si va a esa ruta de bucle externo, es necesario para asegurarse de que la aplicación de Docker realmente funciona correctamente para que no insertar código que podría no funcionar correctamente el sistema de control de código fuente (Git, etcetera).</span><span class="sxs-lookup"><span data-stu-id="3cf34-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="3cf34-178">Por lo tanto, cada desarrollador en primer lugar debe realizar todo el proceso de bucle interno para una prueba local y continuar desarrollando hasta que desean insertar una característica completa o cambiar el sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="3cf34-179">Para crear una imagen en su entorno local y usar el DockerFile, puede usar el comando de compilación de docker, como se muestra en la figura 4-19 (también puede ejecutar redactar docker: compilar aplicaciones compuestas por varios contenedores o servicios).</span><span class="sxs-lookup"><span data-stu-id="3cf34-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="3cf34-180">Figura 4-19: ejecuten la compilación de docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="3cf34-181">Si lo desea, en lugar de ejecutar directamente docker construido a partir de la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET necesarias mediante el uso de la ejecución dotnet comando Publicar y, a continuación, ejecute la compilación de docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="3cf34-182">En este ejemplo, esto crea una imagen de Docker con el nombre cesardl/netcore-webapi-microservicio-docker: primero (: en primer lugar es una etiqueta, como una versión específica).</span><span class="sxs-lookup"><span data-stu-id="3cf34-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="3cf34-183">Puede realizar este paso para cada imagen personalizada que se debe crear para su aplicación de Docker compuesta con varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="3cf34-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="3cf34-184">Se pueden encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) mediante el docker comandos de imágenes, como se muestra en la figura 4-20.</span><span class="sxs-lookup"><span data-stu-id="3cf34-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="3cf34-185">Figura 4-20: ver imágenes existentes con imágenes de docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="3cf34-186">Paso 4: (Opcional) definir los servicios en docker compose.yml al compilar una aplicación de Docker compuesta con varios servicios</span><span class="sxs-lookup"><span data-stu-id="3cf34-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="3cf34-187">Con el archivo compose.yml de docker puede definir un conjunto de servicios relacionados que desee implementar como una aplicación compuesta con los comandos de implementación que se explica en la sección paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="3cf34-188">Debe crear ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener un contenido similar al archivo docker compose.yml siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cf34-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="3cf34-189">En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio de redis (un servicio de caché populares).</span><span class="sxs-lookup"><span data-stu-id="3cf34-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="3cf34-190">Cada servicio se implementará como un contenedor, por lo que debemos usar una imagen de Docker concreta para cada uno.</span><span class="sxs-lookup"><span data-stu-id="3cf34-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="3cf34-191">Para este servicio web determinado, la imagen debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cf34-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="3cf34-192">Compilar desde el archivo DockerFile en el directorio actual</span><span class="sxs-lookup"><span data-stu-id="3cf34-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="3cf34-193">Reenviar el puerto 80 en el contenedor para el puerto 81 en el equipo host expuesto</span><span class="sxs-lookup"><span data-stu-id="3cf34-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="3cf34-194">Montar el directorio del proyecto en el host a /code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen</span><span class="sxs-lookup"><span data-stu-id="3cf34-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="3cf34-195">Vincular el servicio web para el servicio de redis</span><span class="sxs-lookup"><span data-stu-id="3cf34-195">Link the web service to the redis service</span></span>

<span data-ttu-id="3cf34-196">El servicio de redis utiliza el [imagen redis pública más reciente](https://hub.docker.com/_/redis/) extraídos del registro de Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="3cf34-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="3cf34-197">[Redis](http://redis.io/) es un sistema muy popular de caché para aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="3cf34-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="3cf34-198">Paso 5: Compilar y ejecutar la aplicación de Docker</span><span class="sxs-lookup"><span data-stu-id="3cf34-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="3cf34-199">Si la aplicación tiene solo un único contenedor, solo necesita ejecutar mediante la implementación en el Host Docker (virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="3cf34-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="3cf34-200">Sin embargo, si la aplicación está formada por varios servicios, debe *componerla*, demasiado.</span><span class="sxs-lookup"><span data-stu-id="3cf34-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="3cf34-201">Veamos las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="3cf34-201">Let's see the different options.</span></span>

<span data-ttu-id="3cf34-202">***Opción A: ejecutar un único contenedor o servicio***</span><span class="sxs-lookup"><span data-stu-id="3cf34-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="3cf34-203">Puede ejecutar la imagen de Docker mediante el comando docker run, tal y como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="3cf34-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="3cf34-204">Tenga en cuenta que para esta implementación concreta, se le puede redirigir las solicitudes enviadas al puerto 80 para el puerto interno 5000.</span><span class="sxs-lookup"><span data-stu-id="3cf34-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="3cf34-205">Ahora, la aplicación está escuchando en el puerto 80 en el nivel de host externo.</span><span class="sxs-lookup"><span data-stu-id="3cf34-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="3cf34-206">***Opción B: crear y ejecutar una aplicación de varios contenedores***</span><span class="sxs-lookup"><span data-stu-id="3cf34-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="3cf34-207">En la mayoría de los escenarios de empresa, una aplicación de Docker podría estar compuesta por varios servicios.</span><span class="sxs-lookup"><span data-stu-id="3cf34-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="3cf34-208">Para estos casos, puede ejecutar el comando Crear docker seguridad (ilustración 4-21), que usará el archivo de docker compose.yml que podría haber creado previamente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="3cf34-209">Ejecutar este comando, implementa una aplicación compuesta con todos sus contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="3cf34-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="3cf34-210">Figura 4-21: resultados de ejecutar el comando "docker-crear una"</span><span class="sxs-lookup"><span data-stu-id="3cf34-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="3cf34-211">Después de ejecutar docker-crear una, implementar la aplicación y sus contenedores relacionados en el Host Docker, como se muestra en la figura 4-22, en la representación de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="3cf34-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="3cf34-212">Figura 4-22: VM con contenedores de Docker implementado</span><span class="sxs-lookup"><span data-stu-id="3cf34-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="3cf34-213">Tenga en cuenta docker crear una y docker ejecutar quizás sea suficiente para probar los contenedores en el entorno de desarrollo, pero podría no utilizarlos en absoluto si está esperando trabajar con clústeres de Docker y orchestrators como Docker Swarm, Mesosphere DC/OS o Kubernetes Para poder escalar verticalmente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="3cf34-214">Si está usando un clúster como [Docker Swarm modo](https://docs.docker.com/engine/swarm/) (disponible en Docker para Windows y Mac desde la versión 1.12), debe implementar y probar con los comandos adicionales, como crear servicio docker para servicios de inicio único, o cuando estés implementar una aplicación formada por varios contenedores, con docker crear agrupación y docker implementar myBundleFile, mediante la implementación de la aplicación compuesta como una pila, como se explica en el artículo [paquetes de aplicaciones distribuidas](https://blog.docker.com/2016/06/docker-app-bundle/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="3cf34-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="3cf34-215">Para [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) usaría comandos de implementación diferentes y secuencias de comandos, también.</span><span class="sxs-lookup"><span data-stu-id="3cf34-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="3cf34-216">Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual CD local)</span><span class="sxs-lookup"><span data-stu-id="3cf34-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="3cf34-217">Este paso variarán dependiendo de lo que está haciendo la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cf34-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="3cf34-218">En un muy .NET Core API Web simple "Hola mundo" implementado como un único contenedor o el servicio, solo sería necesario tener acceso al servicio proporcionando el puerto TCP especificado en el DockerFile.</span><span class="sxs-lookup"><span data-stu-id="3cf34-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="3cf34-219">Si localhost no está activado, para navegar a su servicio, busque la dirección IP de la máquina mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="3cf34-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="3cf34-220">dirección ip del equipo de docker *el nombre del contenedor*</span><span class="sxs-lookup"><span data-stu-id="3cf34-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="3cf34-221">En el host Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio en ejecución, como se muestra en la figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="3cf34-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="3cf34-222">Figura 4-23: probar la aplicación de Docker localmente mediante localhost</span><span class="sxs-lookup"><span data-stu-id="3cf34-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="3cf34-223">Tenga en cuenta que está utilizando el puerto 80, pero internamente se se redirige al puerto 5000, ya que ese es cómo se implementó con docker ejecutar, como se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="3cf34-224">Puede probarlo mediante CURL desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="3cf34-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="3cf34-225">En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-24.</span><span class="sxs-lookup"><span data-stu-id="3cf34-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="3cf34-226">Figura 4-24: probar una aplicación de Docker localmente mediante CURL</span><span class="sxs-lookup"><span data-stu-id="3cf34-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="3cf34-227">**Depuración de un contenedor con Docker**</span><span class="sxs-lookup"><span data-stu-id="3cf34-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="3cf34-228">Código de Visual Studio admite la depuración Docker si usas Node.js y otras plataformas como contenedores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3cf34-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="3cf34-229">También puede depurar contenedores .NET Core en Docker cuando se utiliza Visual Studio, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cf34-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="3cf34-230">**Obtener más información:** para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y [https://blogs.msdn.microsoft.com/ \ usuario\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="3cf34-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3cf34-231">[Anterior] (docker-aplicaciones-desarrollo-environment.md) [siguiente] (visual-studio-herramientas-de-docker.md)</span><span class="sxs-lookup"><span data-stu-id="3cf34-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
