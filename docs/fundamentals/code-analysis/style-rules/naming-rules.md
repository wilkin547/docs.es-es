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
ms.openlocfilehash: 0eea5e89ac5055a45d9ead14363cc2f2fc574401
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191084"
---
# <a name="naming-rules"></a><span data-ttu-id="fc822-103">Reglas de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fc822-103">Naming rules</span></span>

<span data-ttu-id="fc822-104">Las reglas de nomenclatura se refieren a la denominación de los elementos de código del lenguaje de programación .NET, como clases, propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="fc822-104">Naming rules concern the naming of .NET programming language code elements, such as classes, properties, and methods.</span></span> <span data-ttu-id="fc822-105">Por ejemplo, puede especificar que los miembros públicos deben escribirse en mayúsculas, o que los campos privados deben comenzar por `_`.</span><span class="sxs-lookup"><span data-stu-id="fc822-105">For example, you can specify that public members must be capitalized or that private fields must begin with `_`.</span></span>

<span data-ttu-id="fc822-106">Una regla de nomenclatura tiene tres partes:</span><span class="sxs-lookup"><span data-stu-id="fc822-106">A naming rule has three parts:</span></span>

* <span data-ttu-id="fc822-107">Grupo de símbolos al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="fc822-107">The group of symbols it applies to.</span></span>
* <span data-ttu-id="fc822-108">Estilo de nomenclatura que se va a asociar a la regla.</span><span class="sxs-lookup"><span data-stu-id="fc822-108">The naming style to associate with the rule.</span></span>
* <span data-ttu-id="fc822-109">La gravedad para aplicar la Convención.</span><span class="sxs-lookup"><span data-stu-id="fc822-109">The severity for enforcing the convention.</span></span>

<span data-ttu-id="fc822-110">Las reglas de nomenclatura se definen en un archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="fc822-110">You define naming rules in an EditorConfig file.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="fc822-111">Sintaxis general</span><span class="sxs-lookup"><span data-stu-id="fc822-111">General syntax</span></span>

<span data-ttu-id="fc822-112">Para definir una regla de nomenclatura, un grupo de símbolos o un estilo de nomenclatura, establezca una o varias propiedades con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc822-112">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<prefix>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="fc822-113">Cada propiedad solo se debe establecer una vez, pero algunas opciones de configuración permiten varios valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="fc822-113">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="fc822-114">El orden de las propiedades no es importante.</span><span class="sxs-lookup"><span data-stu-id="fc822-114">The order of the properties is not important.</span></span>

### \<prefix>

<span data-ttu-id="fc822-115">**\<prefix>** Especifica qué tipo de elemento se define &mdash; como regla de nomenclatura, grupo de símbolos o estilo de nomenclatura, &mdash; y debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc822-115">**\<prefix>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="fc822-116">Para establecer una propiedad para</span><span class="sxs-lookup"><span data-stu-id="fc822-116">To set a property for</span></span> | <span data-ttu-id="fc822-117">Usar el prefijo</span><span class="sxs-lookup"><span data-stu-id="fc822-117">Use the prefix</span></span> | <span data-ttu-id="fc822-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc822-118">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="fc822-119">Regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fc822-119">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="fc822-120">Grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="fc822-120">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="fc822-121">Estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fc822-121">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="fc822-122">Cada tipo de &mdash; [regla de nomenclatura](#naming-rule-properties)de definiciones, [grupo de símbolos](#symbol-group-properties)o [estilo de nomenclatura](#naming-style-properties) &mdash; tiene sus propias propiedades compatibles, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fc822-122">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="fc822-123">**\<title>** es un nombre descriptivo que se elige y asocia varios valores de propiedad en una única definición.</span><span class="sxs-lookup"><span data-stu-id="fc822-123">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="fc822-124">Por ejemplo, las siguientes propiedades producen dos definiciones de grupos `interface` de símbolos y `types` , cada una de las cuales tiene dos propiedades establecidas.</span><span class="sxs-lookup"><span data-stu-id="fc822-124">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="fc822-125">Propiedades de la regla de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fc822-125">Naming rule properties</span></span>

