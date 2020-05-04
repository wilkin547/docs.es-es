---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto o la solución de .NET Core en un directorio.
ms.date: 02/24/2020
ms.openlocfilehash: 78ed8098be1b6887fc6a2a647fd169e2bf7f7fd1
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102806"
---
# <a name="dotnet-publish"></a><span data-ttu-id="3790b-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="3790b-103">dotnet publish</span></span>

<span data-ttu-id="3790b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3790b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3790b-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3790b-105">Name</span></span>

<span data-ttu-id="3790b-106">`dotnet publish`: publica la aplicación y sus dependencias en una carpeta para la implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="3790b-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3790b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3790b-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a><span data-ttu-id="3790b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3790b-108">Description</span></span>

<span data-ttu-id="3790b-109">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="3790b-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="3790b-110">La salida incluye los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3790b-110">The output includes the following assets:</span></span>

- <span data-ttu-id="3790b-111">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="3790b-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="3790b-112">Un archivo *.deps.json* que incluye todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="3790b-113">Un archivo *.runtime.config.json* en el que se especifica el tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="3790b-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="3790b-114">Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="3790b-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="3790b-115">La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3790b-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="3790b-116">Es la única manera admitida oficialmente para preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="3790b-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="3790b-117">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3790b-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="3790b-118">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="3790b-119">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="3790b-119">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a><span data-ttu-id="3790b-120">MSBuild</span><span class="sxs-lookup"><span data-stu-id="3790b-120">MSBuild</span></span>

<span data-ttu-id="3790b-121">Con el comando `dotnet publish` se llama a MSBuild, lo que invoca el destino `Publish`.</span><span class="sxs-lookup"><span data-stu-id="3790b-121">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="3790b-122">Todos los parámetros pasados a `dotnet publish` se pasan a MSBuild.</span><span class="sxs-lookup"><span data-stu-id="3790b-122">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="3790b-123">Los parámetros `-c` y `-o` se asignan respectivamente a las propiedades `Configuration` y `OutputPath` de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="3790b-123">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `OutputPath` properties, respectively.</span></span>

