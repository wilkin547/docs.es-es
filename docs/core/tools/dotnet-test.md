---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: ef71e48daa7c4a6f33961d05a2f3def122087b0e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975438"
---
# <a name="dotnet-test"></a><span data-ttu-id="be6a6-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="be6a6-103">dotnet test</span></span>

<span data-ttu-id="be6a6-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="be6a6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="be6a6-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="be6a6-105">Name</span></span>

<span data-ttu-id="be6a6-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="be6a6-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="be6a6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="be6a6-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="be6a6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="be6a6-108">Description</span></span>

<span data-ttu-id="be6a6-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en una solución determinada.</span><span class="sxs-lookup"><span data-stu-id="be6a6-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="be6a6-110">El comando `dotnet test` compila la solución y ejecuta una aplicación host de prueba para cada proyecto de prueba de la solución.</span><span class="sxs-lookup"><span data-stu-id="be6a6-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="be6a6-111">El host de prueba ejecuta las pruebas en el proyecto especificado mediante un marco de pruebas (por ejemplo, MSTest, NUnit o xUnit) e informa del éxito o el error de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="be6a6-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="be6a6-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="be6a6-113">En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="be6a6-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="be6a6-114">El host de pruebas y el marco de pruebas unitarias se empaquetan como paquetes NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="be6a6-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="be6a6-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be6a6-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="be6a6-116">Donde `Microsoft.NET.Test.Sdk` es el host de prueba y `xunit` es el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="be6a6-117">Y `xunit.runner.visualstudio` es un adaptador de prueba, que permite que el marco xUnit funcione con el host de prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="be6a6-118">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="be6a6-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="be6a6-119">Argumentos</span><span class="sxs-lookup"><span data-stu-id="be6a6-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="be6a6-120">Ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-120">Path to the test project.</span></span>
  - <span data-ttu-id="be6a6-121">Ruta de acceso a la solución.</span><span class="sxs-lookup"><span data-stu-id="be6a6-121">Path to the solution.</span></span>
  - <span data-ttu-id="be6a6-122">Ruta de acceso a un directorio que contiene un proyecto o una solución.</span><span class="sxs-lookup"><span data-stu-id="be6a6-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="be6a6-123">Ruta de acceso a un archivo *.dll* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="be6a6-124">Si no se especifica, se busca un proyecto o una solución en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="be6a6-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="be6a6-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="be6a6-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="be6a6-126">Ruta de acceso a un directorio en el que se van hacer búsquedas de adaptadores de prueba adicionales.</span><span class="sxs-lookup"><span data-stu-id="be6a6-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="be6a6-127">Solo se inspeccionan los archivos *.dll* con el sufijo `.TestAdapter.dll`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="be6a6-128">Si no se especifica, la búsqueda se realiza en el directorio del archivo *.dll* de la prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="be6a6-129">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="be6a6-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="be6a6-130">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="be6a6-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="be6a6-131">Cuando se detecta un bloqueo, crea un archivo de secuencia en `TestResults/<Guid>/<Guid>_Sequence.xml` que captura el orden de las pruebas ejecutadas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="be6a6-131">When a crash is detected, it creates an sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="be6a6-132">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="be6a6-132">Defines the build configuration.</span></span> <span data-ttu-id="be6a6-133">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="be6a6-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="be6a6-134">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-134">Enables data collector for the test run.</span></span> <span data-ttu-id="be6a6-135">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="be6a6-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="be6a6-136">Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado y en los archivos que hay junto a él.</span><span class="sxs-lookup"><span data-stu-id="be6a6-136">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="be6a6-137">El proceso que registra los mensajes determina qué archivos se crean, como `*.host_<date>.txt` para el registro del host de prueba y `*.datacollector_<date>.txt` para el registro del recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="be6a6-137">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="be6a6-138">Fuerza el uso del host de prueba de `dotnet` o .NET Framework para los archivos binarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-138">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="be6a6-139">Esta opción solo determina el tipo de host que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="be6a6-139">This option only determines which type of host to use.</span></span> <span data-ttu-id="be6a6-140">La versión de Framework real que se va a usar viene determinada por *runtimeConfig.json* del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="be6a6-140">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="be6a6-141">Si no se especifica, se usa el [atributo de ensamblado TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) para determinar el tipo de host.</span><span class="sxs-lookup"><span data-stu-id="be6a6-141">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="be6a6-142">Si ese atributo se quita de *.dll*, se usa el host de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be6a6-142">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="be6a6-143">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="be6a6-143">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="be6a6-144">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="be6a6-144">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="be6a6-145">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="be6a6-145">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="be6a6-146">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="be6a6-146">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="be6a6-147">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="be6a6-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="be6a6-148">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="be6a6-148">For example, to complete authentication.</span></span> <span data-ttu-id="be6a6-149">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="be6a6-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="be6a6-150">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-150">Specifies a logger for test results.</span></span> <span data-ttu-id="be6a6-151">A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-151">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="be6a6-152">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="be6a6-152">Doesn't build the test project before running it.</span></span> <span data-ttu-id="be6a6-153">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="be6a6-153">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="be6a6-154">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="be6a6-154">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="be6a6-155">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="be6a6-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="be6a6-156">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="be6a6-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="be6a6-157">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="be6a6-157">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="be6a6-158">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-158">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="be6a6-159">En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="be6a6-159">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="be6a6-160">`dotnet test` siempre ejecuta las pruebas desde el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="be6a6-160">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="be6a6-161">Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="be6a6-161">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="be6a6-162">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-162">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="be6a6-163">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="be6a6-163">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="be6a6-164">El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="be6a6-164">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="be6a6-165">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="be6a6-165">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="be6a6-166">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-166">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="be6a6-167">Tenga en cuenta que el elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-167">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="be6a6-168">Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="be6a6-168">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="be6a6-169">El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-169">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="be6a6-170">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="be6a6-170">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="be6a6-171">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-171">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="be6a6-172">Configuración de una serie de pruebas</span><span class="sxs-lookup"><span data-stu-id="be6a6-172">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="be6a6-173">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="be6a6-173">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="be6a6-174">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="be6a6-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="be6a6-175">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="be6a6-176">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-176">The default is `minimal`.</span></span> <span data-ttu-id="be6a6-177">Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="be6a6-177">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="be6a6-178">Argumentos de **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="be6a6-178">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="be6a6-179">Los argumentos `RunSettings` insertados se pasan como los últimos argumentos en la línea de comandos después de "-- " (fíjese en el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="be6a6-179">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="be6a6-180">Los argumentos `RunSettings` insertados se especifican como pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-180">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="be6a6-181">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-181">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="be6a6-182">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="be6a6-182">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="be6a6-183">Para obtener más información, vea [Paso de argumentos de RunSettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="be6a6-183">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="be6a6-184">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="be6a6-184">Examples</span></span>

