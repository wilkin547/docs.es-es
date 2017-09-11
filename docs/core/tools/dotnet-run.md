---
title: 'Comando dotnet run: CLI de .NET Core'
description: "El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 30dd1a7715c8573062837aaf71344258d0036b5d
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-run"></a><span data-ttu-id="156e5-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="156e5-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="156e5-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="156e5-104">Name</span></span>

<span data-ttu-id="156e5-105">`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.</span><span class="sxs-lookup"><span data-stu-id="156e5-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="156e5-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="156e5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="156e5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="156e5-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="156e5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="156e5-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="156e5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="156e5-109">Description</span></span>

<span data-ttu-id="156e5-110">El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando.</span><span class="sxs-lookup"><span data-stu-id="156e5-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="156e5-111">Es útil para un desarrollo iterativo rápido desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="156e5-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="156e5-112">El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código.</span><span class="sxs-lookup"><span data-stu-id="156e5-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="156e5-113">Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="156e5-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="156e5-114">Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="156e5-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="156e5-115">Por ejemplo, si tiene una aplicación `netcoreapp1.0` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="156e5-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="156e5-116">Los archivos se sobrescriben según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="156e5-116">Files are overwritten as needed.</span></span> <span data-ttu-id="156e5-117">Los archivos temporales se colocan en el directorio `obj`.</span><span class="sxs-lookup"><span data-stu-id="156e5-117">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="156e5-118">Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.</span><span class="sxs-lookup"><span data-stu-id="156e5-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="156e5-119">El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados.</span><span class="sxs-lookup"><span data-stu-id="156e5-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="156e5-120">Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando.</span><span class="sxs-lookup"><span data-stu-id="156e5-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="156e5-121">Por ejemplo, para ejecutar `myapp.dll`, use:</span><span class="sxs-lookup"><span data-stu-id="156e5-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="156e5-122">Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).</span><span class="sxs-lookup"><span data-stu-id="156e5-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="156e5-123">Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="156e5-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="156e5-124">Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción.</span><span class="sxs-lookup"><span data-stu-id="156e5-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="156e5-125">En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.</span><span class="sxs-lookup"><span data-stu-id="156e5-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

## <a name="options"></a><span data-ttu-id="156e5-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="156e5-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="156e5-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="156e5-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="156e5-128">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="156e5-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="156e5-129">Todos los argumentos después de este se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="156e5-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="156e5-130">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="156e5-130">Defines the build configuration.</span></span> <span data-ttu-id="156e5-131">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="156e5-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="156e5-132">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="156e5-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="156e5-133">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="156e5-133">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="156e5-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="156e5-134">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="156e5-135">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="156e5-135">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="156e5-136">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar simplemente `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="156e5-136">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="156e5-137">Para obtener más información, consulte [Working with multiple environments](/aspnetcore/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="156e5-137">For more information, see [Working with multiple environments](/aspnetcore/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="156e5-138">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="156e5-138">Doesn't build the project before running.</span></span>

`--no-launch-profile`

<span data-ttu-id="156e5-139">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="156e5-139">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="156e5-140">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="156e5-140">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="156e5-141">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="156e5-141">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="156e5-142">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="156e5-142">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="156e5-143">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="156e5-143">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="156e5-144">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="156e5-144">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="156e5-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="156e5-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="156e5-146">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="156e5-146">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="156e5-147">Todos los argumentos después de este se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="156e5-147">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="156e5-148">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="156e5-148">Defines the build configuration.</span></span> <span data-ttu-id="156e5-149">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="156e5-149">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="156e5-150">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="156e5-150">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="156e5-151">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="156e5-151">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="156e5-152">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="156e5-152">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="156e5-153">Especifica la ruta de acceso y el nombre del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="156e5-153">Specifies the path and name of the project file.</span></span> <span data-ttu-id="156e5-154">(Consulte la NOTA). Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="156e5-154">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="156e5-155">Use la ruta de acceso y el nombre del archivo del proyecto con la opción `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="156e5-155">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="156e5-156">Una regresión en la CLI impide proporcionar una ruta de carpeta con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="156e5-156">A regression in the CLI prevents providing a folder path with .NET Core 1.x SDK.</span></span> <span data-ttu-id="156e5-157">Para obtener más información sobre este problema, consulte [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, no puede iniciar un proyecto [dotnet/cli #5992]).</span><span class="sxs-lookup"><span data-stu-id="156e5-157">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="156e5-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="156e5-158">Examples</span></span>

<span data-ttu-id="156e5-159">Ejecución del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="156e5-159">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="156e5-160">Ejecución del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="156e5-160">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="156e5-161">Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usó el argumento `--`):</span><span class="sxs-lookup"><span data-stu-id="156e5-161">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

