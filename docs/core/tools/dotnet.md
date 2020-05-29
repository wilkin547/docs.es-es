---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para la CLI de .NET Core) y su uso.
ms.date: 02/13/2020
ms.openlocfilehash: 88e92b3ff5e8f68b980015a817434dd2d67df93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378838"
---
# <a name="dotnet-command"></a><span data-ttu-id="b4424-103">comando dotnet</span><span class="sxs-lookup"><span data-stu-id="b4424-103">dotnet command</span></span>

<span data-ttu-id="b4424-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b4424-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b4424-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b4424-105">Name</span></span>

<span data-ttu-id="b4424-106">`dotnet`: controlador genérico de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b4424-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b4424-107">Synopsis</span></span>

<span data-ttu-id="b4424-108">Para obtener información sobre los comandos disponibles y el entorno:</span><span class="sxs-lookup"><span data-stu-id="b4424-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="b4424-109">Para ejecutar un comando (se requiere la instalación de un SDK):</span><span class="sxs-lookup"><span data-stu-id="b4424-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="b4424-110">Para ejecutar una aplicación:</span><span class="sxs-lookup"><span data-stu-id="b4424-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="b4424-111">`--roll-forward` está disponible a partir de .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="b4424-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="b4424-112">En .NET Core 2.x, use `--roll-forward-on-no-candidate-fx`.</span><span class="sxs-lookup"><span data-stu-id="b4424-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="b4424-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4424-113">Description</span></span>

<span data-ttu-id="b4424-114">El comando `dotnet` tiene dos funciones:</span><span class="sxs-lookup"><span data-stu-id="b4424-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="b4424-115">Proporciona comandos para trabajar con proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="b4424-116">Por ejemplo, [`dotnet build`](dotnet-build.md) compila un proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4424-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="b4424-117">Cada comando define sus propias opciones y argumentos.</span><span class="sxs-lookup"><span data-stu-id="b4424-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="b4424-118">Todos los comandos admiten la opción `--help` para ver una breve documentación sobre cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="b4424-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="b4424-119">Ejecuta aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="b4424-120">Hay que especificar la ruta de acceso al archivo `.dll` de una aplicación para poder ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="b4424-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="b4424-121">Ejecutar la aplicación significa buscar y ejecutar el punto de entrada, que en el caso de las aplicaciones de consola es el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="b4424-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="b4424-122">Por ejemplo, `dotnet myapp.dll` ejecuta la aplicación `myapp`.</span><span class="sxs-lookup"><span data-stu-id="b4424-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="b4424-123">Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener más información sobre las opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="b4424-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="b4424-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="b4424-124">Options</span></span>

<span data-ttu-id="b4424-125">Existen distintas opciones disponibles para usar `dotnet` por sí mismo, para ejecutar un comando y para ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="b4424-126">Opciones de dotnet por sí mismo</span><span class="sxs-lookup"><span data-stu-id="b4424-126">Options for dotnet by itself</span></span>

<span data-ttu-id="b4424-127">Las siguientes opciones son para usar `dotnet` por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="b4424-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="b4424-128">Por ejemplo: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="b4424-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="b4424-129">Muestran información sobre el entorno.</span><span class="sxs-lookup"><span data-stu-id="b4424-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="b4424-130">Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="b4424-131">Imprime la versión del SDK de .NET Core en uso.</span><span class="sxs-lookup"><span data-stu-id="b4424-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="b4424-132">Muestra una lista de los runtime de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="b4424-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="b4424-133">Una versión x86 del SDK muestra solo los runtime x86 y una versión x64 solo los runtime x64.</span><span class="sxs-lookup"><span data-stu-id="b4424-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="b4424-134">Muestra una lista de los SDK de .NET Core instalados.</span><span class="sxs-lookup"><span data-stu-id="b4424-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b4424-135">Muestra una lista de los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4424-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="b4424-136">Opciones de SDK para ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="b4424-136">SDK options for running a command</span></span>

