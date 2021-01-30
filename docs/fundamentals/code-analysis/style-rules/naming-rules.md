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
# <a name="naming-rules"></a>Reglas de nomenclatura

En el `.editorconfig` archivo, puede definir **reglas de nomenclatura** para el modo en que los elementos de código del lenguaje de programación .net &mdash; , como las clases, las propiedades y los métodos, &mdash; deben tener nombre. Por ejemplo, puede especificar que los miembros públicos deben escribirse en mayúsculas o que los campos privados deban comenzar por `_` .

Una regla de nomenclatura tiene tres componentes:

* El **grupo de símbolos al** que &mdash; se aplica la regla.
* **Estilo de nomenclatura** que se va a asociar a la regla.
* La gravedad para aplicar la Convención.

## <a name="general-syntax"></a>Sintaxis general

Para definir una regla de nomenclatura, un grupo de símbolos o un estilo de nomenclatura, establezca una o varias propiedades con la sintaxis siguiente:

```ini
<kind>.<title>.<propertyName> = <propertyValue>
```

Cada propiedad solo se debe establecer una vez, pero algunas opciones de configuración permiten varios valores separados por comas.

El orden de las propiedades no es importante.

### \<kind>

**\<kind>** Especifica qué tipo de elemento se define &mdash; como regla de nomenclatura, grupo de símbolos o estilo de nomenclatura, &mdash; y debe ser uno de los siguientes:

| Para establecer una propiedad para | Usar el \<kind> valor | Ejemplo |
| --- | --- | -- |
| Regla de nomenclatura | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| Grupo de símbolos | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| Estilo de nomenclatura | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