<span data-ttu-id="3790b-124">El comando `dotnet publish` acepta opciones de MSBuild, como `-p` para establecer propiedades y `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="3790b-124">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="3790b-125">Por ejemplo, se puede establecer una propiedad de MSBuild mediante el uso del formato: `-p:<NAME>=<VALUE>`.</span><span class="sxs-lookup"><span data-stu-id="3790b-125">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="3790b-126">También se pueden establecer las propiedades relacionadas con la publicación si se hace referencia a un archivo *.pubxml*, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3790b-126">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="3790b-127">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="3790b-127">For more information, see the following resources:</span></span>

- [<span data-ttu-id="3790b-128">Referencia de la línea de comandos de MSBuild</span><span class="sxs-lookup"><span data-stu-id="3790b-128">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="3790b-129">Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3790b-129">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="3790b-130">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3790b-130">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="3790b-131">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3790b-131">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="3790b-132">El archivo de proyecto o solución que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="3790b-132">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="3790b-133">`PROJECT` es la ruta de acceso y el nombre de archivo de un archivo de proyecto de [C#](csproj.md), F# o Visual Basic, o bien la ruta de acceso a un directorio que contiene un archivo de proyecto de C#, F# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3790b-133">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="3790b-134">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="3790b-134">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="3790b-135">`SOLUTION` es la ruta de acceso y el nombre de archivo de un archivo de solución (extensión *.sln*), o bien la ruta de acceso a un directorio que contiene un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="3790b-135">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="3790b-136">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="3790b-136">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="3790b-137">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-137">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="3790b-138">Opciones</span><span class="sxs-lookup"><span data-stu-id="3790b-138">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="3790b-139">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="3790b-139">Defines the build configuration.</span></span> <span data-ttu-id="3790b-140">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-140">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3790b-141">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-141">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="3790b-142">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-142">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="3790b-143">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3790b-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="3790b-144">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="3790b-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3790b-145">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3790b-145">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="3790b-146">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="3790b-146">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="3790b-147">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3790b-147">For example, to complete authentication.</span></span> <span data-ttu-id="3790b-148">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-148">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="3790b-149">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3790b-149">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="3790b-150">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-150">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="3790b-151">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="3790b-151">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="3790b-152">No compila el proyecto antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="3790b-152">Doesn't build the project before publishing.</span></span> <span data-ttu-id="3790b-153">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="3790b-153">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="3790b-154">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="3790b-154">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="3790b-155">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="3790b-155">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="3790b-156">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-156">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3790b-157">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="3790b-157">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3790b-158">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="3790b-158">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="3790b-159">Si no se especifica, el valor predeterminado es *[project_file_folder]./bin/[configuration]/[framework]/publish/* para un archivo ejecutable dependiente del tiempo de ejecución y archivos binarios multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="3790b-159">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="3790b-160">El valor predeterminado es *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* para un archivo ejecutable autocontenido.</span><span class="sxs-lookup"><span data-stu-id="3790b-160">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="3790b-161">En un proyecto web, si la carpeta de salida se encuentra en la carpeta del proyecto, los comandos `dotnet publish` posteriores dan como resultado carpetas de salida anidadas.</span><span class="sxs-lookup"><span data-stu-id="3790b-161">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="3790b-162">Por ejemplo, si la carpeta del proyecto es *myproject* y la carpeta de salida de la publicación es *myproject/publish*, y ejecuta `dotnet publish` dos veces, la segunda ejecución coloca los archivos de contenido, como *.config* y *.json*, en *myproject/publish/publish*.</span><span class="sxs-lookup"><span data-stu-id="3790b-162">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="3790b-163">Para evitar el anidamiento de carpetas de publicación, especifique una que no esté directamente en la carpeta del proyecto, o bien excluya la carpeta de publicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-163">To avoid nesting publish folders, specify a publish folder that is not directly under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="3790b-164">Para excluir una carpeta de publicación denominada *publishoutput*, agregue el elemento siguiente a un elemento `PropertyGroup` en el archivo *.csproj*:</span><span class="sxs-lookup"><span data-stu-id="3790b-164">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="3790b-165">SDK de .NET Core 3.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3790b-165">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="3790b-166">Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo al directorio de trabajo actual, no a la ubicación del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-166">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="3790b-167">Si se especifica una ruta de acceso relativa al publicar una solución, todas las salidas de todos los proyectos van en la carpeta especificada relativa al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="3790b-167">If a relative path is specified when publishing a solution, all output for all projects goes into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="3790b-168">A fin de que la salida de la publicación vaya a carpetas independientes para cada proyecto, especifique una ruta de acceso relativa mediante el uso de la propiedad `PublishDir` de MSBuild en lugar de la opción `--output`.</span><span class="sxs-lookup"><span data-stu-id="3790b-168">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="3790b-169">Por ejemplo, `dotnet publish -p:PublishDir=.\publish` envía la salida de publicación de cada proyecto a una carpeta `publish` en la carpeta que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-169">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="3790b-170">SDK de .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3790b-170">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="3790b-171">Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo a la ubicación del archivo del proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="3790b-171">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="3790b-172">Si se especifica una ruta de acceso relativa al publicar una solución, la salida de cada proyecto va a una carpeta independiente relativa a la ubicación del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-172">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="3790b-173">Si se especifica una ruta de acceso absoluta al publicar una solución, la salida de las publicaciones de todos los proyectos van a la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="3790b-173">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun=true`**

  <span data-ttu-id="3790b-174">Compila los ensamblados de aplicación con el formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="3790b-174">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="3790b-175">R2R es una forma de compilación Ahead Of Time (AOT).</span><span class="sxs-lookup"><span data-stu-id="3790b-175">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="3790b-176">Para obtener más información, vea [Imágenes ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="3790b-176">For more information, see [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span> <span data-ttu-id="3790b-177">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-177">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3790b-178">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3790b-178">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="3790b-179">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="3790b-179">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile=true`**

  <span data-ttu-id="3790b-180">Empaqueta la aplicación en un ejecutable de archivo único específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="3790b-180">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="3790b-181">El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3790b-181">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="3790b-182">Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación.</span><span class="sxs-lookup"><span data-stu-id="3790b-182">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="3790b-183">El inicio es más rápido cuando se vuelve a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3790b-183">Startup is faster when the application is run again.</span></span> <span data-ttu-id="3790b-184">No es necesario extraer la aplicación por segunda vez a menos que se haya usado una versión nueva.</span><span class="sxs-lookup"><span data-stu-id="3790b-184">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="3790b-185">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-185">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3790b-186">Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-186">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="3790b-187">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3790b-187">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="3790b-188">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="3790b-188">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed=true`**

  <span data-ttu-id="3790b-189">Recorta las bibliotecas no utilizadas para reducir el tamaño de implementación de una aplicación cuando se publica un ejecutable independiente.</span><span class="sxs-lookup"><span data-stu-id="3790b-189">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="3790b-190">Para obtener más información, vea [Recorte de implementaciones autocontenidas y ejecutables](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-190">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="3790b-191">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-191">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3790b-192">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3790b-192">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="3790b-193">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="3790b-193">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="3790b-194">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="3790b-194">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="3790b-195">El valor predeterminado es `true` si se especifica un identificador en tiempo de ejecución y el proyecto es de tipo ejecutable (no un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="3790b-195">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="3790b-196">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-196">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="3790b-197">Si se usa esta opción sin especificar `true` o `false`, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="3790b-197">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="3790b-198">En ese caso, no coloque el argumento de la solución o el proyecto inmediatamente después de `--self-contained`, porque se espera que `true` o `false` estén en esa posición.</span><span class="sxs-lookup"><span data-stu-id="3790b-198">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="3790b-199">Equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="3790b-199">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="3790b-200">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3790b-200">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="3790b-201">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3790b-201">Publishes the application for a given runtime.</span></span> <span data-ttu-id="3790b-202">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-202">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="3790b-203">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="3790b-203">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3790b-204">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="3790b-204">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3790b-205">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3790b-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3790b-206">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="3790b-206">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="3790b-207">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-207">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="3790b-208">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3790b-208">Examples</span></span>

- <span data-ttu-id="3790b-209">Cree un [archivo binario multiplataforma dependiente del tiempo de ejecución ](../deploying/index.md#produce-a-cross-platform-binary) para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="3790b-209">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="3790b-210">A partir del SDK de .NET Core 3.0, en este ejemplo también se crea un [ ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="3790b-210">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="3790b-211">Cree un [ejecutable independiente](../deploying/index.md#publish-self-contained) para el proyecto en el directorio actual, para un tiempo de ejecución específico:</span><span class="sxs-lookup"><span data-stu-id="3790b-211">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="3790b-212">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-212">The RID must be in the project file.</span></span>

- <span data-ttu-id="3790b-213">Cree un [ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para el proyecto en el directorio actual, para una plataforma específica:</span><span class="sxs-lookup"><span data-stu-id="3790b-213">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="3790b-214">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3790b-214">The RID must be in the project file.</span></span> <span data-ttu-id="3790b-215">Este ejemplo se aplica al SDK de .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3790b-215">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="3790b-216">Publique el proyecto en el directorio actual, para un tiempo de ejecución específico y una plataforma de destino:</span><span class="sxs-lookup"><span data-stu-id="3790b-216">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="3790b-217">Publique el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="3790b-217">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="3790b-218">Publique la aplicación actual pero sin restaurar las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración:</span><span class="sxs-lookup"><span data-stu-id="3790b-218">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="3790b-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="3790b-219">See also</span></span>

- [<span data-ttu-id="3790b-220">Información general sobre la publicación de aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3790b-220">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="3790b-221">Publicación de aplicaciones .NET Core con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3790b-221">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="3790b-222">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="3790b-222">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="3790b-223">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="3790b-223">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="3790b-224">Trabajo con la certificación de macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="3790b-224">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="3790b-225">Estructura de directorios de una aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="3790b-225">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="3790b-226">Referencia de la línea de comandos de MSBuild</span><span class="sxs-lookup"><span data-stu-id="3790b-226">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="3790b-227">Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3790b-227">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="3790b-228">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3790b-228">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="3790b-229">ILLInk.Tasks</span><span class="sxs-lookup"><span data-stu-id="3790b-229">ILLInk.Tasks</span></span>](https://aka.ms/dotnet-illink)
