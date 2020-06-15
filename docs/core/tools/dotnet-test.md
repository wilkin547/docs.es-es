---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: cbe9e7cce1722efb808c68ee49bb9012be6dcff7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594457"
---
# <a name="dotnet-test"></a><span data-ttu-id="070a1-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="070a1-103">dotnet test</span></span>

<span data-ttu-id="070a1-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="070a1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="070a1-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="070a1-105">Name</span></span>

<span data-ttu-id="070a1-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="070a1-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="070a1-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="070a1-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="070a1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="070a1-108">Description</span></span>

<span data-ttu-id="070a1-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en una solución determinada.</span><span class="sxs-lookup"><span data-stu-id="070a1-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="070a1-110">El comando `dotnet test` compila la solución y ejecuta una aplicación host de prueba para cada proyecto de prueba de la solución.</span><span class="sxs-lookup"><span data-stu-id="070a1-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="070a1-111">El host de prueba ejecuta las pruebas en el proyecto especificado mediante un marco de pruebas (por ejemplo, MSTest, NUnit o xUnit) e informa del éxito o el error de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="070a1-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="070a1-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="070a1-113">En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="070a1-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="070a1-114">El host de pruebas y el marco de pruebas unitarias se empaquetan como paquetes NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="070a1-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="070a1-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="070a1-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="070a1-116">Donde `Microsoft.NET.Test.Sdk` es el host de prueba y `xunit` es el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="070a1-117">Y `xunit.runner.visualstudio` es un adaptador de prueba, que permite que el marco xUnit funcione con el host de prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="070a1-118">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="070a1-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="070a1-119">Argumentos</span><span class="sxs-lookup"><span data-stu-id="070a1-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="070a1-120">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-120">Path to the test project.</span></span>
  - <span data-ttu-id="070a1-121">Ruta de acceso a la solución.</span><span class="sxs-lookup"><span data-stu-id="070a1-121">Path to the solution.</span></span>
  - <span data-ttu-id="070a1-122">Ruta de acceso a un directorio que contiene un proyecto o una solución.</span><span class="sxs-lookup"><span data-stu-id="070a1-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="070a1-123">Ruta de acceso a un archivo *.dll* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="070a1-124">Si no se especifica, se busca un proyecto o una solución en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="070a1-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="070a1-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="070a1-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="070a1-126">Ruta de acceso a un directorio en el que se van hacer búsquedas de adaptadores de prueba adicionales.</span><span class="sxs-lookup"><span data-stu-id="070a1-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="070a1-127">Solo se inspeccionan los archivos *.dll* con el sufijo `.TestAdapter.dll`.</span><span class="sxs-lookup"><span data-stu-id="070a1-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="070a1-128">Si no se especifica, la búsqueda se realiza en el directorio del archivo *.dll* de la prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="070a1-129">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="070a1-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="070a1-130">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="070a1-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="070a1-131">Cuando se detecta un bloqueo, crea un archivo de secuencia en `TestResults/<Guid>/<Guid>_Sequence.xml` que captura el orden de las pruebas ejecutadas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="070a1-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="070a1-132">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="070a1-132">Defines the build configuration.</span></span> <span data-ttu-id="070a1-133">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="070a1-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="070a1-134">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-134">Enables data collector for the test run.</span></span> <span data-ttu-id="070a1-135">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="070a1-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="070a1-136">Para recopilar la cobertura de código en cualquier plataforma compatible con .NET Core, instale [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) y use la opción `--collect:"XPlat Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="070a1-136">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="070a1-137">En Windows, puede recopilar la cobertura de código mediante la opción `--collect "Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="070a1-137">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="070a1-138">Esta opción genera un archivo *.coverage*, que se puede abrir en Visual Studio 2019 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="070a1-138">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="070a1-139">Para más información, vea [Uso de cobertura de código](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) y [Personalización del análisis de cobertura de código](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="070a1-139">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="070a1-140">Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado y en los archivos que hay junto a él.</span><span class="sxs-lookup"><span data-stu-id="070a1-140">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="070a1-141">El proceso que registra los mensajes determina qué archivos se crean, como `*.host_<date>.txt` para el registro del host de prueba y `*.datacollector_<date>.txt` para el registro del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="070a1-141">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="070a1-142">Fuerza el uso del host de prueba de `dotnet` o .NET Framework para los archivos binarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-142">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="070a1-143">Esta opción solo determina el tipo de host que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="070a1-143">This option only determines which type of host to use.</span></span> <span data-ttu-id="070a1-144">La versión de Framework real que se va a usar viene determinada por *runtimeConfig.json* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="070a1-144">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="070a1-145">Si no se especifica, se usa el [atributo de ensamblado TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) para determinar el tipo de host.</span><span class="sxs-lookup"><span data-stu-id="070a1-145">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="070a1-146">Si ese atributo se quita de *.dll*, se usa el host de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="070a1-146">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="070a1-147">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="070a1-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="070a1-148">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="070a1-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="070a1-149">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="070a1-149">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="070a1-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="070a1-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="070a1-151">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="070a1-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="070a1-152">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="070a1-152">For example, to complete authentication.</span></span> <span data-ttu-id="070a1-153">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="070a1-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="070a1-154">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-154">Specifies a logger for test results.</span></span> <span data-ttu-id="070a1-155">A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="070a1-155">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="070a1-156">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="070a1-156">Doesn't build the test project before running it.</span></span> <span data-ttu-id="070a1-157">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="070a1-157">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="070a1-158">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="070a1-158">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="070a1-159">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="070a1-159">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="070a1-160">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="070a1-160">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="070a1-161">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="070a1-161">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="070a1-162">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="070a1-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="070a1-163">En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="070a1-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="070a1-164">`dotnet test` siempre ejecuta las pruebas desde el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="070a1-164">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="070a1-165">Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="070a1-165">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="070a1-166">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-166">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="070a1-167">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="070a1-167">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="070a1-168">El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="070a1-168">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="070a1-169">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="070a1-169">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="070a1-170">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-170">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="070a1-171">El elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="070a1-171">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="070a1-172">Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="070a1-172">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="070a1-173">El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="070a1-173">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="070a1-174">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="070a1-174">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="070a1-175">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="070a1-175">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="070a1-176">Configuración de una serie de pruebas</span><span class="sxs-lookup"><span data-stu-id="070a1-176">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="070a1-177">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="070a1-177">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="070a1-178">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="070a1-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="070a1-179">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="070a1-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="070a1-180">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="070a1-180">The default is `minimal`.</span></span> <span data-ttu-id="070a1-181">Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="070a1-181">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="070a1-182">Argumentos de **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="070a1-182">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="070a1-183">Los argumentos `RunSettings` insertados se pasan como los últimos argumentos en la línea de comandos después de "-- " (fíjese en el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="070a1-183">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="070a1-184">Los argumentos `RunSettings` insertados se especifican como pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="070a1-184">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="070a1-185">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="070a1-185">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="070a1-186">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="070a1-186">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="070a1-187">Para obtener más información, vea [Paso de argumentos de RunSettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="070a1-187">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="070a1-188">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="070a1-188">Examples</span></span>

