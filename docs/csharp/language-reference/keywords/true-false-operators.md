---
title: 'Operadores true y false: Referencia de C#'
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245736"
---
# <a name="true-and-false-operators-c-reference"></a>Operadores true y false (Referencia de C#)

El operador `true` devuelve el valor [bool](bool.md) `true` para indicar que un operando es definitivamente true. El operador `false` devuelve el valor `bool` `true` para indicar que un operando es definitivamente false. Los operadores `true` y `false` no garantizan que se complementan entre sí. Es decir, tanto el operador `true` como `false` podrían devolver el valor `bool` `false` del mismo operando. Si un tipo define uno de los dos operadores, también debe definir otro operador.

Si un tipo con los operadores `true` y `false` definidos [sobrecarga](operator.md) el [operador lógico OR](../operators/or-operator.md) `|` o el [operador lógico AND](../operators/and-operator.md) `&` de una manera determinada, el [operador lógico condicional OR](../operators/conditional-or-operator.md) `||` o el [operador lógico condicional AND](../operators/conditional-and-operator.md) `&&`, respectivamente, se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

Un tipo con el operador `true` definido puede ser el tipo de un resultado de una expresión condicional de control en las instruciones [if](if-else.md), [do](do.md), [while](while.md) y [for](for.md) y en el [operador condicional `?:`](../operators/conditional-operator.md). Para más información, vea la sección [Expresiones booleanas](~/_csharplang/spec/expressions.md#boolean-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md).

> [!TIP]
> Use el tipo `bool?`, si tiene que admitir la lógica de tres valores, por ejemplo, cuando trabaja con bases de datos que admiten un tipo lógico de tres valores. Para más información, consulte la sección [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).

El ejemplo siguiente muestra el tipo que define los operadores `true` y `false`. Además, sobrecarga el operador lógico AND `&` de tal manera que el operador `&&` también se puede evaluar para los operandos de ese tipo.

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

Tenga en cuenta el comportamiento de cortocircuito del operador `&&`. Cuando el método `GetFuelLaunchStatus` devuelve `LaunchStatus.Red`, el segundo operando del operador `&&` no se evalúa. Eso es porque `LaunchStatus.Red` es definitivamente false. A continuación, el resultado de AND lógico no depende del valor del segundo operando. El resultado del ejemplo es el siguiente:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Operadores de C#](../operators/index.md)
- [Literal `true`](true-literal.md)
- [Literal `false`](false-literal.md)