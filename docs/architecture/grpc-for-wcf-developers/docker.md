---
title: Docker-gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones de ASP.NET Core gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cc369da9494ade532187dfc8d19a94a3a037ebab
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841658"
---
# <a name="docker"></a><span data-ttu-id="58298-103">Docker</span><span class="sxs-lookup"><span data-stu-id="58298-103">Docker</span></span>

<span data-ttu-id="58298-104">En esta sección se tratará la creación de imágenes de Docker para aplicaciones ASP.NET Core gRPC, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedores.</span><span class="sxs-lookup"><span data-stu-id="58298-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="58298-105">La aplicación de ejemplo usada, con una aplicación web MVC ASP.NET Core y un servicio gRPC, está disponible en el repositorio [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.</span><span class="sxs-lookup"><span data-stu-id="58298-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="58298-106">Imágenes base de Microsoft para aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="58298-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="58298-107">Microsoft proporciona una variedad de imágenes base para compilar y ejecutar aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="58298-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="58298-108">Para crear una imagen ASP.NET Core 3,0, se usan dos imágenes base: una imagen de SDK para compilar y publicar la aplicación, y una imagen en tiempo de ejecución para la implementación.</span><span class="sxs-lookup"><span data-stu-id="58298-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="58298-109">Imagen</span><span class="sxs-lookup"><span data-stu-id="58298-109">Image</span></span> | <span data-ttu-id="58298-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="58298-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="58298-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="58298-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="58298-112">Para compilar aplicaciones con `docker build`.</span><span class="sxs-lookup"><span data-stu-id="58298-112">For building applications with `docker build`.</span></span> <span data-ttu-id="58298-113">No se va a usar en producción.</span><span class="sxs-lookup"><span data-stu-id="58298-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="58298-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="58298-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="58298-115">Contiene las dependencias de tiempo de ejecución y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="58298-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="58298-116">Para producción.</span><span class="sxs-lookup"><span data-stu-id="58298-116">For production.</span></span> |

<span data-ttu-id="58298-117">Para cada imagen, hay cuatro variantes basadas en distintas distribuciones de Linux, diferenciadas por etiquetas.</span><span class="sxs-lookup"><span data-stu-id="58298-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="58298-118">Etiqueta (s) de imagen</span><span class="sxs-lookup"><span data-stu-id="58298-118">Image tag(s)</span></span> | <span data-ttu-id="58298-119">Linux</span><span class="sxs-lookup"><span data-stu-id="58298-119">Linux</span></span> | <span data-ttu-id="58298-120">Notas</span><span class="sxs-lookup"><span data-stu-id="58298-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="58298-121">3,0-validador, 3,0</span><span class="sxs-lookup"><span data-stu-id="58298-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="58298-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="58298-122">Debian 10</span></span> | <span data-ttu-id="58298-123">La imagen predeterminada si no se especifica ninguna variante del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="58298-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="58298-124">3,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="58298-124">3.0-alpine</span></span> | <span data-ttu-id="58298-125">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="58298-125">Alpine 3.9</span></span> | <span data-ttu-id="58298-126">Las imágenes de Alpine base son mucho más pequeñas que las de Debian o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="58298-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="58298-127">3,0-disco</span><span class="sxs-lookup"><span data-stu-id="58298-127">3.0-disco</span></span> | <span data-ttu-id="58298-128">Ubuntu 19,04</span><span class="sxs-lookup"><span data-stu-id="58298-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="58298-129">3,0-Bionic</span><span class="sxs-lookup"><span data-stu-id="58298-129">3.0-bionic</span></span> | <span data-ttu-id="58298-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="58298-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="58298-131">La imagen de Alpine base es aproximadamente 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu, pero puede que algunos paquetes de software o bibliotecas no estén disponibles en la administración de paquetes de Alpine.</span><span class="sxs-lookup"><span data-stu-id="58298-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="58298-132">Si no está seguro de la imagen que se va a usar, es mejor ajustarla al Debian predeterminado a menos que tenga una necesidad convincente de usar un distribución diferente.</span><span class="sxs-lookup"><span data-stu-id="58298-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58298-133">Asegúrese de usar la misma variante de Linux para la compilación y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="58298-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="58298-134">Es posible que las aplicaciones compiladas y publicadas en una variante no funcionen en otra.</span><span class="sxs-lookup"><span data-stu-id="58298-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="58298-135">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="58298-135">Create a Docker image</span></span>

<span data-ttu-id="58298-136">Una imagen de Docker se define mediante un *Dockerfile*, un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58298-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="58298-137">En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 3,0:</span><span class="sxs-lookup"><span data-stu-id="58298-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="58298-138">Dockerfile tiene dos partes: la primera usa la imagen base `sdk` para compilar y publicar la aplicación. la segunda crea una imagen en tiempo de ejecución de la base `aspnet`.</span><span class="sxs-lookup"><span data-stu-id="58298-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="58298-139">Esto se debe a que la imagen de `sdk` es aproximadamente 900 MB en comparación con aproximadamente 200 MB para la imagen en tiempo de ejecución, y la mayor parte de su contenido no es necesario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="58298-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="58298-140">Pasos de compilación</span><span class="sxs-lookup"><span data-stu-id="58298-140">The build steps</span></span>

| <span data-ttu-id="58298-141">Paso</span><span class="sxs-lookup"><span data-stu-id="58298-141">Step</span></span> | <span data-ttu-id="58298-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="58298-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="58298-143">Declara la imagen base y asigna el alias `builder` (vea la siguiente sección para obtener una explicación).</span><span class="sxs-lookup"><span data-stu-id="58298-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="58298-144">Crea el directorio `/src` y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="58298-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="58298-145">Copia todo el directorio actual del host en el directorio actual de la imagen.</span><span class="sxs-lookup"><span data-stu-id="58298-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="58298-146">Restaura los paquetes externos (ASP.NET Core marco de trabajo de 3,0 se instala previamente con el SDK).</span><span class="sxs-lookup"><span data-stu-id="58298-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="58298-147">Compila y publica una compilación de versión.</span><span class="sxs-lookup"><span data-stu-id="58298-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="58298-148">Tenga en cuenta que la marca `--runtime` no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="58298-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="58298-149">Pasos de la imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="58298-149">The runtime image steps</span></span>

