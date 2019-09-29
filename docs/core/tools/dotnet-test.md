---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 05/29/2018
ms.openlocfilehash: c3115d546efb1f076ae9f9731f83a12183aa4154
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182514"
---
# <a name="dotnet-test"></a><span data-ttu-id="5116c-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="5116c-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5116c-104">Name</span><span class="sxs-lookup"><span data-stu-id="5116c-104">Name</span></span>

<span data-ttu-id="5116c-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="5116c-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5116c-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5116c-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5116c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5116c-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5116c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5116c-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5116c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5116c-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="5116c-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5116c-110">Description</span></span>

<span data-ttu-id="5116c-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="5116c-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="5116c-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="5116c-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="5116c-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="5116c-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="5116c-114">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="5116c-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="5116c-115">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5116c-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="5116c-116">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5116c-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="5116c-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5116c-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="5116c-118">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="5116c-118">Path to the test project.</span></span> <span data-ttu-id="5116c-119">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="5116c-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="5116c-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="5116c-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5116c-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5116c-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="5116c-122">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="5116c-123">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="5116c-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="5116c-124">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="5116c-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="5116c-125">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5116c-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="5116c-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="5116c-126">Defines the build configuration.</span></span> <span data-ttu-id="5116c-127">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="5116c-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="5116c-128">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-128">Enables data collector for the test run.</span></span> <span data-ttu-id="5116c-129">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="5116c-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="5116c-130">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5116c-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5116c-131">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="5116c-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="5116c-132">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="5116c-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="5116c-133">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="5116c-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="5116c-134">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5116c-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="5116c-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="5116c-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="5116c-137">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="5116c-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="5116c-138">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5116c-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="5116c-139">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5116c-140">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="5116c-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="5116c-141">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="5116c-142">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="5116c-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="5116c-143">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="5116c-144">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="5116c-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="5116c-145">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="5116c-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5116c-146">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5116c-147">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5116c-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="5116c-148">Argumentos pasados como configuraciones de RunSettings para la prueba.</span><span class="sxs-lookup"><span data-stu-id="5116c-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="5116c-149">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="5116c-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="5116c-150">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="5116c-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="5116c-151">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="5116c-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="5116c-152">Para obtener más información sobre RunSettings, vea [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: paso de argumentos RunSettings).</span><span class="sxs-lookup"><span data-stu-id="5116c-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5116c-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5116c-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="5116c-154">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="5116c-155">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="5116c-155">Defines the build configuration.</span></span> <span data-ttu-id="5116c-156">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="5116c-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="5116c-157">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-157">Enables data collector for the test run.</span></span> <span data-ttu-id="5116c-158">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="5116c-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="5116c-159">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5116c-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5116c-160">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="5116c-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="5116c-161">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="5116c-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="5116c-162">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="5116c-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="5116c-163">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5116c-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="5116c-164">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="5116c-165">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="5116c-166">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="5116c-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="5116c-167">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5116c-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="5116c-168">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5116c-169">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="5116c-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="5116c-170">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="5116c-171">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="5116c-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="5116c-172">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="5116c-173">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="5116c-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="5116c-174">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="5116c-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5116c-175">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5116c-176">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5116c-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5116c-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5116c-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="5116c-178">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="5116c-179">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="5116c-179">Defines the build configuration.</span></span> <span data-ttu-id="5116c-180">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="5116c-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="5116c-181">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5116c-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5116c-182">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="5116c-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="5116c-183">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="5116c-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="5116c-184">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="5116c-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="5116c-185">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5116c-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="5116c-186">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="5116c-187">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="5116c-188">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="5116c-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5116c-189">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="5116c-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="5116c-190">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="5116c-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="5116c-191">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="5116c-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

<span data-ttu-id="5116c-192">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="5116c-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5116c-193">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="5116c-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5116c-194">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5116c-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="5116c-195">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5116c-195">Examples</span></span>

<span data-ttu-id="5116c-196">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="5116c-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="5116c-197">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="5116c-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="5116c-198">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="5116c-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger trx`

## <a name="filter-option-details"></a><span data-ttu-id="5116c-199">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="5116c-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="5116c-200">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="5116c-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="5116c-201">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="5116c-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="5116c-202">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="5116c-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="5116c-203">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="5116c-203">Test Framework</span></span> | <span data-ttu-id="5116c-204">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="5116c-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5116c-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="5116c-205">MSTest</span></span>         | <ul><li><span data-ttu-id="5116c-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5116c-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="5116c-207">Name</span><span class="sxs-lookup"><span data-stu-id="5116c-207">Name</span></span></li><li><span data-ttu-id="5116c-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="5116c-208">ClassName</span></span></li><li><span data-ttu-id="5116c-209">Prioridad</span><span class="sxs-lookup"><span data-stu-id="5116c-209">Priority</span></span></li><li><span data-ttu-id="5116c-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="5116c-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="5116c-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="5116c-211">xUnit</span></span>          | <ul><li><span data-ttu-id="5116c-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5116c-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="5116c-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5116c-213">DisplayName</span></span></li><li><span data-ttu-id="5116c-214">Rasgos</span><span class="sxs-lookup"><span data-stu-id="5116c-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="5116c-215">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="5116c-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="5116c-216">Operador</span><span class="sxs-lookup"><span data-stu-id="5116c-216">Operator</span></span> | <span data-ttu-id="5116c-217">Función</span><span class="sxs-lookup"><span data-stu-id="5116c-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="5116c-218">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="5116c-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="5116c-219">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="5116c-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="5116c-220">Contiene</span><span class="sxs-lookup"><span data-stu-id="5116c-220">Contains</span></span>        |

<span data-ttu-id="5116c-221">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="5116c-221">`<value>` is a string.</span></span> <span data-ttu-id="5116c-222">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5116c-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="5116c-223">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="5116c-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="5116c-224">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="5116c-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="5116c-225">Operador</span><span class="sxs-lookup"><span data-stu-id="5116c-225">Operator</span></span>            | <span data-ttu-id="5116c-226">Función</span><span class="sxs-lookup"><span data-stu-id="5116c-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="5116c-227">O</span><span class="sxs-lookup"><span data-stu-id="5116c-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="5116c-228">AND</span><span class="sxs-lookup"><span data-stu-id="5116c-228">AND</span></span>      |

<span data-ttu-id="5116c-229">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="5116c-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="5116c-230">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5116c-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5116c-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="5116c-231">See also</span></span>

- [<span data-ttu-id="5116c-232">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="5116c-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="5116c-233">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5116c-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
