---
title: Docker-gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones de ASP.NET Core gRPC
ms.date: 12/15/2020
ms.openlocfilehash: f662dbd67f00b828f3e1dfa47359a450dd1c5900
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938421"
---
# <a name="create-docker-images"></a><span data-ttu-id="e5793-103">Creación de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="e5793-103">Create Docker images</span></span>

<span data-ttu-id="e5793-104">En esta sección se describe la creación de imágenes de Docker para aplicaciones ASP.NET Core gRPC, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedores.</span><span class="sxs-lookup"><span data-stu-id="e5793-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="e5793-105">La aplicación de ejemplo usada, con una aplicación web MVC ASP.NET Core y un servicio gRPC, está disponible en el repositorio [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.</span><span class="sxs-lookup"><span data-stu-id="e5793-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="e5793-106">Imágenes base de Microsoft para aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5793-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="e5793-107">Microsoft proporciona una variedad de imágenes base para compilar y ejecutar aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5793-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="e5793-108">Para crear una imagen ASP.NET Core 3,0, se usan dos imágenes base:</span><span class="sxs-lookup"><span data-stu-id="e5793-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="e5793-109">Una imagen de SDK para compilar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5793-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="e5793-110">Una imagen en tiempo de ejecución para la implementación.</span><span class="sxs-lookup"><span data-stu-id="e5793-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="e5793-111">Imagen</span><span class="sxs-lookup"><span data-stu-id="e5793-111">Image</span></span> | <span data-ttu-id="e5793-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5793-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="e5793-113">mcr.microsoft.com/dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="e5793-113">mcr.microsoft.com/dotnet/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-sdk/) | <span data-ttu-id="e5793-114">Para compilar aplicaciones con `docker build` .</span><span class="sxs-lookup"><span data-stu-id="e5793-114">For building applications with `docker build`.</span></span> <span data-ttu-id="e5793-115">No se va a usar en producción.</span><span class="sxs-lookup"><span data-stu-id="e5793-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="e5793-116">mcr.microsoft.com/dotnet/aspnet</span><span class="sxs-lookup"><span data-stu-id="e5793-116">mcr.microsoft.com/dotnet/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | <span data-ttu-id="e5793-117">Contiene las dependencias de tiempo de ejecución y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5793-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="e5793-118">Para producción.</span><span class="sxs-lookup"><span data-stu-id="e5793-118">For production.</span></span> |

<span data-ttu-id="e5793-119">Para cada imagen, hay cuatro variantes basadas en distintas distribuciones de Linux, diferenciadas por etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e5793-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="e5793-120">Etiqueta (s) de imagen</span><span class="sxs-lookup"><span data-stu-id="e5793-120">Image tag(s)</span></span> | <span data-ttu-id="e5793-121">Linux</span><span class="sxs-lookup"><span data-stu-id="e5793-121">Linux</span></span> | <span data-ttu-id="e5793-122">Notas</span><span class="sxs-lookup"><span data-stu-id="e5793-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="e5793-123">5,0-validador, 5,0</span><span class="sxs-lookup"><span data-stu-id="e5793-123">5.0-buster, 5.0</span></span> | <span data-ttu-id="e5793-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e5793-124">Debian 10</span></span> | <span data-ttu-id="e5793-125">La imagen predeterminada si no se especifica ninguna variante del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e5793-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="e5793-126">5,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="e5793-126">5.0-alpine</span></span> | <span data-ttu-id="e5793-127">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="e5793-127">Alpine 3.9</span></span> | <span data-ttu-id="e5793-128">Las imágenes de Alpine base son mucho más pequeñas que las de Debian o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e5793-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="e5793-129">5,0-disco</span><span class="sxs-lookup"><span data-stu-id="e5793-129">5.0-disco</span></span> | <span data-ttu-id="e5793-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="e5793-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="e5793-131">5,0-Bionic</span><span class="sxs-lookup"><span data-stu-id="e5793-131">5.0-bionic</span></span> | <span data-ttu-id="e5793-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e5793-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="e5793-133">La imagen de la base de Alpine es aproximadamente 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e5793-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="e5793-134">Es posible que algunos paquetes de software o bibliotecas no estén disponibles en la administración de paquetes de Alpine.</span><span class="sxs-lookup"><span data-stu-id="e5793-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="e5793-135">Si no está seguro de la imagen que se va a usar, probablemente debería elegir el Debian predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5793-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5793-136">Asegúrese de usar la misma variante de Linux para la compilación y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e5793-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="e5793-137">Es posible que las aplicaciones compiladas y publicadas en una variante no funcionen en otra.</span><span class="sxs-lookup"><span data-stu-id="e5793-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="e5793-138">Cree una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="e5793-138">Create a Docker image</span></span>

