---
title: 'Comando dotnet: CLI de .NET Core'
description: "Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: bba8d77cda7538bf008dc0f510f9279d3c695c3d
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-command"></a><span data-ttu-id="c29ed-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="c29ed-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c29ed-104">Name</span><span class="sxs-lookup"><span data-stu-id="c29ed-104">Name</span></span>

<span data-ttu-id="c29ed-105">`dotnet`: controlador general para ejecutar comandos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c29ed-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c29ed-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c29ed-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c29ed-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c29ed-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="c29ed-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c29ed-109">Description</span></span>

<span data-ttu-id="c29ed-110">`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="c29ed-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="c29ed-111">Se invoca por sí mismo y proporciona breves instrucciones de uso.</span><span class="sxs-lookup"><span data-stu-id="c29ed-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="c29ed-112">Cada característica específica se implementa como un comando.</span><span class="sxs-lookup"><span data-stu-id="c29ed-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="c29ed-113">Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="c29ed-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="c29ed-114">Todos los argumentos que siguen al comando son sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="c29ed-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="c29ed-115">La única vez que `dotnet` se usa como un comando por sí solo es para ejecutar [aplicaciones dependientes del marco](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c29ed-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="c29ed-116">Especifique una DLL de aplicación después del verbo `dotnet` para ejecutar la aplicación (por ejemplo, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="c29ed-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="c29ed-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="c29ed-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c29ed-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additionaldeps <PATH>`

<span data-ttu-id="c29ed-119">Ruta de acceso a otros *deps.json* archivo.</span><span class="sxs-lookup"><span data-stu-id="c29ed-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c29ed-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="c29ed-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c29ed-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c29ed-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c29ed-122">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c29ed-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c29ed-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c29ed-123">Prints out a short help for the command.</span></span> <span data-ttu-id="c29ed-124">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c29ed-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c29ed-125">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="c29ed-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c29ed-126">Se pone al día con ningún candidato de marco de trabajo compartido.</span><span class="sxs-lookup"><span data-stu-id="c29ed-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="c29ed-127">Habilita la salda detallada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c29ed-128">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="c29ed-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c29ed-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c29ed-130">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="c29ed-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c29ed-131">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c29ed-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c29ed-132">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c29ed-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c29ed-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c29ed-133">Prints out a short help for the command.</span></span> <span data-ttu-id="c29ed-134">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c29ed-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c29ed-135">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="c29ed-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="c29ed-136">Habilita la salda detallada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c29ed-137">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="c29ed-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c29ed-138">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="c29ed-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c29ed-139">General</span><span class="sxs-lookup"><span data-stu-id="c29ed-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c29ed-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="c29ed-141">Comando</span><span class="sxs-lookup"><span data-stu-id="c29ed-141">Command</span></span>                             | <span data-ttu-id="c29ed-142">Función</span><span class="sxs-lookup"><span data-stu-id="c29ed-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c29ed-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c29ed-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c29ed-144">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c29ed-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c29ed-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c29ed-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c29ed-146">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c29ed-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c29ed-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c29ed-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c29ed-148">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="c29ed-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c29ed-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c29ed-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c29ed-150">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c29ed-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c29ed-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c29ed-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c29ed-152">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c29ed-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c29ed-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c29ed-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c29ed-154">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c29ed-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c29ed-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c29ed-156">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="c29ed-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c29ed-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c29ed-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c29ed-158">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="c29ed-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c29ed-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c29ed-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c29ed-160">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c29ed-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c29ed-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c29ed-162">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="c29ed-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c29ed-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c29ed-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c29ed-164">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="c29ed-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c29ed-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c29ed-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c29ed-166">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c29ed-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c29ed-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c29ed-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c29ed-168">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="c29ed-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c29ed-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c29ed-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c29ed-170">Comando</span><span class="sxs-lookup"><span data-stu-id="c29ed-170">Command</span></span>                             | <span data-ttu-id="c29ed-171">Función</span><span class="sxs-lookup"><span data-stu-id="c29ed-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c29ed-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c29ed-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c29ed-173">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c29ed-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c29ed-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c29ed-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c29ed-175">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c29ed-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c29ed-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c29ed-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c29ed-177">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c29ed-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c29ed-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c29ed-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c29ed-179">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c29ed-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c29ed-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c29ed-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c29ed-181">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c29ed-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c29ed-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c29ed-183">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="c29ed-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c29ed-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c29ed-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c29ed-185">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="c29ed-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c29ed-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c29ed-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c29ed-187">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="c29ed-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c29ed-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c29ed-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c29ed-189">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="c29ed-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c29ed-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c29ed-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c29ed-191">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="c29ed-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c29ed-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c29ed-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c29ed-193">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="c29ed-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c29ed-194">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="c29ed-194">Project references</span></span>

<span data-ttu-id="c29ed-195">Comando</span><span class="sxs-lookup"><span data-stu-id="c29ed-195">Command</span></span> | <span data-ttu-id="c29ed-196">Función</span><span class="sxs-lookup"><span data-stu-id="c29ed-196">Function</span></span>
--- | ---
[<span data-ttu-id="c29ed-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c29ed-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c29ed-198">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c29ed-198">Add a project reference.</span></span>
[<span data-ttu-id="c29ed-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c29ed-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c29ed-200">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c29ed-200">List project references.</span></span>
[<span data-ttu-id="c29ed-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c29ed-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c29ed-202">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c29ed-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c29ed-203">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="c29ed-203">NuGet packages</span></span>

<span data-ttu-id="c29ed-204">Comando</span><span class="sxs-lookup"><span data-stu-id="c29ed-204">Command</span></span> | <span data-ttu-id="c29ed-205">Función</span><span class="sxs-lookup"><span data-stu-id="c29ed-205">Function</span></span>
--- | ---
[<span data-ttu-id="c29ed-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c29ed-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c29ed-207">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="c29ed-207">Add a NuGet package.</span></span>
[<span data-ttu-id="c29ed-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c29ed-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c29ed-209">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="c29ed-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c29ed-210">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="c29ed-210">NuGet commands</span></span>

<span data-ttu-id="c29ed-211">Comando</span><span class="sxs-lookup"><span data-stu-id="c29ed-211">Command</span></span> | <span data-ttu-id="c29ed-212">Función</span><span class="sxs-lookup"><span data-stu-id="c29ed-212">Function</span></span>
--- | ---
[<span data-ttu-id="c29ed-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c29ed-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c29ed-214">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="c29ed-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c29ed-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c29ed-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c29ed-216">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="c29ed-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c29ed-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c29ed-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c29ed-218">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="c29ed-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="c29ed-219">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c29ed-219">Examples</span></span>

<span data-ttu-id="c29ed-220">Inicialización de una aplicación de consola de .NET Core de ejemplo que se puede compilar y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="c29ed-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="c29ed-221">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="c29ed-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c29ed-222">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="c29ed-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c29ed-223">Ejecuta una aplicación dependiente del marco denominada `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="c29ed-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c29ed-224">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="c29ed-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="c29ed-225">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="c29ed-225">The primary package cache.</span></span> <span data-ttu-id="c29ed-226">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="c29ed-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c29ed-227">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c29ed-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c29ed-228">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c29ed-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c29ed-229">Establezca `true` para excluir la característica de telemetría (valores aceptados `true`, `1` o `yes`); en caso contrario, establezca `false` para incluir las características de telemetría (valores aceptados `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="c29ed-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c29ed-230">Si no se establece, el valor predeterminado es `false`, y se activa la característica de telemetría.</span><span class="sxs-lookup"><span data-stu-id="c29ed-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>
