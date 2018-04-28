---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 04af96bb53cc4fdac2e52311f9197eb1ee2b112d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="2d767-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2d767-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2d767-104">nombre</span><span class="sxs-lookup"><span data-stu-id="2d767-104">Name</span></span>

<span data-ttu-id="2d767-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="2d767-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2d767-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="2d767-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2d767-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2d767-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2d767-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2d767-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="2d767-109">Description</span><span class="sxs-lookup"><span data-stu-id="2d767-109">Description</span></span>

<span data-ttu-id="2d767-110">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="2d767-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="2d767-111">El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="2d767-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="2d767-112">El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="2d767-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="2d767-113">El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2d767-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="2d767-114">Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d767-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="2d767-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2d767-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2d767-116">Especifica una ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="2d767-116">Specifies a path to the test project.</span></span> <span data-ttu-id="2d767-117">Si se omite, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2d767-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="2d767-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="2d767-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2d767-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2d767-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="2d767-120">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2d767-121">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="2d767-121">Defines the build configuration.</span></span> <span data-ttu-id="2d767-122">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="2d767-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="2d767-123">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-123">Enables data collector for the test run.</span></span> <span data-ttu-id="2d767-124">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="2d767-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="2d767-125">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="2d767-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2d767-126">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="2d767-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="2d767-127">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="2d767-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="2d767-128">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="2d767-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="2d767-129">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="2d767-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="2d767-130">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2d767-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="2d767-131">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="2d767-132">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="2d767-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="2d767-133">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="2d767-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2d767-134">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="2d767-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="2d767-135">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="2d767-136">Si no existe, se creará el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="2d767-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="2d767-137">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="2d767-138">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="2d767-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2d767-139">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="2d767-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2d767-140">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2d767-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2d767-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2d767-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="2d767-142">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2d767-143">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="2d767-143">Defines the build configuration.</span></span> <span data-ttu-id="2d767-144">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="2d767-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="2d767-145">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="2d767-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2d767-146">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="2d767-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="2d767-147">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="2d767-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="2d767-148">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="2d767-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="2d767-149">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="2d767-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="2d767-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2d767-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="2d767-151">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="2d767-152">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="2d767-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2d767-153">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="2d767-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="2d767-154">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2d767-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="2d767-155">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="2d767-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2d767-156">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="2d767-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2d767-157">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2d767-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="2d767-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2d767-158">Examples</span></span>

<span data-ttu-id="2d767-159">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="2d767-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="2d767-160">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="2d767-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="2d767-161">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="2d767-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="2d767-162">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="2d767-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="2d767-163">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="2d767-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="2d767-164">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="2d767-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="2d767-165">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="2d767-165">Test Framework</span></span> | <span data-ttu-id="2d767-166">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="2d767-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2d767-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="2d767-167">MSTest</span></span>         | <ul><li><span data-ttu-id="2d767-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="2d767-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="2d767-169">nombre</span><span class="sxs-lookup"><span data-stu-id="2d767-169">Name</span></span></li><li><span data-ttu-id="2d767-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="2d767-170">ClassName</span></span></li><li><span data-ttu-id="2d767-171">Prioridad</span><span class="sxs-lookup"><span data-stu-id="2d767-171">Priority</span></span></li><li><span data-ttu-id="2d767-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="2d767-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="2d767-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="2d767-173">Xunit</span></span>          | <ul><li><span data-ttu-id="2d767-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="2d767-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="2d767-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2d767-175">DisplayName</span></span></li><li><span data-ttu-id="2d767-176">Rasgos</span><span class="sxs-lookup"><span data-stu-id="2d767-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="2d767-177">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="2d767-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="2d767-178">Operador</span><span class="sxs-lookup"><span data-stu-id="2d767-178">Operator</span></span> | <span data-ttu-id="2d767-179">Función</span><span class="sxs-lookup"><span data-stu-id="2d767-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="2d767-180">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="2d767-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="2d767-181">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="2d767-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="2d767-182">Contiene</span><span class="sxs-lookup"><span data-stu-id="2d767-182">Contains</span></span>        |

<span data-ttu-id="2d767-183">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="2d767-183">`<value>` is a string.</span></span> <span data-ttu-id="2d767-184">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2d767-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="2d767-185">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="2d767-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="2d767-186">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="2d767-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="2d767-187">Operador</span><span class="sxs-lookup"><span data-stu-id="2d767-187">Operator</span></span> | <span data-ttu-id="2d767-188">Función</span><span class="sxs-lookup"><span data-stu-id="2d767-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="2d767-189">O</span><span class="sxs-lookup"><span data-stu-id="2d767-189">OR</span></span>       |
| `&`      | <span data-ttu-id="2d767-190">AND</span><span class="sxs-lookup"><span data-stu-id="2d767-190">AND</span></span>      |

<span data-ttu-id="2d767-191">Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2d767-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="2d767-192">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="2d767-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2d767-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d767-193">See also</span></span>

 [<span data-ttu-id="2d767-194">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="2d767-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="2d767-195">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2d767-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
