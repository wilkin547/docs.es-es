---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 02/27/2020
ms.openlocfilehash: 359e4522b26e2b59092d55eea3fca575d2afaf1f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121037"
---
# <a name="dotnet-test"></a><span data-ttu-id="234e1-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="234e1-103">dotnet test</span></span>

<span data-ttu-id="234e1-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="234e1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="234e1-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="234e1-105">Name</span></span>

<span data-ttu-id="234e1-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="234e1-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="234e1-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="234e1-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path] [--blame] [-c|--configuration]
    [--collect] [-d|--diag] [-f|--framework] [--filter]
    [--interactive] [-l|--logger] [--no-build] [--nologo]
    [--no-restore] [-o|--output] [-r|--results-directory]
    [--runtime] [-s|--settings] [-t|--list-tests]
    [-v|--verbosity] [[--] <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="234e1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="234e1-108">Description</span></span>

<span data-ttu-id="234e1-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="234e1-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="234e1-110">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="234e1-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="234e1-111">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="234e1-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="234e1-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="234e1-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="234e1-113">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="234e1-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="234e1-114">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="234e1-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="234e1-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="234e1-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="234e1-116">Ruta de acceso a la solución o proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="234e1-116">Path to the test project or solution.</span></span> <span data-ttu-id="234e1-117">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="234e1-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="234e1-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="234e1-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="234e1-119">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="234e1-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="234e1-120">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="234e1-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="234e1-121">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="234e1-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="234e1-122">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="234e1-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="234e1-123">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="234e1-123">Defines the build configuration.</span></span> <span data-ttu-id="234e1-124">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="234e1-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="234e1-125">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="234e1-125">Enables data collector for the test run.</span></span> <span data-ttu-id="234e1-126">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="234e1-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="234e1-127">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="234e1-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="234e1-128">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="234e1-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="234e1-129">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="234e1-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="234e1-130">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="234e1-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="234e1-131">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="234e1-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="234e1-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="234e1-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="234e1-133">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="234e1-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="234e1-134">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="234e1-134">For example, to complete authentication.</span></span> <span data-ttu-id="234e1-135">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="234e1-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="234e1-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="234e1-136">Specifies a logger for test results.</span></span> <span data-ttu-id="234e1-137">A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="234e1-137">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="234e1-138">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="234e1-138">Doesn't build the test project before running it.</span></span> <span data-ttu-id="234e1-139">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="234e1-139">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="234e1-140">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="234e1-140">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="234e1-141">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="234e1-141">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="234e1-142">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="234e1-142">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="234e1-143">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="234e1-143">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="234e1-144">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="234e1-144">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="234e1-145">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="234e1-145">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="234e1-146">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="234e1-146">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="234e1-147">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="234e1-147">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="234e1-148">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="234e1-148">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="234e1-149">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="234e1-149">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="234e1-150">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="234e1-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="234e1-151">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="234e1-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="234e1-152">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="234e1-152">The default is `minimal`.</span></span> <span data-ttu-id="234e1-153">Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="234e1-153">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="234e1-154">Argumentos de `RunSettings`</span><span class="sxs-lookup"><span data-stu-id="234e1-154">`RunSettings` arguments</span></span>

  <span data-ttu-id="234e1-155">Los argumentos se pasan como configuraciones de `RunSettings` para la prueba.</span><span class="sxs-lookup"><span data-stu-id="234e1-155">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="234e1-156">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="234e1-156">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="234e1-157">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="234e1-157">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="234e1-158">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="234e1-158">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="234e1-159">Para obtener más información, vea [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: paso de argumentos RunSettings).</span><span class="sxs-lookup"><span data-stu-id="234e1-159">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="234e1-160">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="234e1-160">Examples</span></span>

- <span data-ttu-id="234e1-161">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="234e1-161">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="234e1-162">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="234e1-162">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="234e1-163">Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="234e1-163">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="234e1-164">Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:</span><span class="sxs-lookup"><span data-stu-id="234e1-164">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="234e1-165">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="234e1-165">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="234e1-166">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="234e1-166">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="234e1-167">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="234e1-167">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="234e1-168">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="234e1-168">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="234e1-169">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="234e1-169">Test Framework</span></span> | <span data-ttu-id="234e1-170">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="234e1-170">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="234e1-171">MSTest</span><span class="sxs-lookup"><span data-stu-id="234e1-171">MSTest</span></span>         | <ul><li><span data-ttu-id="234e1-172">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="234e1-172">FullyQualifiedName</span></span></li><li><span data-ttu-id="234e1-173">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="234e1-173">Name</span></span></li><li><span data-ttu-id="234e1-174">ClassName</span><span class="sxs-lookup"><span data-stu-id="234e1-174">ClassName</span></span></li><li><span data-ttu-id="234e1-175">Prioridad</span><span class="sxs-lookup"><span data-stu-id="234e1-175">Priority</span></span></li><li><span data-ttu-id="234e1-176">TestCategory</span><span class="sxs-lookup"><span data-stu-id="234e1-176">TestCategory</span></span></li></ul> |
| <span data-ttu-id="234e1-177">xUnit</span><span class="sxs-lookup"><span data-stu-id="234e1-177">xUnit</span></span>          | <ul><li><span data-ttu-id="234e1-178">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="234e1-178">FullyQualifiedName</span></span></li><li><span data-ttu-id="234e1-179">DisplayName</span><span class="sxs-lookup"><span data-stu-id="234e1-179">DisplayName</span></span></li><li><span data-ttu-id="234e1-180">Rasgos</span><span class="sxs-lookup"><span data-stu-id="234e1-180">Traits</span></span></li></ul>                                   |

<span data-ttu-id="234e1-181">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="234e1-181">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="234e1-182">Operador</span><span class="sxs-lookup"><span data-stu-id="234e1-182">Operator</span></span> | <span data-ttu-id="234e1-183">Función</span><span class="sxs-lookup"><span data-stu-id="234e1-183">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="234e1-184">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="234e1-184">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="234e1-185">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="234e1-185">Not exact match</span></span> |
| `~`      | <span data-ttu-id="234e1-186">Contiene</span><span class="sxs-lookup"><span data-stu-id="234e1-186">Contains</span></span>        |
| `!~`     | <span data-ttu-id="234e1-187">No contiene</span><span class="sxs-lookup"><span data-stu-id="234e1-187">Not contains</span></span>    |

<span data-ttu-id="234e1-188">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="234e1-188">`<value>` is a string.</span></span> <span data-ttu-id="234e1-189">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="234e1-189">All the lookups are case insensitive.</span></span>

<span data-ttu-id="234e1-190">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="234e1-190">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="234e1-191">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="234e1-191">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="234e1-192">Operador</span><span class="sxs-lookup"><span data-stu-id="234e1-192">Operator</span></span>            | <span data-ttu-id="234e1-193">Función</span><span class="sxs-lookup"><span data-stu-id="234e1-193">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="234e1-194">O</span><span class="sxs-lookup"><span data-stu-id="234e1-194">OR</span></span>       |
| `&`                 | <span data-ttu-id="234e1-195">AND</span><span class="sxs-lookup"><span data-stu-id="234e1-195">AND</span></span>      |

<span data-ttu-id="234e1-196">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="234e1-196">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="234e1-197">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="234e1-197">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="234e1-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="234e1-198">See also</span></span>

- [<span data-ttu-id="234e1-199">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="234e1-199">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="234e1-200">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="234e1-200">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="234e1-201">Paso de argumentos runsettings a través de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="234e1-201">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