- <span data-ttu-id="be6a6-185">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="be6a6-185">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="be6a6-186">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="be6a6-186">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="be6a6-187">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="be6a6-187">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="be6a6-188">Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:</span><span class="sxs-lookup"><span data-stu-id="be6a6-188">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="be6a6-189">Ejecute las pruebas del proyecto en el directorio actual e informe de las pruebas que estaban en curso cuando se bloqueó el host de prueba:</span><span class="sxs-lookup"><span data-stu-id="be6a6-189">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="be6a6-190">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="be6a6-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="be6a6-191">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="be6a6-192">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="be6a6-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="be6a6-193">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="be6a6-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="be6a6-194">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="be6a6-194">Test Framework</span></span> | <span data-ttu-id="be6a6-195">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="be6a6-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="be6a6-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="be6a6-196">MSTest</span></span>         | <ul><li><span data-ttu-id="be6a6-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="be6a6-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="be6a6-198">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="be6a6-198">Name</span></span></li><li><span data-ttu-id="be6a6-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="be6a6-199">ClassName</span></span></li><li><span data-ttu-id="be6a6-200">Prioridad</span><span class="sxs-lookup"><span data-stu-id="be6a6-200">Priority</span></span></li><li><span data-ttu-id="be6a6-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="be6a6-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="be6a6-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="be6a6-202">xUnit</span></span>          | <ul><li><span data-ttu-id="be6a6-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="be6a6-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="be6a6-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="be6a6-204">DisplayName</span></span></li><li><span data-ttu-id="be6a6-205">Rasgos</span><span class="sxs-lookup"><span data-stu-id="be6a6-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="be6a6-206">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="be6a6-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="be6a6-207">Operador</span><span class="sxs-lookup"><span data-stu-id="be6a6-207">Operator</span></span> | <span data-ttu-id="be6a6-208">Función</span><span class="sxs-lookup"><span data-stu-id="be6a6-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="be6a6-209">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="be6a6-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="be6a6-210">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="be6a6-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="be6a6-211">Contiene</span><span class="sxs-lookup"><span data-stu-id="be6a6-211">Contains</span></span>        |
| `!~`     | <span data-ttu-id="be6a6-212">No contiene</span><span class="sxs-lookup"><span data-stu-id="be6a6-212">Not contains</span></span>    |

<span data-ttu-id="be6a6-213">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="be6a6-213">`<value>` is a string.</span></span> <span data-ttu-id="be6a6-214">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="be6a6-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="be6a6-215">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="be6a6-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="be6a6-216">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="be6a6-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="be6a6-217">Operador</span><span class="sxs-lookup"><span data-stu-id="be6a6-217">Operator</span></span>            | <span data-ttu-id="be6a6-218">Función</span><span class="sxs-lookup"><span data-stu-id="be6a6-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="be6a6-219">O</span><span class="sxs-lookup"><span data-stu-id="be6a6-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="be6a6-220">AND</span><span class="sxs-lookup"><span data-stu-id="be6a6-220">AND</span></span>      |

<span data-ttu-id="be6a6-221">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="be6a6-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="be6a6-222">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="be6a6-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be6a6-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="be6a6-223">See also</span></span>

- [<span data-ttu-id="be6a6-224">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="be6a6-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="be6a6-225">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="be6a6-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="be6a6-226">Paso de argumentos runsettings a través de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="be6a6-226">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
