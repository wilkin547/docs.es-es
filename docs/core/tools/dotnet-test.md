---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624896"
---
# <a name="dotnet-test"></a><span data-ttu-id="f12fd-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f12fd-103">dotnet test</span></span>

<span data-ttu-id="f12fd-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f12fd-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f12fd-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f12fd-105">Name</span></span>

<span data-ttu-id="f12fd-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="f12fd-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f12fd-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f12fd-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
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

## <a name="description"></a><span data-ttu-id="f12fd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f12fd-108">Description</span></span>

<span data-ttu-id="f12fd-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="f12fd-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="f12fd-110">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f12fd-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="f12fd-111">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="f12fd-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="f12fd-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="f12fd-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="f12fd-113">En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="f12fd-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="f12fd-114">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f12fd-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="f12fd-115">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f12fd-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="f12fd-116">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="f12fd-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="f12fd-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f12fd-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="f12fd-118">Ruta de acceso a la solución o proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="f12fd-118">Path to the test project or solution.</span></span> <span data-ttu-id="f12fd-119">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f12fd-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="f12fd-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="f12fd-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="f12fd-121">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="f12fd-122">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="f12fd-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="f12fd-123">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="f12fd-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="f12fd-124">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f12fd-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="f12fd-125">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f12fd-125">Defines the build configuration.</span></span> <span data-ttu-id="f12fd-126">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="f12fd-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="f12fd-127">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-127">Enables data collector for the test run.</span></span> <span data-ttu-id="f12fd-128">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="f12fd-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="f12fd-129">Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f12fd-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f12fd-130">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="f12fd-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="f12fd-131">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="f12fd-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f12fd-132">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="f12fd-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f12fd-133">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f12fd-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="f12fd-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f12fd-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="f12fd-135">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f12fd-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="f12fd-136">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f12fd-136">For example, to complete authentication.</span></span> <span data-ttu-id="f12fd-137">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f12fd-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="f12fd-138">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-138">Specifies a logger for test results.</span></span> <span data-ttu-id="f12fd-139">A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="f12fd-140">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="f12fd-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="f12fd-141">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="f12fd-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="f12fd-142">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="f12fd-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="f12fd-143">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f12fd-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="f12fd-144">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f12fd-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f12fd-145">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="f12fd-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="f12fd-146">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="f12fd-147">En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="f12fd-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="f12fd-148">`dotnet test` siempre ejecuta las pruebas desde el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="f12fd-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="f12fd-149">Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="f12fd-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="f12fd-150">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="f12fd-151">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="f12fd-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="f12fd-152">El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f12fd-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f12fd-153">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="f12fd-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="f12fd-154">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="f12fd-155">Tenga en cuenta que el elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="f12fd-156">Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f12fd-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="f12fd-157">El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="f12fd-158">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="f12fd-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="f12fd-159">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="f12fd-160">Configuración de una serie de pruebas</span><span class="sxs-lookup"><span data-stu-id="f12fd-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="f12fd-161">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f12fd-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f12fd-162">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="f12fd-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f12fd-163">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f12fd-164">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-164">The default is `minimal`.</span></span> <span data-ttu-id="f12fd-165">Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="f12fd-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="f12fd-166">Argumentos de **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="f12fd-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="f12fd-167">Los argumentos se pasan como configuraciones de `RunSettings` para la prueba.</span><span class="sxs-lookup"><span data-stu-id="f12fd-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="f12fd-168">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="f12fd-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="f12fd-169">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="f12fd-170">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="f12fd-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="f12fd-171">Para obtener más información, vea [Paso de argumentos de RunSettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="f12fd-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="f12fd-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f12fd-172">Examples</span></span>

- <span data-ttu-id="f12fd-173">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="f12fd-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="f12fd-174">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="f12fd-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="f12fd-175">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="f12fd-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="f12fd-176">Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:</span><span class="sxs-lookup"><span data-stu-id="f12fd-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="f12fd-177">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="f12fd-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f12fd-178">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="f12fd-179">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="f12fd-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="f12fd-180">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="f12fd-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="f12fd-181">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="f12fd-181">Test Framework</span></span> | <span data-ttu-id="f12fd-182">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="f12fd-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f12fd-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="f12fd-183">MSTest</span></span>         | <ul><li><span data-ttu-id="f12fd-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f12fd-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="f12fd-185">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f12fd-185">Name</span></span></li><li><span data-ttu-id="f12fd-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="f12fd-186">ClassName</span></span></li><li><span data-ttu-id="f12fd-187">Prioridad</span><span class="sxs-lookup"><span data-stu-id="f12fd-187">Priority</span></span></li><li><span data-ttu-id="f12fd-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="f12fd-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="f12fd-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="f12fd-189">xUnit</span></span>          | <ul><li><span data-ttu-id="f12fd-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f12fd-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="f12fd-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f12fd-191">DisplayName</span></span></li><li><span data-ttu-id="f12fd-192">Rasgos</span><span class="sxs-lookup"><span data-stu-id="f12fd-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="f12fd-193">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="f12fd-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="f12fd-194">Operador</span><span class="sxs-lookup"><span data-stu-id="f12fd-194">Operator</span></span> | <span data-ttu-id="f12fd-195">Función</span><span class="sxs-lookup"><span data-stu-id="f12fd-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="f12fd-196">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="f12fd-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="f12fd-197">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="f12fd-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="f12fd-198">Contiene</span><span class="sxs-lookup"><span data-stu-id="f12fd-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="f12fd-199">No contiene</span><span class="sxs-lookup"><span data-stu-id="f12fd-199">Not contains</span></span>    |

<span data-ttu-id="f12fd-200">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="f12fd-200">`<value>` is a string.</span></span> <span data-ttu-id="f12fd-201">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f12fd-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="f12fd-202">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="f12fd-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="f12fd-203">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="f12fd-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="f12fd-204">Operador</span><span class="sxs-lookup"><span data-stu-id="f12fd-204">Operator</span></span>            | <span data-ttu-id="f12fd-205">Función</span><span class="sxs-lookup"><span data-stu-id="f12fd-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="f12fd-206">O</span><span class="sxs-lookup"><span data-stu-id="f12fd-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="f12fd-207">AND</span><span class="sxs-lookup"><span data-stu-id="f12fd-207">AND</span></span>      |

<span data-ttu-id="f12fd-208">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f12fd-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="f12fd-209">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="f12fd-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f12fd-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="f12fd-210">See also</span></span>

- [<span data-ttu-id="f12fd-211">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="f12fd-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="f12fd-212">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f12fd-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="f12fd-213">Paso de argumentos runsettings a través de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f12fd-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
