---
title: Reglas de formato de estilo de código
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
ms.openlocfilehash: 61e6f6a6afdc6aaf9710eef3143af8ae700ef612
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "96594403"
---
# <a name="formatting-rules"></a><span data-ttu-id="9f870-103">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="9f870-103">Formatting rules</span></span>

<span data-ttu-id="9f870-104">Las reglas de formato afectan a cómo se alinean la sangría, los espacios y las nuevas líneas alrededor de las construcciones del lenguaje de programación .NET.</span><span class="sxs-lookup"><span data-stu-id="9f870-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="9f870-105">Las reglas se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="9f870-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="9f870-106">[Reglas de formato .net](#net-formatting-rules): reglas que se aplican a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f870-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="9f870-107">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `dotnet_` prefijo.</span><span class="sxs-lookup"><span data-stu-id="9f870-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="9f870-108">[Reglas de formato de c#](#c-formatting-rules): reglas que son específicas del lenguaje C# únicamente.</span><span class="sxs-lookup"><span data-stu-id="9f870-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="9f870-109">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `csharp_` prefijo.</span><span class="sxs-lookup"><span data-stu-id="9f870-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="9f870-110">IDENTIFICADOR de regla: "IDE0055" (corregir formato)</span><span class="sxs-lookup"><span data-stu-id="9f870-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="9f870-111">Todas las opciones de formato tienen el identificador `IDE0055` y el título de la regla `Fix formatting` .</span><span class="sxs-lookup"><span data-stu-id="9f870-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="9f870-112">Establezca la gravedad de una infracción de formato en un archivo EditorConfig mediante la siguiente línea de configuración.</span><span class="sxs-lookup"><span data-stu-id="9f870-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="9f870-113">El valor de gravedad debe ser o aplicarse `warning` `error` en la [compilación](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="9f870-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="9f870-114">Para obtener todos los valores de gravedad posibles, consulte [nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="9f870-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="9f870-115">Formato de opción</span><span class="sxs-lookup"><span data-stu-id="9f870-115">Option format</span></span>

<span data-ttu-id="9f870-116">Las opciones de formato de reglas se pueden especificar en un archivo EditorConfig con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="9f870-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="9f870-117">Para muchas reglas, especificará `true` (se prefiere este estilo) o `false` (no se prefiere este estilo) para `value`.</span><span class="sxs-lookup"><span data-stu-id="9f870-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="9f870-118">Para otras reglas, especifique un valor como `flush_left` o `before_and_after` para describir cuándo y dónde aplicar la regla.</span><span class="sxs-lookup"><span data-stu-id="9f870-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="9f870-119">No se especifica un nivel de gravedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="9f870-120">Reglas de formato de .NET</span><span class="sxs-lookup"><span data-stu-id="9f870-120">.NET formatting rules</span></span>

<span data-ttu-id="9f870-121">Las reglas de formato de esta sección se aplican a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f870-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="9f870-122">Organización de instrucciones Using</span><span class="sxs-lookup"><span data-stu-id="9f870-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="9f870-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="9f870-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="9f870-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="9f870-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="9f870-125">Organización de directivas using</span><span class="sxs-lookup"><span data-stu-id="9f870-125">Organize using directives</span></span>

<span data-ttu-id="9f870-126">Estas reglas de formato se refieren a la ordenación y la visualización de directivas `using` y de instrucciones `Imports`.</span><span class="sxs-lookup"><span data-stu-id="9f870-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="9f870-127">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="9f870-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="9f870-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="9f870-129">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-129">Property</span></span>|<span data-ttu-id="9f870-130">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-130">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-131">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-131">**Option name**</span></span> | <span data-ttu-id="9f870-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="9f870-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="9f870-133">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-133">**Applicable languages**</span></span> | <span data-ttu-id="9f870-134">C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f870-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="9f870-135">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-135">**Introduced version**</span></span> | <span data-ttu-id="9f870-136">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-137">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-137">**Option values**</span></span> | <span data-ttu-id="9f870-138">`true` -Ordenar las `System.*` `using` directivas alfabéticamente y colocarlas antes que otras directivas using.</span><span class="sxs-lookup"><span data-stu-id="9f870-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="9f870-139">`false` -No coloque `System.*` `using` Directivas antes de otras `using` directivas.</span><span class="sxs-lookup"><span data-stu-id="9f870-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="9f870-140">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-140">Code examples:</span></span>

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

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="9f870-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="9f870-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="9f870-142">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-142">Property</span></span>|<span data-ttu-id="9f870-143">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-143">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-144">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-144">**Option name**</span></span> | <span data-ttu-id="9f870-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="9f870-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="9f870-146">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-146">**Applicable languages**</span></span> | <span data-ttu-id="9f870-147">C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f870-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="9f870-148">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-148">**Introduced version**</span></span> | <span data-ttu-id="9f870-149">Versión 15.5 de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="9f870-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="9f870-150">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-150">**Option values**</span></span> | <span data-ttu-id="9f870-151">`true`: coloque una línea en blanco entre grupos de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="9f870-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="9f870-152">`false`: no coloque una línea en blanco entre grupos de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="9f870-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="9f870-153">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-153">Code examples:</span></span>

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

## <a name="c-formatting-rules"></a><span data-ttu-id="9f870-154">Reglas de formato de C#</span><span class="sxs-lookup"><span data-stu-id="9f870-154">C# formatting rules</span></span>

<span data-ttu-id="9f870-155">Las reglas de formato de esta sección se aplican únicamente al código de C#.</span><span class="sxs-lookup"><span data-stu-id="9f870-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="9f870-156">Opciones de nueva línea</span><span class="sxs-lookup"><span data-stu-id="9f870-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="9f870-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="9f870-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="9f870-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="9f870-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="9f870-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="9f870-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="9f870-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="9f870-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="9f870-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="9f870-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="9f870-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="9f870-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="9f870-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="9f870-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="9f870-164">Opciones de sangría</span><span class="sxs-lookup"><span data-stu-id="9f870-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="9f870-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="9f870-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="9f870-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="9f870-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="9f870-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="9f870-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="9f870-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="9f870-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="9f870-171">Opciones de espaciado</span><span class="sxs-lookup"><span data-stu-id="9f870-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="9f870-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="9f870-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="9f870-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="9f870-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="9f870-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="9f870-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="9f870-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="9f870-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="9f870-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="9f870-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="9f870-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="9f870-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="9f870-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="9f870-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="9f870-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="9f870-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="9f870-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="9f870-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="9f870-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="9f870-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="9f870-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="9f870-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="9f870-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="9f870-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="9f870-194">Opciones de encapsulado</span><span class="sxs-lookup"><span data-stu-id="9f870-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="9f870-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="9f870-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="9f870-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="9f870-197">Opciones de la directiva using</span><span class="sxs-lookup"><span data-stu-id="9f870-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="9f870-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="9f870-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="9f870-199">Opciones de nueva línea</span><span class="sxs-lookup"><span data-stu-id="9f870-199">New-line options</span></span>

<span data-ttu-id="9f870-200">Estas reglas de formato se refieren al uso de nuevas líneas para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="9f870-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="9f870-201">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-201">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="9f870-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="9f870-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="9f870-203">Esta regla se refiere a si se debe colocar una llave de apertura `{` en la misma línea que el código anterior, o en una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="9f870-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="9f870-204">Para esta regla, se especifica **all**, **none** o uno o varios elementos de código como **methods** o **properties** para definir cuándo se debe aplicar esta regla.</span><span class="sxs-lookup"><span data-stu-id="9f870-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="9f870-205">Para especificar varios elementos de código, sepárelos con una coma (,).</span><span class="sxs-lookup"><span data-stu-id="9f870-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="9f870-206">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-206">Property</span></span>|<span data-ttu-id="9f870-207">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-207">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-208">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-208">**Option name**</span></span> | <span data-ttu-id="9f870-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="9f870-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="9f870-210">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-210">**Applicable languages**</span></span> | <span data-ttu-id="9f870-211">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-211">C#</span></span> |
| <span data-ttu-id="9f870-212">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-212">**Introduced version**</span></span> | <span data-ttu-id="9f870-213">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-214">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-214">**Option values**</span></span> | <span data-ttu-id="9f870-215">`all`: se requiere que las llaves estén en una nueva línea para todas las expresiones (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="9f870-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="9f870-216">`none`: se requiere que las llaves estén en una nueva línea para todas las expresiones ("K&R").</span><span class="sxs-lookup"><span data-stu-id="9f870-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="9f870-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types`: se requiere que las llaves estén en una línea nueva para el elemento de código especificado (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="9f870-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="9f870-218">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-218">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="9f870-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="9f870-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="9f870-220">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-220">Property</span></span>|<span data-ttu-id="9f870-221">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-221">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-222">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-222">**Option name**</span></span> | <span data-ttu-id="9f870-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="9f870-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="9f870-224">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-224">**Applicable languages**</span></span> | <span data-ttu-id="9f870-225">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-225">C#</span></span> |
| <span data-ttu-id="9f870-226">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-226">**Introduced version**</span></span> | <span data-ttu-id="9f870-227">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-228">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-228">**Option values**</span></span> | <span data-ttu-id="9f870-229">`true`: las instrucciones `else` se colocan en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="9f870-230">`false`: las instrucciones `else` se colocan en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="9f870-231">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-231">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="9f870-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="9f870-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="9f870-233">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-233">Property</span></span>|<span data-ttu-id="9f870-234">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-234">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-235">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-235">**Option name**</span></span> | <span data-ttu-id="9f870-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="9f870-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="9f870-237">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-237">**Applicable languages**</span></span> | <span data-ttu-id="9f870-238">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-238">C#</span></span> |
| <span data-ttu-id="9f870-239">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-239">**Introduced version**</span></span> | <span data-ttu-id="9f870-240">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-241">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-241">**Option values**</span></span> | <span data-ttu-id="9f870-242">`true`: las instrucciones `catch` se colocan en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="9f870-243">`false`: las instrucciones `catch` se colocan en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="9f870-244">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-244">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="9f870-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="9f870-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="9f870-246">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-246">Property</span></span>|<span data-ttu-id="9f870-247">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-247">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-248">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-248">**Option name**</span></span> | <span data-ttu-id="9f870-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="9f870-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="9f870-250">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-250">**Applicable languages**</span></span> | <span data-ttu-id="9f870-251">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-251">C#</span></span> |
| <span data-ttu-id="9f870-252">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-252">**Introduced version**</span></span> | <span data-ttu-id="9f870-253">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-254">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-254">**Option values**</span></span> | <span data-ttu-id="9f870-255">`true`: se requiere que las instrucciones `finally` estén en una nueva línea después de la llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="9f870-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="9f870-256">`false`: se requiere que las instrucciones `finally` estén en la misma línea que la llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="9f870-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="9f870-257">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-257">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="9f870-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="9f870-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="9f870-259">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-259">Property</span></span>|<span data-ttu-id="9f870-260">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-260">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-261">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-261">**Option name**</span></span> | <span data-ttu-id="9f870-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="9f870-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="9f870-263">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-263">**Applicable languages**</span></span> | <span data-ttu-id="9f870-264">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-264">C#</span></span> |
| <span data-ttu-id="9f870-265">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-265">**Introduced version**</span></span> | <span data-ttu-id="9f870-266">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-267">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-267">**Option values**</span></span> | <span data-ttu-id="9f870-268">`true`: se requiere que los miembros de inicializadores de objeto estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="9f870-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="9f870-269">`false`: se requiere que los miembros de inicializadores de objeto estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="9f870-270">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-270">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="9f870-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="9f870-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="9f870-272">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-272">Property</span></span>|<span data-ttu-id="9f870-273">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-273">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-274">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-274">**Option name**</span></span> | <span data-ttu-id="9f870-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="9f870-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="9f870-276">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-276">**Applicable languages**</span></span> | <span data-ttu-id="9f870-277">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-277">C#</span></span> |
| <span data-ttu-id="9f870-278">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-278">**Introduced version**</span></span> | <span data-ttu-id="9f870-279">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-280">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-280">**Option values**</span></span> | <span data-ttu-id="9f870-281">`true`: se requiere que los miembros de tipos anónimos estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="9f870-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="9f870-282">`false`: se requiere que los miembros de tipos anónimos estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="9f870-283">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-283">Code examples:</span></span>

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

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="9f870-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="9f870-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="9f870-285">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-285">Property</span></span>|<span data-ttu-id="9f870-286">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-286">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-287">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-287">**Option name**</span></span> | <span data-ttu-id="9f870-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="9f870-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="9f870-289">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-289">**Applicable languages**</span></span> | <span data-ttu-id="9f870-290">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-290">C#</span></span> |
| <span data-ttu-id="9f870-291">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-291">**Introduced version**</span></span> | <span data-ttu-id="9f870-292">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-293">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-293">**Option values**</span></span> | <span data-ttu-id="9f870-294">`true`: se requiere que los elementos de las cláusulas de la expresión de consulta estén en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="9f870-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="9f870-295">`false`: se requiere que los elementos de las cláusulas de la expresión de consulta estén en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="9f870-296">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="9f870-297">Opciones de sangría</span><span class="sxs-lookup"><span data-stu-id="9f870-297">Indentation options</span></span>

<span data-ttu-id="9f870-298">Estas reglas de formato se refieren al uso de la sangría para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="9f870-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="9f870-299">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-299">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="9f870-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="9f870-301">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-301">Property</span></span>|<span data-ttu-id="9f870-302">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-302">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-303">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-303">**Option name**</span></span> | <span data-ttu-id="9f870-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="9f870-305">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-305">**Applicable languages**</span></span> | <span data-ttu-id="9f870-306">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-306">C#</span></span> |
| <span data-ttu-id="9f870-307">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-307">**Introduced version**</span></span> | <span data-ttu-id="9f870-308">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-309">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-309">**Option values**</span></span> | <span data-ttu-id="9f870-310">`true`: aplicar sangría al contenido del caso `switch`.</span><span class="sxs-lookup"><span data-stu-id="9f870-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="9f870-311">`false`: no aplicar sangría al contenido del caso `switch`.</span><span class="sxs-lookup"><span data-stu-id="9f870-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="9f870-312">Cuando esta regla se establece en **true**, i.</span><span class="sxs-lookup"><span data-stu-id="9f870-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="9f870-313">Cuando esta regla se establece en **false**, d.</span><span class="sxs-lookup"><span data-stu-id="9f870-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="9f870-314">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-314">Code examples:</span></span>

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

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="9f870-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="9f870-316">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-316">Property</span></span>|<span data-ttu-id="9f870-317">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-317">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-318">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-318">**Option name**</span></span> | <span data-ttu-id="9f870-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="9f870-320">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-320">**Applicable languages**</span></span> | <span data-ttu-id="9f870-321">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-321">C#</span></span> |
| <span data-ttu-id="9f870-322">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-322">**Introduced version**</span></span> | <span data-ttu-id="9f870-323">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-324">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-324">**Option values**</span></span> | <span data-ttu-id="9f870-325">`true`: aplicar sangría a etiquetas `switch`.</span><span class="sxs-lookup"><span data-stu-id="9f870-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="9f870-326">`false`: no aplicar sangría a etiquetas `switch`.</span><span class="sxs-lookup"><span data-stu-id="9f870-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="9f870-327">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-327">Code examples:</span></span>

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

#### <a name="csharp_indent_labels"></a><span data-ttu-id="9f870-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="9f870-329">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-329">Property</span></span>|<span data-ttu-id="9f870-330">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-330">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-331">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-331">**Option name**</span></span> | <span data-ttu-id="9f870-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="9f870-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="9f870-333">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-333">**Applicable languages**</span></span> | <span data-ttu-id="9f870-334">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-334">C#</span></span> |
| <span data-ttu-id="9f870-335">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-335">**Introduced version**</span></span> | <span data-ttu-id="9f870-336">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-337">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-337">**Option values**</span></span> | <span data-ttu-id="9f870-338">`flush_left`: las etiquetas se colocan en la primera columna de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="9f870-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="9f870-339">`one_less_than_current`: las etiquetas se colocan una sangría menos que el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="9f870-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="9f870-340">`no_change`: las etiquetas se colocan en la misma sangría que el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="9f870-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="9f870-341">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-341">Code examples:</span></span>

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

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="9f870-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="9f870-343">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-343">Property</span></span>|<span data-ttu-id="9f870-344">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-344">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-345">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-345">**Option name**</span></span> | <span data-ttu-id="9f870-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="9f870-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="9f870-347">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-347">**Applicable languages**</span></span> | <span data-ttu-id="9f870-348">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-348">C#</span></span> |
| <span data-ttu-id="9f870-349">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="9f870-350">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-350">Code examples:</span></span>

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

#### <a name="csharp_indent_braces"></a><span data-ttu-id="9f870-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="9f870-351">csharp_indent_braces</span></span>

|<span data-ttu-id="9f870-352">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-352">Property</span></span>|<span data-ttu-id="9f870-353">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-353">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-354">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-354">**Option name**</span></span> | <span data-ttu-id="9f870-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="9f870-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="9f870-356">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-356">**Applicable languages**</span></span> | <span data-ttu-id="9f870-357">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-357">C#</span></span> |
| <span data-ttu-id="9f870-358">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="9f870-359">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-359">Code examples:</span></span>

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

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="9f870-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="9f870-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="9f870-361">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-361">Property</span></span>|<span data-ttu-id="9f870-362">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-362">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-363">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-363">**Option name**</span></span> | <span data-ttu-id="9f870-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="9f870-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="9f870-365">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-365">**Applicable languages**</span></span> | <span data-ttu-id="9f870-366">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-366">C#</span></span> |
| <span data-ttu-id="9f870-367">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="9f870-368">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-368">Code examples:</span></span>

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

### <a name="spacing-options"></a><span data-ttu-id="9f870-369">Opciones de espaciado</span><span class="sxs-lookup"><span data-stu-id="9f870-369">Spacing options</span></span>

<span data-ttu-id="9f870-370">Estas reglas de formato se refieren al uso de caracteres de espacio para dar formato al código.</span><span class="sxs-lookup"><span data-stu-id="9f870-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="9f870-371">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-371">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="9f870-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="9f870-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="9f870-373">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-373">Property</span></span>|<span data-ttu-id="9f870-374">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-374">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-375">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-375">**Option name**</span></span> | <span data-ttu-id="9f870-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="9f870-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="9f870-377">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-377">**Applicable languages**</span></span> | <span data-ttu-id="9f870-378">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-378">C#</span></span> |
| <span data-ttu-id="9f870-379">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-379">**Introduced version**</span></span> | <span data-ttu-id="9f870-380">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-381">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-381">**Option values**</span></span> | <span data-ttu-id="9f870-382">`true`: se inserta un carácter de espacio entre una conversión y el valor</span><span class="sxs-lookup"><span data-stu-id="9f870-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="9f870-383">`false`: se quita el espacio entre la conversión y el valor</span><span class="sxs-lookup"><span data-stu-id="9f870-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="9f870-384">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="9f870-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="9f870-386">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-386">Property</span></span>|<span data-ttu-id="9f870-387">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-387">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-388">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-388">**Option name**</span></span> | <span data-ttu-id="9f870-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="9f870-390">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-390">**Applicable languages**</span></span> | <span data-ttu-id="9f870-391">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-391">C#</span></span> |
| <span data-ttu-id="9f870-392">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-392">**Introduced version**</span></span> | <span data-ttu-id="9f870-393">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-394">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-394">**Option values**</span></span> | <span data-ttu-id="9f870-395">`true`: se inserta un carácter de espacio después de una palabra clave en una instrucción de flujo de control como un bucle `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="9f870-396">`false`: se quita el espacio después de una palabra clave en una instrucción de flujo de control como un bucle `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="9f870-397">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="9f870-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="9f870-399">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-399">Property</span></span>|<span data-ttu-id="9f870-400">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-400">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-401">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-401">**Option name**</span></span> | <span data-ttu-id="9f870-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="9f870-403">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-403">**Applicable languages**</span></span> | <span data-ttu-id="9f870-404">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-404">C#</span></span> |
| <span data-ttu-id="9f870-405">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-405">**Introduced version**</span></span> | <span data-ttu-id="9f870-406">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-407">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-407">**Option values**</span></span> | <span data-ttu-id="9f870-408">`control_flow_statements`: se inserta un espacio entre los paréntesis de instrucciones de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="9f870-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="9f870-409">`expressions`: se inserta un espacio entre los paréntesis de expresiones.</span><span class="sxs-lookup"><span data-stu-id="9f870-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="9f870-410">`type_casts`: se inserta un espacio entre los paréntesis de las conversiones de tipos.</span><span class="sxs-lookup"><span data-stu-id="9f870-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="9f870-411">Si esta regla se omite o si se usa un valor distinto de `control_flow_statements`, `expressions` o `type_casts`, la configuración no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="9f870-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="9f870-412">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="9f870-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="9f870-414">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-414">Property</span></span>|<span data-ttu-id="9f870-415">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-415">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-416">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-416">**Option name**</span></span> | <span data-ttu-id="9f870-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="9f870-418">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-418">**Applicable languages**</span></span> | <span data-ttu-id="9f870-419">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-419">C#</span></span> |
| <span data-ttu-id="9f870-420">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-420">**Introduced version**</span></span> | <span data-ttu-id="9f870-421">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-422">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-422">**Option values**</span></span> | <span data-ttu-id="9f870-423">`true`: se inserta un carácter de espacio antes de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="9f870-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="9f870-424">`false`: se quita el espacio antes de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="9f870-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="9f870-425">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-425">Code examples:</span></span>

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

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="9f870-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="9f870-427">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-427">Property</span></span>|<span data-ttu-id="9f870-428">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-428">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-429">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-429">**Option name**</span></span> | <span data-ttu-id="9f870-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="9f870-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="9f870-431">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-431">**Applicable languages**</span></span> | <span data-ttu-id="9f870-432">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-432">C#</span></span> |
| <span data-ttu-id="9f870-433">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-433">**Introduced version**</span></span> | <span data-ttu-id="9f870-434">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-435">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-435">**Option values**</span></span> | <span data-ttu-id="9f870-436">`true`: se inserta un carácter de espacio después de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="9f870-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="9f870-437">`false`: se quita el espacio después de los dos puntos para las bases o interfaces de una declaración de tipos</span><span class="sxs-lookup"><span data-stu-id="9f870-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="9f870-438">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-438">Code examples:</span></span>

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

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="9f870-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="9f870-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="9f870-440">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-440">Property</span></span>|<span data-ttu-id="9f870-441">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-441">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-442">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-442">**Option name**</span></span> | <span data-ttu-id="9f870-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="9f870-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="9f870-444">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-444">**Applicable languages**</span></span> | <span data-ttu-id="9f870-445">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-445">C#</span></span> |
| <span data-ttu-id="9f870-446">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-446">**Introduced version**</span></span> | <span data-ttu-id="9f870-447">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-448">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-448">**Option values**</span></span> | <span data-ttu-id="9f870-449">`before_and_after`: se inserta un espacio delante y detrás del operador binario.</span><span class="sxs-lookup"><span data-stu-id="9f870-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="9f870-450">`none`: se quitan los espacios delante y detrás del operador binario.</span><span class="sxs-lookup"><span data-stu-id="9f870-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="9f870-451">`ignore`: se omiten los espacios alrededor de operadores binarios,</span><span class="sxs-lookup"><span data-stu-id="9f870-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="9f870-452">Si esta regla se omite o si se usa un valor distinto de `before_and_after`, `none` o `ignore`, la configuración no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="9f870-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="9f870-453">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="9f870-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="9f870-455">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-455">Property</span></span>|<span data-ttu-id="9f870-456">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-456">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-457">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-457">**Option name**</span></span> | <span data-ttu-id="9f870-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="9f870-459">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-459">**Applicable languages**</span></span> | <span data-ttu-id="9f870-460">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-460">C#</span></span> |
| <span data-ttu-id="9f870-461">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-461">**Introduced version**</span></span> | <span data-ttu-id="9f870-462">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-463">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-463">**Option values**</span></span> | <span data-ttu-id="9f870-464">`true`: se coloca un carácter de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una lista de parámetros de declaración de método.</span><span class="sxs-lookup"><span data-stu-id="9f870-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="9f870-465">`false`: se quitan los caracteres de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una lista de parámetros de declaración de método</span><span class="sxs-lookup"><span data-stu-id="9f870-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="9f870-466">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="9f870-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="9f870-468">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-468">Property</span></span>|<span data-ttu-id="9f870-469">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-469">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-470">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-470">**Option name**</span></span> | <span data-ttu-id="9f870-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="9f870-472">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-472">**Applicable languages**</span></span> | <span data-ttu-id="9f870-473">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-473">C#</span></span> |
| <span data-ttu-id="9f870-474">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-474">**Introduced version**</span></span> | <span data-ttu-id="9f870-475">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-476">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-476">**Option values**</span></span> | <span data-ttu-id="9f870-477">`true`: se inserta un espacio dentro de los paréntesis de una lista de parámetros correspondiente a una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="9f870-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="9f870-478">`false`: se quita el espacio dentro de los paréntesis de una lista de parámetros correspondiente a una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="9f870-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="9f870-479">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-479">Code examples:</span></span>

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

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="9f870-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="9f870-481">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-481">Property</span></span>|<span data-ttu-id="9f870-482">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-482">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-483">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-483">**Option name**</span></span> | <span data-ttu-id="9f870-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="9f870-485">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-485">**Applicable languages**</span></span> | <span data-ttu-id="9f870-486">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-486">C#</span></span> |
| <span data-ttu-id="9f870-487">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-487">**Option values**</span></span> | <span data-ttu-id="9f870-488">`true`: se inserta un carácter de espacio entre el nombre del método y el paréntesis de apertura en la declaración de método</span><span class="sxs-lookup"><span data-stu-id="9f870-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="9f870-489">`false`: se quitan los caracteres de espacio entre el nombre del método y el paréntesis de apertura en la declaración de método</span><span class="sxs-lookup"><span data-stu-id="9f870-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="9f870-490">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="9f870-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="9f870-492">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-492">Property</span></span>|<span data-ttu-id="9f870-493">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-493">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-494">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-494">**Option name**</span></span> | <span data-ttu-id="9f870-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="9f870-496">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-496">**Applicable languages**</span></span> | <span data-ttu-id="9f870-497">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-497">C#</span></span> |
| <span data-ttu-id="9f870-498">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-498">**Introduced version**</span></span> | <span data-ttu-id="9f870-499">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-500">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-500">**Option values**</span></span> | <span data-ttu-id="9f870-501">`true`: se coloca un carácter de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="9f870-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="9f870-502">`false`: se quitan los caracteres de espacio después del paréntesis de apertura y antes del paréntesis de cierre de una llamada de método</span><span class="sxs-lookup"><span data-stu-id="9f870-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="9f870-503">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="9f870-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="9f870-505">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-505">Property</span></span>|<span data-ttu-id="9f870-506">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-506">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-507">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-507">**Option name**</span></span> | <span data-ttu-id="9f870-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="9f870-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="9f870-509">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-509">**Applicable languages**</span></span> | <span data-ttu-id="9f870-510">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-510">C#</span></span> |
| <span data-ttu-id="9f870-511">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-511">**Introduced version**</span></span> | <span data-ttu-id="9f870-512">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-513">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-513">**Option values**</span></span> | <span data-ttu-id="9f870-514">`true`: se inserta un espacio entre paréntesis vacíos de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9f870-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="9f870-515">`false`: se quita un espacio entre paréntesis vacíos de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9f870-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="9f870-516">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-516">Code examples:</span></span>

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

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="9f870-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="9f870-518">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-518">Property</span></span>|<span data-ttu-id="9f870-519">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-519">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-520">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-520">**Option name**</span></span> | <span data-ttu-id="9f870-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="9f870-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="9f870-522">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-522">**Applicable languages**</span></span> | <span data-ttu-id="9f870-523">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-523">C#</span></span> |
| <span data-ttu-id="9f870-524">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-524">**Introduced version**</span></span> | <span data-ttu-id="9f870-525">Visual Studio 2017 versión 15.7</span><span class="sxs-lookup"><span data-stu-id="9f870-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="9f870-526">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-526">**Option values**</span></span> | <span data-ttu-id="9f870-527">`true`: se inserta un espacio entre el nombre de la llamada de método y el paréntesis de apertura.</span><span class="sxs-lookup"><span data-stu-id="9f870-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="9f870-528">`false`: se quita un espacio entre el nombre de la llamada de método y el paréntesis de apertura.</span><span class="sxs-lookup"><span data-stu-id="9f870-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="9f870-529">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-529">Code examples:</span></span>

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

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="9f870-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="9f870-531">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-531">Property</span></span>|<span data-ttu-id="9f870-532">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-532">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-533">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-533">**Option name**</span></span> | <span data-ttu-id="9f870-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="9f870-535">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-535">**Applicable languages**</span></span> | <span data-ttu-id="9f870-536">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-536">C#</span></span> |
| <span data-ttu-id="9f870-537">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-537">**Option values**</span></span> | <span data-ttu-id="9f870-538">`true`: se inserta un espacio tras una coma.</span><span class="sxs-lookup"><span data-stu-id="9f870-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="9f870-539">`false`: se quita un espacio después de una coma.</span><span class="sxs-lookup"><span data-stu-id="9f870-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="9f870-540">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="9f870-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="9f870-542">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-542">Property</span></span>|<span data-ttu-id="9f870-543">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-543">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-544">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-544">**Option name**</span></span> | <span data-ttu-id="9f870-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="9f870-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="9f870-546">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-546">**Applicable languages**</span></span> | <span data-ttu-id="9f870-547">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-547">C#</span></span> |
| <span data-ttu-id="9f870-548">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-548">**Option values**</span></span> | <span data-ttu-id="9f870-549">`true`: se inserta un espacio delante de una coma</span><span class="sxs-lookup"><span data-stu-id="9f870-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="9f870-550">`false`: se quita el espacio delante de una coma</span><span class="sxs-lookup"><span data-stu-id="9f870-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="9f870-551">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="9f870-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="9f870-553">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-553">Property</span></span>|<span data-ttu-id="9f870-554">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-554">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-555">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-555">**Option name**</span></span> | <span data-ttu-id="9f870-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="9f870-557">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-557">**Applicable languages**</span></span> | <span data-ttu-id="9f870-558">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-558">C#</span></span> |
| <span data-ttu-id="9f870-559">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-559">**Option values**</span></span> | <span data-ttu-id="9f870-560">`true`: se inserta un espacio después de un punto.</span><span class="sxs-lookup"><span data-stu-id="9f870-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="9f870-561">`false`: se quita un espacio después de un punto.</span><span class="sxs-lookup"><span data-stu-id="9f870-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="9f870-562">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="9f870-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="9f870-564">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-564">Property</span></span>|<span data-ttu-id="9f870-565">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-565">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-566">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-566">**Option name**</span></span> | <span data-ttu-id="9f870-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="9f870-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="9f870-568">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-568">**Applicable languages**</span></span> | <span data-ttu-id="9f870-569">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-569">C#</span></span> |
| <span data-ttu-id="9f870-570">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-570">**Option values**</span></span> | <span data-ttu-id="9f870-571">`true`: se inserta un espacio delante de un punto</span><span class="sxs-lookup"><span data-stu-id="9f870-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="9f870-572">`false`: se quita el espacio delante de un punto</span><span class="sxs-lookup"><span data-stu-id="9f870-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="9f870-573">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="9f870-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="9f870-575">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-575">Property</span></span>|<span data-ttu-id="9f870-576">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-576">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-577">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-577">**Option name**</span></span> | <span data-ttu-id="9f870-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="9f870-579">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-579">**Applicable languages**</span></span> | <span data-ttu-id="9f870-580">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-580">C#</span></span> |
| <span data-ttu-id="9f870-581">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-581">**Option values**</span></span> | <span data-ttu-id="9f870-582">`true`: se inserta un espacio detrás de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="9f870-583">`false`: se quita el espacio detrás de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="9f870-584">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

##### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="9f870-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="9f870-586">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-586">Property</span></span>|<span data-ttu-id="9f870-587">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-587">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-588">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-588">**Option name**</span></span> | <span data-ttu-id="9f870-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="9f870-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="9f870-590">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-590">**Applicable languages**</span></span> | <span data-ttu-id="9f870-591">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-591">C#</span></span> |
| <span data-ttu-id="9f870-592">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-592">**Option values**</span></span> | <span data-ttu-id="9f870-593">`true`: se inserta un espacio delante de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="9f870-594">`false`: se quita el espacio delante de cada punto y coma de una instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="9f870-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="9f870-595">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="9f870-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="9f870-597">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-597">Property</span></span>|<span data-ttu-id="9f870-598">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-598">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-599">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-599">**Option name**</span></span> | <span data-ttu-id="9f870-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="9f870-601">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-601">**Applicable languages**</span></span> | <span data-ttu-id="9f870-602">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-602">C#</span></span> |
| <span data-ttu-id="9f870-603">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-603">**Option values**</span></span> | <span data-ttu-id="9f870-604">`ignore`: no se quitan caracteres de espacio adicionales de las instrucciones de declaración</span><span class="sxs-lookup"><span data-stu-id="9f870-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="9f870-605">`false`: se quitan caracteres de espacio adicionales de las instrucciones de declaración</span><span class="sxs-lookup"><span data-stu-id="9f870-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="9f870-606">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="9f870-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="9f870-608">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-608">Property</span></span>|<span data-ttu-id="9f870-609">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-609">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-610">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-610">**Option name**</span></span> | <span data-ttu-id="9f870-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="9f870-612">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-612">**Applicable languages**</span></span> | <span data-ttu-id="9f870-613">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-613">C#</span></span> |
| <span data-ttu-id="9f870-614">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-614">**Option values**</span></span> | <span data-ttu-id="9f870-615">`true`: se inserta un espacio delante de los corchetes de apertura `[`</span><span class="sxs-lookup"><span data-stu-id="9f870-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="9f870-616">`false`: se quita el espacio delante de los corchetes de apertura `[`</span><span class="sxs-lookup"><span data-stu-id="9f870-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="9f870-617">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="9f870-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="9f870-619">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-619">Property</span></span>|<span data-ttu-id="9f870-620">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-620">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-621">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-621">**Option name**</span></span> | <span data-ttu-id="9f870-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="9f870-623">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-623">**Applicable languages**</span></span> | <span data-ttu-id="9f870-624">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-624">C#</span></span> |
| <span data-ttu-id="9f870-625">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-625">**Option values**</span></span> | <span data-ttu-id="9f870-626">`true`: se inserta un espacio entre corchetes vacíos `[ ]`</span><span class="sxs-lookup"><span data-stu-id="9f870-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="9f870-627">`false`: se quita el espacio entre corchetes vacíos `[]`</span><span class="sxs-lookup"><span data-stu-id="9f870-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="9f870-628">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="9f870-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="9f870-630">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-630">Property</span></span>|<span data-ttu-id="9f870-631">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-631">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-632">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-632">**Option name**</span></span> | <span data-ttu-id="9f870-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="9f870-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="9f870-634">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-634">**Applicable languages**</span></span> | <span data-ttu-id="9f870-635">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-635">C#</span></span> |
| <span data-ttu-id="9f870-636">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-636">**Option values**</span></span> | <span data-ttu-id="9f870-637">`true`: se insertan caracteres de espacio en corchetes no vacíos `[ 0 ]`</span><span class="sxs-lookup"><span data-stu-id="9f870-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="9f870-638">`false`: se quitan caracteres de espacio en corchetes no vacíos `[0]`</span><span class="sxs-lookup"><span data-stu-id="9f870-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="9f870-639">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="9f870-640">Opciones de encapsulado</span><span class="sxs-lookup"><span data-stu-id="9f870-640">Wrap options</span></span>

<span data-ttu-id="9f870-641">Estas reglas de formato se refieren al uso de líneas individuales frente a líneas separadas para las instrucciones y bloques de código.</span><span class="sxs-lookup"><span data-stu-id="9f870-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="9f870-642">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="9f870-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="9f870-644">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-644">Property</span></span>|<span data-ttu-id="9f870-645">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-645">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-646">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-646">**Option name**</span></span> | <span data-ttu-id="9f870-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="9f870-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="9f870-648">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-648">**Applicable languages**</span></span> | <span data-ttu-id="9f870-649">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-649">C#</span></span> |
| <span data-ttu-id="9f870-650">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-650">**Introduced version**</span></span> | <span data-ttu-id="9f870-651">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-652">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-652">**Option values**</span></span> | <span data-ttu-id="9f870-653">`true`: se dejan las instrucciones y declaraciones de miembros en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="9f870-654">`false`: se dejan las instrucciones y declaraciones de miembros en líneas diferentes.</span><span class="sxs-lookup"><span data-stu-id="9f870-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="9f870-655">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="9f870-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="9f870-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="9f870-657">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-657">Property</span></span>|<span data-ttu-id="9f870-658">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-658">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-659">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-659">**Option name**</span></span> | <span data-ttu-id="9f870-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="9f870-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="9f870-661">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-661">**Applicable languages**</span></span> | <span data-ttu-id="9f870-662">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-662">C#</span></span> |
| <span data-ttu-id="9f870-663">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-663">**Introduced version**</span></span> | <span data-ttu-id="9f870-664">Visual Studio 2017 versión 15.3</span><span class="sxs-lookup"><span data-stu-id="9f870-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="9f870-665">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-665">**Option values**</span></span> | <span data-ttu-id="9f870-666">`true`: se deja el bloque de código en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="9f870-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="9f870-667">`false`: se deja el bloque de código en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="9f870-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="9f870-668">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="9f870-669">Opciones de la directiva using</span><span class="sxs-lookup"><span data-stu-id="9f870-669">Using directive options</span></span>

<span data-ttu-id="9f870-670">Esta regla de formato se refiere al uso de directivas using que se colocan dentro y fuera de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9f870-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="9f870-671">Ejemplo del archivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="9f870-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="9f870-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="9f870-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="9f870-673">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f870-673">Property</span></span>|<span data-ttu-id="9f870-674">Valor</span><span class="sxs-lookup"><span data-stu-id="9f870-674">Value</span></span>|
|-|-|
| <span data-ttu-id="9f870-675">**Nombre de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-675">**Option name**</span></span> | <span data-ttu-id="9f870-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="9f870-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="9f870-677">**Lenguajes aplicables**</span><span class="sxs-lookup"><span data-stu-id="9f870-677">**Applicable languages**</span></span> | <span data-ttu-id="9f870-678">C#</span><span class="sxs-lookup"><span data-stu-id="9f870-678">C#</span></span> |
| <span data-ttu-id="9f870-679">**Versión introducida**</span><span class="sxs-lookup"><span data-stu-id="9f870-679">**Introduced version**</span></span> | <span data-ttu-id="9f870-680">Visual Studio 2019, versión 16.1</span><span class="sxs-lookup"><span data-stu-id="9f870-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="9f870-681">**Valores de opción**</span><span class="sxs-lookup"><span data-stu-id="9f870-681">**Option values**</span></span> | <span data-ttu-id="9f870-682">`outside_namespace`: las directivas using se dejan fuera del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9f870-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="9f870-683">`inside_namespace`: las directivas using se dejan dentro del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9f870-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="9f870-684">Ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="9f870-684">Code examples:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9f870-685">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f870-685">See also</span></span>

- [<span data-ttu-id="9f870-686">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="9f870-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="9f870-687">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="9f870-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="9f870-688">Referencia de reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="9f870-688">.NET code style rules reference</span></span>](index.md)
