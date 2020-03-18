---
title: Operadores true y false (referencia de C#)
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 5ccd08a348478902bbbac36e99acf7ffc1fc814b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846225"
---
# <a name="true-and-false-operators-c-reference"></a>Operadores true y false (referencia de C#)

El operador `true` devuelve el valor [bool](../builtin-types/bool.md)`true` para indicar que su operando es definitivamente true. El operador `false` devuelve el valor `bool``true` para indicar que su operando es definitivamente false. Los operadores `true` y `false` no garantizan que se complementan entre sí. Es decir, tanto el operador `true` como `false` podrían devolver el valor `bool``false` del mismo operando. Si un tipo define uno de los dos operadores, también debe definir otro operador.

> [!TIP]
> Use el tipo `bool?`, si tiene que admitir la lógica de tres valores (por ejemplo, cuando trabaja con bases de datos que admiten un tipo booleano de tres valores). C# proporciona los operadores `&` y `|` que admiten la lógica de tres valores con los operandos `bool?`. Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](boolean-logical-operators.md).

## <a name="boolean-expressions"></a>Expresiones booleanas

Un tipo con el operador `true` definido puede ser el tipo de un resultado de una expresión condicional de control en las instruciones [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) y [for](../keywords/for.md) y en el [operador condicional `?:`](conditional-operator.md). Para más información, vea la sección [Expresiones booleanas](~/_csharplang/spec/expressions.md#boolean-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="user-defined-conditional-logical-operators"></a>Operadores lógicos condicionales definidos por el usuario

Si un tipo con los operadores `true` y `false` definidos [sobrecarga](operator-overloading.md) el [operador lógico OR](boolean-logical-operators.md#logical-or-operator-) `|` o el [operador lógico AND](boolean-logical-operators.md#logical-and-operator-) `&` de una manera determinada, el [operador lógico condicional OR](boolean-logical-operators.md#conditional-logical-or-operator-) `||` o el [operador lógico condicional AND](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, respectivamente, se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra el tipo que define los operadores `true` y `false`. Además, el tipo sobrecarga el operador lógico AND `&` de manera que el operador `&&` también se puede evaluar para los operandos de ese tipo.

[!code-csharp[true and false operators example](snippets/TrueFalseOperators.cs)]

Tenga en cuenta el comportamiento de cortocircuito del operador `&&`. Cuando el método `GetFuelLaunchStatus` devuelve `LaunchStatus.Red`, el operando derecho del operador `&&` no se evalúa. Eso es porque `LaunchStatus.Red` es definitivamente false. A continuación, el resultado de AND lógico no depende del valor del operando derecho. El resultado del ejemplo es el siguiente:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
