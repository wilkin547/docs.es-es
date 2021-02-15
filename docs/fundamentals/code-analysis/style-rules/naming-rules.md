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
ms.openlocfilehash: df2cbc8299d853b5730bc39eb25c6f97b6575655
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429213"
---
# <a name="naming-rules"></a><span data-ttu-id="e353d-103">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e353d-103">Naming rules</span></span>

<span data-ttu-id="e353d-104">En el `.editorconfig` archivo, puede definir **reglas de nomenclatura** que especifiquen y apliquen cómo se deben asignar nombres a los elementos de código del lenguaje de programación .net, como &mdash; clases, propiedades y métodos &mdash; .</span><span class="sxs-lookup"><span data-stu-id="e353d-104">In your `.editorconfig` file, you can define **naming rules** that specify and enforce how .NET programming language code elements&mdash;such as classes, properties, and methods&mdash;should be named.</span></span> <span data-ttu-id="e353d-105">Por ejemplo, puede especificar que los miembros públicos deben escribirse en mayúsculas o que los campos privados deban comenzar por `_` .</span><span class="sxs-lookup"><span data-stu-id="e353d-105">For example, you can specify that public members must be capitalized, or that private fields must begin with `_`.</span></span>

<span data-ttu-id="e353d-106">Una regla de nomenclatura tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="e353d-106">A naming rule has three components:</span></span>

* <span data-ttu-id="e353d-107">El **grupo de símbolos** al que se aplica la regla, por ejemplo, los miembros públicos o los campos privados.</span><span class="sxs-lookup"><span data-stu-id="e353d-107">The **symbol group** that the rule applies to, for example, public members or private fields.</span></span>
* <span data-ttu-id="e353d-108">**Estilo de nomenclatura** que se va a asociar a la regla, por ejemplo, que el nombre debe escribirse en mayúsculas o empezar por un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="e353d-108">The **naming style** to associate with the rule, for example, that the name must be capitalized or start with an underscore.</span></span>
* <span data-ttu-id="e353d-109">La gravedad para aplicar la Convención.</span><span class="sxs-lookup"><span data-stu-id="e353d-109">The severity for enforcing the convention.</span></span>

<span data-ttu-id="e353d-110">En primer lugar, debe especificar el grupo de símbolos y el estilo de nomenclatura, y asignar un título a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e353d-110">First, you must specify the symbol group and naming style and give each of them a title.</span></span> <span data-ttu-id="e353d-111">A continuación, especifique la regla de nomenclatura, que vincula todo.</span><span class="sxs-lookup"><span data-stu-id="e353d-111">Then you specify the naming rule, which links everything together.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="e353d-112">Sintaxis general</span><span class="sxs-lookup"><span data-stu-id="e353d-112">General syntax</span></span>

<span data-ttu-id="e353d-113">Para definir una regla de nomenclatura, un grupo de símbolos o un estilo de nomenclatura, establezca una o varias propiedades con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="e353d-113">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<kind>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="e353d-114">Cada propiedad solo se debe establecer una vez, pero algunas opciones de configuración permiten varios valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="e353d-114">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="e353d-115">El orden de las propiedades no es importante.</span><span class="sxs-lookup"><span data-stu-id="e353d-115">The order of the properties is not important.</span></span>

### \<kind>

<span data-ttu-id="e353d-116">**\<kind>** Especifica qué tipo de elemento se define &mdash; como regla de nomenclatura, grupo de símbolos o estilo de nomenclatura, &mdash; y debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e353d-116">**\<kind>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="e353d-117">Para establecer una propiedad para</span><span class="sxs-lookup"><span data-stu-id="e353d-117">To set a property for</span></span> | <span data-ttu-id="e353d-118">Usar el \<kind> valor</span><span class="sxs-lookup"><span data-stu-id="e353d-118">Use the \<kind> value</span></span> | <span data-ttu-id="e353d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e353d-119">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="e353d-120">Regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e353d-120">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="e353d-121">Grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="e353d-121">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="e353d-122">Estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e353d-122">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="e353d-123">Cada tipo de &mdash; [regla de nomenclatura](#naming-rule-properties)de definiciones, [grupo de símbolos](#symbol-group-properties)o [estilo de nomenclatura](#naming-style-properties) &mdash; tiene sus propias propiedades compatibles, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e353d-123">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="e353d-124">**\<title>** es un nombre descriptivo que se elige y asocia varios valores de propiedad en una única definición.</span><span class="sxs-lookup"><span data-stu-id="e353d-124">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="e353d-125">Por ejemplo, las siguientes propiedades producen dos definiciones de grupos `interface` de símbolos y `types` , cada una de las cuales tiene dos propiedades establecidas.</span><span class="sxs-lookup"><span data-stu-id="e353d-125">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="e353d-126">Propiedades de la regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e353d-126">Naming rule properties</span></span>

