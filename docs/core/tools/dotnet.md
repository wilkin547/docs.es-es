---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
ms.date: 06/04/2018
ms.openlocfilehash: 107a529952cce62dac840874fa5d6d8986376adf
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185641"
---
# <a name="dotnet-command"></a><span data-ttu-id="926ea-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="926ea-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="926ea-104">nombre</span><span class="sxs-lookup"><span data-stu-id="926ea-104">Name</span></span>

<span data-ttu-id="926ea-105">`dotnet`: herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="926ea-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="926ea-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="926ea-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="926ea-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="926ea-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="926ea-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="926ea-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="926ea-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="926ea-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="926ea-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="926ea-110">Description</span></span>

<span data-ttu-id="926ea-111">`dotnet` es una herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="926ea-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="926ea-112">Expone los comandos que realizan tareas específicas, como [`dotnet build`](dotnet-build.md) y [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="926ea-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="926ea-113">Cada comando define sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="926ea-113">Each command defines its own arguments.</span></span> <span data-ttu-id="926ea-114">Escriba `--help` después de cada comando para acceder a una breve documentación de ayuda.</span><span class="sxs-lookup"><span data-stu-id="926ea-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="926ea-115">`dotnet` puede usarse para ejecutar aplicaciones si se especifica un archivo DLL de aplicación, como `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="926ea-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="926ea-116">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="926ea-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="926ea-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="926ea-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="926ea-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="926ea-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="926ea-119">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="926ea-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="926ea-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="926ea-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="926ea-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="926ea-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="926ea-122">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="926ea-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="926ea-123">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="926ea-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="926ea-124">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="926ea-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="926ea-125">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="926ea-126">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="926ea-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="926ea-127">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="926ea-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="926ea-128">Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="926ea-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="926ea-129">`N` puede ser:</span><span class="sxs-lookup"><span data-stu-id="926ea-129">`N` can be:</span></span>
* <span data-ttu-id="926ea-130">`0`: se deshabilita la puesta al día incluso de las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="926ea-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="926ea-131">`1`: puesta al día de la versión secundaria, pero no de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="926ea-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="926ea-132">Éste es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="926ea-132">This is the default behavior.</span></span>
* <span data-ttu-id="926ea-133">`2`: puesta al día de las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="926ea-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="926ea-134">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="926ea-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="926ea-135">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="926ea-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="926ea-136">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="926ea-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="926ea-137">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="926ea-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="926ea-138">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="926ea-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="926ea-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="926ea-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="926ea-140">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="926ea-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="926ea-141">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="926ea-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="926ea-142">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="926ea-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="926ea-143">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="926ea-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="926ea-144">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="926ea-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="926ea-145">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="926ea-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="926ea-146">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="926ea-147">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="926ea-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="926ea-148">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="926ea-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="926ea-149">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="926ea-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="926ea-150">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="926ea-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="926ea-151">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="926ea-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="926ea-152">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="926ea-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="926ea-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="926ea-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="926ea-154">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="926ea-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="926ea-155">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="926ea-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="926ea-156">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="926ea-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="926ea-157">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="926ea-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="926ea-158">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="926ea-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="926ea-159">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="926ea-160">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="926ea-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="926ea-161">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="926ea-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="926ea-162">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="926ea-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="926ea-163">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="926ea-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="926ea-164">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="926ea-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="926ea-165">General</span><span class="sxs-lookup"><span data-stu-id="926ea-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="926ea-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="926ea-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="926ea-167">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-167">Command</span></span>                                       | <span data-ttu-id="926ea-168">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="926ea-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="926ea-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="926ea-170">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="926ea-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="926ea-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="926ea-172">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="926ea-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="926ea-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="926ea-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="926ea-174">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="926ea-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="926ea-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="926ea-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="926ea-176">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="926ea-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="926ea-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="926ea-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="926ea-178">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="926ea-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="926ea-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="926ea-180">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="926ea-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="926ea-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="926ea-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="926ea-182">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="926ea-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="926ea-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="926ea-184">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="926ea-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="926ea-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="926ea-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="926ea-186">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="926ea-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="926ea-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="926ea-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="926ea-188">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="926ea-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="926ea-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="926ea-190">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="926ea-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="926ea-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="926ea-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="926ea-192">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="926ea-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="926ea-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="926ea-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="926ea-194">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="926ea-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="926ea-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="926ea-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="926ea-196">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="926ea-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="926ea-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="926ea-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="926ea-198">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-198">Command</span></span>                             | <span data-ttu-id="926ea-199">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="926ea-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="926ea-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="926ea-201">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="926ea-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="926ea-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="926ea-203">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="926ea-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="926ea-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="926ea-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="926ea-205">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="926ea-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="926ea-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="926ea-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="926ea-207">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="926ea-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="926ea-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="926ea-209">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="926ea-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="926ea-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="926ea-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="926ea-211">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="926ea-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="926ea-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="926ea-213">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="926ea-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="926ea-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="926ea-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="926ea-215">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="926ea-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="926ea-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="926ea-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="926ea-217">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="926ea-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="926ea-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="926ea-219">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="926ea-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="926ea-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="926ea-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="926ea-221">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="926ea-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="926ea-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="926ea-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="926ea-223">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="926ea-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="926ea-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="926ea-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="926ea-225">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="926ea-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="926ea-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="926ea-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="926ea-227">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-227">Command</span></span>                             | <span data-ttu-id="926ea-228">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="926ea-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="926ea-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="926ea-230">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="926ea-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="926ea-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="926ea-232">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="926ea-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="926ea-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="926ea-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="926ea-234">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="926ea-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="926ea-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="926ea-236">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="926ea-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="926ea-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="926ea-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="926ea-238">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="926ea-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="926ea-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="926ea-240">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="926ea-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="926ea-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="926ea-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="926ea-242">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="926ea-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="926ea-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="926ea-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="926ea-244">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="926ea-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="926ea-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="926ea-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="926ea-246">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="926ea-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="926ea-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="926ea-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="926ea-248">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="926ea-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="926ea-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="926ea-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="926ea-250">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="926ea-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="926ea-251">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="926ea-251">Project references</span></span>

