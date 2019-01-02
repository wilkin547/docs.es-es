---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
ms.date: 06/04/2018
ms.openlocfilehash: 081f295cc71c3cd46de465efb12f131e7b2d36d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170862"
---
# <a name="dotnet-command"></a><span data-ttu-id="af831-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="af831-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="af831-104">nombre</span><span class="sxs-lookup"><span data-stu-id="af831-104">Name</span></span>

<span data-ttu-id="af831-105">`dotnet`: herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="af831-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="af831-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="af831-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="af831-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="af831-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="af831-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="af831-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af831-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af831-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="af831-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="af831-110">Description</span></span>

<span data-ttu-id="af831-111">`dotnet` es una herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="af831-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="af831-112">Expone los comandos que realizan tareas específicas, como [`dotnet build`](dotnet-build.md) y [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="af831-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="af831-113">Cada comando define sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="af831-113">Each command defines its own arguments.</span></span> <span data-ttu-id="af831-114">Escriba `--help` después de cada comando para acceder a una breve documentación de ayuda.</span><span class="sxs-lookup"><span data-stu-id="af831-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="af831-115">`dotnet` puede usarse para ejecutar aplicaciones si se especifica un archivo DLL de aplicación, como `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="af831-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="af831-116">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="af831-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="af831-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="af831-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="af831-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="af831-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="af831-119">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="af831-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="af831-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="af831-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="af831-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="af831-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="af831-122">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af831-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="af831-123">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="af831-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="af831-124">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="af831-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="af831-125">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="af831-126">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="af831-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="af831-127">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="af831-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="af831-128">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="af831-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="af831-129">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="af831-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="af831-130">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="af831-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="af831-131">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="af831-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="af831-132">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="af831-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="af831-133">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="af831-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="af831-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="af831-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="af831-135">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="af831-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="af831-136">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="af831-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="af831-137">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="af831-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="af831-138">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af831-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="af831-139">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="af831-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="af831-140">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="af831-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="af831-141">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="af831-142">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="af831-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="af831-143">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="af831-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="af831-144">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="af831-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="af831-145">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="af831-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="af831-146">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="af831-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="af831-147">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="af831-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af831-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af831-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="af831-149">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="af831-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="af831-150">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="af831-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="af831-151">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af831-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="af831-152">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="af831-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="af831-153">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="af831-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="af831-154">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="af831-155">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="af831-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="af831-156">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="af831-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="af831-157">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="af831-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="af831-158">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="af831-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="af831-159">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="af831-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="af831-160">General</span><span class="sxs-lookup"><span data-stu-id="af831-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="af831-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="af831-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="af831-162">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-162">Command</span></span>                                       | <span data-ttu-id="af831-163">Función</span><span class="sxs-lookup"><span data-stu-id="af831-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="af831-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="af831-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="af831-165">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="af831-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="af831-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="af831-167">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="af831-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="af831-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="af831-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="af831-169">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="af831-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="af831-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="af831-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="af831-171">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="af831-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="af831-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="af831-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="af831-173">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="af831-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="af831-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="af831-175">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="af831-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="af831-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="af831-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="af831-177">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="af831-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="af831-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="af831-179">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="af831-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="af831-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="af831-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="af831-181">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="af831-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="af831-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="af831-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="af831-183">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="af831-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="af831-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="af831-185">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="af831-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="af831-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="af831-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="af831-187">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="af831-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="af831-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="af831-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="af831-189">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af831-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="af831-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="af831-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="af831-191">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="af831-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="af831-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="af831-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="af831-193">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-193">Command</span></span>                             | <span data-ttu-id="af831-194">Función</span><span class="sxs-lookup"><span data-stu-id="af831-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="af831-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="af831-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="af831-196">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="af831-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="af831-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="af831-198">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="af831-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="af831-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="af831-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="af831-200">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="af831-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="af831-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="af831-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="af831-202">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="af831-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="af831-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="af831-204">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="af831-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="af831-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="af831-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="af831-206">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="af831-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="af831-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="af831-208">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="af831-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="af831-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="af831-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="af831-210">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="af831-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="af831-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="af831-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="af831-212">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="af831-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="af831-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="af831-214">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="af831-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="af831-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="af831-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="af831-216">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="af831-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="af831-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="af831-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="af831-218">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af831-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="af831-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="af831-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="af831-220">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="af831-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af831-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af831-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="af831-222">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-222">Command</span></span>                             | <span data-ttu-id="af831-223">Función</span><span class="sxs-lookup"><span data-stu-id="af831-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="af831-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="af831-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="af831-225">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="af831-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="af831-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="af831-227">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="af831-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="af831-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="af831-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="af831-229">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="af831-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="af831-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="af831-231">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="af831-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="af831-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="af831-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="af831-233">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="af831-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="af831-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="af831-235">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="af831-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="af831-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="af831-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="af831-237">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="af831-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="af831-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="af831-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="af831-239">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="af831-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="af831-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="af831-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="af831-241">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="af831-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="af831-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="af831-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="af831-243">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="af831-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="af831-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="af831-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="af831-245">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="af831-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="af831-246">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="af831-246">Project references</span></span>

