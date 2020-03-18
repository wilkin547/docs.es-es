---
title: Docker - gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones gRPC de ASP.NET Core
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148119"
---
# <a name="create-docker-images"></a><span data-ttu-id="80b4d-103">Crear imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="80b4d-103">Create Docker images</span></span>

<span data-ttu-id="80b4d-104">En esta sección se describe la creación de imágenes de Docker para aplicaciones gRPC de ASP.NET Core, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="80b4d-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="80b4d-105">La aplicación de ejemplo utilizada, con una aplicación web ASP.NET Core MVC y un servicio gRPC, está disponible en el repositorio [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="80b4d-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="80b4d-106">Imágenes base de Microsoft para aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="80b4d-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="80b4d-107">Microsoft proporciona una gama de imágenes base para compilar y ejecutar aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="80b4d-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="80b4d-108">Para crear una imagen ASP.NET Core 3.0, utilice dos imágenes base:</span><span class="sxs-lookup"><span data-stu-id="80b4d-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="80b4d-109">Una imagen de SDK para compilar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="80b4d-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="80b4d-110">Una imagen en tiempo de ejecución para la implementación.</span><span class="sxs-lookup"><span data-stu-id="80b4d-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="80b4d-111">Imagen</span><span class="sxs-lookup"><span data-stu-id="80b4d-111">Image</span></span> | <span data-ttu-id="80b4d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b4d-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="80b4d-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="80b4d-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="80b4d-114">Para crear `docker build`aplicaciones con .</span><span class="sxs-lookup"><span data-stu-id="80b4d-114">For building applications with `docker build`.</span></span> <span data-ttu-id="80b4d-115">No se debe utilizar en producción.</span><span class="sxs-lookup"><span data-stu-id="80b4d-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="80b4d-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="80b4d-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="80b4d-117">Contiene el tiempo de ejecución y ASP.NET dependencias principales.</span><span class="sxs-lookup"><span data-stu-id="80b4d-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="80b4d-118">Para la producción.</span><span class="sxs-lookup"><span data-stu-id="80b4d-118">For production.</span></span> |

<span data-ttu-id="80b4d-119">Para cada imagen, hay cuatro variantes basadas en diferentes distribuciones de Linux, distinguidas por etiquetas.</span><span class="sxs-lookup"><span data-stu-id="80b4d-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="80b4d-120">Etiqueta(s) de imagen (s)</span><span class="sxs-lookup"><span data-stu-id="80b4d-120">Image tag(s)</span></span> | <span data-ttu-id="80b4d-121">Linux</span><span class="sxs-lookup"><span data-stu-id="80b4d-121">Linux</span></span> | <span data-ttu-id="80b4d-122">Notas</span><span class="sxs-lookup"><span data-stu-id="80b4d-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="80b4d-123">3.0-buster, 3.0</span><span class="sxs-lookup"><span data-stu-id="80b4d-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="80b4d-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="80b4d-124">Debian 10</span></span> | <span data-ttu-id="80b4d-125">La imagen predeterminada si no se especifica ninguna variante del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="80b4d-126">3.0-alpino</span><span class="sxs-lookup"><span data-stu-id="80b4d-126">3.0-alpine</span></span> | <span data-ttu-id="80b4d-127">Alpine 3.9</span><span class="sxs-lookup"><span data-stu-id="80b4d-127">Alpine 3.9</span></span> | <span data-ttu-id="80b4d-128">Las imágenes base alpinas son mucho más pequeñas que las de Debian o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="80b4d-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="80b4d-129">3.0-disco</span><span class="sxs-lookup"><span data-stu-id="80b4d-129">3.0-disco</span></span> | <span data-ttu-id="80b4d-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="80b4d-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="80b4d-131">3.0-biónico</span><span class="sxs-lookup"><span data-stu-id="80b4d-131">3.0-bionic</span></span> | <span data-ttu-id="80b4d-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="80b4d-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="80b4d-133">La imagen base Alpine es de alrededor de 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="80b4d-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="80b4d-134">Algunos paquetes de software o bibliotecas podrían no estar disponibles en la gestión de paquetes de Alpine.</span><span class="sxs-lookup"><span data-stu-id="80b4d-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="80b4d-135">Si no está seguro de qué imagen utilizar, probablemente debería elegir el Debian predeterminado.</span><span class="sxs-lookup"><span data-stu-id="80b4d-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80b4d-136">Asegúrese de utilizar la misma variante de Linux para la compilación y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80b4d-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="80b4d-137">Es posible que las aplicaciones creadas y publicadas en una variante no funcionen en otra.</span><span class="sxs-lookup"><span data-stu-id="80b4d-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="80b4d-138">Cree una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="80b4d-138">Create a Docker image</span></span>

