---
description: Opciones del compilador de C# para errores y advertencias. Estas opciones suprimen o habilitan las advertencias y controlan las advertencias como errores.
title: 'Opciones del compilador de C#: errores y advertencias'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- WarningLevel compiler option [C#]
- TreatWarningsAsErrors compiler option [C#]
- WarningsAsErrors compiler option [C#]
- WarningsNotAsErrors compiler option [C#]
- DisabledWarnings compiler option [C#]
- CodeAnalysisRuleSet compiler option [C#]
- ErrorLog compiler option [C#]
- ReportAnalyzer compiler option [C#]
ms.openlocfilehash: 2bdda13d6b8b2b75d80c228da678a5b7fbcb8892
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482496"
---
# <a name="c-compiler-options-to-report-errors-and-warnings"></a><span data-ttu-id="4cb41-104">Opciones del compilador de C#: notificación de errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="4cb41-104">C# Compiler Options to report errors and warnings</span></span>

<span data-ttu-id="4cb41-105">Las opciones siguientes controlan cómo el compilador notifica los errores y las advertencias.</span><span class="sxs-lookup"><span data-stu-id="4cb41-105">The following options control how the compiler reports errors and warnings.</span></span> <span data-ttu-id="4cb41-106">La nueva sintaxis de MSBuild se muestra en **negrita**.</span><span class="sxs-lookup"><span data-stu-id="4cb41-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="4cb41-107">La sintaxis de *csc.exe* anterior se muestra en `code style`.</span><span class="sxs-lookup"><span data-stu-id="4cb41-107">The older *csc.exe* syntax is shown in `code style`.</span></span>

- <span data-ttu-id="4cb41-108">**WarningLevel** / `-warn`: se establece el nivel de advertencia.</span><span class="sxs-lookup"><span data-stu-id="4cb41-108">**WarningLevel** / `-warn`: Set warning level.</span></span>
- <span data-ttu-id="4cb41-109">**TreatWarningsAsErrors** / `-warnaserror`: todas las advertencias se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-109">**TreatWarningsAsErrors** / `-warnaserror`: Treat all warnings as errors</span></span>
- <span data-ttu-id="4cb41-110">**WarningsAsErrors** / `-warnaserror`: una o varias advertencias se tratan como errores</span><span class="sxs-lookup"><span data-stu-id="4cb41-110">**WarningsAsErrors** / `-warnaserror`: Treat one or more warnings as errors</span></span>
- <span data-ttu-id="4cb41-111">**WarningsNotAsErrors** / `-warnaserror`: una o varias advertencias no se tratan como errores</span><span class="sxs-lookup"><span data-stu-id="4cb41-111">**WarningsNotAsErrors** / `-warnaserror`: Treat one or more warnings not as errors</span></span>
- <span data-ttu-id="4cb41-112">**DisabledWarnings** / `-nowarn`: se establece una lista de advertencias deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="4cb41-112">**DisabledWarnings** / `-nowarn`: Set a list of disabled warnings.</span></span>
- <span data-ttu-id="4cb41-113">**CodeAnalysisRuleSet** / `-ruleset`: se especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.</span><span class="sxs-lookup"><span data-stu-id="4cb41-113">**CodeAnalysisRuleSet** / `-ruleset`: Specify a ruleset file that disables specific diagnostics.</span></span>
- <span data-ttu-id="4cb41-114">**ErrorLog** / `-errorlog`: se especifica un archivo para registrar todos los diagnósticos del compilador y el analizador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-114">**ErrorLog** / `-errorlog`: Specify a file to log all compiler and analyzer diagnostics.</span></span>
- <span data-ttu-id="4cb41-115">**ReportAnalyzer** / `-reportanalyzer`: se notifica información adicional del analizador, como el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4cb41-115">**ReportAnalyzer** / `-reportanalyzer`:  Report additional analyzer information, such as execution time.</span></span>

## <a name="warninglevel"></a><span data-ttu-id="4cb41-116">WarningLevel</span><span class="sxs-lookup"><span data-stu-id="4cb41-116">WarningLevel</span></span>

<span data-ttu-id="4cb41-117">La opción **WarningLevel** especifica el nivel de advertencia que debe mostrar el compilador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-117">The **WarningLevel** option specifies the warning level for the compiler to display.</span></span>

```xml
<WarningLevel>3</WarningLevel>
```

<span data-ttu-id="4cb41-118">El valor del elemento es el nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta.</span><span class="sxs-lookup"><span data-stu-id="4cb41-118">The element value is the warning level you want displayed for the compilation: Lower numbers show only high severity warnings.</span></span> <span data-ttu-id="4cb41-119">Los números más altos muestran más advertencias.</span><span class="sxs-lookup"><span data-stu-id="4cb41-119">Higher numbers show more warnings.</span></span> <span data-ttu-id="4cb41-120">El valor debe ser cero o un entero positivo:</span><span class="sxs-lookup"><span data-stu-id="4cb41-120">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="4cb41-121">Nivel de advertencia</span><span class="sxs-lookup"><span data-stu-id="4cb41-121">Warning level</span></span>|<span data-ttu-id="4cb41-122">Significado</span><span class="sxs-lookup"><span data-stu-id="4cb41-122">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="4cb41-123">0</span><span class="sxs-lookup"><span data-stu-id="4cb41-123">0</span></span>|<span data-ttu-id="4cb41-124">Desactiva la emisión de todos los mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="4cb41-124">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="4cb41-125">1</span><span class="sxs-lookup"><span data-stu-id="4cb41-125">1</span></span>|<span data-ttu-id="4cb41-126">Muestra mensajes de advertencia graves.</span><span class="sxs-lookup"><span data-stu-id="4cb41-126">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="4cb41-127">2</span><span class="sxs-lookup"><span data-stu-id="4cb41-127">2</span></span>|<span data-ttu-id="4cb41-128">Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="4cb41-128">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|
|<span data-ttu-id="4cb41-129">3</span><span class="sxs-lookup"><span data-stu-id="4cb41-129">3</span></span>|<span data-ttu-id="4cb41-130">Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="4cb41-130">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|
|<span data-ttu-id="4cb41-131">4 (el valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="4cb41-131">4 (the default)</span></span>|<span data-ttu-id="4cb41-132">Muestra todas las advertencias de nivel 3 además de advertencias informativas.</span><span class="sxs-lookup"><span data-stu-id="4cb41-132">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="4cb41-133">5</span><span class="sxs-lookup"><span data-stu-id="4cb41-133">5</span></span>|<span data-ttu-id="4cb41-134">Muestra las advertencias de nivel 4, además de [advertencias adicionales](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) del compilador incluido con C# 9.0.</span><span class="sxs-lookup"><span data-stu-id="4cb41-134">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="4cb41-135">Mayor que 5</span><span class="sxs-lookup"><span data-stu-id="4cb41-135">Greater than 5</span></span>|<span data-ttu-id="4cb41-136">Cualquier valor mayor que 5 se tratará como 5.</span><span class="sxs-lookup"><span data-stu-id="4cb41-136">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="4cb41-137">Para asegurarse de que siempre reciba todas las advertencias si el compilador se actualiza con nuevos niveles de advertencia, proporciona un valor grande arbitrario (por ejemplo, `9999`).</span><span class="sxs-lookup"><span data-stu-id="4cb41-137">To make sure you always have all warnings if the compiler is updated with new warning levels, put an arbitrary large value (for example, `9999`).</span></span>

<span data-ttu-id="4cb41-138">Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="4cb41-138">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="4cb41-139">Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="4cb41-139">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span> <span data-ttu-id="4cb41-140">Use [**TreatWarningsAsErrors**](#treatwarningsaserrors) para tratar todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-140">Use [**TreatWarningsAsErrors**](#treatwarningsaserrors) to treat all warnings as errors.</span></span> <span data-ttu-id="4cb41-141">Use [**DisabledWarnings**](#disabledwarnings) para deshabilitar advertencias concretas.</span><span class="sxs-lookup"><span data-stu-id="4cb41-141">Use [**DisabledWarnings**](#disabledwarnings) to disable certain warnings.</span></span>  

## <a name="treatwarningsaserrors"></a><span data-ttu-id="4cb41-142">TreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="4cb41-142">TreatWarningsAsErrors</span></span>

<span data-ttu-id="4cb41-143">La opción **TreatWarningsAsErrors** trata todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-143">The **TreatWarningsAsErrors** option treats all warnings as errors.</span></span> <span data-ttu-id="4cb41-144">También puede usar **TreatWarningsAsErrors** para establecer solo algunas advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-144">You can also use the **TreatWarningsAsErrors** to set only some warnings as errors.</span></span> <span data-ttu-id="4cb41-145">Si activa **TreatWarningsAsErrors**, puede usar **TreatWarningsAsErrors** para enumerar las advertencias que no se deben tratar como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-145">If you turn on **TreatWarningsAsErrors**, you can use **TreatWarningsAsErrors** to list warnings that shouldn't be treated as errors.</span></span>

```xml
<TreatWarningsAsErrors></TreatWarningsAsErrors>
```

<span data-ttu-id="4cb41-146">En su lugar, todos los mensajes de advertencia se notifican como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-146">All warning messages are instead reported as errors.</span></span> <span data-ttu-id="4cb41-147">El proceso de compilación se detiene (no se genera ningún archivo de salida).</span><span class="sxs-lookup"><span data-stu-id="4cb41-147">The build process halts (no output files are built).</span></span> <span data-ttu-id="4cb41-148">De forma predeterminada, **TreatWarningsAsErrors** no está en efecto, lo que significa que las advertencias no impedirán la generación de un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="4cb41-148">By default, **TreatWarningsAsErrors** isn't in effect, which means warnings don't prevent the generation of an output file.</span></span> <span data-ttu-id="4cb41-149">Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-149">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="4cb41-150">Se puede especificar el conjunto de todas las advertencias de nulabilidad con la abreviatura [**Nullable**](language.md#nullable).</span><span class="sxs-lookup"><span data-stu-id="4cb41-150">The set of all nullability warnings can be specified with the [**Nullable**](language.md#nullable) shorthand.</span></span> <span data-ttu-id="4cb41-151">Use [**WarningLevel**](#warninglevel) para especificar el nivel de advertencias que quiere que muestre el compilador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-151">Use [**WarningLevel**](#warninglevel) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="4cb41-152">Use [**DisabledWarnings**](#disabledwarnings) para deshabilitar advertencias concretas.</span><span class="sxs-lookup"><span data-stu-id="4cb41-152">Use [**DisabledWarnings**](#disabledwarnings) to disable certain warnings.</span></span>

## <a name="warningsaserrors-and-warningsnotaserrors"></a><span data-ttu-id="4cb41-153">WarningsAsErrors y WarningsNotAsErrors</span><span class="sxs-lookup"><span data-stu-id="4cb41-153">WarningsAsErrors and WarningsNotAsErrors</span></span>

<span data-ttu-id="4cb41-154">Las opciones **WarningsAsErrors** y **WarningsNotAsErrors** invalidan la opción **TreatWarningsAsErrors** de una lista de advertencias.</span><span class="sxs-lookup"><span data-stu-id="4cb41-154">The **WarningsAsErrors** and **WarningsNotAsErrors** options override the **TreatWarningsAsErrors** option for a list of warnings.</span></span>

<span data-ttu-id="4cb41-155">Habilite las advertencias 0219 y 0168 como errores:</span><span class="sxs-lookup"><span data-stu-id="4cb41-155">Enable warnings 0219 and 0168 as errors:</span></span>

```xml
<WarningsAsErrors>0219,0168</WarningsAsErrors>
```

<span data-ttu-id="4cb41-156">Deshabilite las mismas advertencias como errores:</span><span class="sxs-lookup"><span data-stu-id="4cb41-156">Disable the same warnings as errors:</span></span>

```xml
<WarningsNotAsErrors>0219,0168</WarningsNotAsErrors>
```

<span data-ttu-id="4cb41-157">Use **WarningsAsErrors** para configurar un conjunto de advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-157">You use **WarningsAsErrors** to configure a set of warnings as errors.</span></span> <span data-ttu-id="4cb41-158">Use **WarningsNotAsErrors** para configurar un conjunto de advertencias que no deben ser errores cuando se han establecido todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4cb41-158">Use **WarningsNotAsErrors** to configure a set of warnings that should not be errors when you've set all warnings as errors.</span></span>

## <a name="disabledwarnings"></a><span data-ttu-id="4cb41-159">DisabledWarnings</span><span class="sxs-lookup"><span data-stu-id="4cb41-159">DisabledWarnings</span></span>

<span data-ttu-id="4cb41-160">La opción **DisabledWarnings** permite impedir que el compilador muestre una o más advertencias.</span><span class="sxs-lookup"><span data-stu-id="4cb41-160">The **DisabledWarnings** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="4cb41-161">Separe varios números de advertencia con una coma.</span><span class="sxs-lookup"><span data-stu-id="4cb41-161">Separate multiple warning numbers with a comma.</span></span>

```xml
<DisabledWarnings>number1, number2</DisabledWarnings>
```

<span data-ttu-id="4cb41-162">`number1`, `number2` Números de advertencia que quiere que el compilador suprima.</span><span class="sxs-lookup"><span data-stu-id="4cb41-162">`number1`, `number2` Warning number(s) that you want the compiler to suppress.</span></span> <span data-ttu-id="4cb41-163">Debe especificar la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="4cb41-163">You specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="4cb41-164">Por ejemplo, si quiere suprimir *CS0028*, podría especificar `<DisabledWarnings>28</DisabledWarnings>`.</span><span class="sxs-lookup"><span data-stu-id="4cb41-164">For example, if you want to suppress *CS0028*, you could specify `<DisabledWarnings>28</DisabledWarnings>`.</span></span> <span data-ttu-id="4cb41-165">El compilador omitirá silenciosamente los números de advertencia pasados a **DisabledWarnings** que eran válidos en versiones anteriores, pero que se han quitado.</span><span class="sxs-lookup"><span data-stu-id="4cb41-165">The compiler silently ignores warning numbers passed to **DisabledWarnings** that were valid in previous releases, but that have been removed.</span></span> <span data-ttu-id="4cb41-166">Por ejemplo, *CS0679* era válido en el compilador de Visual Studio .NET 2002, pero se ha eliminado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4cb41-166">For example, *CS0679* was valid in the compiler in Visual Studio .NET 2002 but was removed later.</span></span>

 <span data-ttu-id="4cb41-167">Las advertencias siguientes no se pueden suprimir mediante la opción **DisabledWarnings**:</span><span class="sxs-lookup"><span data-stu-id="4cb41-167">The following warnings cannot be suppressed by the **DisabledWarnings** option:</span></span>

- <span data-ttu-id="4cb41-168">Advertencia del compilador (nivel 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="4cb41-168">Compiler Warning (level 1) CS2002</span></span>  
- <span data-ttu-id="4cb41-169">Advertencia del compilador (nivel 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="4cb41-169">Compiler Warning (level 1) CS2023</span></span>
- <span data-ttu-id="4cb41-170">Advertencia del compilador (nivel 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="4cb41-170">Compiler Warning (level 1) CS2029</span></span>

## <a name="codeanalysisruleset"></a><span data-ttu-id="4cb41-171">CodeAnalysisRuleSet</span><span class="sxs-lookup"><span data-stu-id="4cb41-171">CodeAnalysisRuleSet</span></span>

<span data-ttu-id="4cb41-172">Especifica un archivo de conjunto de reglas que configura diagnósticos específicos.</span><span class="sxs-lookup"><span data-stu-id="4cb41-172">Specify a ruleset file that configures specific diagnostics.</span></span>

```xml
<CodeAnalysisRuleSet>MyConfiguration.ruleset</CodeAnalysisRuleSet>
```

<span data-ttu-id="4cb41-173">`MyConfiguration.ruleset` es la ruta del archivo de conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="4cb41-173">Where `MyConfiguration.ruleset` is the path to the ruleset file.</span></span> <span data-ttu-id="4cb41-174">Para obtener más información sobre el uso de conjuntos de reglas, vea el artículo en la [documentación de Visual Studio sobre conjuntos de reglas](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules).</span><span class="sxs-lookup"><span data-stu-id="4cb41-174">For more information on using rule sets, see the article in the [Visual Studio documentation on Rule sets](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules).</span></span>

## <a name="errorlog"></a><span data-ttu-id="4cb41-175">ErrorLog</span><span class="sxs-lookup"><span data-stu-id="4cb41-175">ErrorLog</span></span>

<span data-ttu-id="4cb41-176">Especifique un archivo para registrar todos los diagnósticos del compilador y el analizador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-176">Specify a file to log all compiler and analyzer diagnostics.</span></span>

```xml
<ErrorLog>MyConfiguration.ruleset</ErrorLog>
```

<span data-ttu-id="4cb41-177">La opción **ErrorLog** hace que el compilador genere un [registro de formato de intercambio de resultados de análisis estático (SARIF)](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools).</span><span class="sxs-lookup"><span data-stu-id="4cb41-177">The **ErrorLog** option causes the compiler to output a [Static Analysis Results Interchange Format (SARIF) log](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools).</span></span> <span data-ttu-id="4cb41-178">Los registros SARIF suelen ser leídos por herramientas que analizan los resultados de los diagnósticos del compilador y el analizador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-178">SARIF logs are typically read by tools that analyze the results from compiler and analyzer diagnostics.</span></span>

## <a name="reportanalyzer"></a><span data-ttu-id="4cb41-179">ReportAnalyzer</span><span class="sxs-lookup"><span data-stu-id="4cb41-179">ReportAnalyzer</span></span>

<span data-ttu-id="4cb41-180">Notifica información adicional del analizador, como el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4cb41-180">Report additional analyzer information, such as execution time.</span></span>

```xml
<ReportAnalyzer>true</ReportAnalyzer>
```

<span data-ttu-id="4cb41-181">La opción **ReportAnalyzer** hace que el compilador emita información de registro de MSBuild adicional en la que se detallan las características de rendimiento de los analizadores de la compilación.</span><span class="sxs-lookup"><span data-stu-id="4cb41-181">The **ReportAnalyzer** option causes the compiler to emit extra MSBuild log information that details the performance characteristics of analyzers in the build.</span></span> <span data-ttu-id="4cb41-182">Los creadores del analizador la usan normalmente como parte de la validación del analizador.</span><span class="sxs-lookup"><span data-stu-id="4cb41-182">It's typically used by analyzer authors as part of validating the analyzer.</span></span>
