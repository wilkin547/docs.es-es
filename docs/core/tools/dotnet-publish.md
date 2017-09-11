---
title: 'Comando dotnet publish: CLI de .NET Core'
description: El comando dotnet publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: db6e527a6132be0b6362c68945bb68884f5ad619
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-publish"></a><span data-ttu-id="790d6-104">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="790d6-104">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="790d6-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="790d6-105">Name</span></span>

<span data-ttu-id="790d6-106">`dotnet publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="790d6-106">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="790d6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="790d6-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="790d6-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="790d6-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="790d6-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="790d6-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="790d6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="790d6-110">Description</span></span>

<span data-ttu-id="790d6-111">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="790d6-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="790d6-112">La salida contendrá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="790d6-112">The output will contain the following:</span></span>

* <span data-ttu-id="790d6-113">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="790d6-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="790d6-114">Archivo *.deps.json* que contiene todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="790d6-114">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="790d6-115">Archivo *.runtime.config.json* en el que se especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="790d6-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="790d6-116">Todas las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="790d6-116">The application's dependencies.</span></span> <span data-ttu-id="790d6-117">Estas se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="790d6-117">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="790d6-118">La salida del comando `dotnet publish` está preparada para la implementación de un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac o un equipo portátil) para la ejecución y es la única manera admitida oficialmente de preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="790d6-118">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="790d6-119">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="790d6-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="790d6-120">Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="790d6-121">Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](/aspnet/core/hosting/directory-structure) (Estructura de directorios).</span><span class="sxs-lookup"><span data-stu-id="790d6-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="790d6-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="790d6-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="790d6-123">El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica.</span><span class="sxs-lookup"><span data-stu-id="790d6-123">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="790d6-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="790d6-124">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="790d6-125">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="790d6-125">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="790d6-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="790d6-126">Defines the build configuration.</span></span> <span data-ttu-id="790d6-127">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="790d6-127">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="790d6-128">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="790d6-129">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="790d6-129">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="790d6-130">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="790d6-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="790d6-131">Esto es equivalente a eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="790d6-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="790d6-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="790d6-132">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="790d6-133">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="790d6-133">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="790d6-134">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-134">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="790d6-135">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="790d6-135">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="790d6-136">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="790d6-136">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="790d6-137">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="790d6-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="790d6-138">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="790d6-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="790d6-139">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="790d6-139">Specifies the path for the output directory.</span></span> <span data-ttu-id="790d6-140">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="790d6-140">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`--self-contained`

<span data-ttu-id="790d6-141">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="790d6-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="790d6-142">Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="790d6-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="790d6-143">Para obtener más información sobre los diferentes tipos de implementación, consulte [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-143">For more infomation about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="790d6-144">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="790d6-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="790d6-145">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="790d6-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="790d6-146">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="790d6-147">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="790d6-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="790d6-148">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="790d6-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="790d6-149">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="790d6-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="790d6-150">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="790d6-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="790d6-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="790d6-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="790d6-152">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="790d6-152">Defines the build configuration.</span></span> <span data-ttu-id="790d6-153">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="790d6-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="790d6-154">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="790d6-155">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="790d6-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="790d6-156">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="790d6-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="790d6-157">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="790d6-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="790d6-158">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="790d6-159">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="790d6-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="790d6-160">Esta opción está disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="790d6-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="790d6-161">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="790d6-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="790d6-162">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]* para una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="790d6-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="790d6-163">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="790d6-163">Publishes the application for a given runtime.</span></span> <span data-ttu-id="790d6-164">Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="790d6-164">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="790d6-165">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="790d6-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="790d6-166">El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="790d6-166">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="790d6-167">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="790d6-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="790d6-168">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="790d6-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="790d6-169">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="790d6-169">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="790d6-170">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="790d6-170">Examples</span></span>

<span data-ttu-id="790d6-171">Publica el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="790d6-171">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="790d6-172">Publicar la aplicación con el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="790d6-172">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="790d6-173">Publica el proyecto en el directorio actual mediante el marco de trabajo `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="790d6-173">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="790d6-174">Publica la aplicación actual mediante el marco de trabajo `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):</span><span class="sxs-lookup"><span data-stu-id="790d6-174">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="790d6-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="790d6-175">See also</span></span>

* [<span data-ttu-id="790d6-176">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="790d6-176">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="790d6-177">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="790d6-177">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

