---
title: 'Comando dotnet: CLI de .NET Core'
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44079821"
---
# <a name="dotnet-command"></a><span data-ttu-id="a55a6-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="a55a6-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a55a6-104">nombre</span><span class="sxs-lookup"><span data-stu-id="a55a6-104">Name</span></span>

<span data-ttu-id="a55a6-105">`dotnet`: herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="a55a6-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a55a6-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="a55a6-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a55a6-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a55a6-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a55a6-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a55a6-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a55a6-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a55a6-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="a55a6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a55a6-110">Description</span></span>

<span data-ttu-id="a55a6-111">`dotnet` es una herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="a55a6-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="a55a6-112">Expone los comandos que realizan tareas específicas, como [`dotnet build`](dotnet-build.md) y [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="a55a6-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="a55a6-113">Cada comando define sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="a55a6-113">Each command defines its own arguments.</span></span> <span data-ttu-id="a55a6-114">Escriba `--help` después de cada comando para acceder a una breve documentación de ayuda.</span><span class="sxs-lookup"><span data-stu-id="a55a6-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="a55a6-115">`dotnet` puede usarse para ejecutar aplicaciones si se especifica un archivo DLL de aplicación, como `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="a55a6-116">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="a55a6-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="a55a6-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a55a6-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a55a6-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="a55a6-119">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="a55a6-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="a55a6-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="a55a6-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="a55a6-121">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a55a6-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="a55a6-122">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="a55a6-123">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="a55a6-124">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a55a6-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="a55a6-125">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="a55a6-126">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="a55a6-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="a55a6-127">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="a55a6-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="a55a6-128">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="a55a6-129">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="a55a6-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a55a6-130">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="a55a6-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a55a6-131">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a55a6-132">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="a55a6-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="a55a6-133">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="a55a6-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a55a6-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a55a6-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="a55a6-135">Ruta de acceso a archivo *deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="a55a6-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="a55a6-136">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="a55a6-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="a55a6-137">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a55a6-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="a55a6-138">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="a55a6-139">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="a55a6-140">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a55a6-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="a55a6-141">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="a55a6-142">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="a55a6-143">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="a55a6-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a55a6-144">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="a55a6-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a55a6-145">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a55a6-146">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="a55a6-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="a55a6-147">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="a55a6-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a55a6-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a55a6-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="a55a6-149">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="a55a6-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="a55a6-150">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a55a6-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="a55a6-151">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="a55a6-152">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="a55a6-153">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a55a6-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="a55a6-154">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a55a6-155">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="a55a6-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a55a6-156">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a55a6-157">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="a55a6-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="a55a6-158">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="a55a6-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="a55a6-159">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="a55a6-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="a55a6-160">General</span><span class="sxs-lookup"><span data-stu-id="a55a6-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a55a6-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a55a6-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="a55a6-162">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-162">Command</span></span>                                       | <span data-ttu-id="a55a6-163">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="a55a6-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="a55a6-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="a55a6-165">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="a55a6-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="a55a6-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="a55a6-167">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="a55a6-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a55a6-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="a55a6-169">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="a55a6-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="a55a6-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="a55a6-171">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="a55a6-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="a55a6-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="a55a6-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="a55a6-173">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="a55a6-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="a55a6-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="a55a6-175">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a55a6-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="a55a6-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a55a6-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="a55a6-177">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="a55a6-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a55a6-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="a55a6-179">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="a55a6-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="a55a6-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="a55a6-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="a55a6-181">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="a55a6-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="a55a6-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="a55a6-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="a55a6-183">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="a55a6-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a55a6-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="a55a6-185">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="a55a6-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="a55a6-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="a55a6-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="a55a6-187">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="a55a6-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="a55a6-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="a55a6-189">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="a55a6-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="a55a6-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="a55a6-191">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a55a6-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a55a6-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a55a6-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="a55a6-193">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-193">Command</span></span>                             | <span data-ttu-id="a55a6-194">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="a55a6-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="a55a6-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="a55a6-196">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="a55a6-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a55a6-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="a55a6-198">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="a55a6-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="a55a6-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="a55a6-200">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="a55a6-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="a55a6-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="a55a6-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="a55a6-202">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="a55a6-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="a55a6-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="a55a6-204">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a55a6-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="a55a6-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a55a6-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="a55a6-206">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="a55a6-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a55a6-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="a55a6-208">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="a55a6-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="a55a6-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="a55a6-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="a55a6-210">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="a55a6-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="a55a6-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="a55a6-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="a55a6-212">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="a55a6-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a55a6-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="a55a6-214">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="a55a6-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="a55a6-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="a55a6-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="a55a6-216">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="a55a6-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="a55a6-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="a55a6-218">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="a55a6-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="a55a6-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="a55a6-220">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a55a6-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a55a6-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a55a6-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="a55a6-222">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-222">Command</span></span>                             | <span data-ttu-id="a55a6-223">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="a55a6-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="a55a6-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="a55a6-225">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="a55a6-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a55a6-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="a55a6-227">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a55a6-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="a55a6-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="a55a6-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="a55a6-229">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="a55a6-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="a55a6-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="a55a6-231">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a55a6-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="a55a6-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a55a6-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="a55a6-233">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="a55a6-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a55a6-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="a55a6-235">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="a55a6-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="a55a6-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="a55a6-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="a55a6-237">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="a55a6-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="a55a6-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="a55a6-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="a55a6-239">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="a55a6-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a55a6-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="a55a6-241">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="a55a6-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="a55a6-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="a55a6-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="a55a6-243">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="a55a6-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="a55a6-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="a55a6-245">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a55a6-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="a55a6-246">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="a55a6-246">Project references</span></span>