<span data-ttu-id="fc822-126">Todas las propiedades de las reglas de nomenclatura son necesarias para que una regla surta efecto.</span><span class="sxs-lookup"><span data-stu-id="fc822-126">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="fc822-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fc822-127">Property</span></span> | <span data-ttu-id="fc822-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc822-128">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="fc822-129">El título del grupo de símbolos, que define los símbolos a los que se debe aplicar esta regla.</span><span class="sxs-lookup"><span data-stu-id="fc822-129">The title of the symbol group, defining the symbols to which this rule should be applied</span></span> |
| `style` | <span data-ttu-id="fc822-130">Título del estilo de nomenclatura que debe asociarse a esta regla.</span><span class="sxs-lookup"><span data-stu-id="fc822-130">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="fc822-131">Establece la gravedad con la que se va a aplicar la regla de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="fc822-131">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="fc822-132">Establezca el valor asociado en uno de los [niveles de gravedad](../configuration-options.md#severity-level)disponibles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc822-132">Set the associated value to one of the available [severity levels](../configuration-options.md#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="fc822-133">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="fc822-133">**Notes:**</span></span>

1. <span data-ttu-id="fc822-134">La especificación de gravedad dentro de una regla de nomenclatura solo se respeta dentro de los IDE de desarrollo, como Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc822-134">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="fc822-135">Los compiladores de C# o VB no entienden este valor, por lo que no se respetan durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="fc822-135">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="fc822-136">En su lugar, para aplicar reglas de estilo de nomenclatura en la compilación, debe establecer la gravedad mediante la configuración de gravedad basada en el identificador de regla, tal como se explica en [esta sección](#rule-id-ide1006-naming-rule-violation).</span><span class="sxs-lookup"><span data-stu-id="fc822-136">Instead, to enforce naming style rules on build, you should set the severity by using the rule ID-based severity configuration as explained in [this section](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="fc822-137">Para obtener más información, vea [este problema de GitHub](https://github.com/dotnet/roslyn/issues/44201).</span><span class="sxs-lookup"><span data-stu-id="fc822-137">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="rule-order"></a><span data-ttu-id="fc822-138">Orden de las reglas</span><span class="sxs-lookup"><span data-stu-id="fc822-138">Rule order</span></span>

<span data-ttu-id="fc822-139">No importa el orden en el que se definen las reglas de nomenclatura en un archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="fc822-139">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="fc822-140">Las reglas de nomenclatura se ordenan automáticamente según la definición de las propias reglas.</span><span class="sxs-lookup"><span data-stu-id="fc822-140">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="fc822-141">La [extensión de servicio de lenguaje de EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) puede analizar un archivo EditorConfig y notificar los casos en los que el orden de las reglas del archivo es diferente al que va a usar el compilador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fc822-141">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="fc822-142">Si utiliza una versión de Visual Studio anterior a la versión 16,2 de Visual Studio 2019, las reglas de nomenclatura deben ordenarse de la más específica a la menos específica en el archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="fc822-142">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="fc822-143">La primera regla encontrada que se puede aplicar es la única que se aplica.</span><span class="sxs-lookup"><span data-stu-id="fc822-143">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="fc822-144">Sin embargo, si hay varias *propiedades* de regla con el mismo nombre, la prioridad la tiene la última propiedad encontrada con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="fc822-144">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="fc822-145">Para más información, consulte [Prioridad y jerarquía de los archivos](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span><span class="sxs-lookup"><span data-stu-id="fc822-145">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="fc822-146">Propiedades de grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="fc822-146">Symbol group properties</span></span>

<span data-ttu-id="fc822-147">Puede establecer las siguientes propiedades para los grupos de símbolos, a fin de limitar qué símbolos se incluyen en el grupo.</span><span class="sxs-lookup"><span data-stu-id="fc822-147">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="fc822-148">Para especificar varios valores en un único valor de propiedad, sepárelos con una coma.</span><span class="sxs-lookup"><span data-stu-id="fc822-148">To specify multiple values in a single property setting, separate them with a comma.</span></span>

| <span data-ttu-id="fc822-149">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fc822-149">Property</span></span> | <span data-ttu-id="fc822-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc822-150">Description</span></span> | <span data-ttu-id="fc822-151">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="fc822-151">Allowed values</span></span> | <span data-ttu-id="fc822-152">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="fc822-152">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="fc822-153">Tipos de símbolos del grupo <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc822-153">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="fc822-154">`*` (use este valor para especificar todos los símbolos)</span><span class="sxs-lookup"><span data-stu-id="fc822-154">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="fc822-155">Sí</span><span class="sxs-lookup"><span data-stu-id="fc822-155">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="fc822-156">Niveles de accesibilidad de los símbolos del grupo</span><span class="sxs-lookup"><span data-stu-id="fc822-156">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="fc822-157">`*` (use este valor para especificar todos los niveles de accesibilidad)</span><span class="sxs-lookup"><span data-stu-id="fc822-157">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="fc822-158">`internal` o `friend`</span><span class="sxs-lookup"><span data-stu-id="fc822-158">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="fc822-159">`protected_internal` o `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="fc822-159">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="fc822-160">`local` (para los símbolos definidos dentro de un método)</span><span class="sxs-lookup"><span data-stu-id="fc822-160">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="fc822-161">Sí</span><span class="sxs-lookup"><span data-stu-id="fc822-161">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="fc822-162">Solo coinciden los símbolos con _todos_ los modificadores especificados <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fc822-162">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="fc822-163">`abstract` o `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="fc822-163">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="fc822-164">`static` o `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="fc822-164">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="fc822-165">No</span><span class="sxs-lookup"><span data-stu-id="fc822-165">No</span></span> |

<span data-ttu-id="fc822-166">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="fc822-166">**Notes:**</span></span>

1. <span data-ttu-id="fc822-167">Los miembros de tupla no se admiten actualmente en `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="fc822-167">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="fc822-168">El grupo de símbolos coincide con _todos_ los modificadores de la `required_modifiers` propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc822-168">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="fc822-169">Si omite esta propiedad, no se requiere ningún modificador específico para una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="fc822-169">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="fc822-170">Esto significa que los modificadores de un símbolo no influyen positiva o negativamente en la aplicación de esta regla.</span><span class="sxs-lookup"><span data-stu-id="fc822-170">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="fc822-171">Si el grupo tiene `static` o `shared` en la `required_modifiers` propiedad, el grupo también incluirá `const` símbolos porque son implícitamente `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="fc822-171">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="fc822-172">Sin embargo, si no desea que la `static` regla de nomenclatura se aplique a los `const` símbolos, puede crear una nueva regla de nomenclatura con un grupo de símbolos de `const` .</span><span class="sxs-lookup"><span data-stu-id="fc822-172">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="fc822-173">Propiedades de estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fc822-173">Naming style properties</span></span>

<span data-ttu-id="fc822-174">Un estilo de nomenclatura define las convenciones que desea aplicar a la regla.</span><span class="sxs-lookup"><span data-stu-id="fc822-174">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="fc822-175">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc822-175">For example:</span></span>

* <span data-ttu-id="fc822-176">Poner en mayúsculas `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="fc822-176">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="fc822-177">Empieza por `m_`</span><span class="sxs-lookup"><span data-stu-id="fc822-177">Starts with `m_`</span></span>
* <span data-ttu-id="fc822-178">Termina con `_g`</span><span class="sxs-lookup"><span data-stu-id="fc822-178">Ends with `_g`</span></span>
* <span data-ttu-id="fc822-179">Separar palabras con `__`</span><span class="sxs-lookup"><span data-stu-id="fc822-179">Separate words with `__`</span></span>

<span data-ttu-id="fc822-180">Puede establecer las siguientes propiedades para un estilo de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="fc822-180">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="fc822-181">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fc822-181">Property</span></span> | <span data-ttu-id="fc822-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc822-182">Description</span></span> | <span data-ttu-id="fc822-183">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="fc822-183">Allowed values</span></span> | <span data-ttu-id="fc822-184">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="fc822-184">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="fc822-185">Estilo de mayúsculas para las palabras del símbolo</span><span class="sxs-lookup"><span data-stu-id="fc822-185">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="fc822-186">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc822-186">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="fc822-187">Debe comenzar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="fc822-187">Must begin with these characters</span></span> | | <span data-ttu-id="fc822-188">No</span><span class="sxs-lookup"><span data-stu-id="fc822-188">No</span></span> |
| `required_suffix` | <span data-ttu-id="fc822-189">Debe acabar con estos caracteres</span><span class="sxs-lookup"><span data-stu-id="fc822-189">Must end with these characters</span></span> | | <span data-ttu-id="fc822-190">No</span><span class="sxs-lookup"><span data-stu-id="fc822-190">No</span></span> |
| `word_separator` | <span data-ttu-id="fc822-191">Las palabras del símbolo deben estar separadas con este carácter</span><span class="sxs-lookup"><span data-stu-id="fc822-191">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="fc822-192">No</span><span class="sxs-lookup"><span data-stu-id="fc822-192">No</span></span> |

<span data-ttu-id="fc822-193">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="fc822-193">**Notes:**</span></span>

1. <span data-ttu-id="fc822-194">Debe especificar un estilo de uso de mayúsculas como parte del estilo de nomenclatura; en caso contrario, es posible que el estilo de nomenclatura se ignore.</span><span class="sxs-lookup"><span data-stu-id="fc822-194">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="fc822-195">Estilos de nomenclatura predeterminados</span><span class="sxs-lookup"><span data-stu-id="fc822-195">Default naming styles</span></span>

<span data-ttu-id="fc822-196">Si no especifica ninguna regla de nomenclatura personalizada, se usan los siguientes estilos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="fc822-196">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="fc822-197">Para clases, estructuras, enumeraciones, propiedades y eventos con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case.</span><span class="sxs-lookup"><span data-stu-id="fc822-197">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="fc822-198">Para interfaces con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case con el prefijo necesario **l**.</span><span class="sxs-lookup"><span data-stu-id="fc822-198">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="example"></a><span data-ttu-id="fc822-199">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc822-199">Example</span></span>

<span data-ttu-id="fc822-200">El archivo *.editorconfig* siguiente contiene una convención de nomenclatura que especifica que las propiedades, los métodos, los campos, los eventos y los delegados públicos deben escribirse en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="fc822-200">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="fc822-201">Tenga en cuenta que esta convención de nomenclatura especifica varios tipos de símbolo a los que aplicar la regla, con una coma para separar los valores.</span><span class="sxs-lookup"><span data-stu-id="fc822-201">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

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

## <a name="rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="fc822-202">IDENTIFICADOR de regla: "IDE1006" (infracción de la regla de nomenclatura)</span><span class="sxs-lookup"><span data-stu-id="fc822-202">Rule ID: "IDE1006" (Naming rule violation)</span></span>

<span data-ttu-id="fc822-203">Todas las opciones de nomenclatura tienen el identificador `IDE1006` y el título de la regla `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="fc822-203">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="fc822-204">Puede configurar la gravedad de las infracciones de nomenclatura globalmente en un archivo EditorConfig con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fc822-204">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="fc822-205">El valor de gravedad debe ser o aplicarse `warning` `error` en la [compilación](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="fc822-205">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="fc822-206">Para obtener todos los valores de gravedad posibles, consulte [nivel de gravedad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="fc822-206">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc822-207">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fc822-207">See also</span></span>

- [<span data-ttu-id="fc822-208">Reglas del lenguaje</span><span class="sxs-lookup"><span data-stu-id="fc822-208">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="fc822-209">Reglas de formato</span><span class="sxs-lookup"><span data-stu-id="fc822-209">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="fc822-210">Reglas de nomenclatura de Roslyn</span><span class="sxs-lookup"><span data-stu-id="fc822-210">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="fc822-211">Referencia de reglas de estilo de código de .NET</span><span class="sxs-lookup"><span data-stu-id="fc822-211">.NET code style rules reference</span></span>](index.md)
