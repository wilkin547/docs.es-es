---
title: 'Comando dotnet: CLI de .NET Core'
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: bf69be7eb8dfe454823236012113fa53ed39f2f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="e0d34-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="e0d34-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e0d34-104">nombre</span><span class="sxs-lookup"><span data-stu-id="e0d34-104">Name</span></span>

<span data-ttu-id="e0d34-105">`dotnet`: controlador general para ejecutar comandos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e0d34-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e0d34-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e0d34-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e0d34-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0d34-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="e0d34-109">Description</span><span class="sxs-lookup"><span data-stu-id="e0d34-109">Description</span></span>

<span data-ttu-id="e0d34-110">`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="e0d34-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="e0d34-111">Se invoca por sí mismo y proporciona breves instrucciones de uso.</span><span class="sxs-lookup"><span data-stu-id="e0d34-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="e0d34-112">Cada característica específica se implementa como un comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="e0d34-113">Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="e0d34-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="e0d34-114">Todos los argumentos que siguen al comando son sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="e0d34-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="e0d34-115">La única vez que `dotnet` se usa como un comando por sí solo es para ejecutar [aplicaciones dependientes del marco](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="e0d34-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="e0d34-116">Especifique una DLL de aplicación después del verbo `dotnet` para ejecutar la aplicación (por ejemplo, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="e0d34-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="e0d34-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="e0d34-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e0d34-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="e0d34-119">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="e0d34-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="e0d34-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="e0d34-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="e0d34-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e0d34-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="e0d34-122">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0d34-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="e0d34-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-123">Prints out a short help for the command.</span></span> <span data-ttu-id="e0d34-124">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0d34-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="e0d34-125">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="e0d34-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="e0d34-126">Se pone al día con ningún candidato de marco de trabajo compartido.</span><span class="sxs-lookup"><span data-stu-id="e0d34-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0d34-127">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0d34-128">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e0d34-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e0d34-129">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="e0d34-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="e0d34-130">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="e0d34-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0d34-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="e0d34-132">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="e0d34-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="e0d34-133">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e0d34-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="e0d34-134">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0d34-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="e0d34-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-135">Prints out a short help for the command.</span></span> <span data-ttu-id="e0d34-136">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0d34-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="e0d34-137">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="e0d34-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0d34-138">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0d34-139">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e0d34-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e0d34-140">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="e0d34-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="e0d34-141">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="e0d34-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="e0d34-142">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="e0d34-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="e0d34-143">General</span><span class="sxs-lookup"><span data-stu-id="e0d34-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e0d34-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="e0d34-145">Comando</span><span class="sxs-lookup"><span data-stu-id="e0d34-145">Command</span></span>                             | <span data-ttu-id="e0d34-146">Función</span><span class="sxs-lookup"><span data-stu-id="e0d34-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e0d34-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e0d34-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="e0d34-148">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0d34-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e0d34-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e0d34-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="e0d34-150">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e0d34-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="e0d34-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="e0d34-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="e0d34-152">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="e0d34-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="e0d34-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e0d34-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="e0d34-154">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0d34-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e0d34-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e0d34-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="e0d34-156">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="e0d34-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e0d34-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0d34-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="e0d34-158">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="e0d34-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e0d34-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e0d34-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="e0d34-160">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="e0d34-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e0d34-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e0d34-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="e0d34-162">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="e0d34-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e0d34-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e0d34-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="e0d34-164">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="e0d34-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e0d34-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0d34-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="e0d34-166">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="e0d34-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e0d34-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e0d34-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="e0d34-168">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="e0d34-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e0d34-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e0d34-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="e0d34-170">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0d34-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="e0d34-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e0d34-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="e0d34-172">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="e0d34-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0d34-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="e0d34-174">Comando</span><span class="sxs-lookup"><span data-stu-id="e0d34-174">Command</span></span>                             | <span data-ttu-id="e0d34-175">Función</span><span class="sxs-lookup"><span data-stu-id="e0d34-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e0d34-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e0d34-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="e0d34-177">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0d34-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e0d34-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e0d34-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="e0d34-179">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e0d34-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="e0d34-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e0d34-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="e0d34-181">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0d34-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e0d34-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e0d34-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="e0d34-183">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="e0d34-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e0d34-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0d34-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="e0d34-185">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="e0d34-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e0d34-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e0d34-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="e0d34-187">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="e0d34-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e0d34-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e0d34-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="e0d34-189">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="e0d34-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e0d34-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e0d34-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="e0d34-191">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="e0d34-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e0d34-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0d34-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="e0d34-193">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="e0d34-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e0d34-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e0d34-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="e0d34-195">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="e0d34-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e0d34-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e0d34-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="e0d34-197">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="e0d34-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="e0d34-198">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="e0d34-198">Project references</span></span>

<span data-ttu-id="e0d34-199">Comando</span><span class="sxs-lookup"><span data-stu-id="e0d34-199">Command</span></span> | <span data-ttu-id="e0d34-200">Función</span><span class="sxs-lookup"><span data-stu-id="e0d34-200">Function</span></span>
--- | ---
[<span data-ttu-id="e0d34-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="e0d34-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="e0d34-202">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0d34-202">Add a project reference.</span></span>
[<span data-ttu-id="e0d34-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="e0d34-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="e0d34-204">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0d34-204">List project references.</span></span>
[<span data-ttu-id="e0d34-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="e0d34-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="e0d34-206">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0d34-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="e0d34-207">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="e0d34-207">NuGet packages</span></span>

<span data-ttu-id="e0d34-208">Comando</span><span class="sxs-lookup"><span data-stu-id="e0d34-208">Command</span></span> | <span data-ttu-id="e0d34-209">Función</span><span class="sxs-lookup"><span data-stu-id="e0d34-209">Function</span></span>
--- | ---
[<span data-ttu-id="e0d34-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="e0d34-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="e0d34-211">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="e0d34-211">Add a NuGet package.</span></span>
[<span data-ttu-id="e0d34-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="e0d34-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="e0d34-213">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="e0d34-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="e0d34-214">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="e0d34-214">NuGet commands</span></span>

<span data-ttu-id="e0d34-215">Comando</span><span class="sxs-lookup"><span data-stu-id="e0d34-215">Command</span></span> | <span data-ttu-id="e0d34-216">Función</span><span class="sxs-lookup"><span data-stu-id="e0d34-216">Function</span></span>
--- | ---
[<span data-ttu-id="e0d34-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="e0d34-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="e0d34-218">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="e0d34-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="e0d34-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="e0d34-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="e0d34-220">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="e0d34-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="e0d34-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="e0d34-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="e0d34-222">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="e0d34-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="e0d34-223">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e0d34-223">Examples</span></span>

<span data-ttu-id="e0d34-224">Inicialización de una aplicación de consola de .NET Core de ejemplo que se puede compilar y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="e0d34-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="e0d34-225">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="e0d34-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="e0d34-226">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="e0d34-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="e0d34-227">Ejecuta una aplicación dependiente del marco denominada `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="e0d34-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="e0d34-228">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="e0d34-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e0d34-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="e0d34-230">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="e0d34-230">The primary package cache.</span></span> <span data-ttu-id="e0d34-231">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="e0d34-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="e0d34-232">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0d34-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="e0d34-233">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0d34-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e0d34-234">Establezca `true` para excluir la característica de telemetría (valores aceptados `true`, `1` o `yes`); en caso contrario, establezca `false` para incluir las características de telemetría (valores aceptados `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="e0d34-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e0d34-235">Si no se establece, el valor predeterminado es `false`, y se activa la característica de telemetría.</span><span class="sxs-lookup"><span data-stu-id="e0d34-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="e0d34-236">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="e0d34-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="e0d34-237">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e0d34-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="e0d34-238">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="e0d34-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="e0d34-239">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="e0d34-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0d34-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0d34-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="e0d34-241">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="e0d34-241">The primary package cache.</span></span> <span data-ttu-id="e0d34-242">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="e0d34-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="e0d34-243">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0d34-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="e0d34-244">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0d34-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e0d34-245">Establezca `true` para excluir la característica de telemetría (valores aceptados `true`, `1` o `yes`); en caso contrario, establezca `false` para incluir las características de telemetría (valores aceptados `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="e0d34-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e0d34-246">Si no se establece, el valor predeterminado es `false`, y se activa la característica de telemetría.</span><span class="sxs-lookup"><span data-stu-id="e0d34-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