<span data-ttu-id="926ea-252">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-252">Command</span></span> | <span data-ttu-id="926ea-253">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-253">Function</span></span>
--- | ---
[<span data-ttu-id="926ea-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="926ea-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="926ea-255">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="926ea-255">Adds a project reference.</span></span>
[<span data-ttu-id="926ea-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="926ea-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="926ea-257">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="926ea-257">Lists project references.</span></span>
[<span data-ttu-id="926ea-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="926ea-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="926ea-259">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="926ea-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="926ea-260">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="926ea-260">NuGet packages</span></span>

<span data-ttu-id="926ea-261">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-261">Command</span></span> | <span data-ttu-id="926ea-262">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-262">Function</span></span>
--- | ---
[<span data-ttu-id="926ea-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="926ea-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="926ea-264">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="926ea-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="926ea-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="926ea-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="926ea-266">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="926ea-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="926ea-267">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="926ea-267">NuGet commands</span></span>

<span data-ttu-id="926ea-268">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-268">Command</span></span> | <span data-ttu-id="926ea-269">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-269">Function</span></span>
--- | ---
[<span data-ttu-id="926ea-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="926ea-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="926ea-271">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="926ea-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="926ea-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="926ea-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="926ea-273">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="926ea-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="926ea-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="926ea-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="926ea-275">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="926ea-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="926ea-276">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="926ea-276">Global Tools commands</span></span>

<span data-ttu-id="926ea-277">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="926ea-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="926ea-278">Comando</span><span class="sxs-lookup"><span data-stu-id="926ea-278">Command</span></span> | <span data-ttu-id="926ea-279">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-279">Function</span></span>
--- | ---
[<span data-ttu-id="926ea-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="926ea-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="926ea-281">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="926ea-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="926ea-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="926ea-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="926ea-283">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="926ea-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="926ea-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="926ea-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="926ea-285">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="926ea-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="926ea-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="926ea-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="926ea-287">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="926ea-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="926ea-288">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="926ea-288">Additional tools</span></span>

<span data-ttu-id="926ea-289">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="926ea-290">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="926ea-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="926ea-291">Herramienta</span><span class="sxs-lookup"><span data-stu-id="926ea-291">Tool</span></span>                                              | <span data-ttu-id="926ea-292">Función</span><span class="sxs-lookup"><span data-stu-id="926ea-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="926ea-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="926ea-293">dev-certs</span></span>                                         | <span data-ttu-id="926ea-294">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="926ea-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="926ea-295">ef</span><span class="sxs-lookup"><span data-stu-id="926ea-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="926ea-296">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="926ea-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="926ea-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="926ea-297">sql-cache</span></span>                                         | <span data-ttu-id="926ea-298">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="926ea-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="926ea-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="926ea-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="926ea-300">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="926ea-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="926ea-301">watch</span><span class="sxs-lookup"><span data-stu-id="926ea-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="926ea-302">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="926ea-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="926ea-303">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="926ea-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="926ea-304">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="926ea-304">Examples</span></span>

<span data-ttu-id="926ea-305">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="926ea-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="926ea-306">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="926ea-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="926ea-307">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="926ea-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="926ea-308">Ejecutar un archivo DLL de aplicación como `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="926ea-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="926ea-309">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="926ea-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="926ea-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="926ea-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="926ea-311">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="926ea-311">The primary package cache.</span></span> <span data-ttu-id="926ea-312">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="926ea-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="926ea-313">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="926ea-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="926ea-314">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="926ea-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="926ea-315">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="926ea-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="926ea-316">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="926ea-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="926ea-317">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="926ea-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="926ea-318">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="926ea-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="926ea-319">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="926ea-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="926ea-320">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="926ea-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="926ea-321">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="926ea-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="926ea-322">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="926ea-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="926ea-323">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="926ea-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="926ea-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="926ea-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="926ea-325">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="926ea-325">The primary package cache.</span></span> <span data-ttu-id="926ea-326">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="926ea-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="926ea-327">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="926ea-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="926ea-328">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="926ea-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="926ea-329">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="926ea-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="926ea-330">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="926ea-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="926ea-331">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="926ea-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="926ea-332">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="926ea-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="926ea-333">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="926ea-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="926ea-334">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="926ea-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="926ea-335">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="926ea-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="926ea-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="926ea-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="926ea-337">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="926ea-337">The primary package cache.</span></span> <span data-ttu-id="926ea-338">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="926ea-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="926ea-339">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="926ea-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="926ea-340">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="926ea-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="926ea-341">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="926ea-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="926ea-342">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="926ea-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="926ea-343">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="926ea-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
