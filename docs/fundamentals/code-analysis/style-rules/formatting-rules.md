---
title: Reglas de formato del estilo de código
description: Obtenga información sobre las reglas de estilo de código para aplicar sangrías, espacios y nuevas líneas.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE0055
- formatting rules
helpviewer_keywords:
- IDE0055
- formatting code style rules [EditorConfig]
- formatting rules
- EditorConfig formatting conventions
ms.openlocfilehash: 866949692341f65a5b78c7dd5b8eec918873d3b7
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511806"
---
# <a name="formatting-rules"></a><span data-ttu-id="aba89-103">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="aba89-103">Formatting rules</span></span>

<span data-ttu-id="aba89-104">Las reglas de formato afectan a cómo se alinean la sangría, los espacios y las nuevas líneas alrededor de las construcciones del lenguaje de programación .NET.</span><span class="sxs-lookup"><span data-stu-id="aba89-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="aba89-105">La reglas se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="aba89-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="aba89-106">[Reglas de formato de .NET](#net-formatting-rules): reglas que se aplican a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aba89-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="aba89-107">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el prefijo `dotnet_`.</span><span class="sxs-lookup"><span data-stu-id="aba89-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="aba89-108">[Reglas de formato de C#](#c-formatting-rules): reglas que son específicas del lenguaje C# únicamente.</span><span class="sxs-lookup"><span data-stu-id="aba89-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="aba89-109">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el prefijo `csharp_`.</span><span class="sxs-lookup"><span data-stu-id="aba89-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="aba89-110">Id. de regla: "IDE0055" (corregir formato)</span><span class="sxs-lookup"><span data-stu-id="aba89-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="aba89-111">Todas las opciones de formato tienen el identificador de regla `IDE0055` y el título `Fix formatting`.</span><span class="sxs-lookup"><span data-stu-id="aba89-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="aba89-112">Establezca la gravedad de una infracción de formato en un archivo EditorConfig mediante la siguiente línea de configuración.</span><span class="sxs-lookup"><span data-stu-id="aba89-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="aba89-113">El valor de gravedad debe ser `warning` o `error` para que [se aplique en la compilación](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="aba89-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="aba89-114">Para consultar todos los valores de gravedad posibles, vea [Nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="aba89-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="aba89-115">Formato de opción</span><span class="sxs-lookup"><span data-stu-id="aba89-115">Option format</span></span>

<span data-ttu-id="aba89-116">Las opciones de las reglas de formato se pueden especificar en un archivo EditorConfig con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="aba89-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="aba89-117">Para muchas reglas, especificará `true` (se prefiere este estilo) o `false` (no se prefiere este estilo) para `value`.</span><span class="sxs-lookup"><span data-stu-id="aba89-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="aba89-118">Para otras reglas, especifique un valor como `flush_left` o `before_and_after` para describir cuándo y dónde aplicar la regla.</span><span class="sxs-lookup"><span data-stu-id="aba89-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="aba89-119">No se especifica un nivel de gravedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="aba89-120">Reglas de formato de .NET</span><span class="sxs-lookup"><span data-stu-id="aba89-120">.NET formatting rules</span></span>

<span data-ttu-id="aba89-121">Las reglas de formato de esta sección se aplican a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aba89-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="aba89-122">Organización de instrucciones Using</span><span class="sxs-lookup"><span data-stu-id="aba89-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="aba89-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="aba89-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="aba89-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="aba89-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="aba89-125">Organización de directivas using</span><span class="sxs-lookup"><span data-stu-id="aba89-125">Organize using directives</span></span>

<span data-ttu-id="aba89-126">Estas reglas de formato se refieren a la ordenación y la visualización de directivas `using` y de instrucciones `Imports`.</span><span class="sxs-lookup"><span data-stu-id="aba89-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="aba89-127">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="aba89-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="aba89-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="aba89-129">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-129">Property</span></span>|<span data-ttu-id="aba89-130">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-130">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-131">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-131">**Option name**</span></span> | <span data-ttu-id="aba89-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="aba89-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="aba89-133">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-133">**Applicable languages**</span></span> | <span data-ttu-id="aba89-134">C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aba89-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="aba89-135">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-135">**Introduced version**</span></span> | <span data-ttu-id="aba89-136">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-137">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-137">**Option values**</span></span> | <span data-ttu-id="aba89-138">`true`: se ordenan alfabéticamente las directivas `System.*` `using` y se colocan antes que cualquier otra directiva using.</span><span class="sxs-lookup"><span data-stu-id="aba89-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="aba89-139">`false`: no se colocan las directivas `System.*` `using` antes que otras directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="aba89-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="aba89-140">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-140">Code examples:</span></span>

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="aba89-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="aba89-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="aba89-142">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-142">Property</span></span>|<span data-ttu-id="aba89-143">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-143">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-144">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-144">**Option name**</span></span> | <span data-ttu-id="aba89-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="aba89-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="aba89-146">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-146">**Applicable languages**</span></span> | <span data-ttu-id="aba89-147">C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aba89-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="aba89-148">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-148">**Introduced version**</span></span> | <span data-ttu-id="aba89-149">Versión 15.5 de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="aba89-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="aba89-150">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-150">**Option values**</span></span> | <span data-ttu-id="aba89-151">`true`: coloque una línea en blanco entre grupos de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="aba89-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="aba89-152">`false`: no coloque una línea en blanco entre grupos de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="aba89-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="aba89-153">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-153">Code examples:</span></span>

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

## <a name="c-formatting-rules"></a><span data-ttu-id="aba89-154">Reglas de formato de C#</span><span class="sxs-lookup"><span data-stu-id="aba89-154">C# formatting rules</span></span>

<span data-ttu-id="aba89-155">Las reglas de formato de esta sección se aplican únicamente al código de C#.</span><span class="sxs-lookup"><span data-stu-id="aba89-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="aba89-156">Opciones de nueva línea</span><span class="sxs-lookup"><span data-stu-id="aba89-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="aba89-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="aba89-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="aba89-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="aba89-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="aba89-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="aba89-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="aba89-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="aba89-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="aba89-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="aba89-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="aba89-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="aba89-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="aba89-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="aba89-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="aba89-164">Opciones de sangría</span><span class="sxs-lookup"><span data-stu-id="aba89-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="aba89-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="aba89-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="aba89-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="aba89-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="aba89-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="aba89-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="aba89-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="aba89-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="aba89-171">Opciones de espaciado</span><span class="sxs-lookup"><span data-stu-id="aba89-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="aba89-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="aba89-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="aba89-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="aba89-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="aba89-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="aba89-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="aba89-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="aba89-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="aba89-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="aba89-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="aba89-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="aba89-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="aba89-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="aba89-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="aba89-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="aba89-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="aba89-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="aba89-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="aba89-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="aba89-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="aba89-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="aba89-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="aba89-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="aba89-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="aba89-194">Opciones de encapsulado</span><span class="sxs-lookup"><span data-stu-id="aba89-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="aba89-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="aba89-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="aba89-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="aba89-197">Opciones de la directiva using</span><span class="sxs-lookup"><span data-stu-id="aba89-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="aba89-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="aba89-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="aba89-199">Opciones de nueva línea</span><span class="sxs-lookup"><span data-stu-id="aba89-199">New-line options</span></span>

<span data-ttu-id="aba89-200">Estas reglas de formato se refieren al uso de nuevas líneas para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="aba89-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="aba89-201">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-201">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="aba89-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="aba89-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="aba89-203">Esta regla se refiere a si se debe colocar una llave de apertura `{` en la misma línea que el código anterior, o en una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="aba89-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="aba89-204">Para esta regla, se especifica **all**, **none** o uno o varios elementos de código como **methods** o **properties** para definir cuándo se debe aplicar esta regla.</span><span class="sxs-lookup"><span data-stu-id="aba89-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="aba89-205">Para especificar varios elementos de código, sepárelos con una coma (,).</span><span class="sxs-lookup"><span data-stu-id="aba89-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="aba89-206">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-206">Property</span></span>|<span data-ttu-id="aba89-207">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-207">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-208">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-208">**Option name**</span></span> | <span data-ttu-id="aba89-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="aba89-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="aba89-210">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-210">**Applicable languages**</span></span> | <span data-ttu-id="aba89-211">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-211">C#</span></span> |
| <span data-ttu-id="aba89-212">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-212">**Introduced version**</span></span> | <span data-ttu-id="aba89-213">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-214">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-214">**Option values**</span></span> | <span data-ttu-id="aba89-215">`all`: se requiere que las llaves estén en una nueva línea para todas las expresiones (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="aba89-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="aba89-216">`none`: se requiere que las llaves estén en una nueva línea para todas las expresiones ("K&R").</span><span class="sxs-lookup"><span data-stu-id="aba89-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="aba89-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types`: se requiere que las llaves estén en una línea nueva para el elemento de código especificado (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="aba89-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="aba89-218">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-218">Code examples:</span></span>

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="aba89-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="aba89-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="aba89-220">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-220">Property</span></span>|<span data-ttu-id="aba89-221">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-221">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-222">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-222">**Option name**</span></span> | <span data-ttu-id="aba89-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="aba89-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="aba89-224">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-224">**Applicable languages**</span></span> | <span data-ttu-id="aba89-225">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-225">C#</span></span> |
| <span data-ttu-id="aba89-226">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-226">**Introduced version**</span></span> | <span data-ttu-id="aba89-227">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-228">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-228">**Option values**</span></span> | <span data-ttu-id="aba89-229">`true`: las instrucciones `else` se colocan en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="aba89-230">`false`: las instrucciones `else` se colocan en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="aba89-231">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-231">Code examples:</span></span>

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="aba89-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="aba89-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="aba89-233">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-233">Property</span></span>|<span data-ttu-id="aba89-234">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-234">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-235">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-235">**Option name**</span></span> | <span data-ttu-id="aba89-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="aba89-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="aba89-237">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-237">**Applicable languages**</span></span> | <span data-ttu-id="aba89-238">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-238">C#</span></span> |
| <span data-ttu-id="aba89-239">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-239">**Introduced version**</span></span> | <span data-ttu-id="aba89-240">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-241">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-241">**Option values**</span></span> | <span data-ttu-id="aba89-242">`true`: las instrucciones `catch` se colocan en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="aba89-243">`false`: las instrucciones `catch` se colocan en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="aba89-244">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-244">Code examples:</span></span>

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="aba89-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="aba89-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="aba89-246">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-246">Property</span></span>|<span data-ttu-id="aba89-247">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-247">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-248">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-248">**Option name**</span></span> | <span data-ttu-id="aba89-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="aba89-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="aba89-250">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-250">**Applicable languages**</span></span> | <span data-ttu-id="aba89-251">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-251">C#</span></span> |
| <span data-ttu-id="aba89-252">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-252">**Introduced version**</span></span> | <span data-ttu-id="aba89-253">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-254">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-254">**Option values**</span></span> | <span data-ttu-id="aba89-255">`true`: se requiere que las instrucciones `finally` estén en una nueva línea después de la llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="aba89-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="aba89-256">`false`: se requiere que las instrucciones `finally` estén en la misma línea que la llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="aba89-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="aba89-257">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-257">Code examples:</span></span>

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="aba89-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="aba89-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="aba89-259">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-259">Property</span></span>|<span data-ttu-id="aba89-260">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-260">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-261">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-261">**Option name**</span></span> | <span data-ttu-id="aba89-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="aba89-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="aba89-263">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-263">**Applicable languages**</span></span> | <span data-ttu-id="aba89-264">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-264">C#</span></span> |
| <span data-ttu-id="aba89-265">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-265">**Introduced version**</span></span> | <span data-ttu-id="aba89-266">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-267">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-267">**Option values**</span></span> | <span data-ttu-id="aba89-268">`true`: se requiere que los miembros de inicializadores de objeto estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="aba89-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="aba89-269">`false`: se requiere que los miembros de inicializadores de objeto estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="aba89-270">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-270">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="aba89-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="aba89-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="aba89-272">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-272">Property</span></span>|<span data-ttu-id="aba89-273">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-273">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-274">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-274">**Option name**</span></span> | <span data-ttu-id="aba89-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="aba89-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="aba89-276">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-276">**Applicable languages**</span></span> | <span data-ttu-id="aba89-277">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-277">C#</span></span> |
| <span data-ttu-id="aba89-278">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-278">**Introduced version**</span></span> | <span data-ttu-id="aba89-279">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-280">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-280">**Option values**</span></span> | <span data-ttu-id="aba89-281">`true`: se requiere que los miembros de tipos anónimos estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="aba89-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="aba89-282">`false`: se requiere que los miembros de tipos anónimos estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="aba89-283">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-283">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="aba89-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="aba89-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="aba89-285">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-285">Property</span></span>|<span data-ttu-id="aba89-286">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-286">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-287">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-287">**Option name**</span></span> | <span data-ttu-id="aba89-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="aba89-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="aba89-289">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-289">**Applicable languages**</span></span> | <span data-ttu-id="aba89-290">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-290">C#</span></span> |
| <span data-ttu-id="aba89-291">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-291">**Introduced version**</span></span> | <span data-ttu-id="aba89-292">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-293">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-293">**Option values**</span></span> | <span data-ttu-id="aba89-294">`true`: se requiere que los elementos de las cláusulas de la expresión de consulta estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="aba89-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="aba89-295">`false`: se requiere que los elementos de las cláusulas de la expresión de consulta estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="aba89-296">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="aba89-297">Opciones de sangría</span><span class="sxs-lookup"><span data-stu-id="aba89-297">Indentation options</span></span>

<span data-ttu-id="aba89-298">Estas reglas de formato se refieren al uso de la sangría para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="aba89-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="aba89-299">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-299">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents_when_block = true
```

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="aba89-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="aba89-301">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-301">Property</span></span>|<span data-ttu-id="aba89-302">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-302">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-303">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-303">**Option name**</span></span> | <span data-ttu-id="aba89-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="aba89-305">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-305">**Applicable languages**</span></span> | <span data-ttu-id="aba89-306">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-306">C#</span></span> |
| <span data-ttu-id="aba89-307">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-307">**Introduced version**</span></span> | <span data-ttu-id="aba89-308">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-309">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-309">**Option values**</span></span> | <span data-ttu-id="aba89-310">`true`: aplicar sangría al contenido del caso `switch`.</span><span class="sxs-lookup"><span data-stu-id="aba89-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="aba89-311">`false`: no aplicar sangría al contenido del caso `switch`.</span><span class="sxs-lookup"><span data-stu-id="aba89-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="aba89-312">Cuando esta regla se establece en **true**, i.</span><span class="sxs-lookup"><span data-stu-id="aba89-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="aba89-313">Cuando esta regla se establece en **false**, d.</span><span class="sxs-lookup"><span data-stu-id="aba89-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="aba89-314">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-314">Code examples:</span></span>

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="aba89-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="aba89-316">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-316">Property</span></span>|<span data-ttu-id="aba89-317">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-317">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-318">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-318">**Option name**</span></span> | <span data-ttu-id="aba89-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="aba89-320">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-320">**Applicable languages**</span></span> | <span data-ttu-id="aba89-321">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-321">C#</span></span> |
| <span data-ttu-id="aba89-322">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-322">**Introduced version**</span></span> | <span data-ttu-id="aba89-323">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-324">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-324">**Option values**</span></span> | <span data-ttu-id="aba89-325">`true`: aplicar sangría a etiquetas `switch`.</span><span class="sxs-lookup"><span data-stu-id="aba89-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="aba89-326">`false`: no aplicar sangría a etiquetas `switch`.</span><span class="sxs-lookup"><span data-stu-id="aba89-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="aba89-327">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-327">Code examples:</span></span>

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_labels"></a><span data-ttu-id="aba89-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="aba89-329">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-329">Property</span></span>|<span data-ttu-id="aba89-330">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-330">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-331">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-331">**Option name**</span></span> | <span data-ttu-id="aba89-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="aba89-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="aba89-333">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-333">**Applicable languages**</span></span> | <span data-ttu-id="aba89-334">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-334">C#</span></span> |
| <span data-ttu-id="aba89-335">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-335">**Introduced version**</span></span> | <span data-ttu-id="aba89-336">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-337">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-337">**Option values**</span></span> | <span data-ttu-id="aba89-338">`flush_left`: las etiquetas se colocan en la primera columna de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="aba89-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="aba89-339">`one_less_than_current`: las etiquetas se colocan una sangría menos que el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="aba89-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="aba89-340">`no_change`: las etiquetas se colocan en la misma sangría que el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="aba89-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="aba89-341">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-341">Code examples:</span></span>

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="aba89-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="aba89-343">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-343">Property</span></span>|<span data-ttu-id="aba89-344">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-344">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-345">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-345">**Option name**</span></span> | <span data-ttu-id="aba89-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="aba89-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="aba89-347">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-347">**Applicable languages**</span></span> | <span data-ttu-id="aba89-348">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-348">C#</span></span> |
| <span data-ttu-id="aba89-349">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="aba89-350">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-350">Code examples:</span></span>

```csharp
// csharp_indent_block_contents = true
static void Hello()
{
    Console.WriteLine("Hello");
}

// csharp_indent_block_contents = false
static void Hello()
{
Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_braces"></a><span data-ttu-id="aba89-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="aba89-351">csharp_indent_braces</span></span>

|<span data-ttu-id="aba89-352">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-352">Property</span></span>|<span data-ttu-id="aba89-353">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-353">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-354">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-354">**Option name**</span></span> | <span data-ttu-id="aba89-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="aba89-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="aba89-356">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-356">**Applicable languages**</span></span> | <span data-ttu-id="aba89-357">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-357">C#</span></span> |
| <span data-ttu-id="aba89-358">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="aba89-359">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-359">Code examples:</span></span>

```csharp
// csharp_indent_braces = true
static void Hello()
    {
    Console.WriteLine("Hello");
    }

// csharp_indent_braces = false
static void Hello()
{
    Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="aba89-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="aba89-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="aba89-361">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-361">Property</span></span>|<span data-ttu-id="aba89-362">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-362">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-363">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-363">**Option name**</span></span> | <span data-ttu-id="aba89-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="aba89-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="aba89-365">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-365">**Applicable languages**</span></span> | <span data-ttu-id="aba89-366">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-366">C#</span></span> |
| <span data-ttu-id="aba89-367">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="aba89-368">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-368">Code examples:</span></span>

```csharp
// csharp_indent_case_contents_when_block = true
case 0:
    {
        Console.WriteLine("Hello");
        break;
    }

// csharp_indent_case_contents_when_block = false
case 0:
{
    Console.WriteLine("Hello");
    break;
}
```

### <a name="spacing-options"></a><span data-ttu-id="aba89-369">Opciones de espaciado</span><span class="sxs-lookup"><span data-stu-id="aba89-369">Spacing options</span></span>

<span data-ttu-id="aba89-370">Estas reglas de formato se refieren al uso de caracteres de espacio para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="aba89-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="aba89-371">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-371">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_after_comma = true
csharp_space_before_comma = false
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_before_semicolon_in_for_statement = false
csharp_space_around_declaration_statements = false
csharp_space_before_open_square_brackets = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_square_brackets = false
```

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="aba89-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="aba89-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="aba89-373">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-373">Property</span></span>|<span data-ttu-id="aba89-374">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-374">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-375">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-375">**Option name**</span></span> | <span data-ttu-id="aba89-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="aba89-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="aba89-377">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-377">**Applicable languages**</span></span> | <span data-ttu-id="aba89-378">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-378">C#</span></span> |
| <span data-ttu-id="aba89-379">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-379">**Introduced version**</span></span> | <span data-ttu-id="aba89-380">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-381">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-381">**Option values**</span></span> | <span data-ttu-id="aba89-382">`true`: se inserta un carácter de espacio entre una conversión y el valor</span><span class="sxs-lookup"><span data-stu-id="aba89-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="aba89-383">`false`: se quita el espacio entre la conversión y el valor</span><span class="sxs-lookup"><span data-stu-id="aba89-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="aba89-384">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="aba89-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="aba89-386">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-386">Property</span></span>|<span data-ttu-id="aba89-387">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-387">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-388">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-388">**Option name**</span></span> | <span data-ttu-id="aba89-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="aba89-390">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-390">**Applicable languages**</span></span> | <span data-ttu-id="aba89-391">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-391">C#</span></span> |
| <span data-ttu-id="aba89-392">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-392">**Introduced version**</span></span> | <span data-ttu-id="aba89-393">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-394">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-394">**Option values**</span></span> | <span data-ttu-id="aba89-395">`true`: se inserta un carácter de espacio después de una palabra clave en una instrucción de flujo de control como un bucle `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="aba89-396">`false`: se quita el espacio después de una palabra clave en una instrucción de flujo de control como un bucle `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="aba89-397">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="aba89-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="aba89-399">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-399">Property</span></span>|<span data-ttu-id="aba89-400">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-400">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-401">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-401">**Option name**</span></span> | <span data-ttu-id="aba89-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="aba89-403">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-403">**Applicable languages**</span></span> | <span data-ttu-id="aba89-404">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-404">C#</span></span> |
| <span data-ttu-id="aba89-405">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-405">**Introduced version**</span></span> | <span data-ttu-id="aba89-406">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-407">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-407">**Option values**</span></span> | <span data-ttu-id="aba89-408">`control_flow_statements`: se inserta un espacio entre los paréntesis de instrucciones de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="aba89-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="aba89-409">`expressions`: se inserta un espacio entre los paréntesis de expresiones.</span><span class="sxs-lookup"><span data-stu-id="aba89-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="aba89-410">`type_casts`: se inserta un espacio entre los paréntesis de las conversiones de tipos.</span><span class="sxs-lookup"><span data-stu-id="aba89-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="aba89-411">Si esta regla se omite o si se usa un valor distinto de `control_flow_statements`, `expressions` o `type_casts`, la configuración no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="aba89-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="aba89-412">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="aba89-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="aba89-414">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-414">Property</span></span>|<span data-ttu-id="aba89-415">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-415">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-416">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-416">**Option name**</span></span> | <span data-ttu-id="aba89-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="aba89-418">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-418">**Applicable languages**</span></span> | <span data-ttu-id="aba89-419">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-419">C#</span></span> |
| <span data-ttu-id="aba89-420">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-420">**Introduced version**</span></span> | <span data-ttu-id="aba89-421">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-422">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-422">**Option values**</span></span> | <span data-ttu-id="aba89-423">`true`: se inserta un carácter de espacio antes de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="aba89-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="aba89-424">`false`: se quita el espacio antes de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="aba89-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="aba89-425">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-425">Code examples:</span></span>

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="aba89-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="aba89-427">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-427">Property</span></span>|<span data-ttu-id="aba89-428">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-428">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-429">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-429">**Option name**</span></span> | <span data-ttu-id="aba89-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="aba89-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="aba89-431">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-431">**Applicable languages**</span></span> | <span data-ttu-id="aba89-432">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-432">C#</span></span> |
| <span data-ttu-id="aba89-433">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-433">**Introduced version**</span></span> | <span data-ttu-id="aba89-434">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-435">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-435">**Option values**</span></span> | <span data-ttu-id="aba89-436">`true`: se inserta un carácter de espacio después de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="aba89-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="aba89-437">`false`: se quita el espacio después de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="aba89-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="aba89-438">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-438">Code examples:</span></span>

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="aba89-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="aba89-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="aba89-440">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-440">Property</span></span>|<span data-ttu-id="aba89-441">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-441">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-442">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-442">**Option name**</span></span> | <span data-ttu-id="aba89-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="aba89-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="aba89-444">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-444">**Applicable languages**</span></span> | <span data-ttu-id="aba89-445">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-445">C#</span></span> |
| <span data-ttu-id="aba89-446">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-446">**Introduced version**</span></span> | <span data-ttu-id="aba89-447">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-448">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-448">**Option values**</span></span> | <span data-ttu-id="aba89-449">`before_and_after`: se inserta un espacio delante y detrás del operador binario.</span><span class="sxs-lookup"><span data-stu-id="aba89-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="aba89-450">`none`: se quitan los espacios delante y detrás del operador binario.</span><span class="sxs-lookup"><span data-stu-id="aba89-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="aba89-451">`ignore`: se omiten los espacios alrededor de operadores binarios,</span><span class="sxs-lookup"><span data-stu-id="aba89-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="aba89-452">Si esta regla se omite o si se usa un valor distinto de `before_and_after`, `none` o `ignore`, la configuración no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="aba89-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="aba89-453">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="aba89-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="aba89-455">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-455">Property</span></span>|<span data-ttu-id="aba89-456">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-456">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-457">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-457">**Option name**</span></span> | <span data-ttu-id="aba89-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="aba89-459">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-459">**Applicable languages**</span></span> | <span data-ttu-id="aba89-460">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-460">C#</span></span> |
| <span data-ttu-id="aba89-461">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-461">**Introduced version**</span></span> | <span data-ttu-id="aba89-462">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-463">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-463">**Option values**</span></span> | <span data-ttu-id="aba89-464">`true`: se coloca un carácter de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una lista de parámetros de declaración de método.</span><span class="sxs-lookup"><span data-stu-id="aba89-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="aba89-465">`false`: se quitan los caracteres de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una lista de parámetros de declaración de método</span><span class="sxs-lookup"><span data-stu-id="aba89-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="aba89-466">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="aba89-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="aba89-468">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-468">Property</span></span>|<span data-ttu-id="aba89-469">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-469">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-470">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-470">**Option name**</span></span> | <span data-ttu-id="aba89-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="aba89-472">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-472">**Applicable languages**</span></span> | <span data-ttu-id="aba89-473">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-473">C#</span></span> |
| <span data-ttu-id="aba89-474">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-474">**Introduced version**</span></span> | <span data-ttu-id="aba89-475">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-476">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-476">**Option values**</span></span> | <span data-ttu-id="aba89-477">`true`: se inserta un espacio dentro de los paréntesis de una lista de parámetros correspondiente a una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="aba89-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="aba89-478">`false`: se quita el espacio dentro de los paréntesis de una lista de parámetros correspondiente a una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="aba89-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="aba89-479">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-479">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="aba89-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="aba89-481">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-481">Property</span></span>|<span data-ttu-id="aba89-482">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-482">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-483">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-483">**Option name**</span></span> | <span data-ttu-id="aba89-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="aba89-485">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-485">**Applicable languages**</span></span> | <span data-ttu-id="aba89-486">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-486">C#</span></span> |
| <span data-ttu-id="aba89-487">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-487">**Option values**</span></span> | <span data-ttu-id="aba89-488">`true`: se inserta un carácter de espacio entre el nombre del método y el paréntesis de apertura en la declaración de método</span><span class="sxs-lookup"><span data-stu-id="aba89-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="aba89-489">`false`: se quitan los caracteres de espacio entre el nombre del método y el paréntesis de apertura en la declaración de método</span><span class="sxs-lookup"><span data-stu-id="aba89-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="aba89-490">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="aba89-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="aba89-492">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-492">Property</span></span>|<span data-ttu-id="aba89-493">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-493">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-494">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-494">**Option name**</span></span> | <span data-ttu-id="aba89-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="aba89-496">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-496">**Applicable languages**</span></span> | <span data-ttu-id="aba89-497">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-497">C#</span></span> |
| <span data-ttu-id="aba89-498">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-498">**Introduced version**</span></span> | <span data-ttu-id="aba89-499">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-500">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-500">**Option values**</span></span> | <span data-ttu-id="aba89-501">`true`: se coloca un carácter de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="aba89-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="aba89-502">`false`: se quitan los caracteres de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una llamada de método</span><span class="sxs-lookup"><span data-stu-id="aba89-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="aba89-503">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="aba89-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="aba89-505">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-505">Property</span></span>|<span data-ttu-id="aba89-506">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-506">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-507">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-507">**Option name**</span></span> | <span data-ttu-id="aba89-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="aba89-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="aba89-509">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-509">**Applicable languages**</span></span> | <span data-ttu-id="aba89-510">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-510">C#</span></span> |
| <span data-ttu-id="aba89-511">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-511">**Introduced version**</span></span> | <span data-ttu-id="aba89-512">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-513">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-513">**Option values**</span></span> | <span data-ttu-id="aba89-514">`true`: se inserta un espacio entre paréntesis vacíos de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="aba89-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="aba89-515">`false`: se quita un espacio entre paréntesis vacíos de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="aba89-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="aba89-516">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-516">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="aba89-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="aba89-518">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-518">Property</span></span>|<span data-ttu-id="aba89-519">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-519">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-520">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-520">**Option name**</span></span> | <span data-ttu-id="aba89-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="aba89-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="aba89-522">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-522">**Applicable languages**</span></span> | <span data-ttu-id="aba89-523">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-523">C#</span></span> |
| <span data-ttu-id="aba89-524">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-524">**Introduced version**</span></span> | <span data-ttu-id="aba89-525">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="aba89-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="aba89-526">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-526">**Option values**</span></span> | <span data-ttu-id="aba89-527">`true`: se inserta un espacio entre el nombre de la llamada de método y el paréntesis de apertura.</span><span class="sxs-lookup"><span data-stu-id="aba89-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="aba89-528">`false`: se quita un espacio entre el nombre de la llamada de método y el paréntesis de apertura.</span><span class="sxs-lookup"><span data-stu-id="aba89-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="aba89-529">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-529">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="aba89-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="aba89-531">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-531">Property</span></span>|<span data-ttu-id="aba89-532">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-532">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-533">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-533">**Option name**</span></span> | <span data-ttu-id="aba89-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="aba89-535">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-535">**Applicable languages**</span></span> | <span data-ttu-id="aba89-536">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-536">C#</span></span> |
| <span data-ttu-id="aba89-537">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-537">**Option values**</span></span> | <span data-ttu-id="aba89-538">`true`: se inserta un espacio tras una coma.</span><span class="sxs-lookup"><span data-stu-id="aba89-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="aba89-539">`false`: se quita un espacio después de una coma.</span><span class="sxs-lookup"><span data-stu-id="aba89-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="aba89-540">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="aba89-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="aba89-542">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-542">Property</span></span>|<span data-ttu-id="aba89-543">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-543">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-544">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-544">**Option name**</span></span> | <span data-ttu-id="aba89-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="aba89-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="aba89-546">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-546">**Applicable languages**</span></span> | <span data-ttu-id="aba89-547">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-547">C#</span></span> |
| <span data-ttu-id="aba89-548">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-548">**Option values**</span></span> | <span data-ttu-id="aba89-549">`true`: se inserta un espacio delante de una coma</span><span class="sxs-lookup"><span data-stu-id="aba89-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="aba89-550">`false`: se quita el espacio delante de una coma</span><span class="sxs-lookup"><span data-stu-id="aba89-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="aba89-551">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="aba89-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="aba89-553">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-553">Property</span></span>|<span data-ttu-id="aba89-554">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-554">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-555">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-555">**Option name**</span></span> | <span data-ttu-id="aba89-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="aba89-557">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-557">**Applicable languages**</span></span> | <span data-ttu-id="aba89-558">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-558">C#</span></span> |
| <span data-ttu-id="aba89-559">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-559">**Option values**</span></span> | <span data-ttu-id="aba89-560">`true`: se inserta un espacio después de un punto.</span><span class="sxs-lookup"><span data-stu-id="aba89-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="aba89-561">`false`: se quita un espacio después de un punto.</span><span class="sxs-lookup"><span data-stu-id="aba89-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="aba89-562">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="aba89-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="aba89-564">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-564">Property</span></span>|<span data-ttu-id="aba89-565">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-565">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-566">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-566">**Option name**</span></span> | <span data-ttu-id="aba89-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="aba89-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="aba89-568">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-568">**Applicable languages**</span></span> | <span data-ttu-id="aba89-569">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-569">C#</span></span> |
| <span data-ttu-id="aba89-570">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-570">**Option values**</span></span> | <span data-ttu-id="aba89-571">`true`: se inserta un espacio delante de un punto</span><span class="sxs-lookup"><span data-stu-id="aba89-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="aba89-572">`false`: se quita el espacio delante de un punto</span><span class="sxs-lookup"><span data-stu-id="aba89-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="aba89-573">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="aba89-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="aba89-575">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-575">Property</span></span>|<span data-ttu-id="aba89-576">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-576">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-577">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-577">**Option name**</span></span> | <span data-ttu-id="aba89-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="aba89-579">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-579">**Applicable languages**</span></span> | <span data-ttu-id="aba89-580">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-580">C#</span></span> |
| <span data-ttu-id="aba89-581">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-581">**Option values**</span></span> | <span data-ttu-id="aba89-582">`true`: se inserta un espacio detrás de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="aba89-583">`false`: se quita el espacio detrás de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="aba89-584">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

#### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="aba89-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="aba89-586">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-586">Property</span></span>|<span data-ttu-id="aba89-587">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-587">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-588">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-588">**Option name**</span></span> | <span data-ttu-id="aba89-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="aba89-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="aba89-590">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-590">**Applicable languages**</span></span> | <span data-ttu-id="aba89-591">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-591">C#</span></span> |
| <span data-ttu-id="aba89-592">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-592">**Option values**</span></span> | <span data-ttu-id="aba89-593">`true`: se inserta un espacio delante de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="aba89-594">`false`: se quita el espacio delante de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="aba89-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="aba89-595">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="aba89-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="aba89-597">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-597">Property</span></span>|<span data-ttu-id="aba89-598">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-598">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-599">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-599">**Option name**</span></span> | <span data-ttu-id="aba89-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="aba89-601">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-601">**Applicable languages**</span></span> | <span data-ttu-id="aba89-602">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-602">C#</span></span> |
| <span data-ttu-id="aba89-603">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-603">**Option values**</span></span> | <span data-ttu-id="aba89-604">`ignore`: no se quitan caracteres de espacio adicionales de las instrucciones de declaración</span><span class="sxs-lookup"><span data-stu-id="aba89-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="aba89-605">`false`: se quitan caracteres de espacio adicionales de las instrucciones de declaración</span><span class="sxs-lookup"><span data-stu-id="aba89-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="aba89-606">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="aba89-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="aba89-608">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-608">Property</span></span>|<span data-ttu-id="aba89-609">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-609">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-610">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-610">**Option name**</span></span> | <span data-ttu-id="aba89-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="aba89-612">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-612">**Applicable languages**</span></span> | <span data-ttu-id="aba89-613">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-613">C#</span></span> |
| <span data-ttu-id="aba89-614">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-614">**Option values**</span></span> | <span data-ttu-id="aba89-615">`true`: se inserta un espacio delante de los corchetes de apertura `[`</span><span class="sxs-lookup"><span data-stu-id="aba89-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="aba89-616">`false`: se quita el espacio delante de los corchetes de apertura `[`</span><span class="sxs-lookup"><span data-stu-id="aba89-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="aba89-617">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="aba89-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="aba89-619">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-619">Property</span></span>|<span data-ttu-id="aba89-620">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-620">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-621">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-621">**Option name**</span></span> | <span data-ttu-id="aba89-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="aba89-623">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-623">**Applicable languages**</span></span> | <span data-ttu-id="aba89-624">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-624">C#</span></span> |
| <span data-ttu-id="aba89-625">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-625">**Option values**</span></span> | <span data-ttu-id="aba89-626">`true`: se inserta un espacio entre corchetes vacíos `[ ]`</span><span class="sxs-lookup"><span data-stu-id="aba89-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="aba89-627">`false`: se quita el espacio entre corchetes vacíos `[]`</span><span class="sxs-lookup"><span data-stu-id="aba89-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="aba89-628">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="aba89-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="aba89-630">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-630">Property</span></span>|<span data-ttu-id="aba89-631">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-631">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-632">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-632">**Option name**</span></span> | <span data-ttu-id="aba89-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="aba89-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="aba89-634">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-634">**Applicable languages**</span></span> | <span data-ttu-id="aba89-635">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-635">C#</span></span> |
| <span data-ttu-id="aba89-636">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-636">**Option values**</span></span> | <span data-ttu-id="aba89-637">`true`: se insertan caracteres de espacio en corchetes no vacíos `[ 0 ]`</span><span class="sxs-lookup"><span data-stu-id="aba89-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="aba89-638">`false`: se quitan caracteres de espacio en corchetes no vacíos `[0]`</span><span class="sxs-lookup"><span data-stu-id="aba89-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="aba89-639">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="aba89-640">Opciones de encapsulado</span><span class="sxs-lookup"><span data-stu-id="aba89-640">Wrap options</span></span>

<span data-ttu-id="aba89-641">Estas reglas de formato se refieren al uso de líneas individuales frente a líneas separadas para las instrucciones y bloques de código.</span><span class="sxs-lookup"><span data-stu-id="aba89-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="aba89-642">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="aba89-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="aba89-644">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-644">Property</span></span>|<span data-ttu-id="aba89-645">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-645">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-646">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-646">**Option name**</span></span> | <span data-ttu-id="aba89-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="aba89-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="aba89-648">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-648">**Applicable languages**</span></span> | <span data-ttu-id="aba89-649">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-649">C#</span></span> |
| <span data-ttu-id="aba89-650">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-650">**Introduced version**</span></span> | <span data-ttu-id="aba89-651">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-652">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-652">**Option values**</span></span> | <span data-ttu-id="aba89-653">`true`: se dejan las instrucciones y declaraciones de miembros en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="aba89-654">`false`: se dejan las instrucciones y declaraciones de miembros en líneas diferentes.</span><span class="sxs-lookup"><span data-stu-id="aba89-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="aba89-655">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="aba89-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="aba89-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="aba89-657">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-657">Property</span></span>|<span data-ttu-id="aba89-658">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-658">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-659">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-659">**Option name**</span></span> | <span data-ttu-id="aba89-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="aba89-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="aba89-661">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-661">**Applicable languages**</span></span> | <span data-ttu-id="aba89-662">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-662">C#</span></span> |
| <span data-ttu-id="aba89-663">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-663">**Introduced version**</span></span> | <span data-ttu-id="aba89-664">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="aba89-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="aba89-665">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-665">**Option values**</span></span> | <span data-ttu-id="aba89-666">`true`: se deja el bloque de código en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="aba89-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="aba89-667">`false`: se deja el bloque de código en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="aba89-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="aba89-668">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="aba89-669">Opciones de la directiva using</span><span class="sxs-lookup"><span data-stu-id="aba89-669">Using directive options</span></span>

<span data-ttu-id="aba89-670">Esta regla de formato se refiere al uso de directivas using que se colocan dentro y fuera de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="aba89-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="aba89-671">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="aba89-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="aba89-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="aba89-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="aba89-673">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba89-673">Property</span></span>|<span data-ttu-id="aba89-674">Value</span><span class="sxs-lookup"><span data-stu-id="aba89-674">Value</span></span>|
|-|-|
| <span data-ttu-id="aba89-675">**Nombre de la opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-675">**Option name**</span></span> | <span data-ttu-id="aba89-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="aba89-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="aba89-677">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="aba89-677">**Applicable languages**</span></span> | <span data-ttu-id="aba89-678">C#</span><span class="sxs-lookup"><span data-stu-id="aba89-678">C#</span></span> |
| <span data-ttu-id="aba89-679">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="aba89-679">**Introduced version**</span></span> | <span data-ttu-id="aba89-680">Visual Studio 2019, versión 16.1</span><span class="sxs-lookup"><span data-stu-id="aba89-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="aba89-681">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="aba89-681">**Option values**</span></span> | <span data-ttu-id="aba89-682">`outside_namespace`: las directivas using se dejan fuera del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="aba89-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="aba89-683">`inside_namespace`: las directivas using se dejan dentro del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="aba89-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="aba89-684">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="aba89-684">Code examples:</span></span>

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{

}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
}
```

## <a name="see-also"></a><span data-ttu-id="aba89-685">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba89-685">See also</span></span>

- [<span data-ttu-id="aba89-686">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="aba89-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="aba89-687">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="aba89-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="aba89-688">Referencia sobre las reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="aba89-688">.NET code style rules reference</span></span>](index.md)
