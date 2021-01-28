---
title: Reglas del lenguaje de estilo de código
description: Obtenga información sobre las distintas reglas de estilo de código para utilizar las construcciones de lenguaje C# y Visual Basic.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
- language rules
- EditorConfig language conventions
ms.openlocfilehash: 2aa2261534363f1da6a2109f092e08d210ebd915
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957980"
---
# <a name="language-rules"></a><span data-ttu-id="1176c-103">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="1176c-103">Language rules</span></span>

<span data-ttu-id="1176c-104">Las reglas del lenguaje de estilo de código afectan al uso de varias construcciones de lenguajes de programación de .NET, por ejemplo, modificadores y paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1176c-104">Code style language rules affect how various constructs of .NET programming languages, for example, modifiers and parentheses, are used.</span></span> <span data-ttu-id="1176c-105">Las reglas se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="1176c-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="1176c-106">[Reglas de estilo .net](#net-style-rules): reglas que se aplican a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1176c-106">[.NET style rules](#net-style-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="1176c-107">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `dotnet_style_` prefijo.</span><span class="sxs-lookup"><span data-stu-id="1176c-107">The EditorConfig option names for these rules start with `dotnet_style_` prefix.</span></span>
- <span data-ttu-id="1176c-108">[Reglas de estilo de c#](#c-style-rules): reglas que son específicas del lenguaje c# únicamente.</span><span class="sxs-lookup"><span data-stu-id="1176c-108">[C# style rules](#c-style-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="1176c-109">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `csharp_style_` prefijo.</span><span class="sxs-lookup"><span data-stu-id="1176c-109">The EditorConfig option names for these rules start with `csharp_style_` prefix.</span></span>
- <span data-ttu-id="1176c-110">[Visual Basic reglas de estilo](#visual-basic-style-rules): reglas que son específicas del lenguaje visual BSIC.</span><span class="sxs-lookup"><span data-stu-id="1176c-110">[Visual Basic style rules](#visual-basic-style-rules): Rules that are specific to Visual Bsic language only.</span></span> <span data-ttu-id="1176c-111">Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `visual_basic_style_` prefijo.</span><span class="sxs-lookup"><span data-stu-id="1176c-111">The EditorConfig option names for these rules start with `visual_basic_style_` prefix.</span></span>

## <a name="option-format"></a><span data-ttu-id="1176c-112">Formato de opción</span><span class="sxs-lookup"><span data-stu-id="1176c-112">Option format</span></span>

<span data-ttu-id="1176c-113">Las opciones de las reglas de idioma se pueden especificar en un archivo EditorConfig con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="1176c-113">Options for language rules can be specified in an EditorConfig file with the following format:</span></span>

<span data-ttu-id="1176c-114">`option_name = value` (Visual Studio 2019 versión 16,9 Preview 2 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="1176c-114">`option_name = value` (Visual Studio 2019 version 16.9 Preview 2 and later)</span></span>

<span data-ttu-id="1176c-115">o</span><span class="sxs-lookup"><span data-stu-id="1176c-115">or</span></span>

`option_name = value:severity`

- <span data-ttu-id="1176c-116">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1176c-116">**Value**</span></span>

  <span data-ttu-id="1176c-117">Para cada regla de lenguaje, se especifica un valor que define si o Cuándo se prefiere el estilo.</span><span class="sxs-lookup"><span data-stu-id="1176c-117">For each language rule, you specify a value that defines if or when to prefer the style.</span></span> <span data-ttu-id="1176c-118">Muchas reglas aceptan un valor de `true` (se prefiere este estilo) o `false` (no se prefiere este estilo).</span><span class="sxs-lookup"><span data-stu-id="1176c-118">Many rules accept a value of `true` (prefer this style) or `false` (do not prefer this style).</span></span> <span data-ttu-id="1176c-119">Otras reglas aceptan valores como `when_on_single_line` o `never`.</span><span class="sxs-lookup"><span data-stu-id="1176c-119">Other rules accept values such as `when_on_single_line` or `never`.</span></span>

- <span data-ttu-id="1176c-120">**Gravedad** (opcional en Visual Studio 2019 versión 16,9 Preview 2 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="1176c-120">**Severity** (optional in Visual Studio 2019 version 16.9 Preview 2 and later versions)</span></span>

  <span data-ttu-id="1176c-121">La segunda parte de la regla especifica el [nivel de gravedad](../configuration-options.md#severity-level) de la regla.</span><span class="sxs-lookup"><span data-stu-id="1176c-121">The second part of the rule specifies the [severity level](../configuration-options.md#severity-level) for the rule.</span></span> <span data-ttu-id="1176c-122">Cuando se especifica de esta manera, la configuración de gravedad solo se respeta dentro de los IDE de desarrollo, como Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1176c-122">When specified in this way, the severity setting is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="1176c-123">*No* se respeta durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="1176c-123">It is *not* respected during build.</span></span>

  <span data-ttu-id="1176c-124">Para aplicar reglas de estilo de código en tiempo de compilación, establezca la gravedad usando en su lugar la sintaxis de configuración de gravedad basada en el identificador de regla para los analizadores.</span><span class="sxs-lookup"><span data-stu-id="1176c-124">To enforce code style rules at build time, set the severity by using the rule ID-based severity configuration syntax for analyzers instead.</span></span> <span data-ttu-id="1176c-125">La sintaxis adopta la forma `dotnet_diagnostic.<rule ID>.severity = <severity>`, por ejemplo, `dotnet_diagnostic.IDE0040.severity = silent`.</span><span class="sxs-lookup"><span data-stu-id="1176c-125">The syntax takes the form `dotnet_diagnostic.<rule ID>.severity = <severity>`, for example, `dotnet_diagnostic.IDE0040.severity = silent`.</span></span> <span data-ttu-id="1176c-126">Para obtener más información, consulte [nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="1176c-126">For more information, see [severity level](../configuration-options.md#severity-level).</span></span>

> [!TIP]
>
> <span data-ttu-id="1176c-127">A partir de Visual Studio 2019 16.3, puede configurar reglas de estilo de código desde el menú de bombilla [Acciones rápidas](/visualstudio/ide/quick-actions) después de que se produzca una infracción de estilo.</span><span class="sxs-lookup"><span data-stu-id="1176c-127">Starting in Visual Studio 2019 version 16.3, you can configure code style rules from the [Quick Actions](/visualstudio/ide/quick-actions) light bulb menu after a style violation occurs.</span></span> <span data-ttu-id="1176c-128">Para obtener más información, vea [configurar automáticamente estilos de código en Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1176c-128">For more information, see [Automatically configure code styles in Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).</span></span>

## <a name="net-style-rules"></a><span data-ttu-id="1176c-129">Reglas de estilo .NET</span><span class="sxs-lookup"><span data-stu-id="1176c-129">.NET style rules</span></span>

<span data-ttu-id="1176c-130">Las reglas de estilo de esta sección son aplicables a C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1176c-130">The style rules in this section are applicable to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="1176c-131">calificadores ' this. ' y ' me. '</span><span class="sxs-lookup"><span data-stu-id="1176c-131">'this.' and 'Me.' qualifiers</span></span>](ide0003-ide0009.md)
  - [<span data-ttu-id="1176c-132">dotnet_style_qualification_for_field</span><span class="sxs-lookup"><span data-stu-id="1176c-132">dotnet_style_qualification_for_field</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [<span data-ttu-id="1176c-133">dotnet_style_qualification_for_property</span><span class="sxs-lookup"><span data-stu-id="1176c-133">dotnet_style_qualification_for_property</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [<span data-ttu-id="1176c-134">dotnet_style_qualification_for_method</span><span class="sxs-lookup"><span data-stu-id="1176c-134">dotnet_style_qualification_for_method</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [<span data-ttu-id="1176c-135">dotnet_style_qualification_for_event</span><span class="sxs-lookup"><span data-stu-id="1176c-135">dotnet_style_qualification_for_event</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [<span data-ttu-id="1176c-136">Palabras clave del lenguaje en lugar de nombres de tipos de marco para referencias de tipo</span><span class="sxs-lookup"><span data-stu-id="1176c-136">Language keywords instead of framework type names for type references</span></span>](ide0049.md)
  - [<span data-ttu-id="1176c-137">dotnet_style_predefined_type_for_locals_parameters_members</span><span class="sxs-lookup"><span data-stu-id="1176c-137">dotnet_style_predefined_type_for_locals_parameters_members</span></span>](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [<span data-ttu-id="1176c-138">dotnet_style_predefined_type_for_member_access</span><span class="sxs-lookup"><span data-stu-id="1176c-138">dotnet_style_predefined_type_for_member_access</span></span>](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [<span data-ttu-id="1176c-139">Preferencias de modificadores</span><span class="sxs-lookup"><span data-stu-id="1176c-139">Modifier preferences</span></span>](modifier-preferences.md#net-modifier-preferences)
  - [<span data-ttu-id="1176c-140">dotnet_style_require_accessibility_modifiers</span><span class="sxs-lookup"><span data-stu-id="1176c-140">dotnet_style_require_accessibility_modifiers</span></span>](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [<span data-ttu-id="1176c-141">csharp_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="1176c-141">csharp_preferred_modifier_order</span></span>](ide0036.md#csharp_preferred_modifier_order)
  - [<span data-ttu-id="1176c-142">visual_basic_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="1176c-142">visual_basic_preferred_modifier_order</span></span>](ide0036.md#visual_basic_preferred_modifier_order)
  - [<span data-ttu-id="1176c-143">dotnet_style_readonly_field</span><span class="sxs-lookup"><span data-stu-id="1176c-143">dotnet_style_readonly_field</span></span>](ide0044.md#dotnet_style_readonly_field)
- [<span data-ttu-id="1176c-144">Preferencias de paréntesis</span><span class="sxs-lookup"><span data-stu-id="1176c-144">Parentheses preferences</span></span>](ide0047-ide0048.md)
  - [<span data-ttu-id="1176c-145">dotnet_style_parentheses_in_arithmetic_binary_operators</span><span class="sxs-lookup"><span data-stu-id="1176c-145">dotnet_style_parentheses_in_arithmetic_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [<span data-ttu-id="1176c-146">dotnet_style_parentheses_in_relational_binary_operators</span><span class="sxs-lookup"><span data-stu-id="1176c-146">dotnet_style_parentheses_in_relational_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [<span data-ttu-id="1176c-147">dotnet_style_parentheses_in_other_binary_operators</span><span class="sxs-lookup"><span data-stu-id="1176c-147">dotnet_style_parentheses_in_other_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [<span data-ttu-id="1176c-148">dotnet_style_parentheses_in_other_operators</span><span class="sxs-lookup"><span data-stu-id="1176c-148">dotnet_style_parentheses_in_other_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [<span data-ttu-id="1176c-149">Preferencias de nivel de expresión</span><span class="sxs-lookup"><span data-stu-id="1176c-149">Expression-level preferences</span></span>](expression-level-preferences.md#net-expression-level-preferences)
  - [<span data-ttu-id="1176c-150">dotnet_style_object_initializer</span><span class="sxs-lookup"><span data-stu-id="1176c-150">dotnet_style_object_initializer</span></span>](ide0017.md#dotnet_style_object_initializer)
  - [<span data-ttu-id="1176c-151">dotnet_style_collection_initializer</span><span class="sxs-lookup"><span data-stu-id="1176c-151">dotnet_style_collection_initializer</span></span>](ide0028.md#dotnet_style_collection_initializer)
  - [<span data-ttu-id="1176c-152">dotnet_style_explicit_tuple_names</span><span class="sxs-lookup"><span data-stu-id="1176c-152">dotnet_style_explicit_tuple_names</span></span>](ide0033.md#dotnet_style_explicit_tuple_names)
  - [<span data-ttu-id="1176c-153">dotnet_style_prefer_inferred_tuple_names</span><span class="sxs-lookup"><span data-stu-id="1176c-153">dotnet_style_prefer_inferred_tuple_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [<span data-ttu-id="1176c-154">dotnet_style_prefer_inferred_anonymous_type_member_names</span><span class="sxs-lookup"><span data-stu-id="1176c-154">dotnet_style_prefer_inferred_anonymous_type_member_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [<span data-ttu-id="1176c-155">dotnet_style_prefer_auto_properties</span><span class="sxs-lookup"><span data-stu-id="1176c-155">dotnet_style_prefer_auto_properties</span></span>](ide0032.md#dotnet_style_prefer_auto_properties)
  - [<span data-ttu-id="1176c-156">dotnet_style_prefer_conditional_expression_over_assignment</span><span class="sxs-lookup"><span data-stu-id="1176c-156">dotnet_style_prefer_conditional_expression_over_assignment</span></span>](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [<span data-ttu-id="1176c-157">dotnet_style_prefer_conditional_expression_over_return</span><span class="sxs-lookup"><span data-stu-id="1176c-157">dotnet_style_prefer_conditional_expression_over_return</span></span>](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [<span data-ttu-id="1176c-158">dotnet_style_prefer_compound_assignment</span><span class="sxs-lookup"><span data-stu-id="1176c-158">dotnet_style_prefer_compound_assignment</span></span>](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [<span data-ttu-id="1176c-159">dotnet_style_prefer_simplified_interpolation</span><span class="sxs-lookup"><span data-stu-id="1176c-159">dotnet_style_prefer_simplified_interpolation</span></span>](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [<span data-ttu-id="1176c-160">dotnet_style_prefer_simplified_boolean_expressions</span><span class="sxs-lookup"><span data-stu-id="1176c-160">dotnet_style_prefer_simplified_boolean_expressions</span></span>](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - <span data-ttu-id="1176c-161">[Agregar los casos que faltan a la instrucción switch](ide0010.md) : esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-161">[Add missing cases to switch statement](ide0010.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="1176c-162">[Convertir tipo anónimo en tupla](ide0050.md) : esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-162">[Convert anonymous type to tuple](ide0050.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="1176c-163">[Usar ' System. HashCode. Combine '](ide0070.md) : esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-163">[Use 'System.HashCode.Combine'](ide0070.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="1176c-164">[Convertir ' typeof ' en ' nombre](ide0082.md) de ': esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-164">[Convert 'typeof' to 'nameof'](ide0082.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="1176c-165">Preferencias de la comprobación de NULL</span><span class="sxs-lookup"><span data-stu-id="1176c-165">Null-checking preferences</span></span>](null-checking-preferences.md#net-null-checking-preferences)
  - [<span data-ttu-id="1176c-166">dotnet_style_coalesce_expression</span><span class="sxs-lookup"><span data-stu-id="1176c-166">dotnet_style_coalesce_expression</span></span>](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [<span data-ttu-id="1176c-167">dotnet_style_null_propagation</span><span class="sxs-lookup"><span data-stu-id="1176c-167">dotnet_style_null_propagation</span></span>](ide0031.md#dotnet_style_null_propagation)
  - [<span data-ttu-id="1176c-168">dotnet_style_prefer_is_null_check_over_reference_equality_method</span><span class="sxs-lookup"><span data-stu-id="1176c-168">dotnet_style_prefer_is_null_check_over_reference_equality_method</span></span>](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [<span data-ttu-id="1176c-169">Preferencias de encabezado de archivo</span><span class="sxs-lookup"><span data-stu-id="1176c-169">File header preferences</span></span>](ide0073.md)
  - [<span data-ttu-id="1176c-170">file_header_template</span><span class="sxs-lookup"><span data-stu-id="1176c-170">file_header_template</span></span>](ide0073.md#file_header_template)

## <a name="c-style-rules"></a><span data-ttu-id="1176c-171">Reglas de estilo de C#</span><span class="sxs-lookup"><span data-stu-id="1176c-171">C# style rules</span></span>

<span data-ttu-id="1176c-172">Las reglas de estilo de esta sección solo se aplican al lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="1176c-172">The style rules in this section are applicable to C# language only.</span></span>

- [<span data-ttu-id="1176c-173">preferencias de "var"</span><span class="sxs-lookup"><span data-stu-id="1176c-173">'var' preferences</span></span>](ide0007-ide0008.md)
  - [<span data-ttu-id="1176c-174">csharp_style_var_for_built_in_types</span><span class="sxs-lookup"><span data-stu-id="1176c-174">csharp_style_var_for_built_in_types</span></span>](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [<span data-ttu-id="1176c-175">csharp_style_var_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="1176c-175">csharp_style_var_when_type_is_apparent</span></span>](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [<span data-ttu-id="1176c-176">csharp_style_var_elsewhere</span><span class="sxs-lookup"><span data-stu-id="1176c-176">csharp_style_var_elsewhere</span></span>](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [<span data-ttu-id="1176c-177">Miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="1176c-177">Expression-bodied members</span></span>](expression-bodied-members.md)
  - [<span data-ttu-id="1176c-178">csharp_style_expression_bodied_methods</span><span class="sxs-lookup"><span data-stu-id="1176c-178">csharp_style_expression_bodied_methods</span></span>](ide0022.md#csharp_style_expression_bodied_methods)
  - [<span data-ttu-id="1176c-179">csharp_style_expression_bodied_constructors</span><span class="sxs-lookup"><span data-stu-id="1176c-179">csharp_style_expression_bodied_constructors</span></span>](ide0021.md#csharp_style_expression_bodied_constructors)
  - [<span data-ttu-id="1176c-180">csharp_style_expression_bodied_operators</span><span class="sxs-lookup"><span data-stu-id="1176c-180">csharp_style_expression_bodied_operators</span></span>](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [<span data-ttu-id="1176c-181">csharp_style_expression_bodied_properties</span><span class="sxs-lookup"><span data-stu-id="1176c-181">csharp_style_expression_bodied_properties</span></span>](ide0025.md#csharp_style_expression_bodied_properties)
  - [<span data-ttu-id="1176c-182">csharp_style_expression_bodied_indexers</span><span class="sxs-lookup"><span data-stu-id="1176c-182">csharp_style_expression_bodied_indexers</span></span>](ide0026.md#csharp_style_expression_bodied_indexers)
  - [<span data-ttu-id="1176c-183">csharp_style_expression_bodied_accessors</span><span class="sxs-lookup"><span data-stu-id="1176c-183">csharp_style_expression_bodied_accessors</span></span>](ide0027.md#csharp_style_expression_bodied_accessors)
  - [<span data-ttu-id="1176c-184">csharp_style_expression_bodied_lambdas</span><span class="sxs-lookup"><span data-stu-id="1176c-184">csharp_style_expression_bodied_lambdas</span></span>](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [<span data-ttu-id="1176c-185">csharp_style_expression_bodied_local_functions</span><span class="sxs-lookup"><span data-stu-id="1176c-185">csharp_style_expression_bodied_local_functions</span></span>](ide0061.md#csharp_style_expression_bodied_local_functions)
- [<span data-ttu-id="1176c-186">Preferencias de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="1176c-186">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="1176c-187">csharp_style_pattern_matching_over_is_with_cast_check</span><span class="sxs-lookup"><span data-stu-id="1176c-187">csharp_style_pattern_matching_over_is_with_cast_check</span></span>](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [<span data-ttu-id="1176c-188">csharp_style_pattern_matching_over_as_with_null_check</span><span class="sxs-lookup"><span data-stu-id="1176c-188">csharp_style_pattern_matching_over_as_with_null_check</span></span>](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [<span data-ttu-id="1176c-189">csharp_style_prefer_switch_expression</span><span class="sxs-lookup"><span data-stu-id="1176c-189">csharp_style_prefer_switch_expression</span></span>](ide0066.md#csharp_style_prefer_switch_expression)
  - [<span data-ttu-id="1176c-190">csharp_style_prefer_pattern_matching</span><span class="sxs-lookup"><span data-stu-id="1176c-190">csharp_style_prefer_pattern_matching</span></span>](ide0078.md#csharp_style_prefer_pattern_matching)
  - [<span data-ttu-id="1176c-191">csharp_style_prefer_not_pattern</span><span class="sxs-lookup"><span data-stu-id="1176c-191">csharp_style_prefer_not_pattern</span></span>](ide0083.md#csharp_style_prefer_not_pattern)
- [<span data-ttu-id="1176c-192">Preferencias de nivel de expresión</span><span class="sxs-lookup"><span data-stu-id="1176c-192">Expression-level preferences</span></span>](expression-level-preferences.md#c-expression-level-preferences)
  - [<span data-ttu-id="1176c-193">csharp_style_inlined_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="1176c-193">csharp_style_inlined_variable_declaration</span></span>](ide0018.md#csharp_style_inlined_variable_declaration)
  - [<span data-ttu-id="1176c-194">csharp_prefer_simple_default_expression</span><span class="sxs-lookup"><span data-stu-id="1176c-194">csharp_prefer_simple_default_expression</span></span>](ide0034.md#csharp_prefer_simple_default_expression)
  - [<span data-ttu-id="1176c-195">csharp_style_pattern_local_over_anonymous_function</span><span class="sxs-lookup"><span data-stu-id="1176c-195">csharp_style_pattern_local_over_anonymous_function</span></span>](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [<span data-ttu-id="1176c-196">csharp_style_deconstructed_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="1176c-196">csharp_style_deconstructed_variable_declaration</span></span>](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [<span data-ttu-id="1176c-197">csharp_style_prefer_index_operator</span><span class="sxs-lookup"><span data-stu-id="1176c-197">csharp_style_prefer_index_operator</span></span>](ide0056.md#csharp_style_prefer_index_operator)
  - [<span data-ttu-id="1176c-198">csharp_style_prefer_range_operator</span><span class="sxs-lookup"><span data-stu-id="1176c-198">csharp_style_prefer_range_operator</span></span>](ide0057.md#csharp_style_prefer_range_operator)
  - [<span data-ttu-id="1176c-199">csharp_style_implicit_object_creation_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="1176c-199">csharp_style_implicit_object_creation_when_type_is_apparent</span></span>](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - <span data-ttu-id="1176c-200">[Agregar casos que faltan para cambiar expresión](ide0072.md) : esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-200">[Add missing cases to switch expression](ide0072.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="1176c-201">Preferencias de la comprobación de "NULL"</span><span class="sxs-lookup"><span data-stu-id="1176c-201">"Null" checking preferences</span></span>](null-checking-preferences.md#c-null-checking-preferences)
  - [<span data-ttu-id="1176c-202">csharp_style_throw_expression</span><span class="sxs-lookup"><span data-stu-id="1176c-202">csharp_style_throw_expression</span></span>](ide0016.md#csharp_style_throw_expression)
  - [<span data-ttu-id="1176c-203">csharp_style_conditional_delegate_call</span><span class="sxs-lookup"><span data-stu-id="1176c-203">csharp_style_conditional_delegate_call</span></span>](ide1005.md#csharp_style_conditional_delegate_call)
- [<span data-ttu-id="1176c-204">Preferencias de bloques de código</span><span class="sxs-lookup"><span data-stu-id="1176c-204">Code block preferences</span></span>](code-block-preferences.md)
  - [<span data-ttu-id="1176c-205">csharp_prefer_braces</span><span class="sxs-lookup"><span data-stu-id="1176c-205">csharp_prefer_braces</span></span>](ide0011.md#csharp_prefer_braces)
  - [<span data-ttu-id="1176c-206">csharp_prefer_simple_using_statement</span><span class="sxs-lookup"><span data-stu-id="1176c-206">csharp_prefer_simple_using_statement</span></span>](ide0063.md#csharp_prefer_simple_using_statement)
- [<span data-ttu-id="1176c-207">preferencias de la Directiva ' Using '</span><span class="sxs-lookup"><span data-stu-id="1176c-207">'using' directive preferences</span></span>](ide0065.md)
  - [<span data-ttu-id="1176c-208">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="1176c-208">csharp_using_directive_placement</span></span>](ide0065.md#csharp_using_directive_placement)
- [<span data-ttu-id="1176c-209">Preferencias de modificadores</span><span class="sxs-lookup"><span data-stu-id="1176c-209">Modifier preferences</span></span>](modifier-preferences.md#c-modifier-preferences)
  - [<span data-ttu-id="1176c-210">csharp_prefer_static_local_function</span><span class="sxs-lookup"><span data-stu-id="1176c-210">csharp_prefer_static_local_function</span></span>](ide0062.md#csharp_prefer_static_local_function)
  - <span data-ttu-id="1176c-211">[Convertir campos de struct en grabable](ide0064.md) : esta regla no tiene ninguna opción de estilo de código.</span><span class="sxs-lookup"><span data-stu-id="1176c-211">[Make struct fields writable](ide0064.md) - This rule has no code style option.</span></span>

## <a name="visual-basic-style-rules"></a><span data-ttu-id="1176c-212">Reglas de estilo Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1176c-212">Visual Basic style rules</span></span>

<span data-ttu-id="1176c-213">Las reglas de estilo de esta sección solo se aplican al lenguaje Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1176c-213">The style rules in this section are applicable to Visual Basic language only.</span></span>

- [<span data-ttu-id="1176c-214">Preferencias de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="1176c-214">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="1176c-215">visual_basic_style_prefer_isnot_expression</span><span class="sxs-lookup"><span data-stu-id="1176c-215">visual_basic_style_prefer_isnot_expression</span></span>](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a><span data-ttu-id="1176c-216">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1176c-216">See also</span></span>

- [<span data-ttu-id="1176c-217">Reglas de código innecesario</span><span class="sxs-lookup"><span data-stu-id="1176c-217">Unnecessary code rules</span></span>](unnecessary-code-rules.md)
- [<span data-ttu-id="1176c-218">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="1176c-218">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="1176c-219">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1176c-219">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="1176c-220">Referencia de reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="1176c-220">.NET code style rules reference</span></span>](index.md)
