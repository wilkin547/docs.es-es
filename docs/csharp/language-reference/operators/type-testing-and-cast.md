---
title: 'Operadores de prueba de tipos y expresión de conversión: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para comprobar el tipo de resultado de la expresión y convertirla en otro tipo, si es necesario.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: bc293c359af5744eebc63c0d0f94b4cebe3d450a
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "82021243"
---
# <a name="type-testing-operators-and-cast-expression-c-reference"></a>Operadores de prueba de tipos y expresión de conversión (referencia de C#)

Puede usar los siguientes operadores y expresiones para realizar la comprobación de tipos o la conversión de tipos:

- [operador is](#is-operator): para comprobar si el tipo en tiempo de ejecución de una expresión es compatible con un tipo determinado.
- [operador as](#as-operator): para convertir explícitamente una expresión a un tipo determinado si su tipo en tiempo de ejecución es compatible con ese tipo.
- [expresión Cast](#cast-expression): para realizar una conversión explícita.
- [operador typeof](#typeof-operator): para obtener la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo.

## <a name="is-operator"></a>Operador is

El operador `is` comprueba si el tipo en tiempo de ejecución del resultado de una expresión es compatible con un tipo determinado. A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón.

La expresión con el operador `is` de prueba de tipos tiene el formato siguiente:

```csharp
E is T
```

donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo. `E` no puede ser un método anónimo ni una expresión lambda.

La expresión `E is T` devuelve `true` si el resultado de `E` es distinto de NULL y se puede convertir al tipo `T` por una conversión de referencia, una conversión boxing o una conversión unboxing; de lo contrario, devuelve `false`. El operador `is` no toma en consideración las conversiones definidas por el usuario.

En el ejemplo siguiente se muestra que el operador `is` devuelve `true` si el tipo en tiempo de ejecución del resultado de una expresión se deriva de un tipo determinado, es decir, existe una conversión de referencia entre tipos:

[!code-csharp[is with reference conversion](snippets/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

En el ejemplo siguiente se muestra que el operador `is` tiene en cuenta las conversiones boxing y unboxing pero no considera las [conversiones numéricas](../builtin-types/numeric-conversions.md):

[!code-csharp-interactive[is with int](snippets/TypeTestingAndConversionOperators.cs#IsWithInt)]

Para obtener información acerca de las conversiones de C#, vea el capítulo [Conversiones](~/_csharplang/spec/conversions.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

### <a name="type-testing-with-pattern-matching"></a>Prueba de tipos con coincidencia de patrones

A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón. En concreto, admite el patrón de tipo de la forma siguiente:

```csharp
E is T v
```

donde `E` es una expresión que devuelve un valor, `T` es el nombre de un tipo o un parámetro de tipo y `v` es una nueva variable local de tipo `T`. Si el resultado de `E` no es NULL y puede convertirse en `T` mediante una conversión de referencia, boxing o unboxing, la expresión `E is T v` devuelve `true` y el valor convertido del resultado de `E` se asigna a la variable `v`.

En el siguiente ejemplo se muestra el uso del operador `is` con un patrón de tipo:

[!code-csharp-interactive[is with type pattern](snippets/TypeTestingAndConversionOperators.cs#IsTypePattern)]

Para obtener más información sobre el patrón de tipo y otros patrones admitidos, consulte [Coincidencia de patrones con is](../keywords/is.md#pattern-matching-with-is).

## <a name="as-operator"></a>Operador as

El operador `as` convierte explícitamente el resultado de una expresión en una referencia determinada o un tipo de valor que acepta valores NULL. Si la conversión no es posible, el operador `as` devuelve `null`. A diferencia de la [expresión Cast](#cast-expression), el operador `as` no genera nunca una excepción.

La expresión con el formato

```csharp
E as T
```

donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo produce el mismo resultado que

```csharp
E is T ? (T)(E) : (T)null
```

salvo que `E` solo se evalúa una vez.

El operador `as` solo considera las conversiones de referencia, las que aceptan valores NULL, boxing y unboxing. No puede usar el operador `as` para realizar una conversión definida por el usuario. Para ello, use una [expresión Cast](#cast-expression).

En el siguiente ejemplo se muestra el uso del operador `as`:

[!code-csharp-interactive[as operator](snippets/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> Como se muestra en el ejemplo anterior, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta. A partir de C# 7.0, puede usar el [operador is](#type-testing-with-pattern-matching) para probar si la conversión es correcta y, si es así, asignar su resultado a una nueva variable.

## <a name="cast-expression"></a>Expresión Cast

Una expresión de conversión con el formato `(T)E` realiza una conversión explícita del resultado de la expresión `E` al tipo `T`. Si no existe ninguna conversión explícita del tipo de `E` al tipo `T`, se producirá un error en tiempo de compilación. En el tiempo de ejecución, una conversión explícita podría no completarse correctamente y una expresión de conversión podría generar una excepción.

El ejemplo siguiente muestra las conversiones explícitas numérica y de referencia:

[!code-csharp-interactive[cast expression](snippets/TypeTestingAndConversionOperators.cs#Cast)]

Para obtener más información sobre las conversiones explícitas, vea la sección [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md). Para obtener información sobre cómo definir una conversión personalizada de tipo explícito o implícito, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).

### <a name="other-usages-of-"></a>Otros usos de ()

También puede utilizar paréntesis para [llamar a un método o invocar un delegado](member-access-operators.md#invocation-expression-).

Sirven además para ajustar el orden en el que se van a evaluar operaciones en una expresión. Para obtener más información, vea [Operadores de C# (referencia de C#)](index.md).

## <a name="typeof-operator"></a>typeof (operador)

El operador `typeof` obtiene la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo. El argumento del operador `typeof` debe ser el nombre de un tipo o un parámetro de tipo, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[typeof operator](snippets/TypeTestingAndConversionOperators.cs#TypeOf)]

También se puede usar el operador `typeof` con tipos genéricos sin enlazar. El nombre de un tipo genérico sin enlazar debe contener el número apropiado de comas, que es inferior en una unidad al número de parámetros de tipo. En el siguiente ejemplo se muestra el uso del operador `typeof` con un tipo genérico sin enlazar:

[!code-csharp-interactive[typeof unbound generic](snippets/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

Una expresión no puede ser un argumento del operador `typeof`. Para obtener la instancia de <xref:System.Type?displayProperty=nameWithType> para el tipo en tiempo de ejecución del resultado de una expresión, use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType>.

### <a name="type-testing-with-the-typeof-operator"></a>Prueba de tipos con el operador `typeof`

Use el operador `typeof` para comprobar si el tipo en tiempo de ejecución del resultado de la expresión coincide exactamente con un tipo determinado. En el ejemplo siguiente se muestra la diferencia entre la comprobación de tipos realizada con el operador `typeof` y el [operador is](#is-operator):

[!code-csharp[typeof vs is](snippets/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los operadores `is`, `as` y `typeof` no se pueden sobrecargar.

Un tipo definido por el usuario no se puede sobrecargar el operador `()`, pero puede definir conversiones de tipos personalizadas que pueden realizarse mediante una expresión de conversión. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [El operador is](~/_csharplang/spec/expressions.md#the-is-operator)
- [El operador as](~/_csharplang/spec/expressions.md#the-as-operator)
- [Expresiones de conversión](~/_csharplang/spec/expressions.md#cast-expressions)
- [El operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Elementos genéricos en .NET](../../../standard/generics/index.md)
