---
title: Comando dotnet run
description: El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente.
ms.date: 02/19/2020
ms.openlocfilehash: 77282fd8615ef01b7867c1bf0f741c834b6ddb30
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102778"
---
# <a name="dotnet-run"></a><span data-ttu-id="91a7a-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="91a7a-103">dotnet run</span></span>

<span data-ttu-id="91a7a-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="91a7a-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="91a7a-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="91a7a-105">Name</span></span>

<span data-ttu-id="91a7a-106">`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.</span><span class="sxs-lookup"><span data-stu-id="91a7a-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="91a7a-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="91a7a-107">Synopsis</span></span>

```dotnetcli
dotnet run [-c|--configuration <CONFIGURATION>] [-f|--framework <FRAMEWORK>]
    [--force] [--interactive] [--launch-profile <NAME>] [--no-build]
    [--no-dependencies] [--no-launch-profile] [--no-restore]
    [-p|--project <PATH>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [-v|--verbosity <LEVEL>] [[--] [application arguments]]

dotnet run -h|--help
```

## <a name="description"></a><span data-ttu-id="91a7a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="91a7a-108">Description</span></span>

<span data-ttu-id="91a7a-109">El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando.</span><span class="sxs-lookup"><span data-stu-id="91a7a-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="91a7a-110">Es útil para un desarrollo iterativo rápido desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="91a7a-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="91a7a-111">El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código.</span><span class="sxs-lookup"><span data-stu-id="91a7a-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="91a7a-112">Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="91a7a-113">Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="91a7a-114">Por ejemplo, si tiene una aplicación `netcoreapp2.1` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-114">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="91a7a-115">Los archivos se sobrescriben según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="91a7a-115">Files are overwritten as needed.</span></span> <span data-ttu-id="91a7a-116">Los archivos temporales se colocan en el directorio `obj`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-116">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="91a7a-117">Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.</span><span class="sxs-lookup"><span data-stu-id="91a7a-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="91a7a-118">El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados.</span><span class="sxs-lookup"><span data-stu-id="91a7a-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="91a7a-119">Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando.</span><span class="sxs-lookup"><span data-stu-id="91a7a-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="91a7a-120">Por ejemplo, para ejecutar `myapp.dll`, use:</span><span class="sxs-lookup"><span data-stu-id="91a7a-120">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="91a7a-121">Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).</span><span class="sxs-lookup"><span data-stu-id="91a7a-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="91a7a-122">Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="91a7a-122">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="91a7a-123">Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción.</span><span class="sxs-lookup"><span data-stu-id="91a7a-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="91a7a-124">En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.</span><span class="sxs-lookup"><span data-stu-id="91a7a-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="91a7a-125">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="91a7a-125">Implicit restore</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="91a7a-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="91a7a-126">Options</span></span>

- **`--`**

  <span data-ttu-id="91a7a-127">Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="91a7a-127">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="91a7a-128">Todos los argumentos después de este delimitador se pasan a la aplicación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="91a7a-128">All arguments after this delimiter are passed to the application run.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="91a7a-129">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="91a7a-129">Defines the build configuration.</span></span> <span data-ttu-id="91a7a-130">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="91a7a-130">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="91a7a-131">Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="91a7a-131">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="91a7a-132">El marco debe especificarse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="91a7a-132">The framework must be specified in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="91a7a-133">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="91a7a-133">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="91a7a-134">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="91a7a-134">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="91a7a-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="91a7a-135">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="91a7a-136">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="91a7a-136">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="91a7a-137">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="91a7a-137">Available since .NET Core 3.0 SDK.</span></span>

- **`--launch-profile <NAME>`**

  <span data-ttu-id="91a7a-138">El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91a7a-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="91a7a-139">Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar `Development`, `Staging` y `Production`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="91a7a-140">Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).</span><span class="sxs-lookup"><span data-stu-id="91a7a-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

- **`--no-build`**

  <span data-ttu-id="91a7a-141">No compila el proyecto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="91a7a-141">Doesn't build the project before running.</span></span> <span data-ttu-id="91a7a-142">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="91a7a-142">It also implicit sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="91a7a-143">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="91a7a-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--no-launch-profile`**

  <span data-ttu-id="91a7a-144">No intenta usar *launchSettings.json* para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91a7a-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

- **`--no-restore`**

  <span data-ttu-id="91a7a-145">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="91a7a-145">Doesn't execute an implicit restore when running the command.</span></span>

- **`-p|--project <PATH>`**

  <span data-ttu-id="91a7a-146">Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa).</span><span class="sxs-lookup"><span data-stu-id="91a7a-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="91a7a-147">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="91a7a-147">If not specified, it defaults to the current directory.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="91a7a-148">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="91a7a-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="91a7a-149">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="91a7a-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="91a7a-150">Opción corta `-r` disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="91a7a-150">`-r` short option available since .NET Core 3.0 SDK.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="91a7a-151">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="91a7a-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="91a7a-152">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="91a7a-153">El valor predeterminado es `m`.</span><span class="sxs-lookup"><span data-stu-id="91a7a-153">The default value is `m`.</span></span> <span data-ttu-id="91a7a-154">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="91a7a-154">Available since .NET Core 2.1 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="91a7a-155">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="91a7a-155">Examples</span></span>

- <span data-ttu-id="91a7a-156">Ejecución del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="91a7a-156">Run the project in the current directory:</span></span>

  ```dotnetcli
  dotnet run
  ```

- <span data-ttu-id="91a7a-157">Ejecución del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="91a7a-157">Run the specified project:</span></span>

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- <span data-ttu-id="91a7a-158">Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usa la opción `--` en blanco):</span><span class="sxs-lookup"><span data-stu-id="91a7a-158">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- <span data-ttu-id="91a7a-159">Restaure las dependencias y herramientas del proyecto en el directorio actual mostrando solo la salida mínima y, después, ejecute el proyecto: (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="91a7a-159">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet run --verbosity m
  ```
