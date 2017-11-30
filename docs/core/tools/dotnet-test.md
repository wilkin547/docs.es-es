---
title: 'Comando dotnet test: CLI de .NET Core'
description: "El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 9eb5be38549711717c11767332bfc84920ea927a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dotnet-test"></a><span data-ttu-id="d6f72-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="d6f72-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d6f72-104">Name</span><span class="sxs-lookup"><span data-stu-id="d6f72-104">Name</span></span>

<span data-ttu-id="d6f72-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="d6f72-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d6f72-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d6f72-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d6f72-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d6f72-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d6f72-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d6f72-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d6f72-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6f72-109">Description</span></span>

<span data-ttu-id="d6f72-110">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="d6f72-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="d6f72-111">Las pruebas unitarias son proyectos de aplicación de consola que tienen dependencias en el marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y en el ejecutor de pruebas de dotnet de ese marco de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="d6f72-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="d6f72-112">Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6f72-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="d6f72-113">Los proyectos de prueba también deben especificar el ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="d6f72-114">Para ello se utiliza un elemento `<PackageReference>` ordinario, como se puede ver en el siguiente archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d6f72-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="d6f72-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6f72-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d6f72-116">Especifica una ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="d6f72-116">Specifies a path to the test project.</span></span> <span data-ttu-id="d6f72-117">Si se omite, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="d6f72-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d6f72-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="d6f72-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d6f72-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d6f72-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d6f72-120">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d6f72-121">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="d6f72-121">Defines the build configuration.</span></span> <span data-ttu-id="d6f72-122">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="d6f72-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="d6f72-123">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-123">Enables data collector for the test run.</span></span> <span data-ttu-id="d6f72-124">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="d6f72-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d6f72-125">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d6f72-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d6f72-126">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="d6f72-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d6f72-127">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="d6f72-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d6f72-128">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d6f72-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d6f72-129">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="d6f72-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d6f72-130">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d6f72-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d6f72-131">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d6f72-132">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="d6f72-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="d6f72-133">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="d6f72-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d6f72-134">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="d6f72-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="d6f72-135">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="d6f72-136">Si no existe, se creará el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="d6f72-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d6f72-137">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d6f72-138">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="d6f72-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d6f72-139">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d6f72-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d6f72-140">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d6f72-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d6f72-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d6f72-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d6f72-142">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d6f72-143">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="d6f72-143">Defines the build configuration.</span></span> <span data-ttu-id="d6f72-144">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="d6f72-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d6f72-145">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d6f72-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d6f72-146">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="d6f72-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d6f72-147">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="d6f72-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d6f72-148">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d6f72-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d6f72-149">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="d6f72-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d6f72-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d6f72-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d6f72-151">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d6f72-152">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="d6f72-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d6f72-153">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="d6f72-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d6f72-154">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d6f72-155">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="d6f72-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d6f72-156">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d6f72-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d6f72-157">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d6f72-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d6f72-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d6f72-158">Examples</span></span>

<span data-ttu-id="d6f72-159">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="d6f72-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="d6f72-160">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="d6f72-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="d6f72-161">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="d6f72-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d6f72-162">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="d6f72-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="d6f72-163">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="d6f72-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="d6f72-164">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="d6f72-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="d6f72-165">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="d6f72-165">Test Framework</span></span> | <span data-ttu-id="d6f72-166">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="d6f72-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d6f72-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="d6f72-167">MSTest</span></span>         | <ul><li><span data-ttu-id="d6f72-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d6f72-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="d6f72-169">Name</span><span class="sxs-lookup"><span data-stu-id="d6f72-169">Name</span></span></li><li><span data-ttu-id="d6f72-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="d6f72-170">ClassName</span></span></li><li><span data-ttu-id="d6f72-171">Prioridad</span><span class="sxs-lookup"><span data-stu-id="d6f72-171">Priority</span></span></li><li><span data-ttu-id="d6f72-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="d6f72-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="d6f72-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="d6f72-173">Xunit</span></span>          | <ul><li><span data-ttu-id="d6f72-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d6f72-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="d6f72-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d6f72-175">DisplayName</span></span></li><li><span data-ttu-id="d6f72-176">Rasgos</span><span class="sxs-lookup"><span data-stu-id="d6f72-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="d6f72-177">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="d6f72-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="d6f72-178">Operador</span><span class="sxs-lookup"><span data-stu-id="d6f72-178">Operator</span></span> | <span data-ttu-id="d6f72-179">Función</span><span class="sxs-lookup"><span data-stu-id="d6f72-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="d6f72-180">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="d6f72-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="d6f72-181">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="d6f72-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="d6f72-182">Contiene</span><span class="sxs-lookup"><span data-stu-id="d6f72-182">Contains</span></span>        |

<span data-ttu-id="d6f72-183">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="d6f72-183">`<value>` is a string.</span></span> <span data-ttu-id="d6f72-184">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d6f72-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="d6f72-185">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="d6f72-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="d6f72-186">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="d6f72-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="d6f72-187">Operador</span><span class="sxs-lookup"><span data-stu-id="d6f72-187">Operator</span></span> | <span data-ttu-id="d6f72-188">Función</span><span class="sxs-lookup"><span data-stu-id="d6f72-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="d6f72-189">O</span><span class="sxs-lookup"><span data-stu-id="d6f72-189">OR</span></span>       |
| `&`      | <span data-ttu-id="d6f72-190">AND</span><span class="sxs-lookup"><span data-stu-id="d6f72-190">AND</span></span>      |

<span data-ttu-id="d6f72-191">Puede incluir expresiones entre paréntesis cuando se utilizan operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="d6f72-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="d6f72-192">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="d6f72-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6f72-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f72-193">See also</span></span>

 [<span data-ttu-id="d6f72-194">Marcos y destinos</span><span class="sxs-lookup"><span data-stu-id="d6f72-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="d6f72-195">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d6f72-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
