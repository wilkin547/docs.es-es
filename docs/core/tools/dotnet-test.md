---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 7946196b27489870da1c16b15cbf5f078ae89c61
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44137205"
---
# <a name="dotnet-test"></a><span data-ttu-id="ae65a-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ae65a-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ae65a-104">nombre</span><span class="sxs-lookup"><span data-stu-id="ae65a-104">Name</span></span>

<span data-ttu-id="ae65a-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="ae65a-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ae65a-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ae65a-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ae65a-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ae65a-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ae65a-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ae65a-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ae65a-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ae65a-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ae65a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae65a-110">Description</span></span>

<span data-ttu-id="ae65a-111">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="ae65a-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="ae65a-112">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae65a-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="ae65a-113">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="ae65a-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="ae65a-114">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae65a-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="ae65a-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ae65a-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="ae65a-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ae65a-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ae65a-117">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="ae65a-117">Path to the test project.</span></span> <span data-ttu-id="ae65a-118">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ae65a-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="ae65a-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="ae65a-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ae65a-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ae65a-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ae65a-121">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="ae65a-122">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="ae65a-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="ae65a-123">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="ae65a-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="ae65a-124">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ae65a-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ae65a-125">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="ae65a-125">Defines the build configuration.</span></span> <span data-ttu-id="ae65a-126">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="ae65a-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ae65a-127">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-127">Enables data collector for the test run.</span></span> <span data-ttu-id="ae65a-128">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="ae65a-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ae65a-129">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="ae65a-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ae65a-130">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="ae65a-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ae65a-131">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="ae65a-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ae65a-132">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ae65a-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ae65a-133">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ae65a-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ae65a-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ae65a-135">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ae65a-136">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="ae65a-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ae65a-137">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="ae65a-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ae65a-138">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ae65a-139">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="ae65a-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ae65a-140">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ae65a-141">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="ae65a-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ae65a-142">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ae65a-143">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="ae65a-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ae65a-144">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ae65a-145">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ae65a-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ae65a-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ae65a-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ae65a-147">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ae65a-148">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="ae65a-148">Defines the build configuration.</span></span> <span data-ttu-id="ae65a-149">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="ae65a-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ae65a-150">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-150">Enables data collector for the test run.</span></span> <span data-ttu-id="ae65a-151">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="ae65a-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ae65a-152">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="ae65a-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ae65a-153">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="ae65a-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ae65a-154">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="ae65a-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ae65a-155">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ae65a-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ae65a-156">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ae65a-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ae65a-157">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ae65a-158">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ae65a-159">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="ae65a-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ae65a-160">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="ae65a-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ae65a-161">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ae65a-162">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="ae65a-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ae65a-163">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ae65a-164">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="ae65a-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ae65a-165">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ae65a-166">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="ae65a-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ae65a-167">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ae65a-168">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ae65a-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ae65a-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ae65a-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ae65a-170">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ae65a-171">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="ae65a-171">Defines the build configuration.</span></span> <span data-ttu-id="ae65a-172">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="ae65a-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ae65a-173">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="ae65a-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ae65a-174">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="ae65a-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ae65a-175">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="ae65a-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ae65a-176">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ae65a-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ae65a-177">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ae65a-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ae65a-178">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ae65a-179">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ae65a-180">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="ae65a-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ae65a-181">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="ae65a-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ae65a-182">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="ae65a-183">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="ae65a-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ae65a-184">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="ae65a-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ae65a-185">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ae65a-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ae65a-186">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ae65a-186">Examples</span></span>

<span data-ttu-id="ae65a-187">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="ae65a-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="ae65a-188">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="ae65a-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="ae65a-189">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="ae65a-189">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="ae65a-190">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="ae65a-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ae65a-191">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="ae65a-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="ae65a-192">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="ae65a-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="ae65a-193">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="ae65a-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="ae65a-194">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="ae65a-194">Test Framework</span></span> | <span data-ttu-id="ae65a-195">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="ae65a-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ae65a-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="ae65a-196">MSTest</span></span>         | <ul><li><span data-ttu-id="ae65a-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ae65a-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="ae65a-198">nombre</span><span class="sxs-lookup"><span data-stu-id="ae65a-198">Name</span></span></li><li><span data-ttu-id="ae65a-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="ae65a-199">ClassName</span></span></li><li><span data-ttu-id="ae65a-200">Prioridad</span><span class="sxs-lookup"><span data-stu-id="ae65a-200">Priority</span></span></li><li><span data-ttu-id="ae65a-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="ae65a-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="ae65a-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="ae65a-202">xUnit</span></span>          | <ul><li><span data-ttu-id="ae65a-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ae65a-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="ae65a-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ae65a-204">DisplayName</span></span></li><li><span data-ttu-id="ae65a-205">Rasgos</span><span class="sxs-lookup"><span data-stu-id="ae65a-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="ae65a-206">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="ae65a-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="ae65a-207">Operador</span><span class="sxs-lookup"><span data-stu-id="ae65a-207">Operator</span></span> | <span data-ttu-id="ae65a-208">Función</span><span class="sxs-lookup"><span data-stu-id="ae65a-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="ae65a-209">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="ae65a-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="ae65a-210">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="ae65a-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="ae65a-211">Contiene</span><span class="sxs-lookup"><span data-stu-id="ae65a-211">Contains</span></span>        |

<span data-ttu-id="ae65a-212">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="ae65a-212">`<value>` is a string.</span></span> <span data-ttu-id="ae65a-213">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ae65a-213">All the lookups are case insensitive.</span></span>

<span data-ttu-id="ae65a-214">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="ae65a-214">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="ae65a-215">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="ae65a-215">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="ae65a-216">Operador</span><span class="sxs-lookup"><span data-stu-id="ae65a-216">Operator</span></span>            | <span data-ttu-id="ae65a-217">Función</span><span class="sxs-lookup"><span data-stu-id="ae65a-217">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="ae65a-218">O</span><span class="sxs-lookup"><span data-stu-id="ae65a-218">OR</span></span>       |
| `&`                 | <span data-ttu-id="ae65a-219">AND</span><span class="sxs-lookup"><span data-stu-id="ae65a-219">AND</span></span>      |

<span data-ttu-id="ae65a-220">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ae65a-220">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="ae65a-221">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ae65a-221">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae65a-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae65a-222">See also</span></span>

* [<span data-ttu-id="ae65a-223">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="ae65a-223">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="ae65a-224">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ae65a-224">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
