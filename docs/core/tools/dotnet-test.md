---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 8a10ac9175ee5fcf8649efbb07d8d382ac3afdc7
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696275"
---
# <a name="dotnet-test"></a><span data-ttu-id="72edc-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="72edc-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="72edc-104">nombre</span><span class="sxs-lookup"><span data-stu-id="72edc-104">Name</span></span>

<span data-ttu-id="72edc-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="72edc-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="72edc-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="72edc-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72edc-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72edc-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72edc-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72edc-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72edc-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72edc-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="72edc-110">Description</span><span class="sxs-lookup"><span data-stu-id="72edc-110">Description</span></span>

<span data-ttu-id="72edc-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="72edc-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="72edc-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="72edc-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="72edc-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="72edc-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="72edc-114">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="72edc-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="72edc-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72edc-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="72edc-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="72edc-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="72edc-117">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="72edc-117">Path to the test project.</span></span> <span data-ttu-id="72edc-118">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="72edc-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="72edc-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="72edc-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72edc-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72edc-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="72edc-121">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="72edc-122">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="72edc-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="72edc-123">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="72edc-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="72edc-124">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="72edc-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="72edc-125">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="72edc-125">Defines the build configuration.</span></span> <span data-ttu-id="72edc-126">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="72edc-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="72edc-127">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-127">Enables data collector for the test run.</span></span> <span data-ttu-id="72edc-128">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="72edc-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="72edc-129">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="72edc-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="72edc-130">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="72edc-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="72edc-131">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="72edc-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="72edc-132">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="72edc-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="72edc-133">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="72edc-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="72edc-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="72edc-135">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="72edc-136">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="72edc-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="72edc-137">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="72edc-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="72edc-138">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72edc-139">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="72edc-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="72edc-140">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="72edc-141">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="72edc-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="72edc-142">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="72edc-143">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="72edc-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="72edc-144">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="72edc-145">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="72edc-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72edc-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72edc-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="72edc-147">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="72edc-148">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="72edc-148">Defines the build configuration.</span></span> <span data-ttu-id="72edc-149">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="72edc-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="72edc-150">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-150">Enables data collector for the test run.</span></span> <span data-ttu-id="72edc-151">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="72edc-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="72edc-152">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="72edc-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="72edc-153">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="72edc-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="72edc-154">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="72edc-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="72edc-155">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="72edc-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="72edc-156">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="72edc-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="72edc-157">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="72edc-158">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="72edc-159">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="72edc-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="72edc-160">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="72edc-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="72edc-161">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72edc-162">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="72edc-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="72edc-163">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="72edc-164">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="72edc-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="72edc-165">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="72edc-166">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="72edc-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="72edc-167">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="72edc-168">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="72edc-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72edc-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72edc-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="72edc-170">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="72edc-171">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="72edc-171">Defines the build configuration.</span></span> <span data-ttu-id="72edc-172">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="72edc-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="72edc-173">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="72edc-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="72edc-174">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="72edc-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="72edc-175">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="72edc-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="72edc-176">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="72edc-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="72edc-177">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="72edc-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="72edc-178">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="72edc-179">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="72edc-180">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="72edc-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72edc-181">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="72edc-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="72edc-182">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="72edc-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="72edc-183">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="72edc-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="72edc-184">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="72edc-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="72edc-185">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="72edc-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="72edc-186">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72edc-186">Examples</span></span>

<span data-ttu-id="72edc-187">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="72edc-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="72edc-188">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="72edc-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="72edc-189">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="72edc-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="72edc-190">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="72edc-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="72edc-191">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="72edc-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="72edc-192">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="72edc-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="72edc-193">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="72edc-193">Test Framework</span></span> | <span data-ttu-id="72edc-194">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="72edc-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="72edc-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="72edc-195">MSTest</span></span>         | <ul><li><span data-ttu-id="72edc-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="72edc-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="72edc-197">nombre</span><span class="sxs-lookup"><span data-stu-id="72edc-197">Name</span></span></li><li><span data-ttu-id="72edc-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="72edc-198">ClassName</span></span></li><li><span data-ttu-id="72edc-199">Prioridad</span><span class="sxs-lookup"><span data-stu-id="72edc-199">Priority</span></span></li><li><span data-ttu-id="72edc-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="72edc-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="72edc-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="72edc-201">xUnit</span></span>          | <ul><li><span data-ttu-id="72edc-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="72edc-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="72edc-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="72edc-203">DisplayName</span></span></li><li><span data-ttu-id="72edc-204">Rasgos</span><span class="sxs-lookup"><span data-stu-id="72edc-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="72edc-205">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="72edc-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="72edc-206">Operador</span><span class="sxs-lookup"><span data-stu-id="72edc-206">Operator</span></span> | <span data-ttu-id="72edc-207">Función</span><span class="sxs-lookup"><span data-stu-id="72edc-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="72edc-208">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="72edc-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="72edc-209">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="72edc-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="72edc-210">Contiene</span><span class="sxs-lookup"><span data-stu-id="72edc-210">Contains</span></span>        |

<span data-ttu-id="72edc-211">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="72edc-211">`<value>` is a string.</span></span> <span data-ttu-id="72edc-212">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="72edc-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="72edc-213">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="72edc-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="72edc-214">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="72edc-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="72edc-215">Operador</span><span class="sxs-lookup"><span data-stu-id="72edc-215">Operator</span></span>            | <span data-ttu-id="72edc-216">Función</span><span class="sxs-lookup"><span data-stu-id="72edc-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="72edc-217">O</span><span class="sxs-lookup"><span data-stu-id="72edc-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="72edc-218">AND</span><span class="sxs-lookup"><span data-stu-id="72edc-218">AND</span></span>      |

<span data-ttu-id="72edc-219">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="72edc-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="72edc-220">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="72edc-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72edc-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="72edc-221">See also</span></span>

[<span data-ttu-id="72edc-222">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="72edc-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
[<span data-ttu-id="72edc-223">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="72edc-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
