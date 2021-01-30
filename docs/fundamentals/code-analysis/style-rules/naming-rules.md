---
title: Reglas de nomenclatura de estilo de código
description: Obtenga información sobre las reglas de estilo de código .NET para asignar nombres a los elementos de código.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: 1fce275204b729b4d23729ca432e06a5a249620d
ms.sourcegitcommit: 78eb25647b0c750cd80354ebd6ce83a60668e22c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "99065140"
---
# <a name="naming-rules"></a><span data-ttu-id="0eac6-103">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0eac6-103">Naming rules</span></span>

<span data-ttu-id="0eac6-104">En el `.editorconfig` archivo, puede definir **reglas de nomenclatura** para el modo en que los elementos de código del lenguaje de programación .net &mdash; , como las clases, las propiedades y los métodos, &mdash; deben tener nombre.</span><span class="sxs-lookup"><span data-stu-id="0eac6-104">In your `.editorconfig` file, you can define **naming rules** for how .NET programming language code elements&mdash;such as classes, properties, and methods&mdash;should be named.</span></span> <span data-ttu-id="0eac6-105">Por ejemplo, puede especificar que los miembros públicos deben escribirse en mayúsculas o que los campos privados deban comenzar por `_` .</span><span class="sxs-lookup"><span data-stu-id="0eac6-105">For example, you can specify that public members must be capitalized, or that private fields must begin with `_`.</span></span>

<span data-ttu-id="0eac6-106">Una regla de nomenclatura tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="0eac6-106">A naming rule has three components:</span></span>

* <span data-ttu-id="0eac6-107">El **grupo de símbolos al** que &mdash; se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="0eac6-107">The **symbol group**&mdash;the group of symbols the rule applies to.</span></span>
* <span data-ttu-id="0eac6-108">**Estilo de nomenclatura** que se va a asociar a la regla.</span><span class="sxs-lookup"><span data-stu-id="0eac6-108">The **naming style** to associate with the rule.</span></span>
* <span data-ttu-id="0eac6-109">La gravedad para aplicar la Convención.</span><span class="sxs-lookup"><span data-stu-id="0eac6-109">The severity for enforcing the convention.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="0eac6-110">Sintaxis general</span><span class="sxs-lookup"><span data-stu-id="0eac6-110">General syntax</span></span>

<span data-ttu-id="0eac6-111">Para definir una regla de nomenclatura, un grupo de símbolos o un estilo de nomenclatura, establezca una o varias propiedades con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="0eac6-111">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<kind>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="0eac6-112">Cada propiedad solo se debe establecer una vez, pero algunas opciones de configuración permiten varios valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="0eac6-112">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="0eac6-113">El orden de las propiedades no es importante.</span><span class="sxs-lookup"><span data-stu-id="0eac6-113">The order of the properties is not important.</span></span>

### \<kind>

<span data-ttu-id="0eac6-114">**\<kind>** Especifica qué tipo de elemento se define &mdash; como regla de nomenclatura, grupo de símbolos o estilo de nomenclatura, &mdash; y debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0eac6-114">**\<kind>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="0eac6-115">Para establecer una propiedad para</span><span class="sxs-lookup"><span data-stu-id="0eac6-115">To set a property for</span></span> | <span data-ttu-id="0eac6-116">Usar el \<kind> valor</span><span class="sxs-lookup"><span data-stu-id="0eac6-116">Use the \<kind> value</span></span> | <span data-ttu-id="0eac6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eac6-117">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="0eac6-118">Regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0eac6-118">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="0eac6-119">Grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="0eac6-119">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="0eac6-120">Estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0eac6-120">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="0eac6-121">Cada tipo de &mdash; [regla de nomenclatura](#naming-rule-properties)de definiciones, [grupo de símbolos](#symbol-group-properties)o [estilo de nomenclatura](#naming-style-properties) &mdash; tiene sus propias propiedades compatibles, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0eac6-121">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="0eac6-122">**\<title>** es un nombre descriptivo que se elige y asocia varios valores de propiedad en una única definición.</span><span class="sxs-lookup"><span data-stu-id="0eac6-122">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="0eac6-123">Por ejemplo, las siguientes propiedades producen dos definiciones de grupos `interface` de símbolos y `types` , cada una de las cuales tiene dos propiedades establecidas.</span><span class="sxs-lookup"><span data-stu-id="0eac6-123">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="0eac6-124">Propiedades de la regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0eac6-124">Naming rule properties</span></span>

