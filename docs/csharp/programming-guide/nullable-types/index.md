---
title: 'Tipos de valor que admiten un valor NULL: Guía de programación de C#'
ms.custom: seodec18
description: Información sobre los tipos de valor de C# que admiten un valor NULL y su uso
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#]
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: b8b52e7fb34adf65d5c76d59811ea6dd0ab16a98
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396219"
---
# <a name="nullable-value-types-c-programming-guide"></a>Tipos de valor que admiten un valor NULL (Guía de programación de C#)

Los tipos de valor que admiten un valor NULL son instancias de la estructura <xref:System.Nullable%601?displayProperty=nameWithType>. Los tipos de valor que admiten un valor NULL pueden representar todos los valores de un tipo `T` subyacente y un valor [NULL](../../language-reference/keywords/null.md) adicional. EL tipo `T` subyacente puede ser cualquier [tipo de valor](../../language-reference/keywords/value-types.md) que no acepte valores NULL. `T` no puede ser un tipo de referencia.

> [!NOTE]
> C# 8.0 presenta la característica de tipos de referencia que admiten valores NULL. Para más información, vea [Tipos de referencia que aceptan valores NULL](../../nullable-references.md). Los tipos de valor que admiten valores NULL están disponibles a partir de C# 2.

Por ejemplo, puede asignar `null` o cualquier valor entero de <xref:System.Int32.MinValue?displayProperty=nameWithType> a <xref:System.Int32.MaxValue?displayProperty=nameWithType> a un elemento `Nullable<int>` y [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) o `null` a un elemento `Nullable<bool>`.

Los tipos de valor que admiten valores NULL se usan cuando es necesario representar el valor indefinido de un tipo subyacente. Una variable booleana solo puede tener dos valores: `true` y `false`. No hay ningún valor "sin definir". En muchas aplicaciones de programación, especialmente en las interacciones de las bases de datos, el valor de una variable puede ser indefinido o incluso no estar disponible. Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede no contener ningún valor. En tal caso, se usa un tipo `Nullable<bool>`.

Los tipos de valor que admiten valores NULL tienen las características siguientes:

- Los tipos de valor que admiten valores NULL representan variables de tipo de valor a las que se puede asignar el valor `null`.

- La sintaxis `T?` es una abreviatura de `Nullable<T>`. Las dos formas son intercambiables.

- Asigne un valor a un tipo de valor que admite valores NULL tal como lo haría para un tipo de valor subyacente: `int? x = 10;` o `double? d = 4.108;`. También puede asignar el valor `null`: `int? x = null;`.

- Use las propiedades de solo lectura <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> y <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> para probar si hay valores NULL y recuperar el valor, como se muestra en el ejemplo siguiente: `if (x.HasValue) y = x.Value;`

  - La propiedad <xref:System.Nullable%601.HasValue%2A> devuelve `true` si la variable contiene un valor, o `false` si es `null`.

  - La propiedad <xref:System.Nullable%601.Value%2A> devuelve un valor si <xref:System.Nullable%601.HasValue%2A> devuelve `true`. De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.

- También puede usar los operadores `==` y `!=` con un tipo de valor que admite valores NULL, como se muestra en el ejemplo siguiente: `if (x != null) y = x.Value;`. Si `a` y `b` son ambos NULL, `a == b` se evalúa como `true`.

- A partir de C# 7.0, se puede usar la [coincidencia de patrones](../../pattern-matching.md#the-is-type-pattern-expression) tanto para examinar como para obtener un valor de un tipo que acepta valores NULL: `if (x is int valueOfX) y = valueOfX;`.

- El valor predeterminado de `T?` es una instancia cuya propiedad <xref:System.Nullable%601.HasValue%2A> devuelve `false`.

- Use el método <xref:System.Nullable%601.GetValueOrDefault> para devolver el valor asignado, o bien el [valor predeterminado](../../language-reference/keywords/default-values-table.md) del tipo subyacente si el valor es `null`.

- Use el método <xref:System.Nullable%601.GetValueOrDefault(%600)> para devolver el valor asignado, o bien el valor predeterminado proporcionado si el valor es `null`.

- Use el [operador de fusión NULL](../../language-reference/operators/null-coalescing-operator.md) (`??`) para asignar un valor a una variable de un tipo de valor subyacente basado en un valor que admite NULL: `int? x = null; int y = x ?? -1;`. En el ejemplo, dado que `x` es `null`, el valor resultante de `y` es `-1`.

- Si se establece una conversión definida por el usuario entre dos tipos de valor, esa misma conversión también se puede usar con los correspondientes tipos que admiten un valor NULL.

- No se permite la anidación de tipos de valor que admiten un valor NULL. La línea siguiente no se compilará: `Nullable<Nullable<int>> n;`

Para obtener más información, consulte los temas [Uso de tipos de valor que admiten un valor NULL](using-nullable-types.md) e [Identificación de tipos de valor que admiten un valor NULL](how-to-identify-a-nullable-type.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Operador !](../../language-reference/operators/null-coalescing-operator.md)
- [Tipos de valores que aceptan valores NULL (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
