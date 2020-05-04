---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para la CLI de .NET Core) y su uso.
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739076"
---
# <a name="dotnet-command"></a><span data-ttu-id="4145e-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="4145e-103">dotnet command</span></span>

<span data-ttu-id="4145e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4145e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4145e-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4145e-105">Name</span></span>

<span data-ttu-id="4145e-106">`dotnet`: controlador genérico de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4145e-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4145e-107">Synopsis</span></span>

<span data-ttu-id="4145e-108">Para obtener información sobre los comandos disponibles y el entorno:</span><span class="sxs-lookup"><span data-stu-id="4145e-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="4145e-109">Para ejecutar un comando (se requiere la instalación de un SDK):</span><span class="sxs-lookup"><span data-stu-id="4145e-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="4145e-110">Para ejecutar una aplicación:</span><span class="sxs-lookup"><span data-stu-id="4145e-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="4145e-111">`--roll-forward` está disponible a partir de .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="4145e-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="4145e-112">En .NET Core 2.x, use `--roll-forward-on-no-candidate-fx`.</span><span class="sxs-lookup"><span data-stu-id="4145e-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="4145e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4145e-113">Description</span></span>

<span data-ttu-id="4145e-114">El comando `dotnet` tiene dos funciones:</span><span class="sxs-lookup"><span data-stu-id="4145e-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="4145e-115">Proporciona comandos para trabajar con proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="4145e-116">Por ejemplo, [`dotnet build`](dotnet-build.md) compila un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4145e-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="4145e-117">Cada comando define sus propias opciones y argumentos.</span><span class="sxs-lookup"><span data-stu-id="4145e-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="4145e-118">Todos los comandos admiten la opción `--help` para ver una breve documentación sobre cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="4145e-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="4145e-119">Ejecuta aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="4145e-120">Hay que especificar la ruta de acceso al archivo `.dll` de una aplicación para poder ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="4145e-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="4145e-121">Ejecutar la aplicación significa buscar y ejecutar el punto de entrada, que en el caso de las aplicaciones de consola es el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="4145e-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="4145e-122">Por ejemplo, `dotnet myapp.dll` ejecuta la aplicación `myapp`.</span><span class="sxs-lookup"><span data-stu-id="4145e-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="4145e-123">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener más información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="4145e-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="4145e-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="4145e-124">Options</span></span>

<span data-ttu-id="4145e-125">Existen distintas opciones disponibles para usar `dotnet` por sí mismo, para ejecutar un comando y para ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4145e-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="4145e-126">Opciones de dotnet por sí mismo</span><span class="sxs-lookup"><span data-stu-id="4145e-126">Options for dotnet by itself</span></span>

<span data-ttu-id="4145e-127">Las siguientes opciones son para usar `dotnet` por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="4145e-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="4145e-128">Por ejemplo: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="4145e-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="4145e-129">Muestran información sobre el entorno.</span><span class="sxs-lookup"><span data-stu-id="4145e-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="4145e-130">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="4145e-131">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="4145e-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="4145e-132">Muestra una lista de los runtime de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="4145e-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="4145e-133">Una versión x86 del SDK muestra solo los runtime x86 y una versión x64 solo los runtime x64.</span><span class="sxs-lookup"><span data-stu-id="4145e-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="4145e-134">Muestra una lista de los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="4145e-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4145e-135">Muestra una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4145e-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="4145e-136">Opciones de SDK para ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="4145e-136">SDK options for running a command</span></span>

<span data-ttu-id="4145e-137">Las siguientes opciones son para usar `dotnet` con un comando.</span><span class="sxs-lookup"><span data-stu-id="4145e-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="4145e-138">Por ejemplo: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4145e-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="4145e-139">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="4145e-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="4145e-140">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="4145e-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4145e-141">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4145e-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4145e-142">Estos no se admiten en todos los comandos.</span><span class="sxs-lookup"><span data-stu-id="4145e-142">Not supported in every command.</span></span> <span data-ttu-id="4145e-143">Vea la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="4145e-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4145e-144">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4145e-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="4145e-145">Cada comando define opciones específicas de ese comando.</span><span class="sxs-lookup"><span data-stu-id="4145e-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="4145e-146">Vea la página de comandos específica para obtener una lista de las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="4145e-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="4145e-147">Definición de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4145e-147">Runtime options</span></span>