<span data-ttu-id="0eac6-125">Todas las propiedades de las reglas de nomenclatura son necesarias para que una regla surta efecto.</span><span class="sxs-lookup"><span data-stu-id="0eac6-125">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="0eac6-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="0eac6-126">Property</span></span> | <span data-ttu-id="0eac6-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eac6-127">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="0eac6-128">Título de un grupo de símbolos; la regla de nomenclatura se aplicará a los símbolos de este grupo</span><span class="sxs-lookup"><span data-stu-id="0eac6-128">The title of a symbol group; the naming rule will be applied to the symbols in this group</span></span> |
| `style` | <span data-ttu-id="0eac6-129">Título del estilo de nomenclatura que debe asociarse a esta regla.</span><span class="sxs-lookup"><span data-stu-id="0eac6-129">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="0eac6-130">Establece la gravedad con la que se va a aplicar la regla de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="0eac6-130">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="0eac6-131">Establezca el valor asociado en uno de los [niveles de gravedad](../configuration-options.md#severity-level)disponibles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0eac6-131">Set the associated value to one of the available [severity levels](../configuration-options.md#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="0eac6-132">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="0eac6-132">**Notes:**</span></span>

1. <span data-ttu-id="0eac6-133">La especificación de gravedad dentro de una regla de nomenclatura solo se respeta dentro de los IDE de desarrollo, como Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0eac6-133">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="0eac6-134">Los compiladores de C# o VB no entienden este valor, por lo que no se respetan durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="0eac6-134">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="0eac6-135">Para aplicar reglas de estilo de nomenclatura en la compilación, debe establecer la gravedad mediante la [configuración](#rule-id-ide1006-naming-rule-violation)de la gravedad de la regla de código.</span><span class="sxs-lookup"><span data-stu-id="0eac6-135">To enforce naming style rules on build, you should instead set the severity by using [code rule severity configuration](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="0eac6-136">Para obtener más información, vea [este problema de GitHub](https://github.com/dotnet/roslyn/issues/44201).</span><span class="sxs-lookup"><span data-stu-id="0eac6-136">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="0eac6-137">Propiedades de grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="0eac6-137">Symbol group properties</span></span>

<span data-ttu-id="0eac6-138">Puede establecer las siguientes propiedades para los grupos de símbolos, a fin de limitar qué símbolos se incluyen en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0eac6-138">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="0eac6-139">Para especificar varios valores para una sola propiedad, separe los valores con una coma.</span><span class="sxs-lookup"><span data-stu-id="0eac6-139">To specify multiple values for a single property, separate the values with a comma.</span></span>

| <span data-ttu-id="0eac6-140">Propiedad</span><span class="sxs-lookup"><span data-stu-id="0eac6-140">Property</span></span> | <span data-ttu-id="0eac6-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eac6-141">Description</span></span> | <span data-ttu-id="0eac6-142">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="0eac6-142">Allowed values</span></span> | <span data-ttu-id="0eac6-143">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="0eac6-143">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="0eac6-144">Tipos de símbolos del grupo <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0eac6-144">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="0eac6-145">`*` (use este valor para especificar todos los símbolos)</span><span class="sxs-lookup"><span data-stu-id="0eac6-145">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="0eac6-146">Sí</span><span class="sxs-lookup"><span data-stu-id="0eac6-146">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="0eac6-147">Niveles de accesibilidad de los símbolos del grupo</span><span class="sxs-lookup"><span data-stu-id="0eac6-147">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="0eac6-148">`*` (use este valor para especificar todos los niveles de accesibilidad)</span><span class="sxs-lookup"><span data-stu-id="0eac6-148">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="0eac6-149">`internal` o `friend`</span><span class="sxs-lookup"><span data-stu-id="0eac6-149">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="0eac6-150">`protected_internal` o `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="0eac6-150">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="0eac6-151">`local` (para los símbolos definidos dentro de un método)</span><span class="sxs-lookup"><span data-stu-id="0eac6-151">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="0eac6-152">Sí</span><span class="sxs-lookup"><span data-stu-id="0eac6-152">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="0eac6-153">Solo coinciden los símbolos con _todos_ los modificadores especificados <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0eac6-153">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="0eac6-154">`abstract` o `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="0eac6-154">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="0eac6-155">`static` o `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0eac6-155">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="0eac6-156">No</span><span class="sxs-lookup"><span data-stu-id="0eac6-156">No</span></span> |

<span data-ttu-id="0eac6-157">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="0eac6-157">**Notes:**</span></span>

1. <span data-ttu-id="0eac6-158">Los miembros de tupla no se admiten actualmente en `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="0eac6-158">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="0eac6-159">El grupo de símbolos coincide con _todos_ los modificadores de la `required_modifiers` propiedad.</span><span class="sxs-lookup"><span data-stu-id="0eac6-159">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="0eac6-160">Si omite esta propiedad, no se requiere ningún modificador específico para una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="0eac6-160">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="0eac6-161">Esto significa que los modificadores de un símbolo no influyen positiva o negativamente en la aplicación de esta regla.</span><span class="sxs-lookup"><span data-stu-id="0eac6-161">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="0eac6-162">Si el grupo tiene `static` o `shared` en la `required_modifiers` propiedad, el grupo también incluirá `const` símbolos porque son implícitamente `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="0eac6-162">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="0eac6-163">Sin embargo, si no desea que la `static` regla de nomenclatura se aplique a los `const` símbolos, puede crear una nueva regla de nomenclatura con un grupo de símbolos de `const` .</span><span class="sxs-lookup"><span data-stu-id="0eac6-163">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="0eac6-164">Propiedades de estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0eac6-164">Naming style properties</span></span>

<span data-ttu-id="0eac6-165">Un estilo de nomenclatura define las convenciones que desea aplicar a la regla.</span><span class="sxs-lookup"><span data-stu-id="0eac6-165">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="0eac6-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0eac6-166">For example:</span></span>

* <span data-ttu-id="0eac6-167">Poner en mayúsculas `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="0eac6-167">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="0eac6-168">Empieza por `m_`</span><span class="sxs-lookup"><span data-stu-id="0eac6-168">Starts with `m_`</span></span>
* <span data-ttu-id="0eac6-169">Termina con `_g`</span><span class="sxs-lookup"><span data-stu-id="0eac6-169">Ends with `_g`</span></span>
* <span data-ttu-id="0eac6-170">Separar palabras con `__`</span><span class="sxs-lookup"><span data-stu-id="0eac6-170">Separate words with `__`</span></span>

<span data-ttu-id="0eac6-171">Puede establecer las siguientes propiedades para un estilo de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="0eac6-171">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="0eac6-172">Propiedad</span><span class="sxs-lookup"><span data-stu-id="0eac6-172">Property</span></span> | <span data-ttu-id="0eac6-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eac6-173">Description</span></span> | <span data-ttu-id="0eac6-174">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="0eac6-174">Allowed values</span></span> | <span data-ttu-id="0eac6-175">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="0eac6-175">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="0eac6-176">Estilo de mayúsculas para las palabras del símbolo</span><span class="sxs-lookup"><span data-stu-id="0eac6-176">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="0eac6-177">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0eac6-177">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="0eac6-178">Debe comenzar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="0eac6-178">Must begin with these characters</span></span> | | <span data-ttu-id="0eac6-179">No</span><span class="sxs-lookup"><span data-stu-id="0eac6-179">No</span></span> |
| `required_suffix` | <span data-ttu-id="0eac6-180">Debe acabar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="0eac6-180">Must end with these characters</span></span> | | <span data-ttu-id="0eac6-181">No</span><span class="sxs-lookup"><span data-stu-id="0eac6-181">No</span></span> |
| `word_separator` | <span data-ttu-id="0eac6-182">Las palabras del símbolo deben estar separadas con este carácter</span><span class="sxs-lookup"><span data-stu-id="0eac6-182">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="0eac6-183">No</span><span class="sxs-lookup"><span data-stu-id="0eac6-183">No</span></span> |

<span data-ttu-id="0eac6-184">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="0eac6-184">**Notes:**</span></span>

1. <span data-ttu-id="0eac6-185">Debe especificar un estilo de uso de mayúsculas como parte del estilo de nomenclatura; en caso contrario, es posible que el estilo de nomenclatura se ignore.</span><span class="sxs-lookup"><span data-stu-id="0eac6-185">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="rule-order"></a><span data-ttu-id="0eac6-186">Orden de las reglas</span><span class="sxs-lookup"><span data-stu-id="0eac6-186">Rule order</span></span>

<span data-ttu-id="0eac6-187">No importa el orden en el que se definen las reglas de nomenclatura en un archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="0eac6-187">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="0eac6-188">Las reglas de nomenclatura se ordenan automáticamente según la definición de las propias reglas.</span><span class="sxs-lookup"><span data-stu-id="0eac6-188">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="0eac6-189">La [extensión de servicio de lenguaje de EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) puede analizar un archivo EditorConfig y notificar los casos en los que el orden de las reglas del archivo es diferente al que va a usar el compilador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0eac6-189">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="0eac6-190">Si utiliza una versión de Visual Studio anterior a la versión 16,2 de Visual Studio 2019, las reglas de nomenclatura deben ordenarse de la más específica a la menos específica en el archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="0eac6-190">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="0eac6-191">La primera regla encontrada que se puede aplicar es la única que se aplica.</span><span class="sxs-lookup"><span data-stu-id="0eac6-191">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="0eac6-192">Sin embargo, si hay varias *propiedades* de regla con el mismo nombre, la prioridad la tiene la última propiedad encontrada con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="0eac6-192">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="0eac6-193">Para más información, consulte [Prioridad y jerarquía de los archivos](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span><span class="sxs-lookup"><span data-stu-id="0eac6-193">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="0eac6-194">Estilos de nomenclatura predeterminados</span><span class="sxs-lookup"><span data-stu-id="0eac6-194">Default naming styles</span></span>

<span data-ttu-id="0eac6-195">Si no especifica ninguna regla de nomenclatura personalizada, se usan los siguientes estilos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="0eac6-195">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="0eac6-196">Para clases, estructuras, enumeraciones, propiedades y eventos con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case.</span><span class="sxs-lookup"><span data-stu-id="0eac6-196">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="0eac6-197">Para interfaces con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case con el prefijo necesario **l**.</span><span class="sxs-lookup"><span data-stu-id="0eac6-197">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="code-rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="0eac6-198">IDENTIFICADOR de regla de código: `IDE1006 (Naming rule violation)`</span><span class="sxs-lookup"><span data-stu-id="0eac6-198">Code Rule ID: `IDE1006 (Naming rule violation)`</span></span>

<span data-ttu-id="0eac6-199">Todas las opciones de nomenclatura tienen el identificador `IDE1006` y el título de la regla `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="0eac6-199">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="0eac6-200">Puede configurar la gravedad de las infracciones de nomenclatura globalmente en un archivo EditorConfig con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0eac6-200">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="0eac6-201">El valor de gravedad debe ser o aplicarse `warning` `error` en la [compilación](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="0eac6-201">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="0eac6-202">Para obtener todos los valores de gravedad posibles, consulte [nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="0eac6-202">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="example"></a><span data-ttu-id="0eac6-203">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eac6-203">Example</span></span>

<span data-ttu-id="0eac6-204">El archivo *.editorconfig* siguiente contiene una convención de nomenclatura que especifica que las propiedades, los métodos, los campos, los eventos y los delegados públicos deben escribirse en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="0eac6-204">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="0eac6-205">Tenga en cuenta que esta convención de nomenclatura especifica varios tipos de símbolo a los que aplicar la regla, con una coma para separar los valores.</span><span class="sxs-lookup"><span data-stu-id="0eac6-205">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="see-also"></a><span data-ttu-id="0eac6-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eac6-206">See also</span></span>

- [<span data-ttu-id="0eac6-207">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="0eac6-207">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="0eac6-208">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="0eac6-208">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="0eac6-209">Reglas de nomenclatura de Roslyn</span><span class="sxs-lookup"><span data-stu-id="0eac6-209">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="0eac6-210">Referencia de reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="0eac6-210">.NET code style rules reference</span></span>](index.md)
