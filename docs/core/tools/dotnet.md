---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
ms.date: 06/04/2018
ms.openlocfilehash: 328fd24cd72110bd235c177398f6f147fbb9d144
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373747"
---
# <a name="dotnet-command"></a><span data-ttu-id="9cc5b-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="9cc5b-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9cc5b-104">nombre</span><span class="sxs-lookup"><span data-stu-id="9cc5b-104">Name</span></span>

<span data-ttu-id="9cc5b-105">`dotnet`: herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9cc5b-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9cc5b-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cc5b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cc5b-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cc5b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cc5b-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cc5b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cc5b-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="9cc5b-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9cc5b-110">Description</span></span>

<span data-ttu-id="9cc5b-111">`dotnet` es una herramienta para administrar archivos binarios y código fuente de .NET.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="9cc5b-112">Expone los comandos que realizan tareas específicas, como [`dotnet build`](dotnet-build.md) y [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="9cc5b-113">Cada comando define sus propios argumentos.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-113">Each command defines its own arguments.</span></span> <span data-ttu-id="9cc5b-114">Escriba `--help` después de cada comando para acceder a una breve documentación de ayuda.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="9cc5b-115">`dotnet` puede usarse para ejecutar aplicaciones si se especifica un archivo DLL de aplicación, como `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="9cc5b-116">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="9cc5b-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="9cc5b-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cc5b-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cc5b-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="9cc5b-119">Ruta de acceso a un archivo *.deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="9cc5b-120">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="9cc5b-121">Ruta de acceso a un archivo *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="9cc5b-122">Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="9cc5b-123">Para más información sobre este archivo, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="9cc5b-124">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="9cc5b-125">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="9cc5b-126">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="9cc5b-127">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="9cc5b-128">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="9cc5b-129">Muestra los tiempos de ejecución de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="9cc5b-130">Muestra los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="9cc5b-131">Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="9cc5b-132">`N` puede ser:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-132">`N` can be:</span></span>
- <span data-ttu-id="9cc5b-133">`0`: se deshabilita la puesta al día incluso de las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="9cc5b-134">`1`: puesta al día de la versión secundaria, pero no de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="9cc5b-135">Éste es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-135">This is the default behavior.</span></span>
- <span data-ttu-id="9cc5b-136">`2`: puesta al día de las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="9cc5b-137">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="9cc5b-138">Ruta de acceso a un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="9cc5b-139">Un archivo *runtimeconfig.json* es un archivo de configuración que contiene los valores de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="9cc5b-140">Para más información, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9cc5b-141">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9cc5b-142">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="9cc5b-143">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="9cc5b-144">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cc5b-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cc5b-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="9cc5b-146">Ruta de acceso a un archivo *.deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="9cc5b-147">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="9cc5b-148">Ruta de acceso a un archivo *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="9cc5b-149">Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="9cc5b-150">Para más detalles sobre este archivo, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="9cc5b-151">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="9cc5b-152">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="9cc5b-153">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="9cc5b-154">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="9cc5b-155">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="9cc5b-156">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="9cc5b-157">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="9cc5b-158">Ruta de acceso a un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="9cc5b-159">Un archivo *runtimeconfig.json* es un archivo de configuración que contiene los valores de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="9cc5b-160">Para más detalles, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9cc5b-161">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9cc5b-162">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="9cc5b-163">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="9cc5b-164">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cc5b-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cc5b-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="9cc5b-166">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="9cc5b-167">Ruta de acceso a un archivo *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="9cc5b-168">Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="9cc5b-169">Para más detalles sobre este archivo, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="9cc5b-170">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="9cc5b-171">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="9cc5b-172">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="9cc5b-173">`dotnet --help` imprime una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="9cc5b-174">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="9cc5b-175">Ruta de acceso a un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="9cc5b-176">Un archivo *runtimeconfig.json* es un archivo de configuración que contiene los valores de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="9cc5b-177">Para más detalles, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9cc5b-178">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9cc5b-179">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="9cc5b-180">Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="9cc5b-181">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="9cc5b-182">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="9cc5b-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="9cc5b-183">General</span><span class="sxs-lookup"><span data-stu-id="9cc5b-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cc5b-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cc5b-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="9cc5b-185">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-185">Command</span></span>                                       | <span data-ttu-id="9cc5b-186">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="9cc5b-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="9cc5b-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="9cc5b-188">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="9cc5b-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="9cc5b-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="9cc5b-190">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="9cc5b-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="9cc5b-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="9cc5b-192">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="9cc5b-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="9cc5b-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="9cc5b-194">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="9cc5b-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="9cc5b-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="9cc5b-196">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="9cc5b-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="9cc5b-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="9cc5b-198">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="9cc5b-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cc5b-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="9cc5b-200">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="9cc5b-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="9cc5b-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="9cc5b-202">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="9cc5b-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="9cc5b-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="9cc5b-204">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="9cc5b-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="9cc5b-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="9cc5b-206">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="9cc5b-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="9cc5b-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="9cc5b-208">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="9cc5b-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="9cc5b-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="9cc5b-210">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="9cc5b-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="9cc5b-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="9cc5b-212">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="9cc5b-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="9cc5b-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="9cc5b-214">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cc5b-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cc5b-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="9cc5b-216">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-216">Command</span></span>                             | <span data-ttu-id="9cc5b-217">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="9cc5b-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="9cc5b-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="9cc5b-219">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="9cc5b-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="9cc5b-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="9cc5b-221">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="9cc5b-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="9cc5b-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="9cc5b-223">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="9cc5b-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="9cc5b-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="9cc5b-225">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="9cc5b-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="9cc5b-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="9cc5b-227">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="9cc5b-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cc5b-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="9cc5b-229">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="9cc5b-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="9cc5b-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="9cc5b-231">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="9cc5b-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="9cc5b-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="9cc5b-233">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="9cc5b-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="9cc5b-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="9cc5b-235">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="9cc5b-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="9cc5b-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="9cc5b-237">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="9cc5b-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="9cc5b-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="9cc5b-239">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="9cc5b-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="9cc5b-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="9cc5b-241">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="9cc5b-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="9cc5b-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="9cc5b-243">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cc5b-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cc5b-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="9cc5b-245">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-245">Command</span></span>                             | <span data-ttu-id="9cc5b-246">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="9cc5b-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="9cc5b-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="9cc5b-248">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="9cc5b-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="9cc5b-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="9cc5b-250">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="9cc5b-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="9cc5b-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="9cc5b-252">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="9cc5b-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="9cc5b-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="9cc5b-254">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="9cc5b-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cc5b-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="9cc5b-256">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="9cc5b-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="9cc5b-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="9cc5b-258">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="9cc5b-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="9cc5b-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="9cc5b-260">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="9cc5b-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="9cc5b-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="9cc5b-262">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="9cc5b-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="9cc5b-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="9cc5b-264">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="9cc5b-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="9cc5b-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="9cc5b-266">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="9cc5b-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="9cc5b-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="9cc5b-268">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="9cc5b-269">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="9cc5b-269">Project references</span></span>

<span data-ttu-id="9cc5b-270">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-270">Command</span></span> | <span data-ttu-id="9cc5b-271">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-271">Function</span></span>
--- | ---
[<span data-ttu-id="9cc5b-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="9cc5b-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="9cc5b-273">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-273">Adds a project reference.</span></span>
[<span data-ttu-id="9cc5b-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="9cc5b-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="9cc5b-275">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-275">Lists project references.</span></span>
[<span data-ttu-id="9cc5b-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="9cc5b-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="9cc5b-277">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="9cc5b-278">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="9cc5b-278">NuGet packages</span></span>

<span data-ttu-id="9cc5b-279">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-279">Command</span></span> | <span data-ttu-id="9cc5b-280">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-280">Function</span></span>
--- | ---
[<span data-ttu-id="9cc5b-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="9cc5b-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="9cc5b-282">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="9cc5b-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="9cc5b-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="9cc5b-284">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="9cc5b-285">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="9cc5b-285">NuGet commands</span></span>

<span data-ttu-id="9cc5b-286">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-286">Command</span></span> | <span data-ttu-id="9cc5b-287">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-287">Function</span></span>
--- | ---
[<span data-ttu-id="9cc5b-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="9cc5b-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="9cc5b-289">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="9cc5b-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="9cc5b-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="9cc5b-291">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="9cc5b-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="9cc5b-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="9cc5b-293">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="9cc5b-294">Comandos de herramientas globales</span><span class="sxs-lookup"><span data-stu-id="9cc5b-294">Global Tools commands</span></span>

<span data-ttu-id="9cc5b-295">Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="9cc5b-296">Comando</span><span class="sxs-lookup"><span data-stu-id="9cc5b-296">Command</span></span> | <span data-ttu-id="9cc5b-297">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-297">Function</span></span>
--- | ---
[<span data-ttu-id="9cc5b-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="9cc5b-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="9cc5b-299">Instala una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="9cc5b-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="9cc5b-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="9cc5b-301">Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="9cc5b-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="9cc5b-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="9cc5b-303">Desinstala una herramienta global de su equipo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="9cc5b-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="9cc5b-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="9cc5b-305">Actualiza una herramienta global en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="9cc5b-306">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="9cc5b-306">Additional tools</span></span>

<span data-ttu-id="9cc5b-307">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="9cc5b-308">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="9cc5b-309">Herramienta</span><span class="sxs-lookup"><span data-stu-id="9cc5b-309">Tool</span></span>                                              | <span data-ttu-id="9cc5b-310">Función</span><span class="sxs-lookup"><span data-stu-id="9cc5b-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="9cc5b-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="9cc5b-311">dev-certs</span></span>                                         | <span data-ttu-id="9cc5b-312">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="9cc5b-313">ef</span><span class="sxs-lookup"><span data-stu-id="9cc5b-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="9cc5b-314">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="9cc5b-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="9cc5b-315">sql-cache</span></span>                                         | <span data-ttu-id="9cc5b-316">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="9cc5b-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="9cc5b-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="9cc5b-318">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="9cc5b-319">watch</span><span class="sxs-lookup"><span data-stu-id="9cc5b-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="9cc5b-320">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="9cc5b-321">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="9cc5b-322">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9cc5b-322">Examples</span></span>

<span data-ttu-id="9cc5b-323">Crea una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="9cc5b-324">Restauración de dependencias de una aplicación determinada:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="9cc5b-325">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="9cc5b-326">Ejecutar un archivo DLL de aplicación como `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="9cc5b-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="9cc5b-327">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="9cc5b-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cc5b-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cc5b-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="9cc5b-329">La carpeta de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-329">The global packages folder.</span></span> <span data-ttu-id="9cc5b-330">Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="9cc5b-331">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="9cc5b-332">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="9cc5b-333">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="9cc5b-334">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="9cc5b-335">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="9cc5b-336">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="9cc5b-337">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="9cc5b-338">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="9cc5b-339">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="9cc5b-340">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="9cc5b-341">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cc5b-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cc5b-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="9cc5b-343">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-343">The primary package cache.</span></span> <span data-ttu-id="9cc5b-344">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="9cc5b-345">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="9cc5b-346">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="9cc5b-347">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="9cc5b-348">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="9cc5b-349">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="9cc5b-350">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="9cc5b-351">Si no se establece, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="9cc5b-352">Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="9cc5b-353">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cc5b-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cc5b-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="9cc5b-355">La caché del paquete principal.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-355">The primary package cache.</span></span> <span data-ttu-id="9cc5b-356">Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="9cc5b-357">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="9cc5b-358">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="9cc5b-359">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="9cc5b-360">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="9cc5b-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="9cc5b-361">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="9cc5b-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="9cc5b-362">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cc5b-362">See also</span></span>

- [<span data-ttu-id="9cc5b-363">Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="9cc5b-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
