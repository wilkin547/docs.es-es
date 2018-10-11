---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e80ba874ec8d0fbc49858719dc3b9b6e02254c78
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696461"
---
# <a name="dotnet-test"></a><span data-ttu-id="f292f-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f292f-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f292f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="f292f-104">Name</span></span>

<span data-ttu-id="f292f-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="f292f-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f292f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f292f-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f292f-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f292f-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f292f-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f292f-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f292f-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f292f-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="f292f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f292f-110">Description</span></span>

<span data-ttu-id="f292f-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="f292f-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="f292f-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f292f-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="f292f-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="f292f-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="f292f-114">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="f292f-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="f292f-115">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f292f-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="f292f-116">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f292f-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="f292f-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f292f-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="f292f-118">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="f292f-118">Path to the test project.</span></span> <span data-ttu-id="f292f-119">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f292f-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="f292f-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="f292f-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f292f-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f292f-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="f292f-122">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="f292f-123">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="f292f-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="f292f-124">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="f292f-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="f292f-125">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f292f-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f292f-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f292f-126">Defines the build configuration.</span></span> <span data-ttu-id="f292f-127">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="f292f-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="f292f-128">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-128">Enables data collector for the test run.</span></span> <span data-ttu-id="f292f-129">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="f292f-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="f292f-130">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f292f-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f292f-131">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="f292f-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f292f-132">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="f292f-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f292f-133">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="f292f-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f292f-134">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f292f-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="f292f-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="f292f-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="f292f-137">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="f292f-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="f292f-138">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="f292f-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="f292f-139">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f292f-140">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="f292f-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="f292f-141">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="f292f-142">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="f292f-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="f292f-143">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="f292f-144">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f292f-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f292f-145">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f292f-146">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f292f-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f292f-147">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f292f-147">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="f292f-148">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-148">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f292f-149">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f292f-149">Defines the build configuration.</span></span> <span data-ttu-id="f292f-150">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="f292f-150">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="f292f-151">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-151">Enables data collector for the test run.</span></span> <span data-ttu-id="f292f-152">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="f292f-152">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="f292f-153">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f292f-153">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f292f-154">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="f292f-154">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f292f-155">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="f292f-155">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f292f-156">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="f292f-156">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f292f-157">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f292f-157">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="f292f-158">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-158">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="f292f-159">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-159">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="f292f-160">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="f292f-160">Doesn't build the test project before running it.</span></span> <span data-ttu-id="f292f-161">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="f292f-161">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="f292f-162">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-162">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f292f-163">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="f292f-163">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="f292f-164">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-164">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="f292f-165">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="f292f-165">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="f292f-166">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-166">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="f292f-167">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f292f-167">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f292f-168">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f292f-169">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f292f-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f292f-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f292f-170">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="f292f-171">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-171">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f292f-172">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f292f-172">Defines the build configuration.</span></span> <span data-ttu-id="f292f-173">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="f292f-173">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="f292f-174">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f292f-174">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f292f-175">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="f292f-175">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f292f-176">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="f292f-176">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f292f-177">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="f292f-177">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f292f-178">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f292f-178">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="f292f-179">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-179">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="f292f-180">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-180">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="f292f-181">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="f292f-181">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f292f-182">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="f292f-182">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="f292f-183">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f292f-183">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="f292f-184">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f292f-184">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f292f-185">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f292f-185">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f292f-186">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f292f-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f292f-187">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f292f-187">Examples</span></span>

<span data-ttu-id="f292f-188">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="f292f-188">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="f292f-189">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="f292f-189">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="f292f-190">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="f292f-190">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="f292f-191">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="f292f-191">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f292f-192">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="f292f-192">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="f292f-193">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="f292f-193">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="f292f-194">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="f292f-194">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="f292f-195">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="f292f-195">Test Framework</span></span> | <span data-ttu-id="f292f-196">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="f292f-196">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f292f-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="f292f-197">MSTest</span></span>         | <ul><li><span data-ttu-id="f292f-198">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f292f-198">FullyQualifiedName</span></span></li><li><span data-ttu-id="f292f-199">nombre</span><span class="sxs-lookup"><span data-stu-id="f292f-199">Name</span></span></li><li><span data-ttu-id="f292f-200">ClassName</span><span class="sxs-lookup"><span data-stu-id="f292f-200">ClassName</span></span></li><li><span data-ttu-id="f292f-201">Prioridad</span><span class="sxs-lookup"><span data-stu-id="f292f-201">Priority</span></span></li><li><span data-ttu-id="f292f-202">TestCategory</span><span class="sxs-lookup"><span data-stu-id="f292f-202">TestCategory</span></span></li></ul> |
| <span data-ttu-id="f292f-203">xUnit</span><span class="sxs-lookup"><span data-stu-id="f292f-203">xUnit</span></span>          | <ul><li><span data-ttu-id="f292f-204">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f292f-204">FullyQualifiedName</span></span></li><li><span data-ttu-id="f292f-205">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f292f-205">DisplayName</span></span></li><li><span data-ttu-id="f292f-206">Rasgos</span><span class="sxs-lookup"><span data-stu-id="f292f-206">Traits</span></span></li></ul>                                   |

<span data-ttu-id="f292f-207">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="f292f-207">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="f292f-208">Operador</span><span class="sxs-lookup"><span data-stu-id="f292f-208">Operator</span></span> | <span data-ttu-id="f292f-209">Función</span><span class="sxs-lookup"><span data-stu-id="f292f-209">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="f292f-210">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="f292f-210">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="f292f-211">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="f292f-211">Not exact match</span></span> |
| `~`      | <span data-ttu-id="f292f-212">Contiene</span><span class="sxs-lookup"><span data-stu-id="f292f-212">Contains</span></span>        |

<span data-ttu-id="f292f-213">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="f292f-213">`<value>` is a string.</span></span> <span data-ttu-id="f292f-214">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f292f-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="f292f-215">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="f292f-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="f292f-216">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="f292f-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="f292f-217">Operador</span><span class="sxs-lookup"><span data-stu-id="f292f-217">Operator</span></span>            | <span data-ttu-id="f292f-218">Función</span><span class="sxs-lookup"><span data-stu-id="f292f-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="f292f-219">O</span><span class="sxs-lookup"><span data-stu-id="f292f-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="f292f-220">AND</span><span class="sxs-lookup"><span data-stu-id="f292f-220">AND</span></span>      |

<span data-ttu-id="f292f-221">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f292f-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="f292f-222">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f292f-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f292f-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="f292f-223">See also</span></span>

* [<span data-ttu-id="f292f-224">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="f292f-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="f292f-225">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f292f-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
