---
title: 'Comando dotnet test: CLI de .NET Core'
description: "El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 55329bed71be21a787d6e77d8c0ea67d607676b8
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-test"></a><span data-ttu-id="b3d75-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b3d75-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b3d75-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="b3d75-104">Name</span></span>

<span data-ttu-id="b3d75-105">`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3d75-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b3d75-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b3d75-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b3d75-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b3d75-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b3d75-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b3d75-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="b3d75-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3d75-109">Description</span></span>

<span data-ttu-id="b3d75-110">El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="b3d75-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="b3d75-111">Las pruebas unitarias son proyectos de aplicación de consola que tienen dependencias en el marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y en el ejecutor de pruebas de dotnet de ese marco de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3d75-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="b3d75-112">Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b3d75-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="b3d75-113">Los proyectos de prueba también deben especificar el ejecutor de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="b3d75-114">Para ello se utiliza un elemento `<PackageReference>` ordinario, como se puede ver en el siguiente archivo de proyecto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3d75-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="b3d75-115">[!code-xml[Plantilla de XUnit Basic](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="b3d75-115">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="arguments"></a><span data-ttu-id="b3d75-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b3d75-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b3d75-117">Especifica una ruta de acceso al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="b3d75-117">Specifies a path to the test project.</span></span> <span data-ttu-id="b3d75-118">Si se omite, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b3d75-118">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b3d75-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="b3d75-119">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b3d75-120">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b3d75-120">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b3d75-121">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-121">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b3d75-122">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="b3d75-122">Defines the build configuration.</span></span> <span data-ttu-id="b3d75-123">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="b3d75-123">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="b3d75-124">Habilita el recopilador de datos para la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-124">Enables data collector for the test run.</span></span> <span data-ttu-id="b3d75-125">Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).</span><span class="sxs-lookup"><span data-stu-id="b3d75-125">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b3d75-126">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b3d75-126">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b3d75-127">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="b3d75-127">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b3d75-128">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="b3d75-128">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b3d75-129">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b3d75-129">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b3d75-130">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="b3d75-130">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b3d75-131">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b3d75-131">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b3d75-132">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-132">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b3d75-133">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="b3d75-133">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="b3d75-134">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="b3d75-134">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b3d75-135">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="b3d75-135">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="b3d75-136">El directorio donde se guardarán los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-136">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="b3d75-137">Si no existe, se creará el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="b3d75-137">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b3d75-138">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-138">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b3d75-139">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="b3d75-139">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b3d75-140">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="b3d75-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b3d75-141">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b3d75-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b3d75-142">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b3d75-142">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b3d75-143">Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-143">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b3d75-144">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="b3d75-144">Defines the build configuration.</span></span> <span data-ttu-id="b3d75-145">El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.</span><span class="sxs-lookup"><span data-stu-id="b3d75-145">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b3d75-146">Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b3d75-146">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b3d75-147">Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="b3d75-147">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b3d75-148">Filtra las pruebas del proyecto actual con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="b3d75-148">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b3d75-149">Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b3d75-149">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b3d75-150">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="b3d75-150">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b3d75-151">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b3d75-151">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b3d75-152">Especifica un registrador para los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-152">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b3d75-153">No compila el proyecto de prueba antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="b3d75-153">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b3d75-154">Directorio donde se encuentran los archivos binarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="b3d75-154">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b3d75-155">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-155">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b3d75-156">Enumera todas las pruebas detectadas en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="b3d75-156">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b3d75-157">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="b3d75-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b3d75-158">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b3d75-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b3d75-159">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b3d75-159">Examples</span></span>

<span data-ttu-id="b3d75-160">Ejecución de las pruebas en el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="b3d75-160">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="b3d75-161">Ejecute las pruebas en el proyecto `test1`:</span><span class="sxs-lookup"><span data-stu-id="b3d75-161">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="b3d75-162">Detalles de la opción de filtro</span><span class="sxs-lookup"><span data-stu-id="b3d75-162">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b3d75-163">`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="b3d75-163">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="b3d75-164">`<property>` es un atributo del tipo `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="b3d75-164">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="b3d75-165">Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:</span><span class="sxs-lookup"><span data-stu-id="b3d75-165">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="b3d75-166">Marco de prueba</span><span class="sxs-lookup"><span data-stu-id="b3d75-166">Test Framework</span></span> | <span data-ttu-id="b3d75-167">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="b3d75-167">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b3d75-168">MSTest</span><span class="sxs-lookup"><span data-stu-id="b3d75-168">MSTest</span></span>         | <ul><li><span data-ttu-id="b3d75-169">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b3d75-169">FullyQualifiedName</span></span></li><li><span data-ttu-id="b3d75-170">Name</span><span class="sxs-lookup"><span data-stu-id="b3d75-170">Name</span></span></li><li><span data-ttu-id="b3d75-171">ClassName</span><span class="sxs-lookup"><span data-stu-id="b3d75-171">ClassName</span></span></li><li><span data-ttu-id="b3d75-172">Prioridad</span><span class="sxs-lookup"><span data-stu-id="b3d75-172">Priority</span></span></li><li><span data-ttu-id="b3d75-173">TestCategory</span><span class="sxs-lookup"><span data-stu-id="b3d75-173">TestCategory</span></span></li></ul> |
| <span data-ttu-id="b3d75-174">Xunit</span><span class="sxs-lookup"><span data-stu-id="b3d75-174">Xunit</span></span>          | <ul><li><span data-ttu-id="b3d75-175">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b3d75-175">FullyQualifiedName</span></span></li><li><span data-ttu-id="b3d75-176">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b3d75-176">DisplayName</span></span></li><li><span data-ttu-id="b3d75-177">Rasgos</span><span class="sxs-lookup"><span data-stu-id="b3d75-177">Traits</span></span></li></ul>                                   |

<span data-ttu-id="b3d75-178">`<operator>` describe la relación entre la propiedad y el valor:</span><span class="sxs-lookup"><span data-stu-id="b3d75-178">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="b3d75-179">Operador</span><span class="sxs-lookup"><span data-stu-id="b3d75-179">Operator</span></span> | <span data-ttu-id="b3d75-180">Función</span><span class="sxs-lookup"><span data-stu-id="b3d75-180">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="b3d75-181">Coincidencia exacta</span><span class="sxs-lookup"><span data-stu-id="b3d75-181">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="b3d75-182">Coincidencia no exacta</span><span class="sxs-lookup"><span data-stu-id="b3d75-182">Not exact match</span></span> |
| `~`      | <span data-ttu-id="b3d75-183">Contiene</span><span class="sxs-lookup"><span data-stu-id="b3d75-183">Contains</span></span>        |

<span data-ttu-id="b3d75-184">`<value>` es una cadena.</span><span class="sxs-lookup"><span data-stu-id="b3d75-184">`<value>` is a string.</span></span> <span data-ttu-id="b3d75-185">Todas las búsquedas distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b3d75-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="b3d75-186">Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="b3d75-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="b3d75-187">Las expresiones se pueden combinar con operadores condicionales:</span><span class="sxs-lookup"><span data-stu-id="b3d75-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="b3d75-188">Operador</span><span class="sxs-lookup"><span data-stu-id="b3d75-188">Operator</span></span> | <span data-ttu-id="b3d75-189">Función</span><span class="sxs-lookup"><span data-stu-id="b3d75-189">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="b3d75-190">O</span><span class="sxs-lookup"><span data-stu-id="b3d75-190">OR</span></span>       |
| `&`      | <span data-ttu-id="b3d75-191">AND</span><span class="sxs-lookup"><span data-stu-id="b3d75-191">AND</span></span>      |

<span data-ttu-id="b3d75-192">Cuando se utilizan operadores condicionales puede encerrar expresiones entre paréntesis (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="b3d75-192">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="b3d75-193">Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).</span><span class="sxs-lookup"><span data-stu-id="b3d75-193">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3d75-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3d75-194">See also</span></span>

 <span data-ttu-id="b3d75-195">[Marcos y destinos](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="b3d75-195">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
 [<span data-ttu-id="b3d75-196">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b3d75-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