<span data-ttu-id="e5793-139">Una imagen de Docker se define mediante un *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="e5793-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="e5793-140">Este *Dockerfile* es un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5793-140">This *Dockerfile* is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="e5793-141">En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 5,0:</span><span class="sxs-lookup"><span data-stu-id="e5793-141">The following example shows the simplest Dockerfile for an ASP.NET Core 5.0 application:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="e5793-142">Dockerfile tiene dos partes: la primera usa la `sdk` imagen base para compilar y publicar la aplicación; la segunda crea una imagen en tiempo de ejecución de la `aspnet` base.</span><span class="sxs-lookup"><span data-stu-id="e5793-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="e5793-143">Esto se debe a que la `sdk` imagen es de aproximadamente 900 MB, en comparación con aproximadamente 200 MB para la imagen en tiempo de ejecución, y la mayor parte de su contenido no es necesario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e5793-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="e5793-144">Pasos de compilación</span><span class="sxs-lookup"><span data-stu-id="e5793-144">The build steps</span></span>

| <span data-ttu-id="e5793-145">Paso</span><span class="sxs-lookup"><span data-stu-id="e5793-145">Step</span></span> | <span data-ttu-id="e5793-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5793-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="e5793-147">Declara la imagen base y asigna el `builder` alias.</span><span class="sxs-lookup"><span data-stu-id="e5793-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="e5793-148">Crea el `/src` Directorio y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="e5793-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="e5793-149">Copia todo el directorio actual del host en el directorio actual de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e5793-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="e5793-150">Restaura los paquetes externos (ASP.NET Core marco de trabajo de 3,0 se instala previamente con el SDK).</span><span class="sxs-lookup"><span data-stu-id="e5793-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="e5793-151">Compila y publica una compilación de versión.</span><span class="sxs-lookup"><span data-stu-id="e5793-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="e5793-152">Tenga en cuenta que la `--runtime` marca no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="e5793-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="e5793-153">Pasos de la imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e5793-153">The runtime image steps</span></span>

| <span data-ttu-id="e5793-154">Paso</span><span class="sxs-lookup"><span data-stu-id="e5793-154">Step</span></span> | <span data-ttu-id="e5793-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5793-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="e5793-156">Declara una nueva imagen base.</span><span class="sxs-lookup"><span data-stu-id="e5793-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="e5793-157">Crea el `/app` Directorio y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="e5793-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="e5793-158">Copia la aplicación publicada de la imagen anterior mediante el uso del `builder` alias de la primera `FROM` línea.</span><span class="sxs-lookup"><span data-stu-id="e5793-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="e5793-159">Establece que el comando se ejecute cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e5793-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="e5793-160">El `dotnet` comando de la imagen en tiempo de ejecución solo puede ejecutar archivos dll.</span><span class="sxs-lookup"><span data-stu-id="e5793-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="e5793-161">HTTPS en Docker</span><span class="sxs-lookup"><span data-stu-id="e5793-161">HTTPS in Docker</span></span>

<span data-ttu-id="e5793-162">Imágenes base de Microsoft para Docker establezca la `ASPNETCORE_URLS` variable de entorno en `http://+:80` , lo que significa que Kestrel se ejecuta sin HTTPS en ese puerto.</span><span class="sxs-lookup"><span data-stu-id="e5793-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="e5793-163">Si usa HTTPS con un certificado personalizado (como se describe en [aplicaciones gRPC autohospedadas](self-hosted.md)), debe invalidar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="e5793-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this configuration.</span></span> <span data-ttu-id="e5793-164">Establezca la variable de entorno en la parte de creación de la imagen en tiempo de ejecución de su Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e5793-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="e5793-165">El archivo. dockerignore</span><span class="sxs-lookup"><span data-stu-id="e5793-165">The .dockerignore file</span></span>