- <span data-ttu-id="070a1-189">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="070a1-189">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="070a1-190">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="070a1-190">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="070a1-191">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="070a1-191">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="070a1-192">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de cobertura de código (después de instalar [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span><span class="sxs-lookup"><span data-stu-id="070a1-192">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="070a1-193">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de cobertura de código (solo en Windows):</span><span class="sxs-lookup"><span data-stu-id="070a1-193">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="070a1-194">Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:</span><span class="sxs-lookup"><span data-stu-id="070a1-194">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="070a1-195">Ejecute las pruebas del proyecto en el directorio actual e informe de las pruebas que estaban en curso cuando se bloqueó el host de prueba:</span><span class="sxs-lookup"><span data-stu-id="070a1-195">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="070a1-196">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="070a1-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="070a1-197">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="070a1-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="070a1-198">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="070a1-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="070a1-199">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="070a1-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="070a1-200">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="070a1-200">Test Framework</span></span> | <span data-ttu-id="070a1-201">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="070a1-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="070a1-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="070a1-202">MSTest</span></span>         | <ul><li><span data-ttu-id="070a1-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="070a1-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="070a1-204">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="070a1-204">Name</span></span></li><li><span data-ttu-id="070a1-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="070a1-205">ClassName</span></span></li><li><span data-ttu-id="070a1-206">Prioridad</span><span class="sxs-lookup"><span data-stu-id="070a1-206">Priority</span></span></li><li><span data-ttu-id="070a1-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="070a1-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="070a1-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="070a1-208">xUnit</span></span>          | <ul><li><span data-ttu-id="070a1-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="070a1-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="070a1-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="070a1-210">DisplayName</span></span></li><li><span data-ttu-id="070a1-211">Rasgos</span><span class="sxs-lookup"><span data-stu-id="070a1-211">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="070a1-212">NUnit</span><span class="sxs-lookup"><span data-stu-id="070a1-212">NUnit</span></span>          | <ul><li><span data-ttu-id="070a1-213">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="070a1-213">FullyQualifiedName</span></span></li><li><span data-ttu-id="070a1-214">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="070a1-214">Name</span></span></li><li><span data-ttu-id="070a1-215">TestCategory</span><span class="sxs-lookup"><span data-stu-id="070a1-215">TestCategory</span></span></li><li><span data-ttu-id="070a1-216">Prioridad</span><span class="sxs-lookup"><span data-stu-id="070a1-216">Priority</span></span></li></ul>                                   |

<span data-ttu-id="070a1-217">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="070a1-217">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="070a1-218">Operador</span><span class="sxs-lookup"><span data-stu-id="070a1-218">Operator</span></span> | <span data-ttu-id="070a1-219">Función</span><span class="sxs-lookup"><span data-stu-id="070a1-219">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="070a1-220">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="070a1-220">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="070a1-221">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="070a1-221">Not exact match</span></span> |
| `~`      | <span data-ttu-id="070a1-222">Contiene</span><span class="sxs-lookup"><span data-stu-id="070a1-222">Contains</span></span>        |
| `!~`     | <span data-ttu-id="070a1-223">No contiene</span><span class="sxs-lookup"><span data-stu-id="070a1-223">Not contains</span></span>    |

<span data-ttu-id="070a1-224">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="070a1-224">`<value>` is a string.</span></span> <span data-ttu-id="070a1-225">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="070a1-225">All the lookups are case insensitive.</span></span>

<span data-ttu-id="070a1-226">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="070a1-226">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="070a1-227">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="070a1-227">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="070a1-228">Operador</span><span class="sxs-lookup"><span data-stu-id="070a1-228">Operator</span></span>            | <span data-ttu-id="070a1-229">Función</span><span class="sxs-lookup"><span data-stu-id="070a1-229">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="070a1-230">O</span><span class="sxs-lookup"><span data-stu-id="070a1-230">OR</span></span>       |
| `&`                 | <span data-ttu-id="070a1-231">AND</span><span class="sxs-lookup"><span data-stu-id="070a1-231">AND</span></span>      |

<span data-ttu-id="070a1-232">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="070a1-232">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="070a1-233">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="070a1-233">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="070a1-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="070a1-234">See also</span></span>

- [<span data-ttu-id="070a1-235">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="070a1-235">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="070a1-236">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="070a1-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="070a1-237">Paso de argumentos runsettings a través de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="070a1-237">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
