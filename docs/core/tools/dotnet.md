---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
ms.date: 06/04/2018
ms.openlocfilehash: 2134bf8ed66157619499b027f01d39e03e84411f
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859553"
---
# <a name="dotnet-command"></a><span data-ttu-id="f2257-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="f2257-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f2257-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f2257-104">Name</span></span>

<span data-ttu-id="f2257-105">`dotnet`: herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="f2257-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f2257-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f2257-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f2257-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f2257-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f2257-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f2257-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f2257-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f2257-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="f2257-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f2257-110">Description</span></span>

<span data-ttu-id="f2257-111">`dotnet` es una herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="f2257-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="f2257-112">Expone los comandos que realizan tareas específicas, como [`dotnet build`](dotnet-build.md) y [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="f2257-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="f2257-113">Cada comando define sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="f2257-113">Each command defines its own arguments.</span></span> <span data-ttu-id="f2257-114">Escriba `--help` después de cada comando para acceder a una breve documentación de ayuda.</span><span class="sxs-lookup"><span data-stu-id="f2257-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="f2257-115">`dotnet` puede usarse para ejecutar aplicaciones si se especifica un archivo DLL de aplicación, como `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="f2257-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="f2257-116">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2257-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="f2257-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="f2257-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f2257-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f2257-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="f2257-119">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="f2257-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="f2257-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="f2257-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f2257-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f2257-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f2257-122">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2257-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f2257-123">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="f2257-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f2257-124">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2257-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f2257-125">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="f2257-126">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="f2257-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="f2257-127">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="f2257-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="f2257-128">Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2257-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="f2257-129">`N` puede ser:</span><span class="sxs-lookup"><span data-stu-id="f2257-129">`N` can be:</span></span>
* <span data-ttu-id="f2257-130">`0`: se deshabilita la puesta al día incluso de las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="f2257-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="f2257-131">`1`: puesta al día de la versión secundaria, pero no de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="f2257-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="f2257-132">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f2257-132">This is the default behavior.</span></span>
* <span data-ttu-id="f2257-133">`2`: puesta al día de las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="f2257-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="f2257-134">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="f2257-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f2257-135">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f2257-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f2257-136">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f2257-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f2257-137">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2257-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f2257-138">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="f2257-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f2257-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f2257-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="f2257-140">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="f2257-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="f2257-141">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="f2257-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f2257-142">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f2257-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f2257-143">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2257-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f2257-144">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="f2257-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f2257-145">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2257-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f2257-146">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="f2257-147">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="f2257-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="f2257-148">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="f2257-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f2257-149">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f2257-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f2257-150">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f2257-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f2257-151">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2257-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f2257-152">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="f2257-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f2257-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f2257-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="f2257-154">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="f2257-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f2257-155">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f2257-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f2257-156">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2257-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f2257-157">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="f2257-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f2257-158">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2257-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f2257-159">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f2257-160">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f2257-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f2257-161">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f2257-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f2257-162">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2257-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f2257-163">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="f2257-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="f2257-164">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="f2257-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="f2257-165">General</span><span class="sxs-lookup"><span data-stu-id="f2257-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f2257-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f2257-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="f2257-167">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-167">Command</span></span>                                       | <span data-ttu-id="f2257-168">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f2257-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f2257-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="f2257-170">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f2257-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="f2257-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="f2257-172">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="f2257-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="f2257-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f2257-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="f2257-174">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="f2257-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="f2257-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f2257-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="f2257-176">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="f2257-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f2257-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f2257-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="f2257-178">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f2257-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f2257-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="f2257-180">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f2257-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f2257-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2257-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="f2257-182">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f2257-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f2257-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="f2257-184">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="f2257-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f2257-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f2257-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="f2257-186">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="f2257-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f2257-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f2257-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="f2257-188">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f2257-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f2257-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="f2257-190">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="f2257-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f2257-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f2257-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="f2257-192">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f2257-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f2257-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f2257-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="f2257-194">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2257-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f2257-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f2257-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="f2257-196">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f2257-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f2257-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f2257-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="f2257-198">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-198">Command</span></span>                             | <span data-ttu-id="f2257-199">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f2257-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f2257-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f2257-201">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f2257-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f2257-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f2257-203">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="f2257-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f2257-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f2257-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="f2257-205">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="f2257-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f2257-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f2257-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f2257-207">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f2257-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f2257-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f2257-209">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f2257-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f2257-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2257-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f2257-211">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f2257-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f2257-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f2257-213">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="f2257-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f2257-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f2257-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f2257-215">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="f2257-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f2257-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f2257-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f2257-217">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f2257-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f2257-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f2257-219">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="f2257-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f2257-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f2257-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f2257-221">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f2257-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f2257-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f2257-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="f2257-223">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2257-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f2257-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f2257-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f2257-225">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f2257-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f2257-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f2257-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="f2257-227">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-227">Command</span></span>                             | <span data-ttu-id="f2257-228">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f2257-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f2257-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f2257-230">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f2257-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f2257-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f2257-232">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="f2257-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f2257-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f2257-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f2257-234">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f2257-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f2257-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f2257-236">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f2257-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f2257-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2257-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f2257-238">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f2257-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f2257-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f2257-240">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="f2257-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f2257-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f2257-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f2257-242">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="f2257-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f2257-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f2257-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f2257-244">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="f2257-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f2257-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f2257-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f2257-246">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="f2257-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f2257-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f2257-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f2257-248">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f2257-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f2257-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f2257-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f2257-250">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f2257-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="f2257-251">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="f2257-251">Project references</span></span>