<span data-ttu-id="b4424-137">Las siguientes opciones son para usar `dotnet` con un comando.</span><span class="sxs-lookup"><span data-stu-id="b4424-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="b4424-138">Por ejemplo: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="b4424-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="b4424-139">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b4424-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b4424-140">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="b4424-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b4424-141">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b4424-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b4424-142">Estos no se admiten en todos los comandos.</span><span class="sxs-lookup"><span data-stu-id="b4424-142">Not supported in every command.</span></span> <span data-ttu-id="b4424-143">Vea la página específica de cada comando para asegurarse de que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="b4424-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b4424-144">Imprime la documentación de un comando determinado, como `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="b4424-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="b4424-145">Cada comando define opciones específicas de ese comando.</span><span class="sxs-lookup"><span data-stu-id="b4424-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="b4424-146">Vea la página de comandos específica para obtener una lista de las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4424-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="b4424-147">Definición de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b4424-147">Runtime options</span></span>

<span data-ttu-id="b4424-148">Las siguientes opciones están disponibles cuando `dotnet` ejecuta una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="b4424-149">Por ejemplo: `dotnet myapp.dll --roll-forward Major`.</span><span class="sxs-lookup"><span data-stu-id="b4424-149">For example, `dotnet myapp.dll --roll-forward Major`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="b4424-150">Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.</span><span class="sxs-lookup"><span data-stu-id="b4424-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="b4424-151">Ruta de acceso a un archivo *.deps.json* adicional.</span><span class="sxs-lookup"><span data-stu-id="b4424-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="b4424-152">Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b4424-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="b4424-153">Para más información, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="b4424-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--depsfile <PATH_TO_DEPSFILE>`**

  <span data-ttu-id="b4424-154">Ruta de acceso al archivo *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="b4424-154">Path to the *deps.json* file.</span></span> <span data-ttu-id="b4424-155">Un archivo *deps.json* es un archivo de configuración que contiene información sobre las dependencias necesarias para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-155">A *deps.json* file is a configuration file that contains information about dependencies necessary to run the application.</span></span> <span data-ttu-id="b4424-156">El SDK de .NET Core genera este archivo.</span><span class="sxs-lookup"><span data-stu-id="b4424-156">This file is generated by the .NET Core SDK.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="b4424-157">Ruta de acceso a un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="b4424-157">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="b4424-158">Un archivo *runtimeconfig.json* es un archivo de configuración que contiene opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4424-158">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="b4424-159">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="b4424-159">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="b4424-160">**`--roll-forward <SETTING>`** **Disponible a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="b4424-160">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="b4424-161">Controla cómo se aplica la puesta al día en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-161">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="b4424-162">`SETTING` puede tener uno de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="b4424-162">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="b4424-163">Si no se especifica, el valor predeterminado es `Minor`.</span><span class="sxs-lookup"><span data-stu-id="b4424-163">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="b4424-164">`LatestPatch`: la aplicación se pone al día con la última versión de revisión.</span><span class="sxs-lookup"><span data-stu-id="b4424-164">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="b4424-165">Se deshabilita la puesta al día de versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="b4424-165">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="b4424-166">`Minor`: la aplicación se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="b4424-166">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="b4424-167">Si se encuentra la versión secundaria solicitada, se utiliza la directiva LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="b4424-167">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="b4424-168">`Major`: la aplicación se pone al día con la versión secundaria mínima superior, y con la versión secundaria mínima si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="b4424-168">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="b4424-169">Si se encuentra la versión principal solicitada, se utiliza la directiva Minor.</span><span class="sxs-lookup"><span data-stu-id="b4424-169">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="b4424-170">`LatestMinor`: la aplicación e pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="b4424-170">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="b4424-171">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="b4424-171">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="b4424-172">`LatestMajor`: la aplicación se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="b4424-172">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="b4424-173">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="b4424-173">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="b4424-174">`Disable`: la aplicación no se pone al día.</span><span class="sxs-lookup"><span data-stu-id="b4424-174">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="b4424-175">Solo se enlaza a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="b4424-175">Only bind to specified version.</span></span> <span data-ttu-id="b4424-176">No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4424-176">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="b4424-177">Este valor solo se recomienda a efectos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b4424-177">This value is only recommended for testing.</span></span>

  <span data-ttu-id="b4424-178">A excepción de `Disable`, todos los valores usarán la última versión de revisión disponible.</span><span class="sxs-lookup"><span data-stu-id="b4424-178">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

  <span data-ttu-id="b4424-179">El comportamiento de puesta al día también se puede configurar en una propiedad de archivo de proyecto, en una propiedad de archivo de configuración de runtime y en una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="b4424-179">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="b4424-180">Para obtener más información, vea [Puesta al día del runtime de versiones principales](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="b4424-180">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="b4424-181">**`--roll-forward-on-no-candidate-fx <N>`** **Disponible en el SDK de .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-181">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="b4424-182">Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b4424-182">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="b4424-183">`N` puede ser:</span><span class="sxs-lookup"><span data-stu-id="b4424-183">`N` can be:</span></span>

  - <span data-ttu-id="b4424-184">`0`: se deshabilita la puesta al día incluso de las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="b4424-184">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="b4424-185">`1`: puesta al día de la versión secundaria, pero no de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="b4424-185">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="b4424-186">Éste es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b4424-186">This is the default behavior.</span></span>
  - <span data-ttu-id="b4424-187">`2`: puesta al día de las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="b4424-187">`2` - Roll forward on minor and major versions.</span></span>

  <span data-ttu-id="b4424-188">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="b4424-188">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="b4424-189">A partir de .NET Core 3.0, esta opción se sustituye por `--roll-forward` y es la que debe usarse.</span><span class="sxs-lookup"><span data-stu-id="b4424-189">Starting with .NET Core 3.0, this option is superseded by `--roll-forward`, and that option should be used instead.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="b4424-190">Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-190">Version of the .NET Core runtime to use to run the application.</span></span>

  <span data-ttu-id="b4424-191">Esta opción reemplaza la versión de la primera referencia de marco en el archivo `.runtimeconfig.json` de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-191">This option overrides the version of the first framework reference in the application's `.runtimeconfig.json` file.</span></span> <span data-ttu-id="b4424-192">Esto significa que solo funciona según lo esperado si solo hay una referencia de marco.</span><span class="sxs-lookup"><span data-stu-id="b4424-192">This means it only works as expected if there's just one framework reference.</span></span> <span data-ttu-id="b4424-193">Si la aplicación tiene más de una referencia de marco, el uso de esta opción puede hacer que se produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="b4424-193">If the application has more than one framework reference, using this option may cause errors.</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="b4424-194">comandos de dotnet</span><span class="sxs-lookup"><span data-stu-id="b4424-194">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="b4424-195">General</span><span class="sxs-lookup"><span data-stu-id="b4424-195">General</span></span>

| <span data-ttu-id="b4424-196">Comando</span><span class="sxs-lookup"><span data-stu-id="b4424-196">Command</span></span>                                       | <span data-ttu-id="b4424-197">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-197">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b4424-198">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b4424-198">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="b4424-199">Compila una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-199">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b4424-200">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="b4424-200">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="b4424-201">Interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="b4424-201">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="b4424-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b4424-202">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="b4424-203">Limpia las salidas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="b4424-203">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="b4424-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="b4424-204">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="b4424-205">Muestra documentación más detallada en línea sobre el comando.</span><span class="sxs-lookup"><span data-stu-id="b4424-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="b4424-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b4424-206">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="b4424-207">Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b4424-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b4424-208">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="b4424-209">Proporciona acceso a la línea de comandos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b4424-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b4424-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b4424-210">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="b4424-211">Inicializa un proyecto de C# o F# para una plantilla determinada.</span><span class="sxs-lookup"><span data-stu-id="b4424-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b4424-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b4424-212">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="b4424-213">Crea un paquete de NuGet de su código.</span><span class="sxs-lookup"><span data-stu-id="b4424-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b4424-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b4424-214">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="b4424-215">Publica una aplicación dependiente del maco .NET o autocontenida.</span><span class="sxs-lookup"><span data-stu-id="b4424-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b4424-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b4424-216">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="b4424-217">Restaura las dependencias de una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="b4424-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b4424-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b4424-218">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="b4424-219">Ejecuta la aplicación desde el origen.</span><span class="sxs-lookup"><span data-stu-id="b4424-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b4424-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b4424-220">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="b4424-221">Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="b4424-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b4424-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b4424-222">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="b4424-223">Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4424-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="b4424-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b4424-224">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="b4424-225">Ejecuta pruebas usando un ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b4424-225">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="b4424-226">Referencias de proyecto</span><span class="sxs-lookup"><span data-stu-id="b4424-226">Project references</span></span>

<span data-ttu-id="b4424-227">Comando</span><span class="sxs-lookup"><span data-stu-id="b4424-227">Command</span></span> | <span data-ttu-id="b4424-228">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-228">Function</span></span>
--- | ---
[<span data-ttu-id="b4424-229">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="b4424-229">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="b4424-230">Agrega una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4424-230">Adds a project reference.</span></span>
[<span data-ttu-id="b4424-231">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b4424-231">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="b4424-232">Enumera referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4424-232">Lists project references.</span></span>
[<span data-ttu-id="b4424-233">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="b4424-233">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="b4424-234">Quita una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4424-234">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="b4424-235">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="b4424-235">NuGet packages</span></span>

<span data-ttu-id="b4424-236">Comando</span><span class="sxs-lookup"><span data-stu-id="b4424-236">Command</span></span> | <span data-ttu-id="b4424-237">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-237">Function</span></span>
--- | ---
[<span data-ttu-id="b4424-238">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="b4424-238">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="b4424-239">Agrega un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-239">Adds a NuGet package.</span></span>
[<span data-ttu-id="b4424-240">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="b4424-240">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="b4424-241">Quita un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-241">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="b4424-242">Comandos NuGet</span><span class="sxs-lookup"><span data-stu-id="b4424-242">NuGet commands</span></span>

<span data-ttu-id="b4424-243">Comando</span><span class="sxs-lookup"><span data-stu-id="b4424-243">Command</span></span> | <span data-ttu-id="b4424-244">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-244">Function</span></span>
--- | ---
[<span data-ttu-id="b4424-245">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="b4424-245">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="b4424-246">Elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="b4424-246">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="b4424-247">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="b4424-247">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="b4424-248">Inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="b4424-248">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="b4424-249">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="b4424-249">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="b4424-250">Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="b4424-250">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="b4424-251">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="b4424-251">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="b4424-252">Agrega un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-252">Adds a NuGet source.</span></span>
[<span data-ttu-id="b4424-253">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="b4424-253">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="b4424-254">Deshabilita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-254">Disables a NuGet source.</span></span>
[<span data-ttu-id="b4424-255">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="b4424-255">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="b4424-256">Habilita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-256">Enables a NuGet source.</span></span>
[<span data-ttu-id="b4424-257">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="b4424-257">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="b4424-258">Enumera todos los orígenes de NuGet configurados.</span><span class="sxs-lookup"><span data-stu-id="b4424-258">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="b4424-259">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="b4424-259">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="b4424-260">Quita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-260">Removes a NuGet source.</span></span>
[<span data-ttu-id="b4424-261">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="b4424-261">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="b4424-262">Actualiza un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4424-262">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="b4424-263">Comandos de herramientas locales, globales y de ruta de acceso de herramientas</span><span class="sxs-lookup"><span data-stu-id="b4424-263">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="b4424-264">Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b4424-264">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="b4424-265">Puede encargarse de escribir las herramientas o instalar las escritas por terceros.</span><span class="sxs-lookup"><span data-stu-id="b4424-265">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="b4424-266">Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="b4424-266">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="b4424-267">Para obtener más información, vea [Información general sobre las herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4424-267">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="b4424-268">Las herramientas globales y de ruta de acceso de herramientas están disponibles a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="b4424-268">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="b4424-269">Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b4424-269">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="b4424-270">Comando</span><span class="sxs-lookup"><span data-stu-id="b4424-270">Command</span></span> | <span data-ttu-id="b4424-271">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-271">Function</span></span>
--- | ---
[<span data-ttu-id="b4424-272">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="b4424-272">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="b4424-273">Instala una herramienta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b4424-273">Installs a tool on your machine.</span></span>
[<span data-ttu-id="b4424-274">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="b4424-274">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="b4424-275">Muestra todas las herramientas globales, de ruta de acceso de herramientas o locales instaladas actualmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b4424-275">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="b4424-276">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="b4424-276">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="b4424-277">Desinstala una herramienta del equipo.</span><span class="sxs-lookup"><span data-stu-id="b4424-277">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="b4424-278">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="b4424-278">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="b4424-279">Actualiza una herramienta que está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b4424-279">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="b4424-280">Herramientas adicionales</span><span class="sxs-lookup"><span data-stu-id="b4424-280">Additional tools</span></span>

<span data-ttu-id="b4424-281">A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-281">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="b4424-282">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4424-282">These tools are listed in the following table:</span></span>

| <span data-ttu-id="b4424-283">Herramienta</span><span class="sxs-lookup"><span data-stu-id="b4424-283">Tool</span></span>                                              | <span data-ttu-id="b4424-284">Función</span><span class="sxs-lookup"><span data-stu-id="b4424-284">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="b4424-285">dev-certs</span><span class="sxs-lookup"><span data-stu-id="b4424-285">dev-certs</span></span>                                         | <span data-ttu-id="b4424-286">Crea y administra certificados de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b4424-286">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="b4424-287">ef</span><span class="sxs-lookup"><span data-stu-id="b4424-287">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="b4424-288">Herramientas de línea de comandos de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="b4424-288">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="b4424-289">sql-cache</span><span class="sxs-lookup"><span data-stu-id="b4424-289">sql-cache</span></span>                                         | <span data-ttu-id="b4424-290">Herramientas de línea de comandos de la caché de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4424-290">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="b4424-291">user-secrets</span><span class="sxs-lookup"><span data-stu-id="b4424-291">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="b4424-292">Administra los secretos del usuario de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b4424-292">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="b4424-293">watch</span><span class="sxs-lookup"><span data-stu-id="b4424-293">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="b4424-294">Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos.</span><span class="sxs-lookup"><span data-stu-id="b4424-294">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="b4424-295">Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="b4424-295">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="b4424-296">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4424-296">Examples</span></span>

<span data-ttu-id="b4424-297">Cree una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="b4424-297">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="b4424-298">Compilación de un proyecto y sus dependencias en un directorio determinado:</span><span class="sxs-lookup"><span data-stu-id="b4424-298">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b4424-299">Ejecute una aplicación:</span><span class="sxs-lookup"><span data-stu-id="b4424-299">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="b4424-300">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="b4424-300">Environment variables</span></span>

- <span data-ttu-id="b4424-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="b4424-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="b4424-302">Especifica la ubicación de los runtime de .NET Core, si no están instalados en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b4424-302">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="b4424-303">La ubicación predeterminada en Windows es `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="b4424-303">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="b4424-304">La ubicación predeterminada en Linux y macOS es `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="b4424-304">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="b4424-305">Esta variable de entorno solo se usa cuando se ejecutan aplicaciones a través de archivos ejecutables generados (hosts de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="b4424-305">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="b4424-306">`DOTNET_ROOT(x86)` se usa en su lugar cuando se ejecuta un archivo ejecutable de 32 bits en un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b4424-306">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="b4424-307">La carpeta de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="b4424-307">The global packages folder.</span></span> <span data-ttu-id="b4424-308">Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.</span><span class="sxs-lookup"><span data-stu-id="b4424-308">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="b4424-309">Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4424-309">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="b4424-310">Especifica si los mensajes de bienvenida y de telemetría de .NET Core se muestran en la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4424-310">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="b4424-311">Establézcala en `true` para silenciar estos mensajes (valores `true`, `1` o `yes` aceptados) o en `false` para permitirlos (valores `false`, `0` o `no` aceptados).</span><span class="sxs-lookup"><span data-stu-id="b4424-311">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b4424-312">Si no se establece, el valor predeterminado es `false` y los mensajes se mostrarán en la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4424-312">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="b4424-313">Esta marca no tiene ningún efecto en la telemetría (consulte `DOTNET_CLI_TELEMETRY_OPTOUT` para excluirse del envío de telemetría).</span><span class="sxs-lookup"><span data-stu-id="b4424-313">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="b4424-314">Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4424-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="b4424-315">Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="b4424-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="b4424-316">De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="b4424-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b4424-317">Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.</span><span class="sxs-lookup"><span data-stu-id="b4424-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="b4424-318">Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK.</span><span class="sxs-lookup"><span data-stu-id="b4424-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="b4424-319">Si no se define, establece el valor predeterminado de 1 (`true` lógico).</span><span class="sxs-lookup"><span data-stu-id="b4424-319">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="b4424-320">Establézcalo en 0 (`false` lógico) para no resolver desde la ubicación global y tener instalaciones de .NET Core aisladas.</span><span class="sxs-lookup"><span data-stu-id="b4424-320">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="b4424-321">Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).</span><span class="sxs-lookup"><span data-stu-id="b4424-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="b4424-322">`DOTNET_ROLL_FORWARD` **Disponible a partir de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-322">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4424-323">Determina el comportamiento de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="b4424-323">Determines roll forward behavior.</span></span> <span data-ttu-id="b4424-324">Para obtener más información, vea la opción `--roll-forward` más arriba en este mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="b4424-324">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="b4424-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Disponible a partir de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4424-326">Si se establece en `1` (habilitado), permite la puesta al día a una versión preliminar desde una versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="b4424-326">If set to `1` (enabled), enables rolling forward to a pre-release version from a release version.</span></span> <span data-ttu-id="b4424-327">De forma predeterminada (`0`: deshabilitado), cuando se solicita una versión de lanzamiento de .NET Core en tiempo de ejecución, la puesta al día solo tendrá en cuenta las versiones de lanzamiento instaladas.</span><span class="sxs-lookup"><span data-stu-id="b4424-327">By default (`0` - disabled), when a release version of .NET Core runtime is requested, roll-forward will only consider installed release versions.</span></span>

  <span data-ttu-id="b4424-328">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="b4424-328">For more information, see [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="b4424-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Disponible en .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x.**</span></span>

  <span data-ttu-id="b4424-330">Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`.</span><span class="sxs-lookup"><span data-stu-id="b4424-330">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="b4424-331">Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).</span><span class="sxs-lookup"><span data-stu-id="b4424-331">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="b4424-332">Este valor se ha sustituido en .NET Core 3.0 por `DOTNET_ROLL_FORWARD`, y</span><span class="sxs-lookup"><span data-stu-id="b4424-332">This setting is superseded in .NET Core 3.0 by `DOTNET_ROLL_FORWARD`.</span></span> <span data-ttu-id="b4424-333">esta es la configuración que debe usarse.</span><span class="sxs-lookup"><span data-stu-id="b4424-333">The new settings should be used instead.</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="b4424-334">Establece el idioma de la interfaz de usuario de la CLI mediante un valor de configuración regional como `en-us`.</span><span class="sxs-lookup"><span data-stu-id="b4424-334">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="b4424-335">Los valores admitidos son los mismos que en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4424-335">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="b4424-336">Para obtener más información, vea la sección sobre cómo cambiar el idioma del instalador en la [documentación de instalación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="b4424-336">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="b4424-337">Se aplican las reglas del administrador de recursos de .NET, por lo que no hay que elegir una coincidencia exacta&mdash;(también se pueden elegir descendientes en el árbol `CultureInfo`).</span><span class="sxs-lookup"><span data-stu-id="b4424-337">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="b4424-338">Por ejemplo, si se establece en `fr-CA`, la CLI buscará y usará las traducciones de `fr`.</span><span class="sxs-lookup"><span data-stu-id="b4424-338">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="b4424-339">Si se establece en un idioma que no se admite, la CLI revertirá al inglés.</span><span class="sxs-lookup"><span data-stu-id="b4424-339">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="b4424-340">En el caso de los archivos ejecutables generados habilitados para GUI, se deshabilita el cuadro de diálogo emergente que suele aparecer con ciertos tipos de errores.</span><span class="sxs-lookup"><span data-stu-id="b4424-340">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="b4424-341">Solo escribe en `stderr` y se cierra en esos casos.</span><span class="sxs-lookup"><span data-stu-id="b4424-341">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="b4424-342">Equivale a la opción `--additional-deps` de la CLI.</span><span class="sxs-lookup"><span data-stu-id="b4424-342">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="b4424-343">Invalida el RID detectado.</span><span class="sxs-lookup"><span data-stu-id="b4424-343">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="b4424-344">Ubicación del "almacén compartido" a la que la resolución de ensamblado revierte en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="b4424-344">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="b4424-345">Lista de ensamblados de los que cargar y ejecutar enlaces de inicio.</span><span class="sxs-lookup"><span data-stu-id="b4424-345">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="b4424-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Disponible a partir de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4424-347">Especifica un directorio en el que se extrae una aplicación de un solo archivo antes de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="b4424-347">Specifies a directory to which a single-file application is extracted before it is executed.</span></span>

  <span data-ttu-id="b4424-348">Para más información, consulte [Archivos ejecutables de único archivo](../whats-new/dotnet-core-3-0.md#single-file-executables).</span><span class="sxs-lookup"><span data-stu-id="b4424-348">For more information, see [Single-file executables](../whats-new/dotnet-core-3-0.md#single-file-executables).</span></span>

- <span data-ttu-id="b4424-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="b4424-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="b4424-350">Controla el seguimiento de diagnósticos de los componentes de hospedaje, como `dotnet.exe`, `hostfxr` y `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="b4424-350">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

  * <span data-ttu-id="b4424-351">`COREHOST_TRACE=[0/1]`: el valor predeterminado es `0` (el seguimiento está deshabilitado).</span><span class="sxs-lookup"><span data-stu-id="b4424-351">`COREHOST_TRACE=[0/1]` - default is `0` - tracing disabled.</span></span> <span data-ttu-id="b4424-352">Si se establece en `1`, se habilita el seguimiento de diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="b4424-352">If set to `1`, diagnostics tracing is enabled.</span></span>
  * <span data-ttu-id="b4424-353">`COREHOST_TRACEFILE=<file path>`: solo tiene efecto si el seguimiento se habilita a través de `COREHOST_TRACE=1`.</span><span class="sxs-lookup"><span data-stu-id="b4424-353">`COREHOST_TRACEFILE=<file path>` - only has effect if tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="b4424-354">Cuando se establece, la información de seguimiento se escribe en el archivo especificado; en caso contrario, la información de seguimiento se escribe en `stderr`.</span><span class="sxs-lookup"><span data-stu-id="b4424-354">When set, the tracing information is written to the specified file, otherwise the tracing information is written to `stderr`.</span></span> <span data-ttu-id="b4424-355">**Disponible a partir de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-355">**Available starting with .NET Core 3.x.**</span></span>
  * <span data-ttu-id="b4424-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]`: el valor predeterminado es `4`.</span><span class="sxs-lookup"><span data-stu-id="b4424-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` - default is `4`.</span></span> <span data-ttu-id="b4424-357">La configuración solo se usa cuando el seguimiento está habilitado a través de `COREHOST_TRACE=1`.</span><span class="sxs-lookup"><span data-stu-id="b4424-357">The setting is used only when tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="b4424-358">**Disponible a partir de .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="b4424-358">**Available starting with .NET Core 3.x.**</span></span>
    * <span data-ttu-id="b4424-359">`4`: se escribe toda la información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b4424-359">`4` - all tracing information is written</span></span>
    * <span data-ttu-id="b4424-360">`3`: solo se escriben mensajes informativos, de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="b4424-360">`3` - only informational, warning and error messages are written</span></span>
    * <span data-ttu-id="b4424-361">`2`: solo se escriben mensajes de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="b4424-361">`2` - only warning and error messages are written</span></span>
    * <span data-ttu-id="b4424-362">`1`: solo se escriben mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="b4424-362">`1` - only error messages are written</span></span>

  <span data-ttu-id="b4424-363">La forma habitual de obtener información de seguimiento detallada sobre el inicio de la aplicación es establecer `COREHOST_TRACE=1` y `COREHOST_TRACEFILE=host_trace.txt` y, luego, ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4424-363">The typical way to get detailed trace information about application startup is to set `COREHOST_TRACE=1` and `COREHOST_TRACEFILE=host_trace.txt` and then run the application.</span></span> <span data-ttu-id="b4424-364">Se creará un nuevo archivo `host_trace.txt` en el directorio actual con la información detallada.</span><span class="sxs-lookup"><span data-stu-id="b4424-364">A new file `host_trace.txt` will be created in the current directory with the detailed information.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4424-365">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4424-365">See also</span></span>

- [<span data-ttu-id="b4424-366">Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="b4424-366">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="b4424-367">Opciones de configuración en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b4424-367">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
