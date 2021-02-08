---
title: Configurar reglas de análisis de código
description: Obtenga información sobre cómo configurar reglas de análisis de código en un archivo de configuración de analizador.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: 8f76c9c86c202ef1bad23bffe8379b0b93a53f17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787726"
---
# <a name="configuration-options-for-code-analysis"></a><span data-ttu-id="a5086-103">Opciones de configuración para el análisis de código</span><span class="sxs-lookup"><span data-stu-id="a5086-103">Configuration options for code analysis</span></span>

<span data-ttu-id="a5086-104">Las reglas de análisis de código tienen varias opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5086-104">Code analysis rules have various configuration options.</span></span> <span data-ttu-id="a5086-105">Estas opciones se especifican como pares de clave y valor en un [archivo de configuración de analizador](configuration-files.md) mediante la sintaxis `<option key> = <option value>` .</span><span class="sxs-lookup"><span data-stu-id="a5086-105">These options are specified as key-value pairs in an [analyzer configuration file](configuration-files.md) using the syntax `<option key> = <option value>`.</span></span>

<span data-ttu-id="a5086-106">La opción más común que va a configurar es la [gravedad de la regla](#severity-level).</span><span class="sxs-lookup"><span data-stu-id="a5086-106">The most common option you'll configure is a [rule's severity](#severity-level).</span></span> <span data-ttu-id="a5086-107">Puede configurar el nivel de gravedad para todas las reglas del analizador, incluidas las reglas de [calidad del código](quality-rules/index.md) y [las reglas de estilo de código](style-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5086-107">You can configure severity level for all analyzer rules, including [code quality rules](quality-rules/index.md) and [code style rules](style-rules/index.md).</span></span> <span data-ttu-id="a5086-108">Por ejemplo, para habilitar una regla como advertencia, puede Agregar el siguiente par clave-valor a un EditorConfig archivo.</span><span class="sxs-lookup"><span data-stu-id="a5086-108">For example, to enable a rule as a warning, you can add the following key-value pair to an EditorConfig file.</span></span>

`dotnet_diagnostic.<rule ID>.severity = warning`

<span data-ttu-id="a5086-109">También puede configurar opciones adicionales para personalizar el comportamiento de la regla:</span><span class="sxs-lookup"><span data-stu-id="a5086-109">You can also configure additional options to customize rule behavior:</span></span>

- <span data-ttu-id="a5086-110">Las reglas de calidad de código tienen [opciones adicionales](code-quality-rule-options.md) para configurar el comportamiento, como los nombres de método a los que se debe aplicar una regla.</span><span class="sxs-lookup"><span data-stu-id="a5086-110">Code quality rules have [additional options](code-quality-rule-options.md) to configure behavior, such as which method names a rule should apply to.</span></span>
- <span data-ttu-id="a5086-111">Las reglas de estilo de código tienen [Opciones de estilo de código personalizado](code-style-rule-options.md).</span><span class="sxs-lookup"><span data-stu-id="a5086-111">Code style rules have [custom code style options](code-style-rule-options.md).</span></span>
- <span data-ttu-id="a5086-112">Las reglas del analizador de terceros pueden definir sus propias opciones de configuración, con nombres de clave personalizados y formatos de valor.</span><span class="sxs-lookup"><span data-stu-id="a5086-112">Third party analyzer rules can define their own configuration options, with custom key names and value formats.</span></span>

<span data-ttu-id="a5086-113">La sintaxis para configurar la gravedad de una regla específica en un [archivo de configuración de analizador](configuration-files.md) es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5086-113">The syntax for configuring a specific rule's severity in an [analyzer configuration file](configuration-files.md) is as follows:</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a><span data-ttu-id="a5086-114">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="a5086-114">General options</span></span>

<span data-ttu-id="a5086-115">Estas opciones se aplican al análisis de código en conjunto.</span><span class="sxs-lookup"><span data-stu-id="a5086-115">These options apply to code analysis as a whole.</span></span> <span data-ttu-id="a5086-116">No se pueden aplicar solo a una única regla o conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="a5086-116">They cannot be applied only to a single rule or set of rules.</span></span>

### <a name="exclude-generated-code"></a><span data-ttu-id="a5086-117">Excluir código generado</span><span class="sxs-lookup"><span data-stu-id="a5086-117">Exclude generated code</span></span>

<span data-ttu-id="a5086-118">Puede configurar archivos y carpetas adicionales para que se traten como código generado agregando una `generated_code = true | false` entrada al [archivo de configuración](configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="a5086-118">You can configure additional files and folders to be treated as generated code by adding a `generated_code = true | false` entry to your [configuration file](configuration-files.md).</span></span> <span data-ttu-id="a5086-119">Las advertencias del analizador de código de .NET no son útiles en los archivos de código generados, como los archivos generados por el diseñador, que los usuarios no pueden editar para corregir las infracciones.</span><span class="sxs-lookup"><span data-stu-id="a5086-119">.NET code analyzer warnings aren't useful on generated code files, such as designer-generated files, which users can't edit to fix any violations.</span></span> <span data-ttu-id="a5086-120">En la mayoría de los casos, los analizadores de código omiten los archivos de código generado y no informan de las infracciones de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="a5086-120">In most cases, code analyzers skip generated code files and don't report violations on these files.</span></span>

<span data-ttu-id="a5086-121">De forma predeterminada, los archivos con determinadas extensiones de archivo o encabezados de archivo generados automáticamente se tratan como archivos de código generado.</span><span class="sxs-lookup"><span data-stu-id="a5086-121">By default, files with certain file extensions or auto-generated file headers are treated as generated code files.</span></span> <span data-ttu-id="a5086-122">Por ejemplo, un nombre de archivo que termina con `.designer.cs` o `.generated.cs` se considera código generado.</span><span class="sxs-lookup"><span data-stu-id="a5086-122">For example, a file name ending with `.designer.cs` or `.generated.cs` is considered generated code.</span></span> <span data-ttu-id="a5086-123">Esta opción de configuración permite especificar patrones de nomenclatura adicionales.</span><span class="sxs-lookup"><span data-stu-id="a5086-123">This configuration option lets you specify additional naming patterns.</span></span>

<span data-ttu-id="a5086-124">Por ejemplo, para tratar todos los archivos cuyo nombre termina con `.MyGenerated.cs` como código generado, agregue la entrada siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5086-124">For example, to treat all files whose name ends with `.MyGenerated.cs` as generated code, add the following entry:</span></span>

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a><span data-ttu-id="a5086-125">Opciones específicas de la regla</span><span class="sxs-lookup"><span data-stu-id="a5086-125">Rule-specific options</span></span>

<span data-ttu-id="a5086-126">Las opciones específicas de la regla se pueden aplicar a una sola regla, a un conjunto de reglas o a todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="a5086-126">Rule-specific options can be applied to a single rule, a set of rules, or all rules.</span></span> <span data-ttu-id="a5086-127">Las opciones específicas de la regla incluyen:</span><span class="sxs-lookup"><span data-stu-id="a5086-127">The rule-specific options include:</span></span>

- [<span data-ttu-id="a5086-128">Nivel de gravedad de la regla</span><span class="sxs-lookup"><span data-stu-id="a5086-128">Rule severity level</span></span>](#severity-level)
- [<span data-ttu-id="a5086-129">Opciones específicas de las reglas *de calidad de código*</span><span class="sxs-lookup"><span data-stu-id="a5086-129">Options specific to *code-quality* rules</span></span>](code-quality-rule-options.md)

### <a name="severity-level"></a><span data-ttu-id="a5086-130">Nivel de gravedad</span><span class="sxs-lookup"><span data-stu-id="a5086-130">Severity level</span></span>

<span data-ttu-id="a5086-131">En la tabla siguiente se muestran los diferentes niveles de gravedad de la regla que se pueden configurar para todas las reglas del analizador, incluidas las reglas de [calidad de código](quality-rules/index.md) y [estilo de código](style-rules/index.md) .</span><span class="sxs-lookup"><span data-stu-id="a5086-131">The following table shows the different rule severities that you can configure for all analyzer rules, including [code quality](quality-rules/index.md) and [code style](style-rules/index.md) rules.</span></span>

| <span data-ttu-id="a5086-132">Gravedad</span><span class="sxs-lookup"><span data-stu-id="a5086-132">Severity</span></span> | <span data-ttu-id="a5086-133">Comportamiento en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="a5086-133">Build-time behavior</span></span> |
|-|-|
| `error` | <span data-ttu-id="a5086-134">Las infracciones aparecen como *errores* de compilación y producen errores en las compilaciones.</span><span class="sxs-lookup"><span data-stu-id="a5086-134">Violations appear as build *errors* and cause builds to fail.</span></span>|
| `warning` | <span data-ttu-id="a5086-135">Las infracciones aparecen como *advertencias* de compilación, pero no hacen que se produzca un error en las compilaciones (a menos que tenga una opción establecida para tratar advertencias como errores).</span><span class="sxs-lookup"><span data-stu-id="a5086-135">Violations appear as build *warnings* but do not cause builds to fail (unless you have an option set to treat warnings as errors).</span></span> |
| `suggestion` | <span data-ttu-id="a5086-136">Las infracciones aparecen como *mensajes* de compilación y como sugerencias en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5086-136">Violations appear as build *messages* and as suggestions in the Visual Studio IDE.</span></span> |
| `silent` | <span data-ttu-id="a5086-137">Las infracciones no son visibles para el usuario.</span><span class="sxs-lookup"><span data-stu-id="a5086-137">Violations aren't visible to the user.</span></span> |
| `none` | <span data-ttu-id="a5086-138">La regla se suprime por completo.</span><span class="sxs-lookup"><span data-stu-id="a5086-138">Rule is suppressed completely.</span></span> |
| `default` | <span data-ttu-id="a5086-139">Se usa la gravedad predeterminada de la regla.</span><span class="sxs-lookup"><span data-stu-id="a5086-139">The default severity of the rule is used.</span></span> |

> [!TIP]
> <span data-ttu-id="a5086-140">Para obtener información sobre cómo se exponen las gravedades de las reglas en Visual Studio, vea [niveles de gravedad](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span><span class="sxs-lookup"><span data-stu-id="a5086-140">For information about how rule severities surface in Visual Studio, see [Severity levels](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span></span>

#### <a name="scope"></a><span data-ttu-id="a5086-141">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a5086-141">Scope</span></span>

<span data-ttu-id="a5086-142">Para establecer la gravedad de la regla para una sola regla, use la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5086-142">To set the rule severity for a single rule, use the following syntax.</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

<span data-ttu-id="a5086-143">Use la siguiente sintaxis para establecer la gravedad de la regla predeterminada para una [categoría de reglas](categories.md).</span><span class="sxs-lookup"><span data-stu-id="a5086-143">To set the default rule severity for a [category of rules](categories.md), use the following syntax.</span></span> <span data-ttu-id="a5086-144">La categoría de cada regla se proporciona en las páginas de referencia de reglas individuales, por ejemplo, [CA1000](quality-rules/ca1000.md).</span><span class="sxs-lookup"><span data-stu-id="a5086-144">The category for each rule is provided in the individual rule reference pages, for example, [CA1000](quality-rules/ca1000.md).</span></span>

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

<span data-ttu-id="a5086-145">Para establecer la gravedad de la regla predeterminada para todas las reglas del analizador, use la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="a5086-145">To set the default rule severity for all analyzer rules, use the following syntax.</span></span>

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a><span data-ttu-id="a5086-146">Prioridad</span><span class="sxs-lookup"><span data-stu-id="a5086-146">Precedence</span></span>

<span data-ttu-id="a5086-147">Si tiene varias entradas de configuración de gravedad que se pueden aplicar al mismo identificador de regla, la prioridad se elige en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5086-147">If you have multiple severity configuration entries that can be applied to the same rule ID, precedence is chosen in the following order:</span></span>

- <span data-ttu-id="a5086-148">Una entrada para una regla individual por identificador tiene prioridad sobre una entrada para una categoría.</span><span class="sxs-lookup"><span data-stu-id="a5086-148">An entry for an individual rule by ID takes precedence over an entry for a category.</span></span>
- <span data-ttu-id="a5086-149">Una entrada para una categoría tiene prioridad sobre una entrada para todas las reglas del analizador.</span><span class="sxs-lookup"><span data-stu-id="a5086-149">An entry for a category takes precedence over an entry for all analyzer rules.</span></span>

<span data-ttu-id="a5086-150">Considere el ejemplo siguiente, donde [CA1822](/visualstudio/code-quality/ca1822) tiene la categoría "performance":</span><span class="sxs-lookup"><span data-stu-id="a5086-150">Consider the following example, where [CA1822](/visualstudio/code-quality/ca1822) has the category "Performance":</span></span>

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

<span data-ttu-id="a5086-151">En el ejemplo anterior, las tres entradas de gravedad se aplican a CA1822.</span><span class="sxs-lookup"><span data-stu-id="a5086-151">In the preceding example, all three severity entries are applicable to CA1822.</span></span> <span data-ttu-id="a5086-152">Sin embargo, con las reglas de precedencia especificadas, la primera entrada basada en el identificador de regla gana sobre las siguientes entradas.</span><span class="sxs-lookup"><span data-stu-id="a5086-152">However, using the specified precedence rules, the first rule ID-based entry wins over the next entries.</span></span> <span data-ttu-id="a5086-153">En este ejemplo, CA1822 tendrá una gravedad efectiva de `error` .</span><span class="sxs-lookup"><span data-stu-id="a5086-153">In this example, CA1822 will have an effective severity of `error`.</span></span> <span data-ttu-id="a5086-154">Todas las demás reglas de la categoría "rendimiento" tendrán una gravedad de `warning` .</span><span class="sxs-lookup"><span data-stu-id="a5086-154">All other rules within the "Performance" category will have a severity of `warning`.</span></span>

<span data-ttu-id="a5086-155">Para obtener información sobre cómo se decide la precedencia entre archivos, vea la [sección de precedencia del artículo archivos de configuración](configuration-files.md#precedence).</span><span class="sxs-lookup"><span data-stu-id="a5086-155">For information about how inter-file precedence is decided, see the [Precedence section of the Configuration files article](configuration-files.md#precedence).</span></span>
