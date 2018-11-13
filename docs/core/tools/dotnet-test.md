---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 73b1d832b855798dd053187bbb24e8fb989fedf1
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "46696461"
---
# <a name="dotnet-test"></a><span data-ttu-id="6cf03-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6cf03-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6cf03-104">nombre</span><span class="sxs-lookup"><span data-stu-id="6cf03-104">Name</span></span>

<span data-ttu-id="6cf03-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="6cf03-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6cf03-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6cf03-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cf03-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cf03-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cf03-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cf03-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cf03-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cf03-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="6cf03-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6cf03-110">Description</span></span>

<span data-ttu-id="6cf03-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="6cf03-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="6cf03-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="6cf03-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="6cf03-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="6cf03-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="6cf03-114">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="6cf03-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="6cf03-115">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6cf03-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="6cf03-116">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6cf03-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="6cf03-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6cf03-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="6cf03-118">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="6cf03-118">Path to the test project.</span></span> <span data-ttu-id="6cf03-119">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="6cf03-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="6cf03-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="6cf03-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cf03-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cf03-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="6cf03-122">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="6cf03-123">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="6cf03-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="6cf03-124">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="6cf03-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="6cf03-125">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6cf03-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="6cf03-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="6cf03-126">Defines the build configuration.</span></span> <span data-ttu-id="6cf03-127">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="6cf03-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="6cf03-128">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-128">Enables data collector for the test run.</span></span> <span data-ttu-id="6cf03-129">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="6cf03-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="6cf03-130">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6cf03-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="6cf03-131">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="6cf03-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="6cf03-132">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="6cf03-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="6cf03-133">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="6cf03-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="6cf03-134">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6cf03-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="6cf03-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="6cf03-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="6cf03-137">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="6cf03-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="6cf03-138">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="6cf03-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="6cf03-139">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6cf03-140">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="6cf03-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="6cf03-141">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="6cf03-142">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="6cf03-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="6cf03-143">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="6cf03-144">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="6cf03-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cf03-145">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cf03-146">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="6cf03-147">Argumentos pasados como configuraciones de RunSettings para la prueba.</span><span class="sxs-lookup"><span data-stu-id="6cf03-147">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="6cf03-148">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="6cf03-148">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="6cf03-149">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-149">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="6cf03-150">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="6cf03-150">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="6cf03-151">Para más información sobre RunSettings, consulte [vstest.console.exe: Paso de argumentos RunSettings](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="6cf03-151">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cf03-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cf03-152">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="6cf03-153">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-153">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="6cf03-154">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="6cf03-154">Defines the build configuration.</span></span> <span data-ttu-id="6cf03-155">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="6cf03-155">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="6cf03-156">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-156">Enables data collector for the test run.</span></span> <span data-ttu-id="6cf03-157">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="6cf03-157">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="6cf03-158">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6cf03-158">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="6cf03-159">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="6cf03-159">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="6cf03-160">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="6cf03-160">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="6cf03-161">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="6cf03-161">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="6cf03-162">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6cf03-162">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="6cf03-163">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-163">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="6cf03-164">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-164">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="6cf03-165">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="6cf03-165">Doesn't build the test project before running it.</span></span> <span data-ttu-id="6cf03-166">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="6cf03-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="6cf03-167">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-167">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6cf03-168">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="6cf03-168">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="6cf03-169">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-169">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="6cf03-170">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="6cf03-170">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="6cf03-171">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-171">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="6cf03-172">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="6cf03-172">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cf03-173">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-173">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cf03-174">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-174">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cf03-175">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cf03-175">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="6cf03-176">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-176">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="6cf03-177">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="6cf03-177">Defines the build configuration.</span></span> <span data-ttu-id="6cf03-178">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="6cf03-178">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="6cf03-179">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6cf03-179">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="6cf03-180">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="6cf03-180">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="6cf03-181">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="6cf03-181">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="6cf03-182">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="6cf03-182">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="6cf03-183">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6cf03-183">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="6cf03-184">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-184">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="6cf03-185">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-185">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="6cf03-186">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="6cf03-186">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="6cf03-187">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="6cf03-187">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="6cf03-188">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-188">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="6cf03-189">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="6cf03-189">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cf03-190">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="6cf03-190">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cf03-191">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-191">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="6cf03-192">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6cf03-192">Examples</span></span>

<span data-ttu-id="6cf03-193">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="6cf03-193">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="6cf03-194">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="6cf03-194">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="6cf03-195">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="6cf03-195">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="6cf03-196">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="6cf03-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="6cf03-197">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="6cf03-198">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="6cf03-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="6cf03-199">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="6cf03-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="6cf03-200">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="6cf03-200">Test Framework</span></span> | <span data-ttu-id="6cf03-201">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="6cf03-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6cf03-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="6cf03-202">MSTest</span></span>         | <ul><li><span data-ttu-id="6cf03-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="6cf03-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="6cf03-204">nombre</span><span class="sxs-lookup"><span data-stu-id="6cf03-204">Name</span></span></li><li><span data-ttu-id="6cf03-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="6cf03-205">ClassName</span></span></li><li><span data-ttu-id="6cf03-206">Prioridad</span><span class="sxs-lookup"><span data-stu-id="6cf03-206">Priority</span></span></li><li><span data-ttu-id="6cf03-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="6cf03-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="6cf03-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="6cf03-208">xUnit</span></span>          | <ul><li><span data-ttu-id="6cf03-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="6cf03-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="6cf03-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6cf03-210">DisplayName</span></span></li><li><span data-ttu-id="6cf03-211">Rasgos</span><span class="sxs-lookup"><span data-stu-id="6cf03-211">Traits</span></span></li></ul>                                   |

<span data-ttu-id="6cf03-212">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="6cf03-212">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="6cf03-213">Operador</span><span class="sxs-lookup"><span data-stu-id="6cf03-213">Operator</span></span> | <span data-ttu-id="6cf03-214">Función</span><span class="sxs-lookup"><span data-stu-id="6cf03-214">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="6cf03-215">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="6cf03-215">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="6cf03-216">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="6cf03-216">Not exact match</span></span> |
| `~`      | <span data-ttu-id="6cf03-217">Contiene</span><span class="sxs-lookup"><span data-stu-id="6cf03-217">Contains</span></span>        |

<span data-ttu-id="6cf03-218">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="6cf03-218">`<value>` is a string.</span></span> <span data-ttu-id="6cf03-219">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6cf03-219">All the lookups are case insensitive.</span></span>

<span data-ttu-id="6cf03-220">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="6cf03-220">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="6cf03-221">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="6cf03-221">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="6cf03-222">Operador</span><span class="sxs-lookup"><span data-stu-id="6cf03-222">Operator</span></span>            | <span data-ttu-id="6cf03-223">Función</span><span class="sxs-lookup"><span data-stu-id="6cf03-223">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="6cf03-224">O</span><span class="sxs-lookup"><span data-stu-id="6cf03-224">OR</span></span>       |
| `&`                 | <span data-ttu-id="6cf03-225">AND</span><span class="sxs-lookup"><span data-stu-id="6cf03-225">AND</span></span>      |

<span data-ttu-id="6cf03-226">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6cf03-226">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="6cf03-227">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6cf03-227">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6cf03-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cf03-228">See also</span></span>

* [<span data-ttu-id="6cf03-229">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="6cf03-229">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="6cf03-230">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6cf03-230">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