<span data-ttu-id="f2257-252">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-252">Command</span></span> | <span data-ttu-id="f2257-253">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-253">Function</span></span>
--- | ---
[<span data-ttu-id="f2257-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="f2257-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="f2257-255">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f2257-255">Adds a project reference.</span></span>
[<span data-ttu-id="f2257-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="f2257-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="f2257-257">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f2257-257">Lists project references.</span></span>
[<span data-ttu-id="f2257-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="f2257-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="f2257-259">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f2257-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="f2257-260">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="f2257-260">NuGet packages</span></span>

<span data-ttu-id="f2257-261">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-261">Command</span></span> | <span data-ttu-id="f2257-262">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-262">Function</span></span>
--- | ---
[<span data-ttu-id="f2257-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="f2257-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="f2257-264">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="f2257-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="f2257-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="f2257-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="f2257-266">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="f2257-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="f2257-267">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="f2257-267">NuGet commands</span></span>

<span data-ttu-id="f2257-268">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-268">Command</span></span> | <span data-ttu-id="f2257-269">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-269">Function</span></span>
--- | ---
[<span data-ttu-id="f2257-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="f2257-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="f2257-271">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="f2257-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="f2257-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="f2257-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="f2257-273">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="f2257-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="f2257-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="f2257-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="f2257-275">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="f2257-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="f2257-276">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="f2257-276">Global Tools commands</span></span>

<span data-ttu-id="f2257-277">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="f2257-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="f2257-278">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f2257-278">Command</span></span> | <span data-ttu-id="f2257-279">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-279">Function</span></span>
--- | ---
[<span data-ttu-id="f2257-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="f2257-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="f2257-281">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f2257-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="f2257-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="f2257-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="f2257-283">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="f2257-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="f2257-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="f2257-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="f2257-285">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="f2257-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="f2257-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="f2257-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="f2257-287">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f2257-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="f2257-288">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="f2257-288">Additional tools</span></span>

<span data-ttu-id="f2257-289">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="f2257-290">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2257-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="f2257-291">Herramienta</span><span class="sxs-lookup"><span data-stu-id="f2257-291">Tool</span></span>                                              | <span data-ttu-id="f2257-292">Función</span><span class="sxs-lookup"><span data-stu-id="f2257-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="f2257-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="f2257-293">dev-certs</span></span>                                         | <span data-ttu-id="f2257-294">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f2257-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="f2257-295">ef</span><span class="sxs-lookup"><span data-stu-id="f2257-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="f2257-296">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="f2257-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="f2257-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="f2257-297">sql-cache</span></span>                                         | <span data-ttu-id="f2257-298">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2257-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="f2257-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="f2257-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="f2257-300">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f2257-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="f2257-301">watch</span><span class="sxs-lookup"><span data-stu-id="f2257-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="f2257-302">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="f2257-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="f2257-303">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="f2257-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="f2257-304">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f2257-304">Examples</span></span>

<span data-ttu-id="f2257-305">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f2257-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="f2257-306">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="f2257-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="f2257-307">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="f2257-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="f2257-308">Ejecutar un archivo DLL de aplicación como `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="f2257-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="f2257-309">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="f2257-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f2257-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f2257-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="f2257-311">La carpeta de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="f2257-311">The global packages folder.</span></span> <span data-ttu-id="f2257-312">Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="f2257-312">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f2257-313">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2257-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f2257-314">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2257-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f2257-315">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="f2257-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f2257-316">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="f2257-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f2257-317">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="f2257-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="f2257-318">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="f2257-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="f2257-319">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="f2257-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="f2257-320">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="f2257-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="f2257-321">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="f2257-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="f2257-322">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="f2257-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="f2257-323">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="f2257-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f2257-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f2257-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="f2257-325">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="f2257-325">The primary package cache.</span></span> <span data-ttu-id="f2257-326">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="f2257-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f2257-327">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2257-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f2257-328">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2257-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f2257-329">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="f2257-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f2257-330">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="f2257-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f2257-331">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="f2257-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="f2257-332">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="f2257-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="f2257-333">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="f2257-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="f2257-334">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="f2257-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="f2257-335">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="f2257-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f2257-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f2257-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="f2257-337">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="f2257-337">The primary package cache.</span></span> <span data-ttu-id="f2257-338">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="f2257-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f2257-339">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2257-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f2257-340">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2257-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f2257-341">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="f2257-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f2257-342">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="f2257-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f2257-343">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="f2257-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