<span data-ttu-id="80b4d-139">Una imagen de Docker se define mediante un *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="80b4d-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="80b4d-140">Se trata de un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="80b4d-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="80b4d-141">En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="80b4d-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="80b4d-142">El Dockerfile tiene dos partes: `sdk` la primera utiliza la imagen base para compilar y publicar la aplicación; el segundo crea una `aspnet` imagen en tiempo de ejecución desde la base.</span><span class="sxs-lookup"><span data-stu-id="80b4d-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="80b4d-143">Esto se `sdk` debe a que la imagen es de alrededor de 900 MB, en comparación con alrededor de 200 MB para la imagen en tiempo de ejecución, y la mayoría de su contenido es innecesario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80b4d-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="80b4d-144">Los pasos de construcción</span><span class="sxs-lookup"><span data-stu-id="80b4d-144">The build steps</span></span>

| <span data-ttu-id="80b4d-145">Paso</span><span class="sxs-lookup"><span data-stu-id="80b4d-145">Step</span></span> | <span data-ttu-id="80b4d-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b4d-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="80b4d-147">Declara la imagen base y `builder` asigna el alias.</span><span class="sxs-lookup"><span data-stu-id="80b4d-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="80b4d-148">Crea `/src` el directorio y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="80b4d-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="80b4d-149">Copia todo debajo del directorio actual en el host en el directorio actual de la imagen.</span><span class="sxs-lookup"><span data-stu-id="80b4d-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="80b4d-150">Restaura los paquetes externos (ASP.NET Framework Core 3.0 está preinstalado con el SDK).</span><span class="sxs-lookup"><span data-stu-id="80b4d-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="80b4d-151">Compila y publica una versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="80b4d-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="80b4d-152">Tenga en `--runtime` cuenta que la marca no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="80b4d-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="80b4d-153">Los pasos de la imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="80b4d-153">The runtime image steps</span></span>

| <span data-ttu-id="80b4d-154">Paso</span><span class="sxs-lookup"><span data-stu-id="80b4d-154">Step</span></span> | <span data-ttu-id="80b4d-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b4d-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="80b4d-156">Declara una nueva imagen base.</span><span class="sxs-lookup"><span data-stu-id="80b4d-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="80b4d-157">Crea `/app` el directorio y lo establece como el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="80b4d-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="80b4d-158">Copia la aplicación publicada de la imagen `builder` anterior, `FROM` utilizando el alias de la primera línea.</span><span class="sxs-lookup"><span data-stu-id="80b4d-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="80b4d-159">Establece el comando que se ejecutará cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="80b4d-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="80b4d-160">El `dotnet` comando de la imagen en tiempo de ejecución solo puede ejecutar archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="80b4d-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="80b4d-161">HTTPS en Docker</span><span class="sxs-lookup"><span data-stu-id="80b4d-161">HTTPS in Docker</span></span>

<span data-ttu-id="80b4d-162">Las imágenes base `ASPNETCORE_URLS` de `http://+:80`Microsoft para Docker establecen la variable de entorno en , lo que significa que Kestrel se ejecuta sin HTTPS en ese puerto.</span><span class="sxs-lookup"><span data-stu-id="80b4d-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="80b4d-163">Si usa HTTPS con un certificado personalizado (como se describe en [Aplicaciones gRPC autohospedadas),](self-hosted.md)debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="80b4d-164">Establezca la variable de entorno en la parte de creación de imágenes en tiempo de ejecución del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="80b4d-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="80b4d-165">El archivo .dockerignore</span><span class="sxs-lookup"><span data-stu-id="80b4d-165">The .dockerignore file</span></span>

