---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto o la solución de .NET Core en un directorio.
ms.date: 02/24/2020
ms.openlocfilehash: 45bf8504fd882286041794d27ecb56464fc8d13d
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656670"
---
# <a name="dotnet-publish"></a><span data-ttu-id="f66c6-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f66c6-103">dotnet publish</span></span>

<span data-ttu-id="f66c6-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f66c6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f66c6-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f66c6-105">Name</span></span>

<span data-ttu-id="f66c6-106">`dotnet publish`: publica la aplicación y sus dependencias en una carpeta para la implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f66c6-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f66c6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f66c6-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="f66c6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f66c6-108">Description</span></span>

<span data-ttu-id="f66c6-109">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="f66c6-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="f66c6-110">La salida incluye los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f66c6-110">The output includes the following assets:</span></span>

- <span data-ttu-id="f66c6-111">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="f66c6-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="f66c6-112">Un archivo *.deps.json* que incluye todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="f66c6-113">Un archivo *.runtime.config.json* en el que se especifica el tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="f66c6-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="f66c6-114">Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="f66c6-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="f66c6-115">La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f66c6-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="f66c6-116">Es la única manera admitida oficialmente para preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="f66c6-117">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f66c6-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="f66c6-118">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="f66c6-119">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="f66c6-119">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a><span data-ttu-id="f66c6-120">MSBuild</span><span class="sxs-lookup"><span data-stu-id="f66c6-120">MSBuild</span></span>

<span data-ttu-id="f66c6-121">Con el comando `dotnet publish` se llama a MSBuild, lo que invoca el destino `Publish`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-121">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="f66c6-122">Todos los parámetros pasados a `dotnet publish` se pasan a MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f66c6-122">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="f66c6-123">Los parámetros `-c` y `-o` se asignan respectivamente a las propiedades `Configuration` y `PublishDir` de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f66c6-123">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `PublishDir` properties, respectively.</span></span>

<span data-ttu-id="f66c6-124">El comando `dotnet publish` acepta opciones de MSBuild, como `-p` para establecer propiedades y `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="f66c6-124">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="f66c6-125">Por ejemplo, se puede establecer una propiedad de MSBuild mediante el uso del formato: `-p:<NAME>=<VALUE>`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-125">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span>

<span data-ttu-id="f66c6-126">También se pueden establecer las propiedades relacionadas con la publicación si se hace referencia a un archivo *.pubxml* (disponible a partir del SDK de .NET Core 3.1).</span><span class="sxs-lookup"><span data-stu-id="f66c6-126">You can also set publish-related properties by referring to a *.pubxml* file (available since .NET Core 3.1 SDK).</span></span> <span data-ttu-id="f66c6-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f66c6-127">For example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=FolderProfile
```

<span data-ttu-id="f66c6-128">En el ejemplo anterior se usa el archivo *FolderProfile.pubxml* que se encuentra en la carpeta *\<project_folder>/Properties/PublishProfiles*.</span><span class="sxs-lookup"><span data-stu-id="f66c6-128">The preceding example uses the *FolderProfile.pubxml* file that is found in the *\<project_folder>/Properties/PublishProfiles* folder.</span></span> <span data-ttu-id="f66c6-129">Si especifica una ruta de acceso y una extensión de archivo al establecer la propiedad `PublishProfile`, estas se omiten.</span><span class="sxs-lookup"><span data-stu-id="f66c6-129">If you specify a path and file extension when setting the `PublishProfile` property, they are ignored.</span></span> <span data-ttu-id="f66c6-130">De forma predeterminada, MSBuild busca en la carpeta *Properties/PublishProfiles* y da por hecho la extensión de archivo *pubxml*.</span><span class="sxs-lookup"><span data-stu-id="f66c6-130">MSBuild by default looks in the *Properties/PublishProfiles* folder and assumes the *pubxml* file extension.</span></span> <span data-ttu-id="f66c6-131">Para especificar la ruta de acceso y el nombre de archivo, incluida la extensión, establezca la propiedad `PublishProfileFullPath` en lugar de la propiedad `PublishProfile`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-131">To specify the path and filename including extension, set the `PublishProfileFullPath` property instead of the `PublishProfile` property.</span></span>

<span data-ttu-id="f66c6-132">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="f66c6-132">For more information, see the following resources:</span></span>

