---
title: 'Tipos de enumeración: referencia de C#'
description: Aprenda sobre los tipos de enumeración de C# que representan una opción o una combinación de opciones.
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 617c5ec037ad7a47b43cca2c13da4a77aa682997
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739083"
---
# <a name="enumeration-types-c-reference"></a>Tipos de enumeración (referencia de C#)

Un *tipo de enumeración* es un [tipo de valor](value-types.md) definido por un conjunto de constantes con nombre del tipo [numérico integral](integral-numeric-types.md) subyacente. Para definir un tipo de enumeración, use la palabra clave `enum` y especifique los nombres de *miembros de enumeración*:

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

De forma predeterminada, los valores de constante asociados de miembros de enumeración son del tipo `int`; comienzan con cero y aumentan en uno después del orden del texto de la definición. Puede especificar explícitamente cualquier otro tipo de [numérico entero](integral-numeric-types.md) como un tipo subyacente de un tipo de enumeración. También puede especificar explícitamente los valores de constante asociados, como se muestra en el ejemplo siguiente:

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

No se puede definir un método dentro de la definición de un tipo de enumeración. Para agregar funcionalidad a un tipo de enumeración, cree un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).

El valor predeterminado de un tipo de enumeración `E` es el valor generado por la expresión `(E)0`, incluso si cero no tiene el miembro de enumeración correspondiente.

Un tipo de enumeración se usa para representar una opción de un conjunto de valores mutuamente excluyentes o una combinación de opciones. Para representar una combinación de opciones, defina un tipo de enumeración como marcas de bits.

## <a name="enumeration-types-as-bit-flags"></a>Tipos de enumeración como marcas de bits

Si quiere que un tipo de enumeración represente una combinación de opciones, defina los miembros de enumeración de esas opciones de modo que una opción individual sea un campo de bits. Es decir, los valores asociados de esos miembros de enumeración deben ser las potencias de dos. Luego, puede usar los [operadores lógicos bit a bit`|` o `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) para combinar o formar intersección de combinaciones de opciones, respectivamente. Para indicar que un tipo de enumeración declara campos de bits, aplíquele el atributo [Flags](xref:System.FlagsAttribute). Como se muestra en el ejemplo siguiente, también puede incluir algunas combinaciones típicas en la definición de un tipo de enumeración.

[!code-csharp[enum flags](snippets/EnumType.cs#Flags)]

Para más información y ver algunos ejemplos, consulte la página de referencia de API de <xref:System.FlagsAttribute?displayProperty=nameWithType> y la sección [miembros no exclusivos y el atributo Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) de la página de referencia de API de <xref:System.Enum?displayProperty=nameWithType>.

## <a name="the-systemenum-type-and-enum-constraint"></a>El tipo System.Enum y la restricción de enumeración

El tipo <xref:System.Enum?displayProperty=nameWithType> es la clase base abstracta de todos los tipos de enumeración. Proporciona una serie de métodos para obtener información sobre un tipo de enumeración y sus valores. Para más información y ver algunos ejemplos, consulte la página de referencia de la API <xref:System.Enum?displayProperty=nameWithType>.

A partir C# 7.3, puede usar `System.Enum` en una restricción de clase base (conocida como la [restricción de enumeración](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) para especificar que un parámetro de tipo es un tipo de enumeración.

## <a name="conversions"></a>Conversiones

Para cualquier tipo de enumeración, existen conversiones explícitas entre el tipo de enumeración y su tipo entero subyacente. Si convierte (usa[cast](../operators/type-testing-and-cast.md#cast-expression)) un valor de enumeración a su tipo subyacente, el resultado es el valor entero asociado de un miembro de enumeración.

[!code-csharp[enum conversions](snippets/EnumType.cs#Conversions)]

Use el método <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para determinar si un tipo de enumeración contiene un miembro de enumeración con el valor asociado determinado.

Para cualquier tipo de enumeración, existen conversiones [boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md) a y desde el tipo <xref:System.Enum?displayProperty=nameWithType>, respectivamente.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Enumeraciones](~/_csharplang/spec/enums.md)
- [Operaciones y valores de enumeración](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [Operadores lógicos de enumeración](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [Operadores de comparación de enumeración](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [Conversiones de enumeración explícitas](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [Conversiones de enumeración implícitas](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Cadenas de formato de enumeración](../../../standard/base-types/enumeration-format-strings.md)
- [Instrucciones de diseño: diseño de enumeraciones](../../../standard/design-guidelines/enum.md)
- [Instrucciones de diseño: convenciones de nomenclatura de enumeración](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [switch (Instrucción)](../keywords/switch.md)
