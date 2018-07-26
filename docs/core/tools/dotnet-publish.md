---
title: 'Comando dotnet publish: CLI de .NET Core'
description: El comando dotnet publish publica el proyecto de .NET Core en un directorio.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 38224aa8472f99df107e523667e18892384a20b0
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "39220677"
---
# <a name="dotnet-publish"></a><span data-ttu-id="d2270-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="d2270-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d2270-104">nombre</span><span class="sxs-lookup"><span data-stu-id="d2270-104">Name</span></span>

<span data-ttu-id="d2270-105">`dotnet publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="d2270-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2270-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d2270-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d2270-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d2270-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d2270-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d2270-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2270-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2270-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d2270-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2270-110">Description</span></span>

<span data-ttu-id="d2270-111">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="d2270-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="d2270-112">La salida incluye los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2270-112">The output includes the following assets:</span></span>

* <span data-ttu-id="d2270-113">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="d2270-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="d2270-114">Archivo *.deps.json* que incluye todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="d2270-115">Archivo *.runtime.config.json* en el que se especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="d2270-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="d2270-116">Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="d2270-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="d2270-117">La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2270-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="d2270-118">Es la única manera admitida oficialmente para preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="d2270-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="d2270-119">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d2270-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="d2270-120">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="d2270-121">Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](/aspnet/core/hosting/directory-structure) (Estructura de directorios).</span><span class="sxs-lookup"><span data-stu-id="d2270-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="d2270-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d2270-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d2270-123">El proyecto que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="d2270-123">The project to publish.</span></span> <span data-ttu-id="d2270-124">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="d2270-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d2270-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="d2270-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d2270-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d2270-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d2270-127">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="d2270-127">Defines the build configuration.</span></span> <span data-ttu-id="d2270-128">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2270-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d2270-129">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="d2270-130">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="d2270-131">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d2270-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d2270-132">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d2270-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d2270-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="d2270-134">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2270-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="d2270-135">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="d2270-136">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d2270-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="d2270-137">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="d2270-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="d2270-138">No compila el proyecto antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="d2270-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="d2270-139">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="d2270-139">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="d2270-140">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="d2270-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="d2270-141">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2270-142">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="d2270-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="d2270-143">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="d2270-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="d2270-144">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="d2270-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="d2270-145">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="d2270-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="d2270-146">Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d2270-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="d2270-147">Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d2270-148">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2270-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="d2270-149">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d2270-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="d2270-150">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d2270-151">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="d2270-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d2270-152">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2270-153">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2270-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="d2270-154">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d2270-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d2270-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d2270-156">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="d2270-156">Defines the build configuration.</span></span> <span data-ttu-id="d2270-157">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2270-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d2270-158">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="d2270-159">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="d2270-160">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d2270-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d2270-161">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d2270-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d2270-162">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="d2270-163">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2270-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="d2270-164">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="d2270-165">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d2270-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="d2270-166">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="d2270-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="d2270-167">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="d2270-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="d2270-168">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2270-169">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="d2270-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="d2270-170">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="d2270-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="d2270-171">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="d2270-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="d2270-172">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="d2270-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="d2270-173">Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d2270-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="d2270-174">Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d2270-175">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2270-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="d2270-176">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d2270-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="d2270-177">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d2270-178">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="d2270-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d2270-179">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2270-180">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2270-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="d2270-181">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2270-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2270-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d2270-183">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="d2270-183">Defines the build configuration.</span></span> <span data-ttu-id="d2270-184">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2270-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d2270-185">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="d2270-186">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="d2270-187">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="d2270-188">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d2270-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="d2270-189">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="d2270-190">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d2270-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="d2270-191">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="d2270-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2270-192">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="d2270-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="d2270-193">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="d2270-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="d2270-194">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="d2270-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d2270-195">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2270-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="d2270-196">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d2270-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="d2270-197">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d2270-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d2270-198">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="d2270-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d2270-199">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d2270-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2270-200">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2270-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="d2270-201">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2270-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d2270-202">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d2270-202">Examples</span></span>

<span data-ttu-id="d2270-203">Publica el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="d2270-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="d2270-204">Publicar la aplicación con el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="d2270-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="d2270-205">Publica el proyecto en el directorio actual mediante el marco de trabajo `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="d2270-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="d2270-206">Publica la aplicación actual mediante el marco de trabajo `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):</span><span class="sxs-lookup"><span data-stu-id="d2270-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="d2270-207">Publica la aplicación actual pero no restaura las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="d2270-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="d2270-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2270-208">See also</span></span>

* [<span data-ttu-id="d2270-209">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="d2270-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="d2270-210">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="d2270-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