- [<span data-ttu-id="f66c6-133">Referencia de la línea de comandos de MSBuild</span><span class="sxs-lookup"><span data-stu-id="f66c6-133">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="f66c6-134">Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f66c6-134">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="f66c6-135">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f66c6-135">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="f66c6-136">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f66c6-136">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="f66c6-137">El archivo de proyecto o solución que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="f66c6-137">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="f66c6-138">`PROJECT` es la ruta de acceso y el nombre de archivo de un archivo de proyecto de [C#](csproj.md), F# o Visual Basic, o bien la ruta de acceso a un directorio que contiene un archivo de proyecto de C#, F# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f66c6-138">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="f66c6-139">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="f66c6-139">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="f66c6-140">`SOLUTION` es la ruta de acceso y el nombre de archivo de un archivo de solución (extensión *.sln*), o bien la ruta de acceso a un directorio que contiene un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f66c6-140">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="f66c6-141">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="f66c6-141">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="f66c6-142">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-142">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="f66c6-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="f66c6-143">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="f66c6-144">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-144">Defines the build configuration.</span></span> <span data-ttu-id="f66c6-145">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-145">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f66c6-146">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-146">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f66c6-147">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-147">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="f66c6-148">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f66c6-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="f66c6-149">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="f66c6-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f66c6-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f66c6-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="f66c6-151">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f66c6-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="f66c6-152">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-152">For example, to complete authentication.</span></span> <span data-ttu-id="f66c6-153">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-153">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="f66c6-154">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-154">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="f66c6-155">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-155">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="f66c6-156">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-156">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="f66c6-157">No compila el proyecto antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="f66c6-157">Doesn't build the project before publishing.</span></span> <span data-ttu-id="f66c6-158">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="f66c6-158">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="f66c6-159">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="f66c6-159">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="f66c6-160">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="f66c6-160">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="f66c6-161">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-161">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="f66c6-162">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f66c6-162">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f66c6-163">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="f66c6-163">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="f66c6-164">Si no se especifica, el valor predeterminado es *[project_file_folder]./bin/[configuration]/[framework]/publish/* para un archivo ejecutable dependiente del marco y archivos binarios multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="f66c6-164">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a framework-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="f66c6-165">El valor predeterminado es *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* para un archivo ejecutable autocontenido.</span><span class="sxs-lookup"><span data-stu-id="f66c6-165">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="f66c6-166">En un proyecto web, si la carpeta de salida se encuentra en la carpeta del proyecto, los comandos `dotnet publish` posteriores dan como resultado carpetas de salida anidadas.</span><span class="sxs-lookup"><span data-stu-id="f66c6-166">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="f66c6-167">Por ejemplo, si la carpeta del proyecto es *myproject* y la carpeta de salida de la publicación es *myproject/publish*, y ejecuta `dotnet publish` dos veces, la segunda ejecución coloca los archivos de contenido, como *.config* y *.json*, en *myproject/publish/publish*.</span><span class="sxs-lookup"><span data-stu-id="f66c6-167">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="f66c6-168">Para evitar el anidamiento de carpetas de publicación, especifique una que no esté **directamente** en la carpeta del proyecto, o bien excluya la carpeta de publicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-168">To avoid nesting publish folders, specify a publish folder that is not **directly** under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="f66c6-169">Para excluir una carpeta de publicación denominada *publishoutput*, agregue el elemento siguiente a un elemento `PropertyGroup` en el archivo *.csproj*:</span><span class="sxs-lookup"><span data-stu-id="f66c6-169">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="f66c6-170">SDK de .NET Core 3.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f66c6-170">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="f66c6-171">Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo al directorio de trabajo actual, no a la ubicación del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-171">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="f66c6-172">Si se especifica una ruta de acceso relativa al publicar una solución, todas las salidas de todos los proyectos van en la carpeta especificada relativa al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="f66c6-172">If a relative path is specified when publishing a solution, all output for all projects goes into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="f66c6-173">A fin de que la salida de la publicación vaya a carpetas independientes para cada proyecto, especifique una ruta de acceso relativa mediante el uso de la propiedad `PublishDir` de MSBuild en lugar de la opción `--output`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-173">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="f66c6-174">Por ejemplo, `dotnet publish -p:PublishDir=.\publish` envía la salida de publicación de cada proyecto a una carpeta `publish` en la carpeta que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-174">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="f66c6-175">SDK de .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f66c6-175">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="f66c6-176">Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo a la ubicación del archivo del proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="f66c6-176">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="f66c6-177">Si se especifica una ruta de acceso relativa al publicar una solución, la salida de cada proyecto va a una carpeta independiente relativa a la ubicación del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-177">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="f66c6-178">Si se especifica una ruta de acceso absoluta al publicar una solución, la salida de las publicaciones de todos los proyectos van a la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="f66c6-178">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun=true`**

  <span data-ttu-id="f66c6-179">Compila los ensamblados de aplicación con el formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="f66c6-179">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="f66c6-180">R2R es una forma de compilación Ahead Of Time (AOT).</span><span class="sxs-lookup"><span data-stu-id="f66c6-180">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="f66c6-181">Para obtener más información, vea [Imágenes ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="f66c6-181">For more information, see [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span> <span data-ttu-id="f66c6-182">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-182">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="f66c6-183">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f66c6-183">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="f66c6-184">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="f66c6-184">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile=true`**

  <span data-ttu-id="f66c6-185">Empaqueta la aplicación en un ejecutable de archivo único específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="f66c6-185">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="f66c6-186">El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-186">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="f66c6-187">Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-187">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="f66c6-188">El inicio es más rápido cuando se vuelve a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f66c6-188">Startup is faster when the application is run again.</span></span> <span data-ttu-id="f66c6-189">No es necesario extraer la aplicación por segunda vez a menos que se haya usado una versión nueva.</span><span class="sxs-lookup"><span data-stu-id="f66c6-189">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="f66c6-190">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-190">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="f66c6-191">Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-191">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="f66c6-192">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f66c6-192">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="f66c6-193">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="f66c6-193">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed=true`**

  <span data-ttu-id="f66c6-194">Recorta las bibliotecas no utilizadas para reducir el tamaño de implementación de una aplicación cuando se publica un ejecutable independiente.</span><span class="sxs-lookup"><span data-stu-id="f66c6-194">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="f66c6-195">Para obtener más información, vea [Recorte de implementaciones autocontenidas y ejecutables](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-195">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="f66c6-196">Disponible a partir del SDK de .NET Core 3.0 como una característica en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="f66c6-196">Available since .NET Core 3.0 SDK as a preview feature.</span></span>

  <span data-ttu-id="f66c6-197">Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f66c6-197">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="f66c6-198">Para obtener más información, vea [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="f66c6-198">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="f66c6-199">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="f66c6-199">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="f66c6-200">El valor predeterminado es `true` si se especifica un identificador en tiempo de ejecución y el proyecto es de tipo ejecutable (no un proyecto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="f66c6-200">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="f66c6-201">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-201">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="f66c6-202">Si se usa esta opción sin especificar `true` o `false`, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-202">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="f66c6-203">En ese caso, no coloque el argumento de la solución o el proyecto inmediatamente después de `--self-contained`, porque se espera que `true` o `false` estén en esa posición.</span><span class="sxs-lookup"><span data-stu-id="f66c6-203">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="f66c6-204">Equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-204">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="f66c6-205">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f66c6-205">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f66c6-206">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f66c6-206">Publishes the application for a given runtime.</span></span> <span data-ttu-id="f66c6-207">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-207">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="f66c6-208">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f66c6-208">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f66c6-209">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f66c6-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f66c6-210">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f66c6-211">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="f66c6-211">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="f66c6-212">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-212">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="f66c6-213">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f66c6-213">Examples</span></span>

- <span data-ttu-id="f66c6-214">Cree un [archivo binario multiplataforma dependiente del marco](../deploying/index.md#produce-a-cross-platform-binary) para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="f66c6-214">Create a [framework-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="f66c6-215">A partir del SDK de .NET Core 3.0, en este ejemplo también se crea un [ejecutable dependiente del marco](../deploying/index.md#publish-framework-dependent) para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="f66c6-215">Starting with .NET Core 3.0 SDK, this example also creates a [framework-dependent executable](../deploying/index.md#publish-framework-dependent) for the current platform.</span></span>

- <span data-ttu-id="f66c6-216">Cree un [ejecutable independiente](../deploying/index.md#publish-self-contained) para el proyecto en el directorio actual, para un tiempo de ejecución específico:</span><span class="sxs-lookup"><span data-stu-id="f66c6-216">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="f66c6-217">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-217">The RID must be in the project file.</span></span>

- <span data-ttu-id="f66c6-218">Cree un [ejecutable dependiente del marco](../deploying/index.md#publish-framework-dependent) para el proyecto en el directorio actual, para una plataforma específica:</span><span class="sxs-lookup"><span data-stu-id="f66c6-218">Create a [framework-dependent executable](../deploying/index.md#publish-framework-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="f66c6-219">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f66c6-219">The RID must be in the project file.</span></span> <span data-ttu-id="f66c6-220">Este ejemplo se aplica al SDK de .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f66c6-220">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="f66c6-221">Publique el proyecto en el directorio actual, para un tiempo de ejecución específico y una plataforma de destino:</span><span class="sxs-lookup"><span data-stu-id="f66c6-221">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="f66c6-222">Publique el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="f66c6-222">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="f66c6-223">Publique la aplicación actual pero sin restaurar las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración:</span><span class="sxs-lookup"><span data-stu-id="f66c6-223">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="f66c6-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="f66c6-224">See also</span></span>

- [<span data-ttu-id="f66c6-225">Información general sobre la publicación de aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f66c6-225">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="f66c6-226">Publicación de aplicaciones .NET Core con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f66c6-226">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="f66c6-227">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="f66c6-227">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="f66c6-228">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="f66c6-228">Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="f66c6-229">Trabajo con la certificación de macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="f66c6-229">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="f66c6-230">Estructura de directorios de una aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="f66c6-230">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="f66c6-231">Referencia de la línea de comandos de MSBuild</span><span class="sxs-lookup"><span data-stu-id="f66c6-231">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="f66c6-232">Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f66c6-232">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="f66c6-233">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f66c6-233">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="f66c6-234">ILLInk.Tasks</span><span class="sxs-lookup"><span data-stu-id="f66c6-234">ILLInk.Tasks</span></span>](https://aka.ms/dotnet-illink)
