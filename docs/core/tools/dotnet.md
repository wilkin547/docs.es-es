---
title: 'Comando dotnet: CLI de .NET Core'
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805664"
---
# <a name="dotnet-command"></a><span data-ttu-id="18f5d-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="18f5d-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="18f5d-104">nombre</span><span class="sxs-lookup"><span data-stu-id="18f5d-104">Name</span></span>

<span data-ttu-id="18f5d-105">`dotnet`: controlador general para ejecutar comandos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="18f5d-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18f5d-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="18f5d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18f5d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18f5d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18f5d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18f5d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18f5d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18f5d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="18f5d-110">Description</span><span class="sxs-lookup"><span data-stu-id="18f5d-110">Description</span></span>

<span data-ttu-id="18f5d-111">`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="18f5d-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="18f5d-112">Se invoca por sí mismo y proporciona breves instrucciones de uso.</span><span class="sxs-lookup"><span data-stu-id="18f5d-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="18f5d-113">Cada característica específica se implementa como un comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="18f5d-114">Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="18f5d-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="18f5d-115">Todos los argumentos que siguen al comando son sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="18f5d-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="18f5d-116">La única vez que `dotnet` se usa como un comando por sí solo es para ejecutar [aplicaciones dependientes del marco](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="18f5d-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="18f5d-117">Especifique una DLL de aplicación después del verbo `dotnet` para ejecutar la aplicación (por ejemplo, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="18f5d-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="18f5d-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18f5d-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18f5d-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="18f5d-120">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="18f5d-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="18f5d-121">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="18f5d-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="18f5d-122">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="18f5d-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18f5d-123">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18f5d-124">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-124">Prints out a short help for the command.</span></span> <span data-ttu-id="18f5d-125">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="18f5d-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="18f5d-126">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="18f5d-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="18f5d-127">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="18f5d-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="18f5d-128">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="18f5d-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="18f5d-129">Se pone al día con ningún candidato de marco de trabajo compartido.</span><span class="sxs-lookup"><span data-stu-id="18f5d-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18f5d-130">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18f5d-131">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18f5d-132">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="18f5d-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18f5d-133">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="18f5d-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18f5d-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18f5d-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="18f5d-135">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="18f5d-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="18f5d-136">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="18f5d-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="18f5d-137">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="18f5d-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18f5d-138">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18f5d-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-139">Prints out a short help for the command.</span></span> <span data-ttu-id="18f5d-140">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="18f5d-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="18f5d-141">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="18f5d-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="18f5d-142">Se pone al día con ningún candidato de marco de trabajo compartido.</span><span class="sxs-lookup"><span data-stu-id="18f5d-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18f5d-143">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18f5d-144">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18f5d-145">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="18f5d-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18f5d-146">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="18f5d-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18f5d-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18f5d-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="18f5d-148">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="18f5d-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="18f5d-149">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="18f5d-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18f5d-150">Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18f5d-151">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-151">Prints out a short help for the command.</span></span> <span data-ttu-id="18f5d-152">Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="18f5d-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="18f5d-153">Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.</span><span class="sxs-lookup"><span data-stu-id="18f5d-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18f5d-154">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18f5d-155">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18f5d-156">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="18f5d-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18f5d-157">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="18f5d-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="18f5d-158">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="18f5d-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="18f5d-159">General</span><span class="sxs-lookup"><span data-stu-id="18f5d-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18f5d-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18f5d-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="18f5d-161">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-161">Command</span></span>                                       | <span data-ttu-id="18f5d-162">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18f5d-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18f5d-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="18f5d-164">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18f5d-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="18f5d-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="18f5d-166">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="18f5d-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18f5d-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="18f5d-168">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="18f5d-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="18f5d-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="18f5d-170">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="18f5d-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18f5d-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="18f5d-172">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18f5d-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18f5d-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="18f5d-174">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18f5d-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18f5d-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18f5d-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="18f5d-176">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18f5d-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18f5d-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="18f5d-178">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="18f5d-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18f5d-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18f5d-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="18f5d-180">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="18f5d-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18f5d-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18f5d-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="18f5d-182">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18f5d-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18f5d-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="18f5d-184">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="18f5d-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18f5d-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18f5d-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="18f5d-186">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18f5d-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="18f5d-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="18f5d-188">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="18f5d-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18f5d-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="18f5d-190">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="18f5d-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18f5d-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18f5d-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="18f5d-192">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-192">Command</span></span>                             | <span data-ttu-id="18f5d-193">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18f5d-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18f5d-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="18f5d-195">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18f5d-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18f5d-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="18f5d-197">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="18f5d-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="18f5d-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="18f5d-199">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="18f5d-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="18f5d-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18f5d-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="18f5d-201">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18f5d-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18f5d-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="18f5d-203">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18f5d-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18f5d-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18f5d-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="18f5d-205">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18f5d-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18f5d-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="18f5d-207">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="18f5d-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18f5d-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18f5d-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="18f5d-209">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="18f5d-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18f5d-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18f5d-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="18f5d-211">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18f5d-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18f5d-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="18f5d-213">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="18f5d-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18f5d-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18f5d-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="18f5d-215">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18f5d-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="18f5d-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="18f5d-217">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="18f5d-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18f5d-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="18f5d-219">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="18f5d-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18f5d-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18f5d-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="18f5d-221">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-221">Command</span></span>                             | <span data-ttu-id="18f5d-222">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18f5d-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18f5d-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="18f5d-224">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18f5d-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18f5d-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="18f5d-226">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="18f5d-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="18f5d-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18f5d-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="18f5d-228">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18f5d-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18f5d-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="18f5d-230">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18f5d-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18f5d-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18f5d-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="18f5d-232">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18f5d-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18f5d-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="18f5d-234">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="18f5d-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18f5d-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18f5d-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="18f5d-236">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="18f5d-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18f5d-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18f5d-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="18f5d-238">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18f5d-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18f5d-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="18f5d-240">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="18f5d-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18f5d-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18f5d-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="18f5d-242">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18f5d-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18f5d-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="18f5d-244">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="18f5d-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="18f5d-245">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="18f5d-245">Project references</span></span>

<span data-ttu-id="18f5d-246">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-246">Command</span></span> | <span data-ttu-id="18f5d-247">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-247">Function</span></span>
--- | ---
[<span data-ttu-id="18f5d-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="18f5d-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="18f5d-249">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="18f5d-249">Adds a project reference.</span></span>
[<span data-ttu-id="18f5d-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="18f5d-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="18f5d-251">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="18f5d-251">Lists project references.</span></span>
[<span data-ttu-id="18f5d-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="18f5d-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="18f5d-253">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="18f5d-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="18f5d-254">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="18f5d-254">NuGet packages</span></span>

<span data-ttu-id="18f5d-255">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-255">Command</span></span> | <span data-ttu-id="18f5d-256">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-256">Function</span></span>
--- | ---
[<span data-ttu-id="18f5d-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="18f5d-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="18f5d-258">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="18f5d-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="18f5d-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="18f5d-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="18f5d-260">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="18f5d-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="18f5d-261">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="18f5d-261">NuGet commands</span></span>

<span data-ttu-id="18f5d-262">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-262">Command</span></span> | <span data-ttu-id="18f5d-263">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-263">Function</span></span>
--- | ---
[<span data-ttu-id="18f5d-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="18f5d-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="18f5d-265">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="18f5d-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="18f5d-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="18f5d-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="18f5d-267">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="18f5d-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="18f5d-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="18f5d-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="18f5d-269">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="18f5d-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="18f5d-270">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="18f5d-270">Global Tools commands</span></span>

<span data-ttu-id="18f5d-271">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="18f5d-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="18f5d-272">Comando</span><span class="sxs-lookup"><span data-stu-id="18f5d-272">Command</span></span> | <span data-ttu-id="18f5d-273">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-273">Function</span></span>
--- | ---
[<span data-ttu-id="18f5d-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="18f5d-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="18f5d-275">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="18f5d-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="18f5d-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="18f5d-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="18f5d-277">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="18f5d-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="18f5d-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="18f5d-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="18f5d-279">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="18f5d-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="18f5d-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="18f5d-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="18f5d-281">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="18f5d-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="18f5d-282">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="18f5d-282">Additional tools</span></span>

<span data-ttu-id="18f5d-283">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="18f5d-284">Estas herramientas incluyen:</span><span class="sxs-lookup"><span data-stu-id="18f5d-284">These tools include:</span></span>

| <span data-ttu-id="18f5d-285">Herramienta</span><span class="sxs-lookup"><span data-stu-id="18f5d-285">Tool</span></span>                                              | <span data-ttu-id="18f5d-286">Función</span><span class="sxs-lookup"><span data-stu-id="18f5d-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="18f5d-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="18f5d-287">dev-certs</span></span>                                         | <span data-ttu-id="18f5d-288">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="18f5d-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="18f5d-289">ef</span><span class="sxs-lookup"><span data-stu-id="18f5d-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="18f5d-290">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="18f5d-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="18f5d-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="18f5d-291">sql-cache</span></span>                                         | <span data-ttu-id="18f5d-292">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18f5d-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="18f5d-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="18f5d-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="18f5d-294">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="18f5d-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="18f5d-295">watch</span><span class="sxs-lookup"><span data-stu-id="18f5d-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="18f5d-296">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="18f5d-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="18f5d-297">Para obtener más información sobre cada herramienta, ejecute `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="18f5d-298">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="18f5d-298">Examples</span></span>

