---
title: Comando dotnet run
description: El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente.
ms.date: 10/31/2019
ms.openlocfilehash: 5920f0d1f04204b286fdf6f51f5fd13644846390
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734106"
---
# <a name="dotnet-run"></a><span data-ttu-id="0f283-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="0f283-103">dotnet run</span></span>

<span data-ttu-id="0f283-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0f283-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="0f283-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0f283-105">Name</span></span>

<span data-ttu-id="0f283-106">`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.</span><span class="sxs-lookup"><span data-stu-id="0f283-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0f283-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0f283-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="0f283-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0f283-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0f283-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0f283-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0f283-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0f283-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f283-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f283-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="0f283-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f283-112">Description</span></span>

<span data-ttu-id="0f283-113">El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="0f283-114">Es útil para un desarrollo iterativo rápido desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0f283-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="0f283-115">El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código.</span><span class="sxs-lookup"><span data-stu-id="0f283-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="0f283-116">Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="0f283-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="0f283-117">Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="0f283-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="0f283-118">Por ejemplo, si tiene una aplicación `netcoreapp2.1` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="0f283-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="0f283-119">Los archivos se sobrescriben según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0f283-119">Files are overwritten as needed.</span></span> <span data-ttu-id="0f283-120">Los archivos temporales se colocan en el directorio `obj`.</span><span class="sxs-lookup"><span data-stu-id="0f283-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="0f283-121">Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.</span><span class="sxs-lookup"><span data-stu-id="0f283-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="0f283-122">El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados.</span><span class="sxs-lookup"><span data-stu-id="0f283-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="0f283-123">Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="0f283-124">Por ejemplo, para ejecutar `myapp.dll`, use:</span><span class="sxs-lookup"><span data-stu-id="0f283-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="0f283-125">Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).</span><span class="sxs-lookup"><span data-stu-id="0f283-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="0f283-126">Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="0f283-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="0f283-127">Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción.</span><span class="sxs-lookup"><span data-stu-id="0f283-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="0f283-128">En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.</span><span class="sxs-lookup"><span data-stu-id="0f283-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="0f283-129">Opciones</span><span class="sxs-lookup"><span data-stu-id="0f283-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="0f283-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0f283-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="0f283-131">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0f283-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="0f283-132">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0f283-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f283-133">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="0f283-133">Defines the build configuration.</span></span> <span data-ttu-id="0f283-134">El valor predeterminado de la mayoría de los proyectos es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="0f283-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f283-135">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="0f283-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="0f283-136">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f283-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="0f283-137">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f283-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="0f283-138">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="0f283-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="0f283-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="0f283-140">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="0f283-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="0f283-141">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="0f283-142">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="0f283-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="0f283-143">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="0f283-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="0f283-144">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0f283-144">Doesn't build the project before running.</span></span> <span data-ttu-id="0f283-145">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="0f283-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="0f283-146">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="0f283-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="0f283-147">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="0f283-148">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="0f283-149">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="0f283-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="0f283-150">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0f283-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="0f283-151">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="0f283-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="0f283-152">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="0f283-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="0f283-153">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0f283-154">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0f283-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0f283-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0f283-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="0f283-156">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0f283-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="0f283-157">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0f283-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f283-158">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="0f283-158">Defines the build configuration.</span></span> <span data-ttu-id="0f283-159">El valor predeterminado de la mayoría de los proyectos es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="0f283-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f283-160">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="0f283-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="0f283-161">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f283-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="0f283-162">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f283-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="0f283-163">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="0f283-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="0f283-164">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="0f283-165">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="0f283-166">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="0f283-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="0f283-167">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="0f283-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="0f283-168">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0f283-168">Doesn't build the project before running.</span></span> <span data-ttu-id="0f283-169">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="0f283-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="0f283-170">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="0f283-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="0f283-171">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="0f283-172">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="0f283-173">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="0f283-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="0f283-174">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0f283-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="0f283-175">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="0f283-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="0f283-176">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="0f283-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="0f283-177">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0f283-178">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0f283-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0f283-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0f283-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="0f283-180">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0f283-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="0f283-181">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0f283-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f283-182">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="0f283-182">Defines the build configuration.</span></span> <span data-ttu-id="0f283-183">El valor predeterminado de la mayoría de los proyectos es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="0f283-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f283-184">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="0f283-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="0f283-185">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f283-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="0f283-186">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f283-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="0f283-187">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="0f283-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="0f283-188">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="0f283-189">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="0f283-190">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="0f283-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="0f283-191">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="0f283-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="0f283-192">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0f283-192">Doesn't build the project before running.</span></span> <span data-ttu-id="0f283-193">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="0f283-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="0f283-194">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="0f283-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="0f283-195">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f283-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="0f283-196">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="0f283-197">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="0f283-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="0f283-198">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0f283-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="0f283-199">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="0f283-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="0f283-200">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="0f283-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f283-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f283-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="0f283-202">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0f283-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="0f283-203">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0f283-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f283-204">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="0f283-204">Defines the build configuration.</span></span> <span data-ttu-id="0f283-205">El valor predeterminado de la mayoría de los proyectos es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="0f283-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f283-206">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="0f283-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="0f283-207">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f283-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="0f283-208">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0f283-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="0f283-209">Especifica la ruta de acceso y el nombre del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f283-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="0f283-210">(Consulte la NOTA). Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0f283-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="0f283-211">Use la ruta de acceso y el nombre del archivo del proyecto con la opción `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="0f283-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="0f283-212">Una regresión en la CLI impide proporcionar una ruta de carpeta con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="0f283-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="0f283-213">Para obtener más información sobre este problema, consulte [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, no puede iniciar un proyecto [dotnet/cli #5992]).</span><span class="sxs-lookup"><span data-stu-id="0f283-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="0f283-214">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0f283-214">Examples</span></span>

<span data-ttu-id="0f283-215">Ejecución del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="0f283-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="0f283-216">Ejecución del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="0f283-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="0f283-217">Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usa la opción `--` en blanco):</span><span class="sxs-lookup"><span data-stu-id="0f283-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="0f283-218">Restaure las dependencias y herramientas del proyecto en el directorio actual mostrando solo la salida mínima y, después, ejecute el proyecto: (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="0f283-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
