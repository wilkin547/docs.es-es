---
title: Ejecución de aplicaciones de consola en Docker
description: Aprenda a ejecutar una aplicación de consola existente de .NET Framework en un contenedor de Docker de Windows.
author: spboyer
ms.date: 09/28/2016
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: 379e0814d7d254935ef23a483d5e0f9163babcd1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145285"
---
# <a name="running-console-applications-in-windows-containers"></a><span data-ttu-id="82287-103">Ejecución de aplicaciones de consola en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="82287-103">Running console applications in Windows containers</span></span>

<span data-ttu-id="82287-104">Las aplicaciones de consola se usan para muchos fines, que abarcan desde la consulta simple de un estado a tareas de procesamiento de imágenes de documentos de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="82287-104">Console applications are used for many purposes; from simple querying of a status to long running document image processing tasks.</span></span> <span data-ttu-id="82287-105">En cualquier caso, la posibilidad de iniciar y escalar estas aplicaciones se enfrenta a limitaciones de adquisiciones de hardware, tiempos de inicio o ejecución de varias instancias.</span><span class="sxs-lookup"><span data-stu-id="82287-105">In any case, the ability to start up and scale these applications are met with limitations of hardware acquisitions, startup times or running multiple instances.</span></span>

<span data-ttu-id="82287-106">La migración de las aplicaciones de consola a contenedores de Docker y Windows Server permite iniciar estas aplicaciones desde un estado limpio, lo que facilita su funcionamiento y cierre sin problemas.</span><span class="sxs-lookup"><span data-stu-id="82287-106">Moving your console applications to use Docker and Windows Server containers allows for starting these applications from a clean state, enabling them to perform the operation and then shutdown cleanly.</span></span> <span data-ttu-id="82287-107">En este tema se explican los pasos necesarios para migrar una aplicación de consola a un contenedor basado en Windows y para iniciarla mediante un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82287-107">This topic will show the steps needed to move a console application to a Windows based container and start it using a PowerShell script.</span></span>

<span data-ttu-id="82287-108">La aplicación de consola de ejemplo es un ejemplo sencillo que toma un argumento, una pregunta en este caso, y devuelve una respuesta aleatoria.</span><span class="sxs-lookup"><span data-stu-id="82287-108">The sample console application is a simple example which takes an argument, a question in this case, and returns a random answer.</span></span> <span data-ttu-id="82287-109">Podría tomar un `customer_id` y procesar sus impuestos o crear una miniatura para un argumento `image_url`.</span><span class="sxs-lookup"><span data-stu-id="82287-109">This could take a `customer_id` and process their taxes, or create a thumbnail for an `image_url` argument.</span></span>

<span data-ttu-id="82287-110">Además de la respuesta, se ha agregado `Environment.MachineName` a ella para mostrar la diferencia entre la ejecución local de la aplicación y en un contenedor de Windows.</span><span class="sxs-lookup"><span data-stu-id="82287-110">In addition to the answer, the `Environment.MachineName` has been added to the response to show the difference between running the application locally and in a Windows container.</span></span> <span data-ttu-id="82287-111">Cuando la aplicación se ejecuta localmente, se debería devolver el nombre del equipo local, mientras que cuando se ejecuta en un contenedor de Windows, se devuelve el identificador de sesión del contenedor.</span><span class="sxs-lookup"><span data-stu-id="82287-111">When running the application locally, your local machine name should be returned and when running in a Windows Container; the container session id is returned.</span></span>

<span data-ttu-id="82287-112">El [ejemplo completo](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) está disponible en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="82287-112">The [complete example](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) is available in the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="82287-113">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="82287-113">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="82287-114">Antes de empezar a trabajar en la migración de la aplicación a un contenedor, debe estar familiarizado con algunos términos de Docker.</span><span class="sxs-lookup"><span data-stu-id="82287-114">You need to be familiar with some Docker terms before you begin working on moving your application to a container.</span></span>

> <span data-ttu-id="82287-115">Una *imagen de Docker* es una plantilla de solo lectura que define el entorno de un contenedor en ejecución, incluidos el sistema operativo (SO), los componentes del sistema y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="82287-115">A *Docker image* is a read-only template that defines the environment for a running container, including the operating system (OS), system components, and application(s).</span></span>

<span data-ttu-id="82287-116">Una característica importante de las imágenes de Docker es que se forman a partir de una imagen base.</span><span class="sxs-lookup"><span data-stu-id="82287-116">One important feature of Docker images is that images are composed from a base image.</span></span> <span data-ttu-id="82287-117">Cada nueva imagen agrega un pequeño conjunto de características a una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="82287-117">Each new image adds a small set of features to an existing image.</span></span> 