Cada tipo de &mdash; [regla de nomenclatura](#naming-rule-properties)de definiciones, [grupo de símbolos](#symbol-group-properties)o [estilo de nomenclatura](#naming-style-properties) &mdash; tiene sus propias propiedades compatibles, tal y como se describe en las secciones siguientes.

### \<title>

**\<title>** es un nombre descriptivo que se elige y asocia varios valores de propiedad en una única definición. Por ejemplo, las siguientes propiedades producen dos definiciones de grupos `interface` de símbolos y `types` , cada una de las cuales tiene dos propiedades establecidas.

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a>Propiedades de la regla de nomenclatura

Todas las propiedades de las reglas de nomenclatura son necesarias para que una regla surta efecto.

| Propiedad | Descripción |
| -- | -- |
| `symbols` | Título de un grupo de símbolos; la regla de nomenclatura se aplicará a los símbolos de este grupo |
| `style` | Título del estilo de nomenclatura que debe asociarse a esta regla. |
| `severity` |  Establece la gravedad con la que se va a aplicar la regla de nomenclatura. Establezca el valor asociado en uno de los [niveles de gravedad](../configuration-options.md#severity-level)disponibles. <sup>1</sup> |

**Notas:**

1. La especificación de gravedad dentro de una regla de nomenclatura solo se respeta dentro de los IDE de desarrollo, como Visual Studio. Los compiladores de C# o VB no entienden este valor, por lo que no se respetan durante la compilación. Para aplicar reglas de estilo de nomenclatura en la compilación, debe establecer la gravedad mediante la [configuración](#rule-id-ide1006-naming-rule-violation)de la gravedad de la regla de código. Para obtener más información, vea [este problema de GitHub](https://github.com/dotnet/roslyn/issues/44201).

## <a name="symbol-group-properties"></a>Propiedades de grupo de símbolos

Puede establecer las siguientes propiedades para los grupos de símbolos, a fin de limitar qué símbolos se incluyen en el grupo. Para especificar varios valores para una sola propiedad, separe los valores con una coma.

| Propiedad | Descripción | Valores permitidos | Obligatorio |
| -- | -- | -- | -- |
| `applicable_kinds` | Tipos de símbolos del grupo <sup>1</sup> | `*` (use este valor para especificar todos los símbolos)<br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | Sí |
| `applicable_accessibilities` | Niveles de accesibilidad de los símbolos del grupo | `*` (use este valor para especificar todos los niveles de accesibilidad)<br/>`public`<br/>`internal` o `friend`<br/>`private`<br/>`protected`<br/>`protected_internal` o `protected_friend`<br/>`private_protected`<br/>`local` (para los símbolos definidos dentro de un método) | Sí |
| `required_modifiers` | Solo coinciden los símbolos con _todos_ los modificadores especificados <sup>2</sup> | `abstract` o `must_inherit`<br/>`async`<br/>`const`<br/>`readonly`<br/>`static` o `shared` <sup>3</sup> | No |

**Notas:**

1. Los miembros de tupla no se admiten actualmente en `applicable_kinds` .
2. El grupo de símbolos coincide con _todos_ los modificadores de la `required_modifiers` propiedad.  Si omite esta propiedad, no se requiere ningún modificador específico para una coincidencia. Esto significa que los modificadores de un símbolo no influyen positiva o negativamente en la aplicación de esta regla.
3. Si el grupo tiene `static` o `shared` en la `required_modifiers` propiedad, el grupo también incluirá `const` símbolos porque son implícitamente `static` / `Shared` . Sin embargo, si no desea que la `static` regla de nomenclatura se aplique a los `const` símbolos, puede crear una nueva regla de nomenclatura con un grupo de símbolos de `const` .

## <a name="naming-style-properties"></a>Propiedades de estilo de nomenclatura

Un estilo de nomenclatura define las convenciones que desea aplicar a la regla. Por ejemplo:

* Poner en mayúsculas `PascalCase`
* Empieza por `m_`
* Termina con `_g`
* Separar palabras con `__`

Puede establecer las siguientes propiedades para un estilo de nomenclatura:

| Propiedad | Descripción | Valores permitidos | Obligatorio |
| -- | -- | -- | -- |
| `capitalization` | Estilo de mayúsculas para las palabras del símbolo | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | Sí<sup>1</sup> |
| `required_prefix` | Debe comenzar con estos caracteres | | No |
| `required_suffix` | Debe acabar con estos caracteres | | No |
| `word_separator` | Las palabras del símbolo deben estar separadas con este carácter | | No |

**Notas:**

1. Debe especificar un estilo de uso de mayúsculas como parte del estilo de nomenclatura; en caso contrario, es posible que el estilo de nomenclatura se ignore.

## <a name="rule-order"></a>Orden de las reglas

No importa el orden en el que se definen las reglas de nomenclatura en un archivo EditorConfig. Las reglas de nomenclatura se ordenan automáticamente según la definición de las propias reglas. La [extensión de servicio de lenguaje de EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) puede analizar un archivo EditorConfig y notificar los casos en los que el orden de las reglas del archivo es diferente al que va a usar el compilador en tiempo de ejecución.

> [!NOTE]
>
> Si utiliza una versión de Visual Studio anterior a la versión 16,2 de Visual Studio 2019, las reglas de nomenclatura deben ordenarse de la más específica a la menos específica en el archivo EditorConfig. La primera regla encontrada que se puede aplicar es la única que se aplica. Sin embargo, si hay varias *propiedades* de regla con el mismo nombre, la prioridad la tiene la última propiedad encontrada con ese nombre. Para más información, consulte [Prioridad y jerarquía de los archivos](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).

## <a name="default-naming-styles"></a>Estilos de nomenclatura predeterminados

Si no especifica ninguna regla de nomenclatura personalizada, se usan los siguientes estilos predeterminados:

- Para clases, estructuras, enumeraciones, propiedades y eventos con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case.

- Para interfaces con accesibilidad `public`, `private`, `internal`, `protected` o `protected_internal`, el estilo de nomenclatura predeterminado es Pascal Case con el prefijo necesario **l**.

## <a name="code-rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a>IDENTIFICADOR de regla de código: `IDE1006 (Naming rule violation)`

Todas las opciones de nomenclatura tienen el identificador `IDE1006` y el título de la regla `Naming rule violation` . Puede configurar la gravedad de las infracciones de nomenclatura globalmente en un archivo EditorConfig con la siguiente sintaxis:

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

El valor de gravedad debe ser o aplicarse `warning` `error` en la [compilación](../overview.md#code-style-analysis). Para obtener todos los valores de gravedad posibles, consulte [nivel de gravedad](../configuration-options.md#severity-level).

## <a name="example"></a>Ejemplo

El archivo *.editorconfig* siguiente contiene una convención de nomenclatura que especifica que las propiedades, los métodos, los campos, los eventos y los delegados públicos deben escribirse en mayúsculas. Tenga en cuenta que esta convención de nomenclatura especifica varios tipos de símbolo a los que aplicar la regla, con una coma para separar los valores.

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

## <a name="see-also"></a>Vea también

- [Reglas del lenguaje](language-rules.md)
- [Reglas de formato](formatting-rules.md)
- [Reglas de nomenclatura de Roslyn](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [Referencia de reglas de estilo de código de .NET](index.md)
