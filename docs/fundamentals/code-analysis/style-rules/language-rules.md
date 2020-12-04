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
ms.openlocfilehash: b77d9aa2a528a6cf540babd5e5acc148e48c489c
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594743"
---
# <a name="language-rules"></a>Reglas del lenguaje

Las reglas del lenguaje de estilo de código afectan al uso de varias construcciones de lenguajes de programación de .NET, por ejemplo, modificadores y paréntesis. Las reglas se dividen en las siguientes categorías:

- [Reglas de estilo .net](#net-style-rules): reglas que se aplican a C# y Visual Basic. Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `dotnet_style_` prefijo.
- [Reglas de estilo de c#](#c-style-rules): reglas que son específicas del lenguaje c# únicamente. Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `csharp_style_` prefijo.
- [Visual Basic reglas de estilo](#visual-basic-style-rules): reglas que son específicas del lenguaje visual BSIC. Los nombres de las opciones de EditorConfig para estas reglas comienzan con el `visual_basic_style_` prefijo.

## <a name="option-format"></a>Formato de opción

Las opciones de las reglas de idioma se pueden especificar en un archivo EditorConfig con el siguiente formato:

`option_name = value:severity`

- **Valor**: para cada regla de lenguaje, se especifica un valor que define si o Cuándo se prefiere el estilo. Muchas reglas aceptan un valor de `true` (se prefiere este estilo) o `false` (no se prefiere este estilo). Otras reglas aceptan valores como `when_on_single_line` o `never`.
- **Gravedad**: la segunda parte de la regla especifica el [nivel de gravedad](../configuration-options.md#severity-level) de la regla. La especificación de gravedad como parte de la sintaxis de las opciones anteriores solo se respeta dentro de los IDE de desarrollo, como Visual Studio. Los compiladores de C# o VB no entienden este valor, por lo que no se respetan durante la compilación. En su lugar, para aplicar reglas de estilo de código en la compilación, debe establecer la gravedad mediante la sintaxis de configuración de gravedad basada en el identificador de regla para los analizadores. La sintaxis adopta la forma `dotnet_diagnostic.<rule ID>.severity = <severity>`, por ejemplo, `dotnet_diagnostic.IDE0040.severity = silent`. Para obtener más información, vea [este problema de GitHub](https://github.com/dotnet/roslyn/issues/44201).

> [!TIP]
>
> A partir de Visual Studio 2019 16.3, puede configurar reglas de estilo de código desde el menú de bombilla [Acciones rápidas](/visualstudio/ide/quick-actions) después de que se produzca una infracción de estilo. Para obtener más información, vea [configurar automáticamente estilos de código en Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).

## <a name="net-style-rules"></a>Reglas de estilo .NET

Las reglas de estilo de esta sección son aplicables a C# y Visual Basic.

- [calificadores ' this. ' y ' me. '](ide0003-ide0009.md)
  - [dotnet_style_qualification_for_field](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [dotnet_style_qualification_for_property](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [dotnet_style_qualification_for_method](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [dotnet_style_qualification_for_event](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [Palabras clave del lenguaje en lugar de nombres de tipos de marco para referencias de tipo](ide0049.md)
  - [dotnet_style_predefined_type_for_locals_parameters_members](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [dotnet_style_predefined_type_for_member_access](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [Preferencias de modificadores](modifier-preferences.md#net-modifier-preferences)
  - [dotnet_style_require_accessibility_modifiers](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [csharp_preferred_modifier_order](ide0036.md#csharp_preferred_modifier_order)
  - [visual_basic_preferred_modifier_order](ide0036.md#visual_basic_preferred_modifier_order)
  - [dotnet_style_readonly_field](ide0044.md#dotnet_style_readonly_field)
- [Preferencias de paréntesis](ide0047-ide0048.md)
  - [dotnet_style_parentheses_in_arithmetic_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [dotnet_style_parentheses_in_relational_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [dotnet_style_parentheses_in_other_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [dotnet_style_parentheses_in_other_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [Preferencias de nivel de expresión](expression-level-preferences.md#net-expression-level-preferences)
  - [dotnet_style_object_initializer](ide0017.md#dotnet_style_object_initializer)
  - [dotnet_style_collection_initializer](ide0028.md#dotnet_style_collection_initializer)
  - [dotnet_style_explicit_tuple_names](ide0033.md#dotnet_style_explicit_tuple_names)
  - [dotnet_style_prefer_inferred_tuple_names](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [dotnet_style_prefer_inferred_anonymous_type_member_names](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [dotnet_style_prefer_auto_properties](ide0032.md#dotnet_style_prefer_auto_properties)
  - [dotnet_style_prefer_conditional_expression_over_assignment](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [dotnet_style_prefer_conditional_expression_over_return](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [dotnet_style_prefer_compound_assignment](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [dotnet_style_prefer_simplified_interpolation](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [dotnet_style_prefer_simplified_boolean_expressions](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - [Agregar los casos que faltan a la instrucción switch](ide0010.md) : esta regla no tiene ninguna opción de estilo de código.
  - [Convertir tipo anónimo en tupla](ide0050.md) : esta regla no tiene ninguna opción de estilo de código.
  - [Usar ' System. HashCode. Combine '](ide0070.md) : esta regla no tiene ninguna opción de estilo de código.
  - [Convertir ' typeof ' en ' nombre](ide0082.md) de ': esta regla no tiene ninguna opción de estilo de código.
- [Preferencias de la comprobación de NULL](null-checking-preferences.md#net-null-checking-preferences)
  - [dotnet_style_coalesce_expression](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [dotnet_style_null_propagation](ide0031.md#dotnet_style_null_propagation)
  - [dotnet_style_prefer_is_null_check_over_reference_equality_method](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [Preferencias de encabezado de archivo](ide0073.md)
  - [file_header_template](ide0073.md#file_header_template)

## <a name="c-style-rules"></a>Reglas de estilo de C#

Las reglas de estilo de esta sección solo se aplican al lenguaje C#.

- [preferencias de "var"](ide0007-ide0008.md)
  - [csharp_style_var_for_built_in_types](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [csharp_style_var_when_type_is_apparent](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [csharp_style_var_elsewhere](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [Miembros con forma de expresión](expression-bodied-members.md)
  - [csharp_style_expression_bodied_methods](ide0022.md#csharp_style_expression_bodied_methods)
  - [csharp_style_expression_bodied_constructors](ide0021.md#csharp_style_expression_bodied_constructors)
  - [csharp_style_expression_bodied_operators](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [csharp_style_expression_bodied_properties](ide0025.md#csharp_style_expression_bodied_properties)
  - [csharp_style_expression_bodied_indexers](ide0026.md#csharp_style_expression_bodied_indexers)
  - [csharp_style_expression_bodied_accessors](ide0027.md#csharp_style_expression_bodied_accessors)
  - [csharp_style_expression_bodied_lambdas](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [csharp_style_expression_bodied_local_functions](ide0061.md#csharp_style_expression_bodied_local_functions)
- [Preferencias de coincidencia de patrones](pattern-matching-preferences.md)
  - [csharp_style_pattern_matching_over_is_with_cast_check](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [csharp_style_pattern_matching_over_as_with_null_check](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [csharp_style_prefer_switch_expression](ide0066.md#csharp_style_prefer_switch_expression)
  - [csharp_style_prefer_pattern_matching](ide0078.md#csharp_style_prefer_pattern_matching)
  - [csharp_style_prefer_not_pattern](ide0083.md#csharp_style_prefer_not_pattern)
- [Preferencias de nivel de expresión](expression-level-preferences.md#c-expression-level-preferences)
  - [csharp_style_inlined_variable_declaration](ide0018.md#csharp_style_inlined_variable_declaration)
  - [csharp_prefer_simple_default_expression](ide0034.md#csharp_prefer_simple_default_expression)
  - [csharp_style_pattern_local_over_anonymous_function](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [csharp_style_deconstructed_variable_declaration](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [csharp_style_prefer_index_operator](ide0056.md#csharp_style_prefer_index_operator)
  - [csharp_style_prefer_range_operator](ide0057.md#csharp_style_prefer_range_operator)
  - [csharp_style_implicit_object_creation_when_type_is_apparent](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - [Agregar casos que faltan para cambiar expresión](ide0072.md) : esta regla no tiene ninguna opción de estilo de código.
- [Preferencias de la comprobación de "NULL"](null-checking-preferences.md#c-null-checking-preferences)
  - [csharp_style_throw_expression](ide0016.md#csharp_style_throw_expression)
  - [csharp_style_conditional_delegate_call](ide1005.md#csharp_style_conditional_delegate_call)
- [Preferencias de bloques de código](code-block-preferences.md)
  - [csharp_prefer_braces](ide0011.md#csharp_prefer_braces)
  - [csharp_prefer_simple_using_statement](ide0063.md#csharp_prefer_simple_using_statement)
- [preferencias de la Directiva ' Using '](ide0065.md)
  - [csharp_using_directive_placement](ide0065.md#csharp_using_directive_placement)
- [Preferencias de modificadores](modifier-preferences.md#c-modifier-preferences)
  - [csharp_prefer_static_local_function](ide0062.md#csharp_prefer_static_local_function)
  - [Convertir campos de struct en grabable](ide0064.md) : esta regla no tiene ninguna opción de estilo de código.

## <a name="visual-basic-style-rules"></a>Reglas de estilo Visual Basic

Las reglas de estilo de esta sección solo se aplican al lenguaje Visual Basic.

- [Preferencias de coincidencia de patrones](pattern-matching-preferences.md)
  - [visual_basic_style_prefer_isnot_expression](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a>Vea también

- [Reglas de código innecesario](unnecessary-code-rules.md)
- [Reglas de formato](formatting-rules.md)
- [Reglas de nomenclatura](naming-rules.md)
- [Referencia de reglas de estilo de código de .NET](index.md)