<span data-ttu-id="a55a6-247">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-247">Command</span></span> | <span data-ttu-id="a55a6-248">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-248">Function</span></span>
--- | ---
[<span data-ttu-id="a55a6-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="a55a6-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="a55a6-250">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a55a6-250">Adds a project reference.</span></span>
[<span data-ttu-id="a55a6-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="a55a6-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="a55a6-252">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a55a6-252">Lists project references.</span></span>
[<span data-ttu-id="a55a6-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="a55a6-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="a55a6-254">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a55a6-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="a55a6-255">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="a55a6-255">NuGet packages</span></span>

<span data-ttu-id="a55a6-256">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-256">Command</span></span> | <span data-ttu-id="a55a6-257">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-257">Function</span></span>
--- | ---
[<span data-ttu-id="a55a6-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="a55a6-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="a55a6-259">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="a55a6-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="a55a6-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="a55a6-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="a55a6-261">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="a55a6-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="a55a6-262">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="a55a6-262">NuGet commands</span></span>

<span data-ttu-id="a55a6-263">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-263">Command</span></span> | <span data-ttu-id="a55a6-264">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-264">Function</span></span>
--- | ---
[<span data-ttu-id="a55a6-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="a55a6-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="a55a6-266">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="a55a6-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="a55a6-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="a55a6-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="a55a6-268">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="a55a6-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="a55a6-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="a55a6-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="a55a6-270">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="a55a6-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="a55a6-271">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="a55a6-271">Global Tools commands</span></span>

<span data-ttu-id="a55a6-272">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="a55a6-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="a55a6-273">Comando</span><span class="sxs-lookup"><span data-stu-id="a55a6-273">Command</span></span> | <span data-ttu-id="a55a6-274">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-274">Function</span></span>
--- | ---
[<span data-ttu-id="a55a6-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="a55a6-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="a55a6-276">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a55a6-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="a55a6-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="a55a6-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="a55a6-278">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="a55a6-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="a55a6-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="a55a6-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="a55a6-280">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="a55a6-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="a55a6-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="a55a6-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="a55a6-282">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a55a6-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="a55a6-283">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="a55a6-283">Additional tools</span></span>

<span data-ttu-id="a55a6-284">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="a55a6-285">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a55a6-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="a55a6-286">Herramienta</span><span class="sxs-lookup"><span data-stu-id="a55a6-286">Tool</span></span>                                              | <span data-ttu-id="a55a6-287">Función</span><span class="sxs-lookup"><span data-stu-id="a55a6-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="a55a6-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="a55a6-288">dev-certs</span></span>                                         | <span data-ttu-id="a55a6-289">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a55a6-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="a55a6-290">ef</span><span class="sxs-lookup"><span data-stu-id="a55a6-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="a55a6-291">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="a55a6-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="a55a6-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="a55a6-292">sql-cache</span></span>                                         | <span data-ttu-id="a55a6-293">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a55a6-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="a55a6-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="a55a6-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="a55a6-295">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a55a6-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="a55a6-296">watch</span><span class="sxs-lookup"><span data-stu-id="a55a6-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="a55a6-297">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="a55a6-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="a55a6-298">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="a55a6-299">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a55a6-299">Examples</span></span>

<span data-ttu-id="a55a6-300">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="a55a6-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="a55a6-301">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="a55a6-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="a55a6-302">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="a55a6-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="a55a6-303">Ejecutar un archivo DLL de aplicación como `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="a55a6-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="a55a6-304">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="a55a6-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a55a6-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a55a6-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="a55a6-306">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="a55a6-306">The primary package cache.</span></span> <span data-ttu-id="a55a6-307">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="a55a6-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="a55a6-308">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="a55a6-309">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a55a6-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="a55a6-310">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="a55a6-311">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="a55a6-312">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="a55a6-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="a55a6-313">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="a55a6-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="a55a6-314">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="a55a6-315">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="a55a6-316">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="a55a6-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="a55a6-317">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="a55a6-318">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="a55a6-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a55a6-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a55a6-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="a55a6-320">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="a55a6-320">The primary package cache.</span></span> <span data-ttu-id="a55a6-321">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="a55a6-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="a55a6-322">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="a55a6-323">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a55a6-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="a55a6-324">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="a55a6-325">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="a55a6-326">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="a55a6-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="a55a6-327">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="a55a6-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="a55a6-328">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a55a6-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="a55a6-329">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="a55a6-330">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="a55a6-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a55a6-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a55a6-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="a55a6-332">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="a55a6-332">The primary package cache.</span></span> <span data-ttu-id="a55a6-333">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="a55a6-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="a55a6-334">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55a6-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="a55a6-335">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a55a6-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="a55a6-336">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="a55a6-337">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="a55a6-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="a55a6-338">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="a55a6-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
