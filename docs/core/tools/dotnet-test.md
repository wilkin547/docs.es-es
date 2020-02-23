---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 05/29/2018
ms.openlocfilehash: 909815151265117395c6d8d13b4443a245c05f9e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451199"
---
# <a name="dotnet-test"></a><span data-ttu-id="32844-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="32844-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="32844-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="32844-104">Name</span></span>

<span data-ttu-id="32844-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="32844-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="32844-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="32844-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="32844-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="32844-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="32844-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="32844-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="32844-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="32844-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="32844-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="32844-110">Description</span></span>

<span data-ttu-id="32844-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="32844-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="32844-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="32844-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="32844-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="32844-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="32844-114">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="32844-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="32844-115">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="32844-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="32844-116">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32844-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="32844-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="32844-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="32844-118">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="32844-118">Path to the test project.</span></span> <span data-ttu-id="32844-119">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="32844-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="32844-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="32844-120">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="32844-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="32844-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="32844-122">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="32844-123">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="32844-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="32844-124">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="32844-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="32844-125">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="32844-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="32844-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="32844-126">Defines the build configuration.</span></span> <span data-ttu-id="32844-127">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="32844-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="32844-128">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-128">Enables data collector for the test run.</span></span> <span data-ttu-id="32844-129">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="32844-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="32844-130">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="32844-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32844-131">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="32844-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="32844-132">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="32844-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="32844-133">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="32844-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="32844-134">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="32844-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="32844-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="32844-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="32844-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="32844-137">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="32844-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="32844-138">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="32844-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="32844-139">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="32844-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32844-140">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="32844-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="32844-141">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="32844-142">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="32844-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="32844-143">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="32844-144">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="32844-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="32844-145">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="32844-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32844-146">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="32844-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32844-147">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="32844-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="32844-148">Argumentos pasados como configuraciones de RunSettings para la prueba.</span><span class="sxs-lookup"><span data-stu-id="32844-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="32844-149">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="32844-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="32844-150">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="32844-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="32844-151">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="32844-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="32844-152">Para obtener más información sobre RunSettings, vea [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: paso de argumentos RunSettings).</span><span class="sxs-lookup"><span data-stu-id="32844-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="32844-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="32844-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="32844-154">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="32844-155">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="32844-155">Defines the build configuration.</span></span> <span data-ttu-id="32844-156">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="32844-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="32844-157">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-157">Enables data collector for the test run.</span></span> <span data-ttu-id="32844-158">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="32844-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="32844-159">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="32844-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32844-160">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="32844-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="32844-161">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="32844-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="32844-162">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="32844-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="32844-163">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="32844-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="32844-164">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="32844-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="32844-165">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="32844-166">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="32844-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="32844-167">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="32844-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="32844-168">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="32844-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32844-169">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="32844-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="32844-170">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="32844-171">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="32844-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="32844-172">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="32844-173">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="32844-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="32844-174">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="32844-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32844-175">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="32844-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32844-176">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="32844-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="32844-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="32844-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="32844-178">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="32844-179">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="32844-179">Defines the build configuration.</span></span> <span data-ttu-id="32844-180">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="32844-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="32844-181">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="32844-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32844-182">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="32844-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="32844-183">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="32844-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="32844-184">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="32844-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="32844-185">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="32844-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="32844-186">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="32844-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="32844-187">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="32844-188">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="32844-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32844-189">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="32844-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="32844-190">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="32844-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="32844-191">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="32844-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="32844-192">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="32844-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32844-193">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="32844-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32844-194">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="32844-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="32844-195">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="32844-195">Examples</span></span>

<span data-ttu-id="32844-196">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="32844-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="32844-197">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="32844-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="32844-198">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="32844-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger trx`

## <a name="filter-option-details"></a><span data-ttu-id="32844-199">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="32844-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="32844-200">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="32844-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="32844-201">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="32844-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="32844-202">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="32844-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="32844-203">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="32844-203">Test Framework</span></span> | <span data-ttu-id="32844-204">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="32844-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="32844-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="32844-205">MSTest</span></span>         | <ul><li><span data-ttu-id="32844-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="32844-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="32844-207">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="32844-207">Name</span></span></li><li><span data-ttu-id="32844-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="32844-208">ClassName</span></span></li><li><span data-ttu-id="32844-209">Prioridad</span><span class="sxs-lookup"><span data-stu-id="32844-209">Priority</span></span></li><li><span data-ttu-id="32844-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="32844-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="32844-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="32844-211">xUnit</span></span>          | <ul><li><span data-ttu-id="32844-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="32844-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="32844-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="32844-213">DisplayName</span></span></li><li><span data-ttu-id="32844-214">Rasgos</span><span class="sxs-lookup"><span data-stu-id="32844-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="32844-215">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="32844-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="32844-216">Operador</span><span class="sxs-lookup"><span data-stu-id="32844-216">Operator</span></span> | <span data-ttu-id="32844-217">Función</span><span class="sxs-lookup"><span data-stu-id="32844-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="32844-218">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="32844-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="32844-219">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="32844-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="32844-220">Contiene</span><span class="sxs-lookup"><span data-stu-id="32844-220">Contains</span></span>        |
| `!~`     | <span data-ttu-id="32844-221">No contiene</span><span class="sxs-lookup"><span data-stu-id="32844-221">Not contains</span></span>    |

<span data-ttu-id="32844-222">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="32844-222">`<value>` is a string.</span></span> <span data-ttu-id="32844-223">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="32844-223">All the lookups are case insensitive.</span></span>

<span data-ttu-id="32844-224">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="32844-224">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="32844-225">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="32844-225">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="32844-226">Operador</span><span class="sxs-lookup"><span data-stu-id="32844-226">Operator</span></span>            | <span data-ttu-id="32844-227">Función</span><span class="sxs-lookup"><span data-stu-id="32844-227">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="32844-228">O</span><span class="sxs-lookup"><span data-stu-id="32844-228">OR</span></span>       |
| `&`                 | <span data-ttu-id="32844-229">AND</span><span class="sxs-lookup"><span data-stu-id="32844-229">AND</span></span>      |

<span data-ttu-id="32844-230">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="32844-230">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="32844-231">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="32844-231">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32844-232">Vea también</span><span class="sxs-lookup"><span data-stu-id="32844-232">See also</span></span>

- [<span data-ttu-id="32844-233">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="32844-233">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="32844-234">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="32844-234">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