<span data-ttu-id="e353d-127">Todas las propiedades de las reglas de nomenclatura son necesarias para que una regla surta efecto.</span><span class="sxs-lookup"><span data-stu-id="e353d-127">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="e353d-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e353d-128">Property</span></span> | <span data-ttu-id="e353d-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e353d-129">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="e353d-130">Título de un grupo de símbolos; la regla de nomenclatura se aplicará a los símbolos de este grupo</span><span class="sxs-lookup"><span data-stu-id="e353d-130">The title of a symbol group; the naming rule will be applied to the symbols in this group</span></span> |
| `style` | <span data-ttu-id="e353d-131">Título del estilo de nomenclatura que debe asociarse a esta regla.</span><span class="sxs-lookup"><span data-stu-id="e353d-131">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="e353d-132">Establece la gravedad con la que se va a aplicar la regla de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="e353d-132">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="e353d-133">Establezca el valor asociado en uno de los [niveles de gravedad](../configuration-options.md#severity-level)disponibles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e353d-133">Set the associated value to one of the available [severity levels](../configuration-options.md#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="e353d-134">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="e353d-134">**Notes:**</span></span>

1. <span data-ttu-id="e353d-135">La especificación de gravedad dentro de una regla de nomenclatura solo se respeta dentro de los IDE de desarrollo, como Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e353d-135">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="e353d-136">Los compiladores de C# o VB no entienden este valor, por lo que no se respetan durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="e353d-136">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="e353d-137">Para aplicar reglas de estilo de nomenclatura en la compilación, debe establecer la gravedad mediante la [configuración](#rule-id-ide1006-naming-rule-violation)de la gravedad de la regla de código.</span><span class="sxs-lookup"><span data-stu-id="e353d-137">To enforce naming style rules on build, you should instead set the severity by using [code rule severity configuration](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="e353d-138">Para obtener más información, vea [este problema de GitHub](https://github.com/dotnet/roslyn/issues/44201).</span><span class="sxs-lookup"><span data-stu-id="e353d-138">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="e353d-139">Propiedades de grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="e353d-139">Symbol group properties</span></span>

<span data-ttu-id="e353d-140">Puede establecer las siguientes propiedades para los grupos de símbolos, a fin de limitar qué símbolos se incluyen en el grupo.</span><span class="sxs-lookup"><span data-stu-id="e353d-140">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="e353d-141">Para especificar varios valores para una sola propiedad, separe los valores con una coma.</span><span class="sxs-lookup"><span data-stu-id="e353d-141">To specify multiple values for a single property, separate the values with a comma.</span></span>

| <span data-ttu-id="e353d-142">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e353d-142">Property</span></span> | <span data-ttu-id="e353d-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="e353d-143">Description</span></span> | <span data-ttu-id="e353d-144">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="e353d-144">Allowed values</span></span> | <span data-ttu-id="e353d-145">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e353d-145">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="e353d-146">Tipos de símbolos del grupo <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e353d-146">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="e353d-147">`*` (use este valor para especificar todos los símbolos)</span><span class="sxs-lookup"><span data-stu-id="e353d-147">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="e353d-148">Sí</span><span class="sxs-lookup"><span data-stu-id="e353d-148">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="e353d-149">Niveles de accesibilidad de los símbolos del grupo</span><span class="sxs-lookup"><span data-stu-id="e353d-149">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="e353d-150">`*` (use este valor para especificar todos los niveles de accesibilidad)</span><span class="sxs-lookup"><span data-stu-id="e353d-150">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="e353d-151">`internal` o `friend`</span><span class="sxs-lookup"><span data-stu-id="e353d-151">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="e353d-152">`protected_internal` o `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="e353d-152">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="e353d-153">`local` (para los símbolos definidos dentro de un método)</span><span class="sxs-lookup"><span data-stu-id="e353d-153">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="e353d-154">Sí</span><span class="sxs-lookup"><span data-stu-id="e353d-154">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="e353d-155">Solo coinciden los símbolos con _todos_ los modificadores especificados <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e353d-155">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="e353d-156">`abstract` o `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="e353d-156">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="e353d-157">`static` o `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e353d-157">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="e353d-158">No</span><span class="sxs-lookup"><span data-stu-id="e353d-158">No</span></span> |

<span data-ttu-id="e353d-159">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="e353d-159">**Notes:**</span></span>

1. <span data-ttu-id="e353d-160">Los miembros de tupla no se admiten actualmente en `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="e353d-160">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="e353d-161">El grupo de símbolos coincide con _todos_ los modificadores de la `required_modifiers` propiedad.</span><span class="sxs-lookup"><span data-stu-id="e353d-161">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="e353d-162">Si omite esta propiedad, no se requiere ningún modificador específico para una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="e353d-162">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="e353d-163">Esto significa que los modificadores de un símbolo no influyen positiva o negativamente en la aplicación de esta regla.</span><span class="sxs-lookup"><span data-stu-id="e353d-163">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="e353d-164">Si el grupo tiene `static` o `shared` en la `required_modifiers` propiedad, el grupo también incluirá `const` símbolos porque son implícitamente `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="e353d-164">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="e353d-165">Sin embargo, si no desea que la `static` regla de nomenclatura se aplique a los `const` símbolos, puede crear una nueva regla de nomenclatura con un grupo de símbolos de `const` .</span><span class="sxs-lookup"><span data-stu-id="e353d-165">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="e353d-166">Propiedades de estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e353d-166">Naming style properties</span></span>

<span data-ttu-id="e353d-167">Un estilo de nomenclatura define las convenciones que desea aplicar a la regla.</span><span class="sxs-lookup"><span data-stu-id="e353d-167">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="e353d-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e353d-168">For example:</span></span>

* <span data-ttu-id="e353d-169">Poner en mayúsculas `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="e353d-169">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="e353d-170">Empieza por `m_`</span><span class="sxs-lookup"><span data-stu-id="e353d-170">Starts with `m_`</span></span>
* <span data-ttu-id="e353d-171">Termina con `_g`</span><span class="sxs-lookup"><span data-stu-id="e353d-171">Ends with `_g`</span></span>
* <span data-ttu-id="e353d-172">Separar palabras con `__`</span><span class="sxs-lookup"><span data-stu-id="e353d-172">Separate words with `__`</span></span>

<span data-ttu-id="e353d-173">Puede establecer las siguientes propiedades para un estilo de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="e353d-173">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="e353d-174">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e353d-174">Property</span></span> | <span data-ttu-id="e353d-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="e353d-175">Description</span></span> | <span data-ttu-id="e353d-176">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="e353d-176">Allowed values</span></span> | <span data-ttu-id="e353d-177">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e353d-177">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="e353d-178">Estilo de mayúsculas para las palabras del símbolo</span><span class="sxs-lookup"><span data-stu-id="e353d-178">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="e353d-179">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e353d-179">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="e353d-180">Debe comenzar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="e353d-180">Must begin with these characters</span></span> | | <span data-ttu-id="e353d-181">No</span><span class="sxs-lookup"><span data-stu-id="e353d-181">No</span></span> |
| `required_suffix` | <span data-ttu-id="e353d-182">Debe acabar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="e353d-182">Must end with these characters</span></span> | | <span data-ttu-id="e353d-183">No</span><span class="sxs-lookup"><span data-stu-id="e353d-183">No</span></span> |
| `word_separator` | <span data-ttu-id="e353d-184">Las palabras del símbolo deben estar separadas con este carácter</span><span class="sxs-lookup"><span data-stu-id="e353d-184">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="e353d-185">No</span><span class="sxs-lookup"><span data-stu-id="e353d-185">No</span></span> |

<span data-ttu-id="e353d-186">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="e353d-186">**Notes:**</span></span>

1. <span data-ttu-id="e353d-187">Debe especificar un estilo de uso de mayúsculas como parte del estilo de nomenclatura; en caso contrario, es posible que el estilo de nomenclatura se ignore.</span><span class="sxs-lookup"><span data-stu-id="e353d-187">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="rule-order"></a><span data-ttu-id="e353d-188">Orden de las reglas</span><span class="sxs-lookup"><span data-stu-id="e353d-188">Rule order</span></span>

<span data-ttu-id="e353d-189">No importa el orden en el que se definen las reglas de nomenclatura en un archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="e353d-189">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="e353d-190">Las reglas de nomenclatura se ordenan automáticamente según la definición de las propias reglas.</span><span class="sxs-lookup"><span data-stu-id="e353d-190">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="e353d-191">La [extensión de servicio de lenguaje de EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) puede analizar un archivo EditorConfig y notificar los casos en los que el orden de las reglas del archivo es diferente al que va a usar el compilador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e353d-191">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e353d-192">Si utiliza una versión de Visual Studio anterior a la versión 16,2 de Visual Studio 2019, las reglas de nomenclatura deben ordenarse de la más específica a la menos específica en el archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="e353d-192">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="e353d-193">La primera regla encontrada que se puede aplicar es la única que se aplica.</span><span class="sxs-lookup"><span data-stu-id="e353d-193">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="e353d-194">Sin embargo, si hay varias *propiedades* de regla con el mismo nombre, la prioridad la tiene la última propiedad encontrada con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="e353d-194">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="e353d-195">Para más información, consulte [Prioridad y jerarquía de los archivos](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span><span class="sxs-lookup"><span data-stu-id="e353d-195">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="e353d-196">Estilos de nomenclatura predeterminados</span><span class="sxs-lookup"><span data-stu-id="e353d-196">Default naming styles</span></span>

<span data-ttu-id="e353d-197">Si no especifica ninguna regla de nomenclatura personalizada, se usan los siguientes estilos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="e353d-197">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="e353d-198">Para clases, estructuras, enumeraciones, propiedades y eventos con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case.</span><span class="sxs-lookup"><span data-stu-id="e353d-198">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="e353d-199">Para interfaces con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case con el prefijo necesario **l**.</span><span class="sxs-lookup"><span data-stu-id="e353d-199">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="code-rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="e353d-200">IDENTIFICADOR de regla de código: `IDE1006 (Naming rule violation)`</span><span class="sxs-lookup"><span data-stu-id="e353d-200">Code Rule ID: `IDE1006 (Naming rule violation)`</span></span>

<span data-ttu-id="e353d-201">Todas las opciones de nomenclatura tienen el identificador `IDE1006` y el título de la regla `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="e353d-201">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="e353d-202">Puede configurar la gravedad de las infracciones de nomenclatura globalmente en un archivo EditorConfig con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e353d-202">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="e353d-203">El valor de gravedad debe ser o aplicarse `warning` `error` en la [compilación](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="e353d-203">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="e353d-204">Para obtener todos los valores de gravedad posibles, consulte [nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="e353d-204">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="example"></a><span data-ttu-id="e353d-205">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e353d-205">Example</span></span>

<span data-ttu-id="e353d-206">El archivo *.editorconfig* siguiente contiene una convención de nomenclatura que especifica que las propiedades, los métodos, los campos, los eventos y los delegados públicos deben escribirse en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="e353d-206">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="e353d-207">Tenga en cuenta que esta convención de nomenclatura especifica varios tipos de símbolo a los que aplicar la regla, con una coma para separar los valores.</span><span class="sxs-lookup"><span data-stu-id="e353d-207">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e353d-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e353d-208">See also</span></span>

- [<span data-ttu-id="e353d-209">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="e353d-209">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="e353d-210">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="e353d-210">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="e353d-211">Reglas de nomenclatura de Roslyn</span><span class="sxs-lookup"><span data-stu-id="e353d-211">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="e353d-212">Referencia de reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="e353d-212">.NET code style rules reference</span></span>](index.md)
