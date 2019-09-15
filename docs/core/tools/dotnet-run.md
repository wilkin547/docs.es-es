---
title: Comando dotnet run
description: El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente.
ms.date: 05/29/2018
ms.openlocfilehash: b21987ef9ee4dd7d8fdb93d0853b7faa93001688
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969752"
---
# <a name="dotnet-run"></a><span data-ttu-id="e7a28-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e7a28-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e7a28-104">nombre</span><span class="sxs-lookup"><span data-stu-id="e7a28-104">Name</span></span>

<span data-ttu-id="e7a28-105">`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.</span><span class="sxs-lookup"><span data-stu-id="e7a28-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e7a28-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e7a28-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e7a28-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e7a28-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e7a28-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e7a28-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e7a28-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e7a28-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e7a28-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e7a28-110">Description</span></span>

<span data-ttu-id="e7a28-111">El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="e7a28-112">Es útil para un desarrollo iterativo rápido desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e7a28-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="e7a28-113">El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código.</span><span class="sxs-lookup"><span data-stu-id="e7a28-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="e7a28-114">Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="e7a28-115">Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="e7a28-116">Por ejemplo, si tiene una aplicación `netcoreapp2.1` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-116">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="e7a28-117">Los archivos se sobrescriben según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e7a28-117">Files are overwritten as needed.</span></span> <span data-ttu-id="e7a28-118">Los archivos temporales se colocan en el directorio `obj`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="e7a28-119">Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.</span><span class="sxs-lookup"><span data-stu-id="e7a28-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="e7a28-120">El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados.</span><span class="sxs-lookup"><span data-stu-id="e7a28-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="e7a28-121">Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="e7a28-122">Por ejemplo, para ejecutar `myapp.dll`, use:</span><span class="sxs-lookup"><span data-stu-id="e7a28-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="e7a28-123">Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).</span><span class="sxs-lookup"><span data-stu-id="e7a28-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="e7a28-124">Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="e7a28-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="e7a28-125">Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción.</span><span class="sxs-lookup"><span data-stu-id="e7a28-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="e7a28-126">En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.</span><span class="sxs-lookup"><span data-stu-id="e7a28-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="e7a28-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="e7a28-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e7a28-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e7a28-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="e7a28-129">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e7a28-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e7a28-130">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e7a28-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e7a28-131">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-131">Defines the build configuration.</span></span> <span data-ttu-id="e7a28-132">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e7a28-133">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="e7a28-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e7a28-134">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7a28-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e7a28-135">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e7a28-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e7a28-136">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e7a28-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e7a28-137">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e7a28-138">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e7a28-139">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="e7a28-140">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="e7a28-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e7a28-141">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="e7a28-141">Doesn't build the project before running.</span></span> <span data-ttu-id="e7a28-142">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="e7a28-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="e7a28-143">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="e7a28-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e7a28-144">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e7a28-145">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e7a28-146">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="e7a28-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e7a28-147">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7a28-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e7a28-148">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="e7a28-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e7a28-149">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e7a28-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e7a28-150">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e7a28-151">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e7a28-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e7a28-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="e7a28-153">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e7a28-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e7a28-154">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e7a28-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e7a28-155">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-155">Defines the build configuration.</span></span> <span data-ttu-id="e7a28-156">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e7a28-157">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="e7a28-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e7a28-158">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7a28-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e7a28-159">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e7a28-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e7a28-160">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e7a28-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e7a28-161">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e7a28-162">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e7a28-163">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="e7a28-164">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="e7a28-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e7a28-165">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="e7a28-165">Doesn't build the project before running.</span></span> <span data-ttu-id="e7a28-166">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="e7a28-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="e7a28-167">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="e7a28-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e7a28-168">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e7a28-169">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e7a28-170">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="e7a28-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e7a28-171">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7a28-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e7a28-172">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="e7a28-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e7a28-173">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e7a28-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e7a28-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e7a28-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="e7a28-175">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e7a28-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e7a28-176">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e7a28-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e7a28-177">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="e7a28-177">Defines the build configuration.</span></span> <span data-ttu-id="e7a28-178">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e7a28-179">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="e7a28-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e7a28-180">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7a28-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="e7a28-181">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e7a28-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="e7a28-182">Especifica la ruta de acceso y el nombre del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7a28-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="e7a28-183">(Consulte la NOTA). Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7a28-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="e7a28-184">Use la ruta de acceso y el nombre del archivo del proyecto con la opción `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="e7a28-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="e7a28-185">Una regresión en la CLI impide proporcionar una ruta de carpeta con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="e7a28-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="e7a28-186">Para obtener más información sobre este problema, consulte [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, no puede iniciar un proyecto [dotnet/cli #5992]).</span><span class="sxs-lookup"><span data-stu-id="e7a28-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="e7a28-187">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e7a28-187">Examples</span></span>

<span data-ttu-id="e7a28-188">Ejecución del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="e7a28-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="e7a28-189">Ejecución del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="e7a28-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="e7a28-190">Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usa la opción `--` en blanco):</span><span class="sxs-lookup"><span data-stu-id="e7a28-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="e7a28-191">Restaure las dependencias y herramientas del proyecto en el directorio actual mostrando solo la salida mínima y, después, ejecute el proyecto: (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="e7a28-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
