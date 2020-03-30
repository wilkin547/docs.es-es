---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 02/27/2020
ms.openlocfilehash: a11814f9fdc6326e681a09d7d2654b968014f318
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507313"
---
# <a name="dotnet-test"></a><span data-ttu-id="b1fa2-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b1fa2-103">dotnet test</span></span>

<span data-ttu-id="b1fa2-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b1fa2-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b1fa2-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b1fa2-105">Name</span></span>

<span data-ttu-id="b1fa2-106">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b1fa2-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b1fa2-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="b1fa2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1fa2-108">Description</span></span>

<span data-ttu-id="b1fa2-109">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="b1fa2-110">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="b1fa2-111">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="b1fa2-112">Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="b1fa2-113">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="b1fa2-114">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="b1fa2-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b1fa2-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="b1fa2-116">Ruta de acceso a la solución o proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-116">Path to the test project or solution.</span></span> <span data-ttu-id="b1fa2-117">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b1fa2-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="b1fa2-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="b1fa2-119">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="b1fa2-120">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="b1fa2-121">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="b1fa2-122">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="b1fa2-123">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-123">Defines the build configuration.</span></span> <span data-ttu-id="b1fa2-124">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="b1fa2-125">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-125">Enables data collector for the test run.</span></span> <span data-ttu-id="b1fa2-126">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="b1fa2-127">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b1fa2-128">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="b1fa2-129">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b1fa2-130">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b1fa2-131">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="b1fa2-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="b1fa2-133">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="b1fa2-134">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-134">For example, to complete authentication.</span></span> <span data-ttu-id="b1fa2-135">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="b1fa2-136">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-136">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="b1fa2-137">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="b1fa2-138">También establece la marca - `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-138">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="b1fa2-139">Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-139">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="b1fa2-140">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b1fa2-141">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-141">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="b1fa2-142">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-142">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="b1fa2-143">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-143">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="b1fa2-144">Si el directorio especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-144">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="b1fa2-145">Runtime de destino que probar.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-145">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="b1fa2-146">El archivo `.runsettings` que se usará para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-146">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="b1fa2-147">Configuración de pruebas unitarias con un archivo `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-147">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="b1fa2-148">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-148">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b1fa2-149">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b1fa2-150">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="b1fa2-151">Argumentos de `RunSettings`</span><span class="sxs-lookup"><span data-stu-id="b1fa2-151">`RunSettings` arguments</span></span>

  <span data-ttu-id="b1fa2-152">Los argumentos se pasan como configuraciones de `RunSettings` para la prueba.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-152">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="b1fa2-153">Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-153">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="b1fa2-154">Se usa un espacio para separar varios pares de `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-154">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="b1fa2-155">Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="b1fa2-155">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="b1fa2-156">Para obtener más información, vea [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: paso de argumentos RunSettings).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-156">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="b1fa2-157">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b1fa2-157">Examples</span></span>

- <span data-ttu-id="b1fa2-158">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-158">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="b1fa2-159">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-159">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="b1fa2-160">Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-160">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="b1fa2-161">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="b1fa2-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b1fa2-162">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="b1fa2-163">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="b1fa2-164">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="b1fa2-165">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="b1fa2-165">Test Framework</span></span> | <span data-ttu-id="b1fa2-166">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="b1fa2-166">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b1fa2-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="b1fa2-167">MSTest</span></span>         | <ul><li><span data-ttu-id="b1fa2-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b1fa2-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="b1fa2-169">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b1fa2-169">Name</span></span></li><li><span data-ttu-id="b1fa2-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="b1fa2-170">ClassName</span></span></li><li><span data-ttu-id="b1fa2-171">Prioridad</span><span class="sxs-lookup"><span data-stu-id="b1fa2-171">Priority</span></span></li><li><span data-ttu-id="b1fa2-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="b1fa2-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="b1fa2-173">xUnit</span><span class="sxs-lookup"><span data-stu-id="b1fa2-173">xUnit</span></span>          | <ul><li><span data-ttu-id="b1fa2-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b1fa2-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="b1fa2-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b1fa2-175">DisplayName</span></span></li><li><span data-ttu-id="b1fa2-176">Rasgos</span><span class="sxs-lookup"><span data-stu-id="b1fa2-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="b1fa2-177">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="b1fa2-178">Operador</span><span class="sxs-lookup"><span data-stu-id="b1fa2-178">Operator</span></span> | <span data-ttu-id="b1fa2-179">Función</span><span class="sxs-lookup"><span data-stu-id="b1fa2-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="b1fa2-180">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="b1fa2-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="b1fa2-181">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="b1fa2-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="b1fa2-182">Contiene</span><span class="sxs-lookup"><span data-stu-id="b1fa2-182">Contains</span></span>        |
| `!~`     | <span data-ttu-id="b1fa2-183">No contiene</span><span class="sxs-lookup"><span data-stu-id="b1fa2-183">Not contains</span></span>    |

<span data-ttu-id="b1fa2-184">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-184">`<value>` is a string.</span></span> <span data-ttu-id="b1fa2-185">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="b1fa2-186">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="b1fa2-187">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="b1fa2-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="b1fa2-188">Operador</span><span class="sxs-lookup"><span data-stu-id="b1fa2-188">Operator</span></span>            | <span data-ttu-id="b1fa2-189">Función</span><span class="sxs-lookup"><span data-stu-id="b1fa2-189">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="b1fa2-190">O</span><span class="sxs-lookup"><span data-stu-id="b1fa2-190">OR</span></span>       |
| `&`                 | <span data-ttu-id="b1fa2-191">AND</span><span class="sxs-lookup"><span data-stu-id="b1fa2-191">AND</span></span>      |

<span data-ttu-id="b1fa2-192">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="b1fa2-192">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="b1fa2-193">Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b1fa2-193">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1fa2-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1fa2-194">See also</span></span>

- [<span data-ttu-id="b1fa2-195">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="b1fa2-195">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="b1fa2-196">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b1fa2-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
