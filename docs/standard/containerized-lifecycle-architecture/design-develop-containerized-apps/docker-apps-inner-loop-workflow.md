---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Obtenga información sobre el flujo de trabajo de "bucle interno" para el desarrollo de aplicaciones de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 03eb4662e55551678105fa9ef25b42cc05c132a5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219093"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="18622-103">Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="18622-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="18622-104">Antes de desencadenar el flujo de trabajo del bucle exterior que abarca el DevOps completa del ciclo, todo comienza en el equipo de cada desarrollador, codificación de la propia aplicación, con sus lenguajes preferidos o plataformas y probarlo localmente (figura 4-14).</span><span class="sxs-lookup"><span data-stu-id="18622-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="18622-105">Pero en todos los casos, tendrá un punto muy importante en común, con independencia de qué lenguaje, marco o plataformas elija.</span><span class="sxs-lookup"><span data-stu-id="18622-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="18622-106">En este flujo de trabajo específico, siempre desarrolla y prueba contenedores de Docker, pero localmente.</span><span class="sxs-lookup"><span data-stu-id="18622-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="18622-107">Figura 4-14: Contexto de desarrollo de bucle interno</span><span class="sxs-lookup"><span data-stu-id="18622-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="18622-108">El contenedor o la instancia de una imagen de Docker contiene estos componentes:</span><span class="sxs-lookup"><span data-stu-id="18622-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="18622-109">Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="18622-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="18622-110">Archivos agregados por el desarrollador (por ejemplo, archivos binarios de aplicación)</span><span class="sxs-lookup"><span data-stu-id="18622-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="18622-111">Configuración (por ejemplo, configuración del entorno y dependencias)</span><span class="sxs-lookup"><span data-stu-id="18622-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="18622-112">Instrucciones para los procesos que ejecutar docker</span><span class="sxs-lookup"><span data-stu-id="18622-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="18622-113">Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como el proceso (descrito en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="18622-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="18622-114">Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluye, porque es necesario hacer una sola vez.</span><span class="sxs-lookup"><span data-stu-id="18622-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="18622-115">Creación de una sola aplicación en un contenedor de Docker con Visual Studio Code y CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="18622-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="18622-116">Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="18622-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="18622-117">Figura 4-15 muestra los pasos básicos que normalmente se necesitan para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.</span><span class="sxs-lookup"><span data-stu-id="18622-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="18622-118">Figura 4-15: Flujo de trabajo de alto nivel para el ciclo de vida de aplicaciones de Docker en contenedor mediante la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="18622-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="18622-119">Paso 1: Empezar a programar en Visual Studio Code y crear la instantánea inicial de aplicación/servicio</span><span class="sxs-lookup"><span data-stu-id="18622-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="18622-120">La manera de desarrollar la aplicación es bastante similar a la manera de que hacerlo sin Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="18622-121">La diferencia es que al desarrollar, implementar y probar su aplicación o servicios que se ejecutan dentro de contenedores de Docker que se colocan en su entorno local (por ejemplo, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="18622-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="18622-122">**Configurar el entorno local**</span><span class="sxs-lookup"><span data-stu-id="18622-122">**Setting up your local environment**</span></span>

<span data-ttu-id="18622-123">Con las últimas versiones de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.</span><span class="sxs-lookup"><span data-stu-id="18622-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="18622-124">**Obtener más información** para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="18622-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="18622-125">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="18622-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="18622-126">Además, necesitará un editor de código para que realmente puede desarrollar su aplicación a la vez mediante la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="18622-127">Microsoft proporciona código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [soporte para numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y más lenguajes modernos) [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="18622-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="18622-128">Este editor es una opción ideal para desarrolladores de Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="18622-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="18622-129">En Windows, también se puede usar la aplicación completa de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18622-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="18622-130">**Obtener más información** para obtener instrucciones sobre cómo instalar Visual Studio para Windows, Mac o Linux, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="18622-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>

<span data-ttu-id="18622-131">También puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero si usa Visual Studio Code, hace que resulte fácil al autor de Dockerfile y los archivos docker-compose.yml en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="18622-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="18622-132">Además, puede ejecutar tareas de Visual Studio Code desde el IDE que le solicitará las secuencias de comandos que se pueden ejecutar operaciones elaboradas mediante la CLI de Docker debajo.</span><span class="sxs-lookup"><span data-stu-id="18622-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="18622-133">Código de Visual Studio proporciona una extensión, que deberá instalar.</span><span class="sxs-lookup"><span data-stu-id="18622-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="18622-134">Para ello, presione Ctrl + Mayús + P, escriba **instalar ext**, y, a continuación, ejecutar las extensiones: Instale el comando de extensión para que aparezca la lista de extensiones de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="18622-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="18622-135">A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione el Dockerfile y Docker Compose archivo (yml) extensión del soporte técnico, como se muestra en la figura 4-16.</span><span class="sxs-lookup"><span data-stu-id="18622-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="18622-136">Figura 4-16: Instalar la extensión de Docker en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="18622-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="18622-137">Paso 2: Crear un DockerFile relacionado con una imagen existente (sin formato del sistema operativo o entornos de desarrollo como Ruby, Node.js y .NET Core)</span><span class="sxs-lookup"><span data-stu-id="18622-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="18622-138">Necesita un DockerFile por contenedor para implementarse y una imagen personalizada que se crea, por lo tanto, si la aplicación se compone de un único servicio personalizado, tendrá un solo DockerFile.</span><span class="sxs-lookup"><span data-stu-id="18622-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="18622-139">Sin embargo, si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará un Dockerfile por servicio.</span><span class="sxs-lookup"><span data-stu-id="18622-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="18622-140">El DockerFile se coloca normalmente en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="18622-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="18622-141">Puede crear el archivo DockerFile y agréguelo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="18622-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="18622-142">Puede usar una herramienta de línea de comandos denominada [yo docker](https://github.com/Microsoft/generator-docker), que aplica la técnica scaffolding archivos desde el proyecto en el lenguaje que prefiera y agrega los archivos de configuración de Docker necesarios.</span><span class="sxs-lookup"><span data-stu-id="18622-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="18622-143">Básicamente, para ayudar a desarrolladores principiantes, crea el archivo DockerFile adecuado, docker-compose.yml y otras secuencias de comandos asociados para compilar y ejecutar los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="18622-144">Este generador de yeoman le pedirá que con unas cuantas preguntas, que pide su host de contenedor de lenguaje y el destino de desarrollo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="18622-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![Yo docker](./media/image21.png)

<span data-ttu-id="18622-146">Por ejemplo, la figura 4-17 muestra dos capturas de pantalla de los terminales en Windows y en el equipo Mac, en ambos casos, con yo docker, lo que generará los proyectos de código muestra (actualmente .NET Core, Golang y Node.js como idiomas admitidos) ya está configurados para funcionar en parte superior de Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="18622-147">Figura 4-17: yo docker herramienta de comandos en Windows (izquierda) y en un equipo Mac</span><span class="sxs-lookup"><span data-stu-id="18622-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="18622-148">Figura 4-18 se presenta un ejemplo que usa yo docker una vez que un proyecto existente de .NET Core en el lugar donde se ha aplicado scaffolding.</span><span class="sxs-lookup"><span data-stu-id="18622-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="18622-149">Figura 4-18: yo docker con un núcleo de .NET existentes del proyecto en su lugar</span><span class="sxs-lookup"><span data-stu-id="18622-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="18622-150">En el DockerFile, especificar qué imagen de Docker básica que va a usar (por ejemplo, mediante "desde microsoft/dotnet:1.0.0-core").</span><span class="sxs-lookup"><span data-stu-id="18622-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="18622-151">Normalmente se compilará la imagen personalizada en una imagen base que se puede obtener desde cualquier repositorio oficial en la parte superior del [registro de Docker Hub](https://hub.docker.com/) (como un [imágenes para .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o un [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="18622-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="18622-152">***Opción A: Use una imagen de Docker oficial existente***</span><span class="sxs-lookup"><span data-stu-id="18622-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="18622-153">Uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).</span><span class="sxs-lookup"><span data-stu-id="18622-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="18622-154">Siguiente es un DockerFile de ejemplo para un contenedor de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="18622-154">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="18622-155">En este caso, usa la versión 1.0.1 de la imagen oficial de Docker de ASP.NET Core para Linux denominado microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="18622-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="18622-156">Para obtener más información, consulte el [página de la imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) y [página de la imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="18622-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="18622-157">También podría estar utilizando otra imagen comparable como nodo: 4-onbuild para Node.js o muchas otras imágenes preconfiguradas para los lenguajes de desarrollo, que están disponibles en [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="18622-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="18622-158">En el DockerFile, también debe indicar a Docker que escucha el puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).</span><span class="sxs-lookup"><span data-stu-id="18622-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="18622-159">Hay otras líneas de configuración que se puede agregar en el DockerFile, según el lenguaje o marco que usa, por lo que Docker sabe cómo ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18622-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="18622-160">Por ejemplo, se necesita la línea ENTRYPOINT con \["dotnet", "MyCustomMicroservice.dll"\] para ejecutar una aplicación .NET Core, aunque puede tener varias variantes según el enfoque para compilar y ejecutar su servicio.</span><span class="sxs-lookup"><span data-stu-id="18622-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="18622-161">Si usa el SDK y la CLI de dotnet para compilar y ejecutar la aplicación. NET, sería ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="18622-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="18622-162">La conclusión es que la línea ENTRYPOINT más líneas adicionales serán diferentes según el lenguaje o plataforma que elija para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="18622-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="18622-163">**Obtener más información** para obtener información sobre la creación de imágenes de Docker para aplicaciones .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="18622-163">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="18622-164">Para más información acerca de cómo crear sus propias imágenes, vaya a [ https://docs.docker.com/engine/\ dockerimages/tutoriales/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="18622-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="18622-165">**Repositorios de imágenes multiplataforma**</span><span class="sxs-lookup"><span data-stu-id="18622-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="18622-166">Como contenedores de Windows se vuelven más predominantes, un único repositorio puede contener variantes de plataforma, como una imagen de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="18622-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="18622-167">Se trata de una nueva característica incluida en Docker que hace posible que utilizan un único repositorio para abarcar varias plataformas, como los proveedores de [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio, que está disponible en el registro de DockerHub.</span><span class="sxs-lookup"><span data-stu-id="18622-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="18622-168">Extraer esta imagen de un host de Windows como la característica cobra vida, se extrae la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extraerá la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="18622-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="18622-169">***Opción B: Crear su imagen base desde cero***</span><span class="sxs-lookup"><span data-stu-id="18622-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="18622-170">Puede crear su propia imagen de base de Docker desde cero como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="18622-171">Este es un escenario que probablemente no es mejor para usted si está empezando con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="18622-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="18622-172">Paso 3: Crear las imágenes de Docker personalizadas insertar su servicio en él</span><span class="sxs-lookup"><span data-stu-id="18622-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="18622-173">Para cada servicio personalizado que consta de la aplicación, deberá crear una imagen relacionada.</span><span class="sxs-lookup"><span data-stu-id="18622-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="18622-174">Si la aplicación se compone de un único servicio o aplicación web, necesitará una imagen de única.</span><span class="sxs-lookup"><span data-stu-id="18622-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="18622-175">Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso de compilación automatizada siempre que inserte el código fuente en un repositorio de Git (integración continua), por lo que las imágenes se crearán en el entorno global de su código fuente.</span><span class="sxs-lookup"><span data-stu-id="18622-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="18622-176">Sin embargo, antes de que se considere la posibilidad de ir a esa ruta de bucle exterior, debemos asegurarnos de que la aplicación de Docker realmente funciona correctamente para que no inserción código que podría no funcionar correctamente en el sistema de control de código fuente (Git, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="18622-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="18622-177">Por lo tanto, cada desarrollador en primer lugar debe hacer todo el proceso de bucle interno para probar localmente y continuar desarrollando hasta que desean insertar una característica completa o cambio en el sistema de control de origen.</span><span class="sxs-lookup"><span data-stu-id="18622-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="18622-178">Para crear una imagen en su entorno local y mediante el DockerFile, puede usar el comando docker build, como se muestra en la figura 4-19 (también puede ejecutar docker-compose up--de compilación de aplicaciones compuestas por varios contenedores y servicios).</span><span class="sxs-lookup"><span data-stu-id="18622-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="18622-179">Figura 4-19: Ejecuta la compilación de docker</span><span class="sxs-lookup"><span data-stu-id="18622-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="18622-180">Si lo desea, en lugar de ejecutar directamente docker construido a partir de la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET necesarias mediante la ejecución de dotnet publicar el comando y, a continuación, ejecute la compilación de docker.</span><span class="sxs-lookup"><span data-stu-id="18622-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="18622-181">En este ejemplo, esto crea una imagen de Docker con el nombre cesardl/netcore-webapi-microservicio-docker: first (: first es una etiqueta, como una versión específica).</span><span class="sxs-lookup"><span data-stu-id="18622-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="18622-182">Puede realizar este paso para cada imagen personalizada, deberá crear la aplicación de Docker compuesta con varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="18622-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="18622-183">Puede encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) utilizando el docker de comando de imágenes, como se muestra en la figura 4-20.</span><span class="sxs-lookup"><span data-stu-id="18622-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="18622-184">Figura 4-20: Visualización de imágenes existente con imágenes de docker</span><span class="sxs-lookup"><span data-stu-id="18622-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="18622-185">Paso 4: (Opcional) Definir los servicios en docker-compose.yml al compilar una aplicación compuesta de Docker con varios servicios</span><span class="sxs-lookup"><span data-stu-id="18622-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="18622-186">Con el archivo docker-compose.yml puede definir un conjunto de servicios relacionados para implementarse como una aplicación compuesta con los comandos de implementación que se explica en la sección paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="18622-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="18622-187">Debe crear ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener un contenido similar al siguiente archivo docker-compose.yml:</span><span class="sxs-lookup"><span data-stu-id="18622-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="18622-188">En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio redis (un servicio de caché popular).</span><span class="sxs-lookup"><span data-stu-id="18622-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="18622-189">Cada servicio se implementará como un contenedor, por lo que necesitamos utilizar una imagen de Docker concreta para cada uno.</span><span class="sxs-lookup"><span data-stu-id="18622-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="18622-190">Para este servicio web en particular, la imagen debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18622-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="18622-191">Compilar desde el archivo DockerFile en el directorio actual</span><span class="sxs-lookup"><span data-stu-id="18622-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="18622-192">Reenviar el puerto 80 expuesto en el contenedor al puerto 81 en el equipo host</span><span class="sxs-lookup"><span data-stu-id="18622-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="18622-193">Montar el directorio del proyecto en el host a/Code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen</span><span class="sxs-lookup"><span data-stu-id="18622-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="18622-194">Vincular el servicio web para el servicio redis</span><span class="sxs-lookup"><span data-stu-id="18622-194">Link the web service to the redis service</span></span>

<span data-ttu-id="18622-195">El servicio redis usa el [imagen más reciente de redis pública](https://hub.docker.com/_/redis/) extrae del registro de Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="18622-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="18622-196">[Redis](https://redis.io/) es un sistema muy popular de caché para aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="18622-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="18622-197">Paso 5: Compilar y ejecutar la aplicación de Docker</span><span class="sxs-lookup"><span data-stu-id="18622-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="18622-198">Si la aplicación tiene solo un único contenedor, solo deberá ejecutarla mediante su implementación en el Host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="18622-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="18622-199">Sin embargo, si la aplicación se compone de varios servicios, deberá *componerla*, demasiado.</span><span class="sxs-lookup"><span data-stu-id="18622-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="18622-200">Vamos a ver las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="18622-200">Let's see the different options.</span></span>

<span data-ttu-id="18622-201">***Opción A: Ejecutar un único contenedor o servicio***</span><span class="sxs-lookup"><span data-stu-id="18622-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="18622-202">Puede ejecutar la imagen de Docker mediante el comando docker run, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="18622-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="18622-203">Tenga en cuenta que para esta implementación concreta, se deberá se redirigiendo las solicitudes enviadas al puerto 80 al puerto interno 5000.</span><span class="sxs-lookup"><span data-stu-id="18622-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="18622-204">Ahora, la aplicación está escuchando en el puerto 80 en el nivel de host externo.</span><span class="sxs-lookup"><span data-stu-id="18622-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="18622-205">***Opción B: Redactar y ejecutar una aplicación de varios contenedores***</span><span class="sxs-lookup"><span data-stu-id="18622-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="18622-206">En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios.</span><span class="sxs-lookup"><span data-stu-id="18622-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="18622-207">En estos casos, puede ejecutar el comando docker-compose copia (figura 4-21), que va a utilizar el archivo docker-compose.yml que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="18622-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="18622-208">Ejecutar este comando implementa una aplicación compuesta con todos sus contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="18622-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="18622-209">Figura 4-21: Resultados de ejecutar el comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="18622-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="18622-210">Después de ejecutar docker-compose seguridad, implementar la aplicación y sus contenedores relacionados en el Host de Docker, como se muestra en la figura 4-22, en la representación de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="18622-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="18622-211">Figura 4-22: Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="18622-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="18622-212">Docker compose de nota de seguridad y ejecución de docker podría ser suficiente para probar los contenedores en el entorno de desarrollo, pero puede que no los use en absoluto si se esperan trabajar con clústeres de Docker y orquestadores como Docker Swarm, Mesosphere DC/OS o Kubernetes Para poder escalar verticalmente.</span><span class="sxs-lookup"><span data-stu-id="18622-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="18622-213">Si usa un clúster como [modo Docker Swarm](https://docs.docker.com/engine/swarm/) (disponible en Docker para Windows y Mac desde la versión 1.12), debe implementar y probar con otros comandos, como crear servicio de docker para servicios únicos, o cuando haya implementar una aplicación que se compone de varios contenedores, usar docker compose agrupación y myBundleFile, de implementación de docker mediante la implementación de la aplicación compuesta como una pila, como se explica en el artículo [paquetes de aplicaciones distribuidas](https://blog.docker.com/2016/06/docker-app-bundle/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="18622-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="18622-214">Para [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) usaría los comandos de implementación diferentes y secuencias de comandos, también.</span><span class="sxs-lookup"><span data-stu-id="18622-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="18622-215">Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual local de CD)</span><span class="sxs-lookup"><span data-stu-id="18622-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="18622-216">Este paso variarán dependiendo de lo que hace la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18622-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="18622-217">En un muy .NET Core API Web simple "Hello World" implementar como un único contenedor o servicio, solo sería necesario acceder al servicio proporcionando el puerto TCP especificado en el archivo DockerFile.</span><span class="sxs-lookup"><span data-stu-id="18622-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="18622-218">Si localhost no está activado, para navegar a su servicio, busque la dirección IP para la máquina mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="18622-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="18622-219">docker-machine ip *su nombre de contenedor*</span><span class="sxs-lookup"><span data-stu-id="18622-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="18622-220">En el host de Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio que se está ejecutando, como se muestra en la figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="18622-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="18622-221">Figura 4-23: Probar la aplicación de Docker local mediante localhost</span><span class="sxs-lookup"><span data-stu-id="18622-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="18622-222">Tenga en cuenta que está utilizando el puerto 80, pero internamente se ha redireccionado al puerto 5000, ya que es cómo se implementa con docker en ejecución, como se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="18622-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="18622-223">Puede probar esto con CURL desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="18622-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="18622-224">En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-24.</span><span class="sxs-lookup"><span data-stu-id="18622-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="18622-225">Figura 4-24: Probar una aplicación de Docker localmente mediante CURL</span><span class="sxs-lookup"><span data-stu-id="18622-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="18622-226">**Depuración de un contenedor que se ejecutan en Docker**</span><span class="sxs-lookup"><span data-stu-id="18622-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="18622-227">Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como contenedores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18622-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="18622-228">También se pueden depurar contenedores .NET Core en Docker cuando se usa Visual Studio, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="18622-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="18622-229">**Más información:** para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y [ https://blogs.msdn.microsoft.com/\ usuario\_ed/2016/02/27 / Visual-Studio-Code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-More/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="18622-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="18622-230">[Anterior](docker-apps-development-environment.md)
>[Siguiente](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="18622-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>