<span data-ttu-id="80b4d-166">Al `.gitignore` igual que los archivos que excluyen determinados archivos y directorios del control de código fuente, el `.dockerignore` archivo se puede utilizar para excluir archivos y directorios de ser copiados en la imagen durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="80b4d-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="80b4d-167">Esto no sólo ahorra tiempo copiando, sino que también `obj` puede evitar algunos errores que surgen de tener el directorio de su PC copiado en la imagen.</span><span class="sxs-lookup"><span data-stu-id="80b4d-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="80b4d-168">Como mínimo, debe agregar entradas `bin` `obj` para `.dockerignore` y a su archivo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="80b4d-169">Compilación de la imagen</span><span class="sxs-lookup"><span data-stu-id="80b4d-169">Build the image</span></span>

<span data-ttu-id="80b4d-170">Para una solución con una sola aplicación y, por lo tanto, un solo Dockerfile, es más sencillo colocar el Dockerfile en el directorio base.</span><span class="sxs-lookup"><span data-stu-id="80b4d-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="80b4d-171">En otras palabras, colóquelo `.sln` en el mismo directorio que el archivo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="80b4d-172">En ese caso, para compilar la `docker build` imagen, utilice el siguiente comando desde el directorio que contiene El Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="80b4d-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="80b4d-173">La marca `--tag` con nombre confuso (que `-t`se puede acortar a ) especifica el nombre completo de la imagen, incluida la etiqueta real si se especifica.</span><span class="sxs-lookup"><span data-stu-id="80b4d-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="80b4d-174">El `.` final especifica el contexto en el que se ejecutará la compilación; el directorio de `COPY` trabajo actual para los comandos en el Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="80b4d-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="80b4d-175">Si tiene varias aplicaciones dentro de una única solución, puede mantener el `.csproj` Dockerfile para cada aplicación en su propia carpeta, junto al archivo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="80b4d-176">Debe ejecutar el `docker build` comando desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen.</span><span class="sxs-lookup"><span data-stu-id="80b4d-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="80b4d-177">Puede especificar un Dockerfile debajo del `--file` directorio `-f`actual mediante el indicador (o ).</span><span class="sxs-lookup"><span data-stu-id="80b4d-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="80b4d-178">Ejecute la imagen en un contenedor de su máquina</span><span class="sxs-lookup"><span data-stu-id="80b4d-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="80b4d-179">Para ejecutar la imagen en la `docker run` instancia de Docker local, utilice el comando.</span><span class="sxs-lookup"><span data-stu-id="80b4d-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="80b4d-180">El `-ti` indicador conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="80b4d-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="80b4d-181">Publica `-p 5000:80` (enlaces) el puerto 80 en el contenedor al puerto 5000 en la interfaz de red localhost.</span><span class="sxs-lookup"><span data-stu-id="80b4d-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="80b4d-182">Inserte la imagen en un registro</span><span class="sxs-lookup"><span data-stu-id="80b4d-182">Push the image to a registry</span></span>

<span data-ttu-id="80b4d-183">Después de comprobar que la imagen funciona, insóquela en un registro de Docker para que esté disponible en otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="80b4d-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="80b4d-184">Las redes internas tendrán que aprovisionar un registro de Docker.</span><span class="sxs-lookup"><span data-stu-id="80b4d-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="80b4d-185">Esto puede ser tan simple como ejecutar la [propia `registry` imagen de Docker](https://docs.docker.com/registry/deploying/) (el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles.</span><span class="sxs-lookup"><span data-stu-id="80b4d-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="80b4d-186">Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) o Docker [Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="80b4d-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="80b4d-187">Para insertar en Docker Hub, prefije el nombre de la imagen con el nombre de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="80b4d-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="80b4d-188">Para insertar en un registro privado, prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.</span><span class="sxs-lookup"><span data-stu-id="80b4d-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="80b4d-189">Una vez que la imagen está en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="80b4d-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="80b4d-190">[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="80b4d-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