<span data-ttu-id="4145e-148">Las siguientes opciones están disponibles cuando `dotnet` ejecuta una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4145e-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="4145e-149">Por ejemplo: `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="4145e-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="4145e-150">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="4145e-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="4145e-151">Ruta de acceso a un archivo *.deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="4145e-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="4145e-152">Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4145e-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4145e-153">Para más información, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="4145e-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="4145e-154">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4145e-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="4145e-155">Ruta de acceso a un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="4145e-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="4145e-156">Un archivo *runtimeconfig.json* es un archivo de configuración que contiene opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4145e-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="4145e-157">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4145e-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="4145e-158">**`--roll-forward-on-no-candidate-fx <N>`** **Disponible en el SDK de .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="4145e-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4145e-159">Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4145e-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="4145e-160">`N` puede ser:</span><span class="sxs-lookup"><span data-stu-id="4145e-160">`N` can be:</span></span>

  - <span data-ttu-id="4145e-161">`0`: se deshabilita la puesta al día incluso de las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="4145e-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="4145e-162">`1`: puesta al día de la versión secundaria, pero no de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="4145e-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="4145e-163">Éste es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4145e-163">This is the default behavior.</span></span>
  - <span data-ttu-id="4145e-164">`2`: puesta al día de las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="4145e-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="4145e-165">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="4145e-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="4145e-166">**`--roll-forward <SETTING>`** **Disponible a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="4145e-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="4145e-167">Controla cómo se aplica la puesta al día en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4145e-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="4145e-168">`SETTING` puede tener uno de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="4145e-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="4145e-169">Si no se especifica, el valor predeterminado es `Minor`.</span><span class="sxs-lookup"><span data-stu-id="4145e-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="4145e-170">`LatestPatch`: la aplicación se pone al día con la última versión de revisión.</span><span class="sxs-lookup"><span data-stu-id="4145e-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="4145e-171">Se deshabilita la puesta al día de versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="4145e-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="4145e-172">`Minor`: la aplicación se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="4145e-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="4145e-173">Si se encuentra la versión secundaria solicitada, se utiliza la directiva LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="4145e-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="4145e-174">`Major`: la aplicación se pone al día con la versión secundaria mínima superior, y con la versión secundaria mínima si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="4145e-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="4145e-175">Si se encuentra la versión principal solicitada, se utiliza la directiva Minor.</span><span class="sxs-lookup"><span data-stu-id="4145e-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="4145e-176">`LatestMinor`: la aplicación e pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="4145e-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="4145e-177">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="4145e-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4145e-178">`LatestMajor`: la aplicación se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="4145e-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="4145e-179">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="4145e-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4145e-180">`Disable`: la aplicación no se pone al día.</span><span class="sxs-lookup"><span data-stu-id="4145e-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="4145e-181">Solo se enlaza a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="4145e-181">Only bind to specified version.</span></span> <span data-ttu-id="4145e-182">No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="4145e-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="4145e-183">Este valor solo se recomienda a efectos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="4145e-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="4145e-184">A excepción de `Disable`, todos los valores usarán la última versión de revisión disponible.</span><span class="sxs-lookup"><span data-stu-id="4145e-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="4145e-185">El comportamiento de puesta al día también se puede configurar en una propiedad de archivo de proyecto, en una propiedad de archivo de configuración de runtime y en una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="4145e-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="4145e-186">Para obtener más información, vea [Puesta al día del runtime de versiones principales](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4145e-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="4145e-187">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="4145e-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="4145e-188">General</span><span class="sxs-lookup"><span data-stu-id="4145e-188">General</span></span>

| <span data-ttu-id="4145e-189">Comando</span><span class="sxs-lookup"><span data-stu-id="4145e-189">Command</span></span>                                       | <span data-ttu-id="4145e-190">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4145e-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4145e-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="4145e-192">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4145e-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="4145e-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="4145e-194">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="4145e-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="4145e-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4145e-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="4145e-196">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="4145e-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="4145e-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="4145e-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="4145e-198">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="4145e-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="4145e-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4145e-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="4145e-200">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4145e-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4145e-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="4145e-202">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4145e-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4145e-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4145e-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="4145e-204">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="4145e-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4145e-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4145e-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="4145e-206">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="4145e-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4145e-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4145e-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="4145e-208">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="4145e-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4145e-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4145e-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="4145e-210">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="4145e-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4145e-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4145e-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="4145e-212">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="4145e-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4145e-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4145e-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="4145e-214">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="4145e-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4145e-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4145e-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="4145e-216">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4145e-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="4145e-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4145e-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="4145e-218">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="4145e-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="4145e-219">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="4145e-219">Project references</span></span>

<span data-ttu-id="4145e-220">Comando</span><span class="sxs-lookup"><span data-stu-id="4145e-220">Command</span></span> | <span data-ttu-id="4145e-221">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-221">Function</span></span>
--- | ---
[<span data-ttu-id="4145e-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="4145e-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="4145e-223">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4145e-223">Adds a project reference.</span></span>
[<span data-ttu-id="4145e-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4145e-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="4145e-225">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4145e-225">Lists project references.</span></span>
[<span data-ttu-id="4145e-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="4145e-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="4145e-227">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4145e-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="4145e-228">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="4145e-228">NuGet packages</span></span>

<span data-ttu-id="4145e-229">Comando</span><span class="sxs-lookup"><span data-stu-id="4145e-229">Command</span></span> | <span data-ttu-id="4145e-230">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-230">Function</span></span>
--- | ---
[<span data-ttu-id="4145e-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4145e-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="4145e-232">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="4145e-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="4145e-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="4145e-234">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="4145e-235">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="4145e-235">NuGet commands</span></span>

<span data-ttu-id="4145e-236">Comando</span><span class="sxs-lookup"><span data-stu-id="4145e-236">Command</span></span> | <span data-ttu-id="4145e-237">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-237">Function</span></span>
--- | ---
[<span data-ttu-id="4145e-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4145e-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="4145e-239">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="4145e-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="4145e-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4145e-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="4145e-241">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="4145e-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="4145e-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="4145e-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="4145e-243">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="4145e-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="4145e-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="4145e-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="4145e-245">Agrega un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="4145e-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="4145e-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="4145e-247">Deshabilita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="4145e-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="4145e-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="4145e-249">Habilita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="4145e-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="4145e-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="4145e-251">Enumera todos los orígenes de NuGet configurados.</span><span class="sxs-lookup"><span data-stu-id="4145e-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="4145e-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="4145e-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="4145e-253">Quita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="4145e-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="4145e-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="4145e-255">Actualiza un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4145e-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="4145e-256">Comandos de herramientas locales, globales y de ruta de acceso de herramientas</span><span class="sxs-lookup"><span data-stu-id="4145e-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="4145e-257">Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4145e-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="4145e-258">Puede encargarse de escribir las herramientas o instalar las escritas por terceros.</span><span class="sxs-lookup"><span data-stu-id="4145e-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="4145e-259">Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="4145e-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="4145e-260">Para obtener más información, vea [Información general sobre las herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4145e-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="4145e-261">Las herramientas globales y de ruta de acceso de herramientas están disponibles a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="4145e-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="4145e-262">Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4145e-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="4145e-263">Comando</span><span class="sxs-lookup"><span data-stu-id="4145e-263">Command</span></span> | <span data-ttu-id="4145e-264">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-264">Function</span></span>
--- | ---
[<span data-ttu-id="4145e-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="4145e-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="4145e-266">Instala una herramienta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4145e-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="4145e-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4145e-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="4145e-268">Muestra todas las herramientas globales, de ruta de acceso de herramientas o locales instaladas actualmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4145e-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="4145e-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="4145e-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="4145e-270">Desinstala una herramienta del equipo.</span><span class="sxs-lookup"><span data-stu-id="4145e-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="4145e-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="4145e-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="4145e-272">Actualiza una herramienta que está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4145e-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="4145e-273">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="4145e-273">Additional tools</span></span>

<span data-ttu-id="4145e-274">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="4145e-275">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="4145e-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="4145e-276">Herramienta</span><span class="sxs-lookup"><span data-stu-id="4145e-276">Tool</span></span>                                              | <span data-ttu-id="4145e-277">Función</span><span class="sxs-lookup"><span data-stu-id="4145e-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="4145e-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="4145e-278">dev-certs</span></span>                                         | <span data-ttu-id="4145e-279">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4145e-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="4145e-280">ef</span><span class="sxs-lookup"><span data-stu-id="4145e-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="4145e-281">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="4145e-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="4145e-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="4145e-282">sql-cache</span></span>                                         | <span data-ttu-id="4145e-283">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4145e-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="4145e-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="4145e-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="4145e-285">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4145e-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="4145e-286">watch</span><span class="sxs-lookup"><span data-stu-id="4145e-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="4145e-287">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="4145e-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="4145e-288">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="4145e-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="4145e-289">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4145e-289">Examples</span></span>

<span data-ttu-id="4145e-290">Cree una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="4145e-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="4145e-291">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="4145e-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="4145e-292">Ejecute una aplicación:</span><span class="sxs-lookup"><span data-stu-id="4145e-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="4145e-293">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="4145e-293">Environment variables</span></span>

- <span data-ttu-id="4145e-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="4145e-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="4145e-295">Especifica la ubicación de los runtime de .NET Core, si no están instalados en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4145e-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="4145e-296">La ubicación predeterminada en Windows es `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="4145e-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="4145e-297">La ubicación predeterminada en Linux y macOS es `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="4145e-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="4145e-298">Esta variable de entorno solo se usa cuando se ejecutan aplicaciones a través de archivos ejecutables generados (hosts de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="4145e-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="4145e-299">`DOTNET_ROOT(x86)` se usa en su lugar cuando se ejecuta un archivo ejecutable de 32 bits en un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4145e-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="4145e-300">La carpeta de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="4145e-300">The global packages folder.</span></span> <span data-ttu-id="4145e-301">Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="4145e-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="4145e-302">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4145e-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="4145e-303">Especifica si los mensajes de bienvenida y de telemetría de .NET Core se muestran en la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="4145e-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="4145e-304">Establézcala en `true` para silenciar estos mensajes (valores `true`, `1` o `yes` aceptados) o en `false` para permitirlos (valores `false`, `0` o `no` aceptados).</span><span class="sxs-lookup"><span data-stu-id="4145e-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4145e-305">Si no se establece, el valor predeterminado es `false` y los mensajes se mostrarán en la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="4145e-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="4145e-306">Esta marca no tiene ningún efecto en la telemetría (consulte `DOTNET_CLI_TELEMETRY_OPTOUT` para excluirse del envío de telemetría).</span><span class="sxs-lookup"><span data-stu-id="4145e-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="4145e-307">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4145e-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4145e-308">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="4145e-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4145e-309">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="4145e-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4145e-310">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="4145e-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="4145e-311">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="4145e-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="4145e-312">Si no se define, establece el valor predeterminado de 1 (`true` lógico).</span><span class="sxs-lookup"><span data-stu-id="4145e-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="4145e-313">Establézcalo en 0 (`false` lógico) para no resolver desde la ubicación global y tener instalaciones de .NET Core aisladas.</span><span class="sxs-lookup"><span data-stu-id="4145e-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="4145e-314">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="4145e-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="4145e-315">`DOTNET_ROLL_FORWARD` **Disponible a partir del SDK de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="4145e-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="4145e-316">Determina el comportamiento de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="4145e-316">Determines roll forward behavior.</span></span> <span data-ttu-id="4145e-317">Para obtener más información, vea la opción `--roll-forward` más arriba en este mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="4145e-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="4145e-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Disponible en el SDK de .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="4145e-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4145e-319">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="4145e-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="4145e-320">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="4145e-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="4145e-321">Establece el idioma de la interfaz de usuario de la CLI mediante un valor de configuración regional como `en-us`.</span><span class="sxs-lookup"><span data-stu-id="4145e-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="4145e-322">Los valores admitidos son los mismos que en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4145e-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="4145e-323">Para obtener más información, vea la sección sobre cómo cambiar el idioma del instalador en la [documentación de instalación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="4145e-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="4145e-324">Se aplican las reglas del administrador de recursos de .NET, por lo que no hay que elegir una coincidencia exacta&mdash;(también se pueden elegir descendientes en el árbol `CultureInfo`).</span><span class="sxs-lookup"><span data-stu-id="4145e-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="4145e-325">Por ejemplo, si se establece en `fr-CA`, la CLI buscará y usará las traducciones de `fr`.</span><span class="sxs-lookup"><span data-stu-id="4145e-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="4145e-326">Si se establece en un idioma que no se admite, la CLI revertirá al inglés.</span><span class="sxs-lookup"><span data-stu-id="4145e-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="4145e-327">En el caso de los archivos ejecutables generados habilitados para GUI, se deshabilita el cuadro de diálogo emergente que suele aparecer con ciertos tipos de errores.</span><span class="sxs-lookup"><span data-stu-id="4145e-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="4145e-328">Solo escribe en `stderr` y se cierra en esos casos.</span><span class="sxs-lookup"><span data-stu-id="4145e-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="4145e-329">Equivale a la opción `--additional-deps` de la CLI.</span><span class="sxs-lookup"><span data-stu-id="4145e-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="4145e-330">Invalida el RID detectado.</span><span class="sxs-lookup"><span data-stu-id="4145e-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="4145e-331">Ubicación del "almacén compartido" a la que la resolución de ensamblado revierte en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="4145e-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="4145e-332">Lista de ensamblados de los que cargar y ejecutar enlaces de inicio.</span><span class="sxs-lookup"><span data-stu-id="4145e-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="4145e-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="4145e-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="4145e-334">Controla el seguimiento de diagnósticos de los componentes de hospedaje, como `dotnet.exe`, `hostfxr` y `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="4145e-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4145e-335">Vea también</span><span class="sxs-lookup"><span data-stu-id="4145e-335">See also</span></span>

- [<span data-ttu-id="4145e-336">Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="4145e-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="4145e-337">Opciones de configuración en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4145e-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