<span data-ttu-id="e5793-166">De forma muy similar a `.gitignore` los archivos que excluyen determinados archivos y directorios del control de código fuente, el `.dockerignore` archivo se puede usar para excluir archivos y directorios de copiarse en la imagen durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="e5793-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="e5793-167">Este archivo no solo ahorra tiempo en la copia, sino que también puede evitar algunos errores que surgen cuando se `obj` copia el directorio del equipo en la imagen.</span><span class="sxs-lookup"><span data-stu-id="e5793-167">This file not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="e5793-168">Como mínimo, debe agregar entradas para `bin` y `obj` en el `.dockerignore` archivo.</span><span class="sxs-lookup"><span data-stu-id="e5793-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="e5793-169">Compilación de la imagen</span><span class="sxs-lookup"><span data-stu-id="e5793-169">Build the image</span></span>

<span data-ttu-id="e5793-170">En el caso de una `StockKube.sln` solución que contenga dos aplicaciones diferentes `StockData` y `StockWeb` , es más sencillo colocar el Dockerfile para cada uno de ellos en el directorio base.</span><span class="sxs-lookup"><span data-stu-id="e5793-170">For a `StockKube.sln` solution containing two different applications `StockData` and `StockWeb`, it's simplest to put the Dockerfile for each one of them in the base directory.</span></span> <span data-ttu-id="e5793-171">En ese caso, para compilar la imagen, use el siguiente `docker build` comando desde el mismo directorio donde `.sln` reside el archivo.</span><span class="sxs-lookup"><span data-stu-id="e5793-171">In that case, to build the image, use the following `docker build` command from the same directory where `.sln` file resides.</span></span>

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

<span data-ttu-id="e5793-172">La marca con el nombre confuso `--tag` (que se puede acortar a `-t` ) especifica el nombre completo de la imagen, incluida la etiqueta real si se especifica.</span><span class="sxs-lookup"><span data-stu-id="e5793-172">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="e5793-173">`.`Al final especifica el contexto en el que se ejecutará la compilación; el directorio de trabajo actual para los `COPY` comandos de Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e5793-173">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="e5793-174">Si tiene varias aplicaciones en una única solución, puede mantener el Dockerfile para cada aplicación en su propia carpeta, junto al `.csproj` archivo.</span><span class="sxs-lookup"><span data-stu-id="e5793-174">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="e5793-175">Siga ejecutando el `docker build` comando desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen.</span><span class="sxs-lookup"><span data-stu-id="e5793-175">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="e5793-176">Puede especificar un Dockerfile debajo del directorio actual mediante la `--file` marca (o `-f` ).</span><span class="sxs-lookup"><span data-stu-id="e5793-176">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="e5793-177">Ejecutar la imagen en un contenedor en el equipo</span><span class="sxs-lookup"><span data-stu-id="e5793-177">Run the image in a container on your machine</span></span>

<span data-ttu-id="e5793-178">Para ejecutar la imagen en la instancia de Docker local, use el `docker run` comando.</span><span class="sxs-lookup"><span data-stu-id="e5793-178">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

<span data-ttu-id="e5793-179">La `-ti` marca conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="e5793-179">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="e5793-180">El `-p 5000:80` Puerto de publicación (vínculos) 80 del contenedor al puerto 5000 en la interfaz de red de localhost.</span><span class="sxs-lookup"><span data-stu-id="e5793-180">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="e5793-181">Inserte la imagen en un registro</span><span class="sxs-lookup"><span data-stu-id="e5793-181">Push the image to a registry</span></span>

<span data-ttu-id="e5793-182">Una vez que haya comprobado que la imagen funciona, inserte en un registro de Docker para que esté disponible en otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="e5793-182">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="e5793-183">Las redes internas deberán aprovisionar un registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="e5793-183">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="e5793-184">Esta actividad puede ser tan sencilla como la ejecución de la [propia `registry` imagen de Docker](https://docs.docker.com/registry/deploying/) (el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e5793-184">This activity can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="e5793-185">Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](/azure/container-registry/) o [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="e5793-185">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="e5793-186">Para enviar a Docker Hub, Prefije el nombre de la imagen con el nombre de usuario o de la organización.</span><span class="sxs-lookup"><span data-stu-id="e5793-186">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

<span data-ttu-id="e5793-187">Para enviar a un registro privado, Prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.</span><span class="sxs-lookup"><span data-stu-id="e5793-187">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

<span data-ttu-id="e5793-188">Una vez que la imagen se encuentra en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e5793-188">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e5793-189">[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="e5793-189">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