<span data-ttu-id="18f5d-299">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="18f5d-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="18f5d-300">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="18f5d-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="18f5d-301">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="18f5d-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="18f5d-302">Ejecuta una aplicación dependiente del marco denominada `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="18f5d-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="18f5d-303">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="18f5d-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18f5d-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18f5d-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="18f5d-305">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="18f5d-305">The primary package cache.</span></span> <span data-ttu-id="18f5d-306">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="18f5d-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18f5d-307">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18f5d-308">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18f5d-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18f5d-309">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18f5d-310">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18f5d-311">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="18f5d-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="18f5d-312">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="18f5d-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="18f5d-313">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="18f5d-314">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="18f5d-315">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="18f5d-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="18f5d-316">Deshabilita la puesta al día de versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="18f5d-316">Disables minor version roll forward.</span></span> <span data-ttu-id="18f5d-317">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="18f5d-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18f5d-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18f5d-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="18f5d-319">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="18f5d-319">The primary package cache.</span></span> <span data-ttu-id="18f5d-320">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="18f5d-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18f5d-321">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18f5d-322">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18f5d-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18f5d-323">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18f5d-324">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18f5d-325">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="18f5d-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="18f5d-326">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="18f5d-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="18f5d-327">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="18f5d-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="18f5d-328">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="18f5d-329">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="18f5d-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18f5d-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18f5d-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="18f5d-331">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="18f5d-331">The primary package cache.</span></span> <span data-ttu-id="18f5d-332">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="18f5d-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18f5d-333">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18f5d-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18f5d-334">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18f5d-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18f5d-335">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18f5d-336">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18f5d-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18f5d-337">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="18f5d-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