> <span data-ttu-id="82287-118">Un *contenedor de Docker* es una instancia en ejecución de una imagen.</span><span class="sxs-lookup"><span data-stu-id="82287-118">A *Docker container* is a running instance of an image.</span></span> 

<span data-ttu-id="82287-119">Una aplicación se escala al ejecutar la misma imagen en muchos contenedores.</span><span class="sxs-lookup"><span data-stu-id="82287-119">You scale an application by running the same image in many containers.</span></span>
<span data-ttu-id="82287-120">Conceptualmente, esto es similar a la ejecución de la misma aplicación en varios hosts.</span><span class="sxs-lookup"><span data-stu-id="82287-120">Conceptually, this is similar to running the same application in multiple hosts.</span></span>

<span data-ttu-id="82287-121">Puede obtener más información sobre la arquitectura de Docker si lee [Docker Overview (Introducción a Docker)](https://docs.docker.com/engine/understanding-docker/) en el sitio de Docker.</span><span class="sxs-lookup"><span data-stu-id="82287-121">You can learn more about the Docker architecture by reading the [Docker Overview](https://docs.docker.com/engine/understanding-docker/) on the Docker site.</span></span> 

<span data-ttu-id="82287-122">La migración de la aplicación de consola se realiza en unos pocos pasos.</span><span class="sxs-lookup"><span data-stu-id="82287-122">Moving your console application is a matter of a few steps.</span></span>

1. [<span data-ttu-id="82287-123">Compilar la aplicación</span><span class="sxs-lookup"><span data-stu-id="82287-123">Build the application</span></span>](#building-the-application)
1. [<span data-ttu-id="82287-124">Creación de un Dockerfile para la imagen</span><span class="sxs-lookup"><span data-stu-id="82287-124">Creating a Dockerfile for the image</span></span>](#creating-the-dockerfile)
1. [<span data-ttu-id="82287-125">Proceso para compilar y ejecutar el contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="82287-125">Process to build and run the Docker container</span></span>](#creating-the-image)

## <a name="prerequisites"></a><span data-ttu-id="82287-126">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82287-126">Prerequisites</span></span>
<span data-ttu-id="82287-127">Los contenedores de Windows son compatibles con [Actualización de aniversario de Windows 10](https://www.microsoft.com/en-us/software-download/windows10/) o [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span><span class="sxs-lookup"><span data-stu-id="82287-127">Windows containers are supported on [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) or [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span></span>

> [!NOTE]
><span data-ttu-id="82287-128">Si usa Windows Server 2016, debe habilitar los contenedores de forma manual, ya que el instalador de Docker para Windows no habilitará la característica.</span><span class="sxs-lookup"><span data-stu-id="82287-128">If you are using Windows Server 2016, you must enable containers manually since the Docker for Windows installer will not enable the feature.</span></span> <span data-ttu-id="82287-129">Asegúrese de que todas las actualizaciones del sistema operativo se hayan ejecutado y luego siga las instrucciones del artículo [Implementación de host de contenedor](/virtualization/windowscontainers/deploy-containers/deploy-containers-on-server) para instalar los contenedores y las características de Docker.</span><span class="sxs-lookup"><span data-stu-id="82287-129">Make sure all updates have run for the OS and then follow the instructions from the [Container Host Deployment](/virtualization/windowscontainers/deploy-containers/deploy-containers-on-server) article to install the containers and Docker features.</span></span>

<span data-ttu-id="82287-130">Para admitir los contenedores de Windows, debe tener Docker para Windows, versión 1.12 Beta 26 o superior.</span><span class="sxs-lookup"><span data-stu-id="82287-130">You need to have Docker for Windows, version 1.12 Beta 26 or higher to support Windows containers.</span></span> <span data-ttu-id="82287-131">De forma predeterminada, Docker habilita los contenedores basados en Linux. Cambie a los contenedores de Windows al hacer clic con el botón derecho en el icono de Docker de la bandeja del sistema y seleccionar la opción para **cambiar a contenedores de Windows**.</span><span class="sxs-lookup"><span data-stu-id="82287-131">By default, Docker enables Linux based containers; switch to Windows containers by right clicking the Docker icon in the system tray and select **Switch to Windows containers**.</span></span> <span data-ttu-id="82287-132">Docker ejecutará el proceso de cambio. Es posible que sea necesario reiniciar.</span><span class="sxs-lookup"><span data-stu-id="82287-132">Docker will run the process to change and a restart may be required.</span></span>

![Contenedores de Windows](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a><span data-ttu-id="82287-134">Compilación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="82287-134">Building the application</span></span>
<span data-ttu-id="82287-135">Normalmente las aplicaciones de consola se distribuyen a través de un instalador, un FTP o una implementación de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="82287-135">Typically console applications are distributed through an installer, FTP, or File Share deployment.</span></span> <span data-ttu-id="82287-136">Al implementar en un contenedor, los activos tienen que compilarse y colocarse en una ubicación que se pueda usar una vez creada la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="82287-136">When deploying to a container, the assets need to be compiled and staged to a location that can be used when the Docker image is created.</span></span>

<span data-ttu-id="82287-137">En *build.ps1*, el script usa [MSBuild](/visualstudio/msbuild/msbuild) para compilar la aplicación a fin de completar la tarea de creación de los activos.</span><span class="sxs-lookup"><span data-stu-id="82287-137">In *build.ps1*, the script uses [MSBuild](/visualstudio/msbuild/msbuild) to compile the application to complete the task of building the assets.</span></span> <span data-ttu-id="82287-138">Algunos parámetros se pasan a MSBuild para finalizar los activos necesarios.</span><span class="sxs-lookup"><span data-stu-id="82287-138">There are a few parameters passed to MSBuild to finalize the needed assets.</span></span> <span data-ttu-id="82287-139">El nombre del archivo del proyecto o la solución que se va a compilar, la ubicación de la salida y, por último, la configuración (lanzamiento o depuración).</span><span class="sxs-lookup"><span data-stu-id="82287-139">The name of the project file or solution to be compiled, the location for the output and finally the configuration (Release or Debug).</span></span>

<span data-ttu-id="82287-140">En la llamada a `Invoke-MSBuild`, `OutputPath` se establece en **publish** y `Configuration` en **Release**.</span><span class="sxs-lookup"><span data-stu-id="82287-140">In the call to `Invoke-MSBuild` the `OutputPath` is set to **publish** and  `Configuration` set to **Release**.</span></span> 

```powershell
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj -p:OutputPath=.\publish -p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a><span data-ttu-id="82287-141">Creación del Dockerfile</span><span class="sxs-lookup"><span data-stu-id="82287-141">Creating the Dockerfile</span></span>
<span data-ttu-id="82287-142">La imagen base usada para una aplicación de consola de .NET Framework es `microsoft/windowsservercore`, disponible públicamente en [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span><span class="sxs-lookup"><span data-stu-id="82287-142">The base image used for a console .NET Framework application is `microsoft/windowsservercore`, publicly available on [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span></span> <span data-ttu-id="82287-143">La imagen base contiene una instalación mínima de Windows Server 2016, .NET Framework 4.6.2 y sirve como imagen base de sistema operativo para los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="82287-143">The base image contains a minimal installation of Windows Server 2016, .NET Framework 4.6.2 and serves as the base OS image for Windows Containers.</span></span>

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
<span data-ttu-id="82287-144">La primera línea del Dockerfile designa la imagen base mediante la instrucción [`FROM`](https://docs.docker.com/engine/reference/builder/#/from).</span><span class="sxs-lookup"><span data-stu-id="82287-144">The first line in the Dockerfile designates the base image using the [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) instruction.</span></span> <span data-ttu-id="82287-145">Después, el elemento [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) del archivo copia los activos de la aplicación de la carpeta **publish** en la carpeta raíz del contenedor y, por último, el establecimiento de [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) de la imagen indica que este es el comando o la aplicación que se va a ejecutar cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="82287-145">Next, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in the file copies the application assets from the **publish** folder to root folder of the container and last; setting the [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) of the image states that this is the command or application that will run when the container starts.</span></span> 

## <a name="creating-the-image"></a><span data-ttu-id="82287-146">Creación de la imagen</span><span class="sxs-lookup"><span data-stu-id="82287-146">Creating the image</span></span>
<span data-ttu-id="82287-147">Para crear la imagen de Docker, se agrega el código siguiente al script *build.ps1*.</span><span class="sxs-lookup"><span data-stu-id="82287-147">In order to create the Docker image, the following code is added to the *build.ps1* script.</span></span> <span data-ttu-id="82287-148">Cuando se ejecuta el script, se crea la imagen `console-random-answer-generator` mediante los activos compilados a partir del elemento MSBuild definido en la sección [Compilación de la aplicación](#building-the-application).</span><span class="sxs-lookup"><span data-stu-id="82287-148">When the script is run, the `console-random-answer-generator` image is created using the assets compiled from MSBuild defined in the [Building the application](#building-the-application) section.</span></span>

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

<span data-ttu-id="82287-149">Ejecute el script mediante el elemento `.\build.ps1` desde el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82287-149">Run the script using `.\build.ps1` from the PowerShell command prompt.</span></span>

<span data-ttu-id="82287-150">Una vez completada la compilación, si usa el comando `docker images` desde una línea de comandos o el símbolo del sistema de PowerShell, verá que la imagen está creada y lista para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="82287-150">When the build is complete, using the `docker images` command from a command line or PowerShell prompt; you'll see that the image is created and ready to be run.</span></span>

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a><span data-ttu-id="82287-151">Ejecución del contenedor</span><span class="sxs-lookup"><span data-stu-id="82287-151">Running the container</span></span>
<span data-ttu-id="82287-152">Puede iniciar el contenedor desde la línea de comandos mediante los comandos de Docker.</span><span class="sxs-lookup"><span data-stu-id="82287-152">You can start the container from the command line using the Docker commands.</span></span>

```
docker run console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="82287-153">El resultado es</span><span class="sxs-lookup"><span data-stu-id="82287-153">The output is</span></span>

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

<span data-ttu-id="82287-154">Si ejecuta el comando `docker ps -a` desde PowerShell, puede ver que el contenedor todavía existe.</span><span class="sxs-lookup"><span data-stu-id="82287-154">If you run the `docker ps -a` command from PowerShell, you can see that the container still exists.</span></span>

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

<span data-ttu-id="82287-155">La columna STATUS muestra que, "hace aproximadamente un minuto", la aplicación estaba completa y se podía cerrar.</span><span class="sxs-lookup"><span data-stu-id="82287-155">The STATUS column shows at "About a minute ago", the application was complete and could be shut down.</span></span> <span data-ttu-id="82287-156">Si el comando se ejecuta cien veces, habría cien contenedores estáticos sin ningún trabajo que hacer.</span><span class="sxs-lookup"><span data-stu-id="82287-156">If the command was run a hundred times, there would be a hundred containers left static with no work to do.</span></span> <span data-ttu-id="82287-157">En el escenario inicial, la operación ideal era realizar el trabajo y cerrar o limpiar.</span><span class="sxs-lookup"><span data-stu-id="82287-157">In the beginning scenario the ideal operation was to do the work and shutdown or cleanup.</span></span> <span data-ttu-id="82287-158">Para lograr ese flujo de trabajo, agregue la opción `--rm` al comando `docker run`, con lo que se quitará el contenedor en cuanto se reciba la señal `Exited`.</span><span class="sxs-lookup"><span data-stu-id="82287-158">To accomplish that workflow, adding the `--rm` option to the `docker run` command will remove the container as soon as the `Exited` signal is received.</span></span>

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="82287-159">Si ejecuta el comando con esta opción y luego examina el resultado del comando `docker ps -a`, observará que el identificador del contenedor (`Environment.MachineName`) no está en la lista.</span><span class="sxs-lookup"><span data-stu-id="82287-159">Running the command with this option and then looking at the output of `docker ps -a` command; notice that the container id (the `Environment.MachineName`) is not in the list.</span></span>

### <a name="running-the-container-using-powershell"></a><span data-ttu-id="82287-160">Ejecución del contenedor mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="82287-160">Running the container using PowerShell</span></span>
<span data-ttu-id="82287-161">En los archivos del proyecto de ejemplo también hay un *run.ps1*, que es un ejemplo de cómo usar PowerShell para ejecutar la aplicación que acepta los argumentos.</span><span class="sxs-lookup"><span data-stu-id="82287-161">In the sample project files there is also a *run.ps1* which is an example of how to use PowerShell to run the application accepting the arguments.</span></span>

<span data-ttu-id="82287-162">Para ejecutar, abra PowerShell y use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="82287-162">To run, open PowerShell and use the following command:</span></span>

```powershell
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a><span data-ttu-id="82287-163">Resumen</span><span class="sxs-lookup"><span data-stu-id="82287-163">Summary</span></span>
<span data-ttu-id="82287-164">Con solo agregar un Dockerfile y publicar la aplicación, puede colocar en contenedores las aplicaciones de consola de .NET Framework y aprovechar las ventajas que ofrece la ejecución de varias instancias, el inicio y la detención limpios y otras capacidades de Windows Server 2016 sin realizar cambio alguno en el código de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="82287-164">Just by adding a Dockerfile and publishing the application, you can containerize your .NET Framework console applications and now take the advantage of running multiple instances, clean start and stop and more Windows Server 2016 capabilities without making any changes to the application code at all.</span></span>