<span data-ttu-id="af831-247">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-247">Command</span></span> | <span data-ttu-id="af831-248">Función</span><span class="sxs-lookup"><span data-stu-id="af831-248">Function</span></span>
--- | ---
[<span data-ttu-id="af831-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="af831-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="af831-250">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="af831-250">Adds a project reference.</span></span>
[<span data-ttu-id="af831-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="af831-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="af831-252">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="af831-252">Lists project references.</span></span>
[<span data-ttu-id="af831-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="af831-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="af831-254">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="af831-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="af831-255">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="af831-255">NuGet packages</span></span>

<span data-ttu-id="af831-256">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-256">Command</span></span> | <span data-ttu-id="af831-257">Función</span><span class="sxs-lookup"><span data-stu-id="af831-257">Function</span></span>
--- | ---
[<span data-ttu-id="af831-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="af831-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="af831-259">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="af831-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="af831-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="af831-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="af831-261">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="af831-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="af831-262">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="af831-262">NuGet commands</span></span>

<span data-ttu-id="af831-263">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-263">Command</span></span> | <span data-ttu-id="af831-264">Función</span><span class="sxs-lookup"><span data-stu-id="af831-264">Function</span></span>
--- | ---
[<span data-ttu-id="af831-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="af831-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="af831-266">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="af831-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="af831-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="af831-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="af831-268">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="af831-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="af831-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="af831-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="af831-270">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="af831-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="af831-271">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="af831-271">Global Tools commands</span></span>

<span data-ttu-id="af831-272">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="af831-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="af831-273">Comando</span><span class="sxs-lookup"><span data-stu-id="af831-273">Command</span></span> | <span data-ttu-id="af831-274">Función</span><span class="sxs-lookup"><span data-stu-id="af831-274">Function</span></span>
--- | ---
[<span data-ttu-id="af831-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="af831-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="af831-276">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="af831-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="af831-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="af831-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="af831-278">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="af831-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="af831-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="af831-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="af831-280">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="af831-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="af831-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="af831-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="af831-282">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="af831-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="af831-283">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="af831-283">Additional tools</span></span>

<span data-ttu-id="af831-284">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af831-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="af831-285">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="af831-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="af831-286">Herramienta</span><span class="sxs-lookup"><span data-stu-id="af831-286">Tool</span></span>                                              | <span data-ttu-id="af831-287">Función</span><span class="sxs-lookup"><span data-stu-id="af831-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="af831-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="af831-288">dev-certs</span></span>                                         | <span data-ttu-id="af831-289">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="af831-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="af831-290">ef</span><span class="sxs-lookup"><span data-stu-id="af831-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="af831-291">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="af831-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="af831-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="af831-292">sql-cache</span></span>                                         | <span data-ttu-id="af831-293">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af831-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="af831-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="af831-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="af831-295">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="af831-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="af831-296">watch</span><span class="sxs-lookup"><span data-stu-id="af831-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="af831-297">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="af831-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="af831-298">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="af831-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="af831-299">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="af831-299">Examples</span></span>

<span data-ttu-id="af831-300">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="af831-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="af831-301">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="af831-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="af831-302">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="af831-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="af831-303">Ejecutar un archivo DLL de aplicación como `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="af831-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="af831-304">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="af831-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="af831-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="af831-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="af831-306">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="af831-306">The primary package cache.</span></span> <span data-ttu-id="af831-307">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="af831-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="af831-308">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af831-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="af831-309">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af831-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="af831-310">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="af831-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="af831-311">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="af831-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="af831-312">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="af831-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="af831-313">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="af831-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="af831-314">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="af831-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="af831-315">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="af831-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="af831-316">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="af831-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="af831-317">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="af831-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="af831-318">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="af831-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="af831-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="af831-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="af831-320">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="af831-320">The primary package cache.</span></span> <span data-ttu-id="af831-321">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="af831-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="af831-322">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af831-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="af831-323">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af831-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="af831-324">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="af831-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="af831-325">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="af831-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="af831-326">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="af831-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="af831-327">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="af831-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="af831-328">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="af831-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="af831-329">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="af831-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="af831-330">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="af831-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af831-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af831-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="af831-332">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="af831-332">The primary package cache.</span></span> <span data-ttu-id="af831-333">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="af831-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="af831-334">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af831-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="af831-335">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af831-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="af831-336">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="af831-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="af831-337">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="af831-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="af831-338">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="af831-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
