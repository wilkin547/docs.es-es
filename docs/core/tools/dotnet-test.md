---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: d67521084330b206afca89baf59228b99ca799a1
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656760"
---
# <a name="dotnet-test"></a><span data-ttu-id="28cfc-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="28cfc-103">dotnet test</span></span>

<span data-ttu-id="28cfc-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="28cfc-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="28cfc-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="28cfc-105">Name</span></span>

<span data-ttu-id="28cfc-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="28cfc-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="28cfc-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="28cfc-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="28cfc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="28cfc-108">Description</span></span>

<span data-ttu-id="28cfc-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en una solución determinada.</span><span class="sxs-lookup"><span data-stu-id="28cfc-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="28cfc-110">El comando `dotnet test` compila la solución y ejecuta una aplicación host de prueba para cada proyecto de prueba de la solución.</span><span class="sxs-lookup"><span data-stu-id="28cfc-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="28cfc-111">El host de prueba ejecuta las pruebas en el proyecto especificado mediante un marco de pruebas (por ejemplo, MSTest, NUnit o xUnit) e informa del éxito o el error de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="28cfc-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="28cfc-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="28cfc-113">En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="28cfc-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="28cfc-114">El host de pruebas y el marco de pruebas unitarias se empaquetan como paquetes NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="28cfc-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="28cfc-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="28cfc-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="28cfc-116">Donde `Microsoft.NET.Test.Sdk` es el host de prueba y `xunit` es el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="28cfc-117">Y `xunit.runner.visualstudio` es un adaptador de prueba, que permite que el marco xUnit funcione con el host de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="28cfc-118">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="28cfc-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="28cfc-119">Argumentos</span><span class="sxs-lookup"><span data-stu-id="28cfc-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="28cfc-120">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-120">Path to the test project.</span></span>
  - <span data-ttu-id="28cfc-121">Ruta de acceso a la solución.</span><span class="sxs-lookup"><span data-stu-id="28cfc-121">Path to the solution.</span></span>
  - <span data-ttu-id="28cfc-122">Ruta de acceso a un directorio que contiene un proyecto o una solución.</span><span class="sxs-lookup"><span data-stu-id="28cfc-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="28cfc-123">Ruta de acceso a un archivo *.dll* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="28cfc-124">Si no se especifica, se busca un proyecto o una solución en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="28cfc-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="28cfc-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="28cfc-125">Options</span></span>

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  <span data-ttu-id="28cfc-126">Ruta de acceso a un directorio en el que se van hacer búsquedas de adaptadores de prueba adicionales.</span><span class="sxs-lookup"><span data-stu-id="28cfc-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="28cfc-127">Solo se inspeccionan los archivos *.dll* con el sufijo `.TestAdapter.dll`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="28cfc-128">Si no se especifica, la búsqueda se realiza en el directorio del archivo *.dll* de la prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="28cfc-129">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="28cfc-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="28cfc-130">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="28cfc-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="28cfc-131">Cuando se detecta un bloqueo, crea un archivo de secuencia en `TestResults/<Guid>/<Guid>_Sequence.xml` que captura el orden de las pruebas ejecutadas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="28cfc-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- <span data-ttu-id="28cfc-132">**`--blame-crash`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-132">**`--blame-crash`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-133">Ejecuta las pruebas en modo de culpa y recopila un volcado de memoria cuando el host de prueba se cierra de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="28cfc-133">Runs the tests in blame mode and collects a crash dump when the test host exits unexpectedly.</span></span> <span data-ttu-id="28cfc-134">Esta opción solo se admite en Windows.</span><span class="sxs-lookup"><span data-stu-id="28cfc-134">This option is only supported on Windows.</span></span> <span data-ttu-id="28cfc-135">Un directorio que contenga *procdump.exe* y *procdump64.exe* debe estar en la variable de entorno PATH o PROCDUMP_PATH.</span><span class="sxs-lookup"><span data-stu-id="28cfc-135">A directory that contains *procdump.exe* and *procdump64.exe* must be in the PATH or PROCDUMP_PATH environment variable.</span></span> <span data-ttu-id="28cfc-136">[Descargue las herramientas](https://docs.microsoft.com/sysinternals/downloads/procdump).</span><span class="sxs-lookup"><span data-stu-id="28cfc-136">[Download the tools](https://docs.microsoft.com/sysinternals/downloads/procdump).</span></span> <span data-ttu-id="28cfc-137">Implica `--blame`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-137">Implies `--blame`.</span></span>

- <span data-ttu-id="28cfc-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-139">El tipo de volcado de memoria que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="28cfc-139">The type of crash dump to be collected.</span></span> <span data-ttu-id="28cfc-140">Implica `--blame-crash`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-140">Implies `--blame-crash`.</span></span>

- <span data-ttu-id="28cfc-141">**`--blame-crash-collect-always`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-141">**`--blame-crash-collect-always`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-142">Recopila un volcado de memoria en la salida de host de prueba esperada e inesperada.</span><span class="sxs-lookup"><span data-stu-id="28cfc-142">Collects a crash dump on expected as well as unexpected test host exit.</span></span>

- <span data-ttu-id="28cfc-143">**`--blame-hang`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-143">**`--blame-hang`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-144">Ejecute las pruebas en modo de culpa y recopile un volcado de bloqueo cuando una prueba supere el tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="28cfc-144">Run the tests in blame mode and collects a hang dump when a test exceeds the given timeout.</span></span>

- <span data-ttu-id="28cfc-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-146">El tipo de volcado de memoria que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="28cfc-146">The type of crash dump to be collected.</span></span> <span data-ttu-id="28cfc-147">Debe ser `full`, `mini` o `none`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-147">It should be `full`, `mini`, or `none`.</span></span> <span data-ttu-id="28cfc-148">Cuando se especifica `none`, el host de prueba finaliza en el tiempo de espera, pero no se recopila ningún volcado.</span><span class="sxs-lookup"><span data-stu-id="28cfc-148">When `none` is specified, test host is terminated on timeout, but no dump is collected.</span></span> <span data-ttu-id="28cfc-149">Implica `--blame-hang`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-149">Implies `--blame-hang`.</span></span>

- <span data-ttu-id="28cfc-150">**`--blame-hang-timeout <TIMESPAN>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)</span><span class="sxs-lookup"><span data-stu-id="28cfc-150">**`--blame-hang-timeout <TIMESPAN>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="28cfc-151">Tiempo de espera por prueba, después del cual se desencadena un volcado de bloqueo y finaliza el proceso de host de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-151">Per-test timeout, after which a hang dump is triggered and the test host process is terminated.</span></span> <span data-ttu-id="28cfc-152">El valor de tiempo de espera se especifica en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="28cfc-152">The timeout value is specified in one of the following formats:</span></span>
  
  - <span data-ttu-id="28cfc-153">1,5 h</span><span class="sxs-lookup"><span data-stu-id="28cfc-153">1.5h</span></span>
  - <span data-ttu-id="28cfc-154">90 m</span><span class="sxs-lookup"><span data-stu-id="28cfc-154">90m</span></span>
  - <span data-ttu-id="28cfc-155">5400 s</span><span class="sxs-lookup"><span data-stu-id="28cfc-155">5400s</span></span>
  - <span data-ttu-id="28cfc-156">5 400 000 ms</span><span class="sxs-lookup"><span data-stu-id="28cfc-156">5400000ms</span></span>

  <span data-ttu-id="28cfc-157">Cuando no se usa ninguna unidad (por ejemplo, 5 400 000), se supone que el valor está en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="28cfc-157">When no unit is used (for example, 5400000), the value is assumed to be in milliseconds.</span></span> <span data-ttu-id="28cfc-158">Cuando se usa junto con las pruebas basadas en datos, el comportamiento de tiempo de espera depende del adaptador de prueba usado.</span><span class="sxs-lookup"><span data-stu-id="28cfc-158">When used together with data driven tests, the timeout behavior depends on the test adapter used.</span></span> <span data-ttu-id="28cfc-159">En xUnit y NUnit, el tiempo de espera se renueva después de cada caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-159">For xUnit and NUnit the timeout is renewed after every test case.</span></span> <span data-ttu-id="28cfc-160">En MSTest, el tiempo de espera se usa en todos los casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-160">For MSTest, the timeout is used for all test cases.</span></span> <span data-ttu-id="28cfc-161">Esta opción se admite en Windows con netcoreapp2.1 y versiones posteriores, y en Linux con netcoreapp3.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="28cfc-161">This option is supported on Windows with netcoreapp2.1 and later, and on Linux with netcoreapp3.1 and later.</span></span> <span data-ttu-id="28cfc-162">macOS no se admite.</span><span class="sxs-lookup"><span data-stu-id="28cfc-162">macOS is not supported.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="28cfc-163">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="28cfc-163">Defines the build configuration.</span></span> <span data-ttu-id="28cfc-164">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="28cfc-164">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_NAME>`**

  <span data-ttu-id="28cfc-165">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-165">Enables data collector for the test run.</span></span> <span data-ttu-id="28cfc-166">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="28cfc-166">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="28cfc-167">Para recopilar la cobertura de código en cualquier plataforma compatible con .NET Core, instale [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) y use la opción `--collect:"XPlat Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-167">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="28cfc-168">En Windows, puede recopilar la cobertura de código mediante la opción `--collect "Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-168">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="28cfc-169">Esta opción genera un archivo *.coverage*, que se puede abrir en Visual Studio 2019 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="28cfc-169">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="28cfc-170">Para más información, vea [Uso de cobertura de código](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) y [Personalización del análisis de cobertura de código](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="28cfc-170">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <LOG_FILE>`**

  <span data-ttu-id="28cfc-171">Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado y en los archivos que hay junto a él.</span><span class="sxs-lookup"><span data-stu-id="28cfc-171">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="28cfc-172">El proceso que registra los mensajes determina qué archivos se crean, como `*.host_<date>.txt` para el registro del host de prueba y `*.datacollector_<date>.txt` para el registro del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="28cfc-172">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="28cfc-173">Fuerza el uso del host de prueba de `dotnet` o .NET Framework para los archivos binarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-173">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="28cfc-174">Esta opción solo determina el tipo de host que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="28cfc-174">This option only determines which type of host to use.</span></span> <span data-ttu-id="28cfc-175">La versión de Framework real que se va a usar viene determinada por *runtimeConfig.json* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="28cfc-175">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="28cfc-176">Si no se especifica, se usa el [atributo de ensamblado TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) para determinar el tipo de host.</span><span class="sxs-lookup"><span data-stu-id="28cfc-176">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="28cfc-177">Si ese atributo se quita de *.dll*, se usa el host de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28cfc-177">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="28cfc-178">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="28cfc-178">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="28cfc-179">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="28cfc-179">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="28cfc-180">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="28cfc-180">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="28cfc-181">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="28cfc-181">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="28cfc-182">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="28cfc-182">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="28cfc-183">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="28cfc-183">For example, to complete authentication.</span></span> <span data-ttu-id="28cfc-184">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="28cfc-184">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER>`**

  <span data-ttu-id="28cfc-185">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-185">Specifies a logger for test results.</span></span> <span data-ttu-id="28cfc-186">A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-186">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="28cfc-187">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="28cfc-187">Doesn't build the test project before running it.</span></span> <span data-ttu-id="28cfc-188">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="28cfc-188">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="28cfc-189">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="28cfc-189">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="28cfc-190">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="28cfc-190">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="28cfc-191">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="28cfc-191">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="28cfc-192">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="28cfc-192">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="28cfc-193">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-193">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="28cfc-194">En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="28cfc-194">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="28cfc-195">`dotnet test` siempre ejecuta las pruebas desde el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="28cfc-195">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="28cfc-196">Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="28cfc-196">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <RESULTS_DIR>`**

  <span data-ttu-id="28cfc-197">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-197">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="28cfc-198">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="28cfc-198">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="28cfc-199">El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="28cfc-199">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="28cfc-200">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="28cfc-200">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="28cfc-201">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-201">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="28cfc-202">El elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-202">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="28cfc-203">Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="28cfc-203">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="28cfc-204">El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-204">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="28cfc-205">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="28cfc-205">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="28cfc-206">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-206">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="28cfc-207">Configuración de una serie de pruebas</span><span class="sxs-lookup"><span data-stu-id="28cfc-207">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="28cfc-208">Enumera las pruebas detectadas en vez de ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-208">List the discovered tests instead of running the tests.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="28cfc-209">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="28cfc-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="28cfc-210">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="28cfc-211">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-211">The default is `minimal`.</span></span> <span data-ttu-id="28cfc-212">Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="28cfc-212">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="28cfc-213">Argumentos de **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="28cfc-213">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="28cfc-214">Los argumentos `RunSettings` insertados se pasan como los últimos argumentos en la línea de comandos después de "-- " (fíjese en el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="28cfc-214">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="28cfc-215">Los argumentos `RunSettings` insertados se especifican como pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-215">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="28cfc-216">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-216">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="28cfc-217">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="28cfc-217">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="28cfc-218">Para obtener más información, vea [Paso de argumentos de RunSettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="28cfc-218">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="28cfc-219">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="28cfc-219">Examples</span></span>

- <span data-ttu-id="28cfc-220">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="28cfc-220">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="28cfc-221">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="28cfc-221">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="28cfc-222">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="28cfc-222">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="28cfc-223">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de cobertura de código (después de instalar la integración de recopiladores de [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md)):</span><span class="sxs-lookup"><span data-stu-id="28cfc-223">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) collectors integration):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="28cfc-224">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de cobertura de código (solo en Windows):</span><span class="sxs-lookup"><span data-stu-id="28cfc-224">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="28cfc-225">Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:</span><span class="sxs-lookup"><span data-stu-id="28cfc-225">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="28cfc-226">Ejecute las pruebas del proyecto en el directorio actual e informe de las pruebas que estaban en curso cuando se bloqueó el host de prueba:</span><span class="sxs-lookup"><span data-stu-id="28cfc-226">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="28cfc-227">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="28cfc-227">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="28cfc-228">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-228">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="28cfc-229">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="28cfc-229">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="28cfc-230">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="28cfc-230">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="28cfc-231">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="28cfc-231">Test Framework</span></span> | <span data-ttu-id="28cfc-232">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="28cfc-232">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="28cfc-233">MSTest</span><span class="sxs-lookup"><span data-stu-id="28cfc-233">MSTest</span></span>         | <ul><li><span data-ttu-id="28cfc-234">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="28cfc-234">FullyQualifiedName</span></span></li><li><span data-ttu-id="28cfc-235">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="28cfc-235">Name</span></span></li><li><span data-ttu-id="28cfc-236">ClassName</span><span class="sxs-lookup"><span data-stu-id="28cfc-236">ClassName</span></span></li><li><span data-ttu-id="28cfc-237">Prioridad</span><span class="sxs-lookup"><span data-stu-id="28cfc-237">Priority</span></span></li><li><span data-ttu-id="28cfc-238">TestCategory</span><span class="sxs-lookup"><span data-stu-id="28cfc-238">TestCategory</span></span></li></ul> |
| <span data-ttu-id="28cfc-239">xUnit</span><span class="sxs-lookup"><span data-stu-id="28cfc-239">xUnit</span></span>          | <ul><li><span data-ttu-id="28cfc-240">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="28cfc-240">FullyQualifiedName</span></span></li><li><span data-ttu-id="28cfc-241">DisplayName</span><span class="sxs-lookup"><span data-stu-id="28cfc-241">DisplayName</span></span></li><li><span data-ttu-id="28cfc-242">Rasgos</span><span class="sxs-lookup"><span data-stu-id="28cfc-242">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="28cfc-243">NUnit</span><span class="sxs-lookup"><span data-stu-id="28cfc-243">NUnit</span></span>          | <ul><li><span data-ttu-id="28cfc-244">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="28cfc-244">FullyQualifiedName</span></span></li><li><span data-ttu-id="28cfc-245">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="28cfc-245">Name</span></span></li><li><span data-ttu-id="28cfc-246">TestCategory</span><span class="sxs-lookup"><span data-stu-id="28cfc-246">TestCategory</span></span></li><li><span data-ttu-id="28cfc-247">Prioridad</span><span class="sxs-lookup"><span data-stu-id="28cfc-247">Priority</span></span></li></ul>                                   |

<span data-ttu-id="28cfc-248">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="28cfc-248">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="28cfc-249">Operador</span><span class="sxs-lookup"><span data-stu-id="28cfc-249">Operator</span></span> | <span data-ttu-id="28cfc-250">Función</span><span class="sxs-lookup"><span data-stu-id="28cfc-250">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="28cfc-251">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="28cfc-251">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="28cfc-252">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="28cfc-252">Not exact match</span></span> |
| `~`      | <span data-ttu-id="28cfc-253">Contiene</span><span class="sxs-lookup"><span data-stu-id="28cfc-253">Contains</span></span>        |
| `!~`     | <span data-ttu-id="28cfc-254">No contiene</span><span class="sxs-lookup"><span data-stu-id="28cfc-254">Not contains</span></span>    |

<span data-ttu-id="28cfc-255">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="28cfc-255">`<value>` is a string.</span></span> <span data-ttu-id="28cfc-256">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28cfc-256">All the lookups are case insensitive.</span></span>

<span data-ttu-id="28cfc-257">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="28cfc-257">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="28cfc-258">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="28cfc-258">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="28cfc-259">Operador</span><span class="sxs-lookup"><span data-stu-id="28cfc-259">Operator</span></span>            | <span data-ttu-id="28cfc-260">Función</span><span class="sxs-lookup"><span data-stu-id="28cfc-260">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="28cfc-261">O</span><span class="sxs-lookup"><span data-stu-id="28cfc-261">OR</span></span>       |
| `&`                 | <span data-ttu-id="28cfc-262">AND</span><span class="sxs-lookup"><span data-stu-id="28cfc-262">AND</span></span>      |

<span data-ttu-id="28cfc-263">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="28cfc-263">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="28cfc-264">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="28cfc-264">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28cfc-265">Vea también</span><span class="sxs-lookup"><span data-stu-id="28cfc-265">See also</span></span>

- [<span data-ttu-id="28cfc-266">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="28cfc-266">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="28cfc-267">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="28cfc-267">.NET Core Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="28cfc-268">Paso de argumentos runsettings a través de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="28cfc-268">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
