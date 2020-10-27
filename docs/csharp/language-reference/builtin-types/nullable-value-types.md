---
title: 'Tipos de valor que admiten valores NULL: Referencia de C#'
description: Información sobre los tipos de valor de C# que admiten un valor NULL y su uso
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 3ab2dff6b7399b0458a69d4498b2ebda24f6c5cc
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471840"
---
# <a name="nullable-value-types-c-reference"></a>Tipos de valor que admiten valores NULL (referencia de C#)

Un *tipo de valor que admite un valor NULL* `T?` representa todos los valores de su [tipo de valor](value-types.md) subyacente `T` y un valor [NULL](../keywords/null.md) adicional. Por ejemplo, puede asignar cualquiera de los tres valores siguientes a una variable `bool?`: `true`, `false` o `null`. Un tipo de valor subyacente `T` no puede ser un tipo de valor que acepte valores NULL por sí mismo.

> [!NOTE]
> C# 8.0 presenta la característica de tipos de referencia que admiten un valor NULL. Para más información, consulte [Tipos de referencia que admiten un valor NULL](nullable-reference-types.md). Los tipos de valor que admiten valores NULL están disponibles a partir de C# 2.

Todos los tipos que admiten valores NULL son instancias de la estructura <xref:System.Nullable%601?displayProperty=nameWithType> genérica. Puede hacer referencia a un tipo de valor que admite valores NULL con un tipo subyacente `T` en cualquiera de las formas intercambiables siguientes: `Nullable<T>` o `T?`.

Normalmente, los tipos de valor que admiten valores NULL se usan cuando es necesario representar el valor indefinido de un tipo de valor subyacente. Por ejemplo, una variable booleana, o `bool`, solo puede ser `true` o `false`. Sin embargo, en algunas aplicaciones, un valor de variable puede estar sin definir o faltar. Por ejemplo, un campo de base de datos puede contener `true` o `false`, o puede no contener ningún valor, es decir, `NULL`. Puede usar el tipo `bool?` en ese escenario.

## <a name="declaration-and-assignment"></a>Declaración y asignación

Como un tipo de valor se puede convertir de forma implícita al tipo de valor que admite valores NULL correspondiente, un valor se puede asignar a un tipo que admite valores NULL como se haría para su tipo de valor subyacente. También se puede asignar el valor `null`. Por ejemplo:

[!code-csharp[declare and assign](snippets/shared/NullableValueTypes.cs#Declaration)]

El valor predeterminado de un tipo de valor que admite valores NULL se representa como `null`, es decir, es una instancia cuya propiedad <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> devuelve `false`.

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Examen de una instancia de tipo de valor que admite valores NULL

A partir C# 7.0, puede usar el operador [`is` con un patrón de tipo ](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) para examinar una instancia de un tipo de valor que admite valores NULL para `null` y recuperar un valor de un tipo subyacente:

[!code-csharp-interactive[use pattern matching](snippets/shared/NullableValueTypes.cs#PatternMatching)]

Siempre puede usar las siguientes propiedades de solo lectura para examinar y obtener un valor de una variable de tipo de valor que admite valores NULL:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica si una instancia de un tipo que admite valores NULL tiene un valor de su tipo subyacente.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> obtiene el valor de un tipo subyacente si <xref:System.Nullable%601.HasValue%2A> es `true`. Si <xref:System.Nullable%601.HasValue%2A> es `false`, la propiedad <xref:System.Nullable%601.Value%2A> inicia una excepción <xref:System.InvalidOperationException>.

En el ejemplo siguiente se usa la propiedad `HasValue` para comprobar si la variable contiene un valor antes de mostrarlo:

[!code-csharp-interactive[use HasValue](snippets/shared/NullableValueTypes.cs#HasValue)]

También se puede comparar una variable de un tipo de valor que admite valores NULL con `null` en lugar de usar la propiedad `HasValue`, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[use comparison with null](snippets/shared/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Conversión de un tipo de valor que admite un valor NULL a un tipo subyacente

Si desea asignar un valor de un tipo que admite valores NULL a una variable de tipo de valor que no admite valores NULL, puede que tenga que especificar el valor que se va a asignar en lugar de `null`. Use el [operador de fusión de NULL `??`](../operators/null-coalescing-operator.md) para ello (también puede usar el método <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> con el mismo fin):

[!code-csharp-interactive[?? operator](snippets/shared/NullableValueTypes.cs#NullCoalescing)]

Si desea utilizar el valor [predeterminado](default-values.md) del tipo de valor subyacente en lugar de `null`, use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>.

También puede convertir de forma explícita un tipo de valor que admite valores NULL en uno que no los admite, como se indica en el ejemplo siguiente:

[!code-csharp[explicit cast](snippets/shared/NullableValueTypes.cs#Cast)]

En tiempo de ejecución, si el valor de un tipo de valor que admite un valor NULL es `null`, la conversión explícita inicia una <xref:System.InvalidOperationException>.

Un tipo de valor que no admite valores NULL `T` se convierte implícitamente al tipo que admite valores NULL `T?` correspondiente.

## <a name="lifted-operators"></a>Operadores de elevación

Los [operadores](../operators/index.md) unarios y binarios predefinidos o los operadores sobrecargados que admite un tipo de valor `T` también se admiten en el tipo de valor que admite un valor NULL `T?` correspondiente. Estos operadores, también conocidos como *operadores de elevación* , generan un valor `null` si uno o los dos operandos son `null`; de lo contrario, el operador usa los valores contenidos de sus operandos para calcular el resultado. Por ejemplo:

[!code-csharp[lifted operators](snippets/shared/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Para el tipo `bool?`, los operadores predefinidos `&` y `|` no siguen las reglas descritas en esta sección: el resultado de una evaluación de operador puede ser distinto de NULL incluso si uno de los operandos es `null`. Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../operators/boolean-logical-operators.md).

En el caso de los [operadores de comparación](../operators/comparison-operators.md) `<`, `>`, `<=` y `>=`, si uno o ambos operandos son `null`, el resultado es `false`; de lo contrario, se comparan los valores contenidos de los operandos. No asuma que, como una comparación determinada (por ejemplo, `<=`) devuelve `false`, la comparación contraria (`>`) devolverá `true`. En el ejemplo siguiente se muestra que 10 no es

- mayor ni igual que `null`,
- ni es menor que `null`.

[!code-csharp-interactive[relational and equality operators](snippets/shared/NullableValueTypes.cs#ComparisonOperators)]

En el caso de los [operadores de igualdad](../operators/equality-operators.md#equality-operator-) `==`, si ambos operandos son `null`, el resultado es `true`; si solo uno de los operandos es `null`, el resultado es `false`; de lo contrario, se comparan los valores contenidos de los operandos.

En el caso de los [operadores de desigualdad](../operators/equality-operators.md#inequality-operator-) `!=`, si ambos operandos son `null`, el resultado es `false`; si solo uno de los operandos es `null`, el resultado es `true`; de lo contrario, se comparan los valores contenidos de los operandos.

Si existe una [conversión definida por el usuario](../operators/user-defined-conversion-operators.md) entre dos tipos de valor, esa misma conversión también se puede usar entre los correspondientes tipos que aceptan valores NULL.

## <a name="boxing-and-unboxing"></a>Conversión boxing y conversión unboxing

La [conversión boxing](../../programming-guide/types/boxing-and-unboxing.md) de una instancia de un tipo de valor que acepta valores NULL `T?` se realiza de la siguiente manera:

- Si <xref:System.Nullable%601.HasValue%2A> devuelve `false`, se genera la referencia nula.
- Si <xref:System.Nullable%601.HasValue%2A> devuelve `true`, se aplica la conversión boxing al correspondiente valor del tipo de valor subyacente `T`, no a la instancia de <xref:System.Nullable%601>.

Se puede aplicar conversión unboxing a un tipo de valor `T` con conversión boxing al tipo `T?` que acepta valores NULL correspondiente, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[boxing and unboxing](snippets/shared/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Identificación de tipos que admiten valores NULL

El ejemplo siguiente muestra cómo determinar si una instancia <xref:System.Type?displayProperty=nameWithType> representa un tipo de valor construido que admite valores NULL, es decir, el tipo <xref:System.Nullable%601?displayProperty=nameWithType> con un parámetro de tipo especificado `T`:

[!code-csharp-interactive[whether Type is nullable](snippets/shared/NullableValueTypes.cs#IsTypeNullable)]

Como se muestra en el ejemplo, se usa el operador [typeof](../operators/type-testing-and-cast.md#typeof-operator) para crear una instancia <xref:System.Type?displayProperty=nameWithType>.

Si quiere determinar si una instancia es de un tipo de valor que admite un valor NULL, no use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType> para obtener una instancia de <xref:System.Type> para probarla con el código anterior. Cuando se llama al método <xref:System.Object.GetType%2A?displayProperty=nameWithType> en una instancia de un tipo de valor que admite un valor NULL, [se aplica la conversión boxing](#boxing-and-unboxing) a la instancia para convertirla en <xref:System.Object>. Como la conversión boxing de una instancia que no es NULL de un tipo de valor que admite valores NULL equivale a la conversión boxing de un valor del tipo subyacente, <xref:System.Object.GetType%2A> devuelve una instancia <xref:System.Type> que representa el tipo de valor subyacente que admite valores NULL:

[!code-csharp-interactive[GetType example](snippets/shared/NullableValueTypes.cs#GetType)]

No use el operador [is](../operators/type-testing-and-cast.md#is-operator) para determinar si una instancia es de un tipo de valor que admite valores NULL. Como se muestra en el ejemplo siguiente, no se pueden distinguir los tipos de instancias de un tipo de valor que admite valores NULL y su tipo subyacente mediante el operador `is`:

[!code-csharp-interactive[is operator example](snippets/shared/NullableValueTypes.cs#IsOperator)]

Se puede usar el código que se presenta en el ejemplo siguiente para determinar si una instancia es de un tipo de valor que admite un valor NULL:

[!code-csharp-interactive[whether an instance is of a nullable type](snippets/shared/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> Los métodos que se describen en esta sección no son aplicables en el caso de los [tipos de referencia nula](nullable-reference-types.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Nullable types](~/_csharplang/spec/types.md#nullable-types) (Tipos que aceptan valores NULL [Guía de programación de C#])
- [Operadores de elevación](~/_csharplang/spec/expressions.md#lifted-operators)
- [Conversiones implícitas que aceptan valores NULL](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Conversiones explícitas que aceptan valores NULL](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [Operadores de conversión de elevación](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [¿Qué significa exactamente "elevado"?](/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Tipos de referencia que aceptan valores null](nullable-reference-types.md)