| <span data-ttu-id="58298-150">Paso</span><span class="sxs-lookup"><span data-stu-id="58298-150">Step</span></span> | <span data-ttu-id="58298-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="58298-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="58298-152">Declara una nueva imagen base.</span><span class="sxs-lookup"><span data-stu-id="58298-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="58298-153">Crea el directorio `/app` y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="58298-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="58298-154">Copia la aplicación publicada de la imagen anterior, mediante el `builder` alias de la primera línea `FROM`.</span><span class="sxs-lookup"><span data-stu-id="58298-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="58298-155">Establece que el comando se ejecute cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="58298-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="58298-156">El comando `dotnet` de la imagen en tiempo de ejecución solo puede ejecutar archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="58298-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="58298-157">HTTPS en Docker</span><span class="sxs-lookup"><span data-stu-id="58298-157">HTTPS in Docker</span></span>

<span data-ttu-id="58298-158">Imágenes base de Microsoft para Docker establezca la variable de entorno `ASPNETCORE_URLS` en `http://+:80`, lo que significa que Kestrel se ejecutará sin HTTPS en ese puerto.</span><span class="sxs-lookup"><span data-stu-id="58298-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="58298-159">Si usa HTTPS con un certificado personalizado (como se describe en [la sección anterior](self-hosted.md)), debe invalidarlo estableciendo la variable **de entorno en la parte de creación** de la imagen en tiempo de ejecución de su Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="58298-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="58298-160">El archivo. dockerignore</span><span class="sxs-lookup"><span data-stu-id="58298-160">The .dockerignore file</span></span>

<span data-ttu-id="58298-161">Al igual que los archivos de `.gitignore` que excluyen determinados archivos y directorios del control de código fuente, el archivo de `.dockerignore` se puede usar para excluir los archivos y directorios que se copian en la imagen durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="58298-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="58298-162">Esto no solo ahorra tiempo en la copia, sino que también puede evitar algunos errores confusos que surgen de tener (en particular) el directorio `obj` del equipo copiado en la imagen.</span><span class="sxs-lookup"><span data-stu-id="58298-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="58298-163">Debe agregar al menos entradas para `bin` y `obj` al archivo `.dockerignore`.</span><span class="sxs-lookup"><span data-stu-id="58298-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="58298-164">Compilar la imagen</span><span class="sxs-lookup"><span data-stu-id="58298-164">Build the image</span></span>

<span data-ttu-id="58298-165">Para una solución con una sola aplicación y, por lo tanto, un solo Dockerfile, es más sencillo colocar el Dockerfile en el directorio base; es decir, el mismo directorio que el archivo de `.sln`.</span><span class="sxs-lookup"><span data-stu-id="58298-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="58298-166">En ese caso, para compilar la imagen, use el siguiente comando de `docker build` desde el directorio que contiene Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="58298-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="58298-167">La marca de `--tag` con el nombre confuso (que se puede acortar a `-t`) especifica el nombre completo de la imagen, *incluida* la etiqueta real si se especifica.</span><span class="sxs-lookup"><span data-stu-id="58298-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="58298-168">El `.` al final especifica el *contexto* en el que se ejecutará la compilación; directorio de trabajo actual para los comandos `COPY` de Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="58298-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="58298-169">Si tiene varias aplicaciones en una única solución, puede mantener el Dockerfile para cada aplicación en su propia carpeta, junto al archivo `.csproj`, pero debe ejecutar el comando `docker build` desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen.</span><span class="sxs-lookup"><span data-stu-id="58298-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="58298-170">Puede especificar un Dockerfile debajo del directorio actual mediante la marca `--file` (o `-f`).</span><span class="sxs-lookup"><span data-stu-id="58298-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="58298-171">Ejecutar la imagen en un contenedor en el equipo</span><span class="sxs-lookup"><span data-stu-id="58298-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="58298-172">Para ejecutar la imagen en la instancia de Docker local, use el comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="58298-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="58298-173">La marca de `-ti` conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="58298-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="58298-174">El `-p 5000:80` publica (vínculos) el puerto 80 en el contenedor en el puerto 80 en la interfaz de red de localhost.</span><span class="sxs-lookup"><span data-stu-id="58298-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="58298-175">Inserte la imagen en un registro</span><span class="sxs-lookup"><span data-stu-id="58298-175">Push the image to a registry</span></span>

<span data-ttu-id="58298-176">Una vez que haya comprobado que la imagen funciona, debe insertarla en un registro de Docker para que esté disponible en otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="58298-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="58298-177">Las redes internas deberán aprovisionar un registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="58298-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="58298-178">Esto puede ser tan sencillo como la ejecución de la [propia imagen `registry` de Docker](https://docs.docker.com/registry/deploying/) (es decir, el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles.</span><span class="sxs-lookup"><span data-stu-id="58298-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="58298-179">Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) o [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="58298-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="58298-180">Para enviarlo a Docker Hub, anteponga el nombre de la imagen al nombre de usuario o de la organización.</span><span class="sxs-lookup"><span data-stu-id="58298-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="58298-181">Para enviar a un registro privado, Prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.</span><span class="sxs-lookup"><span data-stu-id="58298-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="58298-182">Una vez que la imagen se encuentra en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="58298-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="58298-183">[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="58298-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
