---
description: 'Operador ?: (referencia de C#)'
title: 'Operador ?: (referencia de C#)'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738884"
---
# <a name="-operator-c-reference"></a>Operador ?: (referencia de C#)

El operador condicional `?:`, también conocido como operador condicional ternario, evalúa una expresión booleana y devuelve el resultado de una de las dos expresiones, en función de que la expresión booleana se evalúe como `true` o `false`.

La sintaxis del operador condicional es la siguiente:

```csharp
condition ? consequent : alternative
```

La expresión `condition` debe evaluarse como `true` o `false`. Si `condition` se evalúa como `true`, se evalúa la expresión `consequent` y su resultado se convierte en el resultado de la operación. Si `condition` se evalúa como `false`, se evalúa la expresión `alternative` y su resultado se convierte en el resultado de la operación. Solo se evalúan `consequent` o `alternative`.

A partir de C# 9.0, las expresiones condicionales tienen tipo de destino. Es decir, si se conoce el tipo de destino de una expresión condicional, los tipos de `consequent` y `alternative` se deben poder convertir implícitamente al tipo de destino, como se muestra en el ejemplo siguiente:

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

Si se desconoce el tipo de destino de una expresión condicional (por ejemplo, al usar la palabra clave [`var`](../keywords/var.md)) o en C# 8.0 y versiones anteriores, el tipo de `consequent` y `alternative` debe ser el mismo, o bien debe haber una conversión implícita de un tipo a otro:

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

El operador condicional es asociativo a la derecha, es decir, una expresión de la forma

```csharp
a ? b : c ? d : e
```

se evalúa como

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> Puede utilizar el siguiente recurso mnemotécnico para recordar cómo se evalúa el operador condicional:
>
> ```text
> is this condition true ? yes : no
> ```

En el siguiente ejemplo se muestra el uso del operador condicional:

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Expresión condicional ref

A partir de C# 7.2, las variables locales de tipo [ref](../keywords/ref.md#ref-locals) o [ref readonly](../keywords/ref.md#ref-readonly-locals) se pueden asignar condicionalmente con una expresión condicional ref. También puede usar una expresión condicional ref como un [valor devuelto de referencia](../keywords/ref.md#reference-return-values) o como un [método de argumento de `ref`](../keywords/ref.md#passing-an-argument-by-reference).

La sintaxis de una expresión condicional ref es la siguiente:

```csharp
condition ? ref consequent : ref alternative
```

Como sucede con el operador condicional original, una expresión condicional ref evalúa solo una de las dos expresiones, ya sea `consequent` o `alternative`.

En el caso de una expresión condicional ref, los tipos de `consequent` y `alternative` deben coincidir. Las expresiones condicionales ref no tienen tipo de destino.

En el ejemplo siguiente se muestra el uso de una expresión condicional ref:

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operador condicional y una instrucción `if..else`

Es posible que el uso del operador condicional en lugar de una instrucción [if-else](../keywords/if-else.md) genere código más conciso en aquellos casos en los que tenga que calcular un valor condicionalmente. El ejemplo siguiente muestra dos maneras de clasificar un entero como negativo o no negativo:

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador condicional.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre [operadores condicionales](~/_csharplang/spec/expressions.md#conditional-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para obtener más información sobre de las características agregadas en C# 7.2 y versiones posteriores, vea las siguientes notas de propuesta de características:

- [Expresiones condicionales ref (C# 7.2)](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [Expresión condicional con tipo de destino (C# 9.0)](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Instrucción if-else](../keywords/if-else.md)
- [Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operadores ?? y ??=](null-coalescing-operator.md)
- [ref (palabra clave)](../keywords/ref.md)
