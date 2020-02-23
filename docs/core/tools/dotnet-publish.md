---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto de .NET Core en un directorio.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451297"
---
# <a name="dotnet-publish"></a><span data-ttu-id="49003-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="49003-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="49003-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="49003-104">Name</span></span>

<span data-ttu-id="49003-105">`dotnet publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="49003-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="49003-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="49003-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="49003-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="49003-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="49003-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="49003-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="49003-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="49003-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="49003-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="49003-110">Description</span></span>

<span data-ttu-id="49003-111">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="49003-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="49003-112">La salida incluye los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="49003-112">The output includes the following assets:</span></span>

- <span data-ttu-id="49003-113">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="49003-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="49003-114">Archivo *.deps.json* que incluye todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="49003-115">Archivo *.runtime.config.json* en el que se especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="49003-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="49003-116">Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="49003-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="49003-117">La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="49003-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="49003-118">Es la única manera admitida oficialmente para preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="49003-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="49003-119">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49003-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="49003-120">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="49003-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="49003-121">Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](/aspnet/core/hosting/directory-structure) (Estructura de directorios).</span><span class="sxs-lookup"><span data-stu-id="49003-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="49003-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="49003-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="49003-123">El proyecto que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="49003-123">The project to publish.</span></span> <span data-ttu-id="49003-124">Es la ruta de acceso y el nombre de archivo de un archivo de proyecto [C#](csproj.md), F# o Visual Basic, o la ruta de acceso a un directorio que contiene un archivo de proyecto C#, F# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="49003-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="49003-125">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="49003-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="49003-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="49003-126">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="49003-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="49003-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="49003-128">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="49003-128">Defines the build configuration.</span></span> <span data-ttu-id="49003-129">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="49003-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="49003-130">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="49003-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="49003-131">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="49003-132">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="49003-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="49003-133">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="49003-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="49003-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="49003-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="49003-135">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49003-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="49003-136">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="49003-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="49003-137">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="49003-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="49003-138">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="49003-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="49003-139">No compila el proyecto antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="49003-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="49003-140">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="49003-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="49003-141">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="49003-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="49003-142">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="49003-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="49003-143">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="49003-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="49003-144">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="49003-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="49003-145">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="49003-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="49003-146">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="49003-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="49003-147">Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="49003-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="49003-148">Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="49003-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="49003-149">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49003-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="49003-150">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="49003-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="49003-151">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="49003-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="49003-152">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="49003-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="49003-153">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="49003-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="49003-154">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="49003-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="49003-155">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="49003-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="49003-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="49003-157">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="49003-157">Defines the build configuration.</span></span> <span data-ttu-id="49003-158">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="49003-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="49003-159">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="49003-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="49003-160">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="49003-161">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="49003-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="49003-162">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="49003-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="49003-163">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="49003-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="49003-164">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49003-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="49003-165">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="49003-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="49003-166">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="49003-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="49003-167">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="49003-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="49003-168">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="49003-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="49003-169">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="49003-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="49003-170">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="49003-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="49003-171">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="49003-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="49003-172">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="49003-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="49003-173">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="49003-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="49003-174">Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="49003-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="49003-175">Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="49003-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="49003-176">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49003-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="49003-177">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="49003-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="49003-178">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="49003-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="49003-179">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="49003-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="49003-180">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="49003-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="49003-181">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="49003-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="49003-182">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="49003-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="49003-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="49003-184">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="49003-184">Defines the build configuration.</span></span> <span data-ttu-id="49003-185">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="49003-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="49003-186">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="49003-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="49003-187">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="49003-188">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="49003-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="49003-189">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49003-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="49003-190">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="49003-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="49003-191">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="49003-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="49003-192">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="49003-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="49003-193">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="49003-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="49003-194">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="49003-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="49003-195">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="49003-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="49003-196">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49003-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="49003-197">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="49003-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="49003-198">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="49003-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="49003-199">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="49003-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="49003-200">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="49003-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="49003-201">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="49003-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="49003-202">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49003-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="49003-203">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="49003-203">Examples</span></span>

<span data-ttu-id="49003-204">Publica el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="49003-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="49003-205">Publicar la aplicación con el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="49003-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="49003-206">Publica el proyecto en el directorio actual mediante el marco de trabajo `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="49003-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="49003-207">Publica la aplicación actual mediante el marco de trabajo `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):</span><span class="sxs-lookup"><span data-stu-id="49003-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="49003-208">Publica la aplicación actual pero no restaura las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="49003-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="49003-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="49003-209">See also</span></span>

- [<span data-ttu-id="49003-210">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="49003-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="49003-211">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="49003-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
