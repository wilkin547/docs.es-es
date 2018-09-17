---
title: false (Operador, Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45648930"
---
# <a name="false-operator-c-reference"></a>false (Operador, Referencia de C#)

Devuelve el valor [bool](bool.md) `true` para indicar que un operando es `false` y devuelve `false` en caso contrario.

Antes de C# 2.0, los operadores `true` y `false` se usaban para crear tipos de valor que aceptan valores NULL definidos por el usuario que eran compatibles con tipos como `SqlBool`. Pero ahora este lenguaje proporciona compatibilidad integrada para tipos de valor que aceptan valores NULL y, siempre que sea posible, deben usarse en lugar de sobrecargar los operadores `true` y `false`. Para obtener más información, vea [Nullable Types](../../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#]).

Con valores booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)` porque es posible que uno o los dos valores sean NULL. Debe sobrecargar los operadores `true` y `false` por separado para controlar correctamente los valores NULL en la expresión. En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

Un tipo que sobrecarga los operadores `true` y `false` puede usarse para la expresión de control en instrucciones [if](if-else.md), [do](do.md), [while](while.md) y [for](for.md), y en [expresiones condicionales](../operators/conditional-operator.md).

Si un tipo define el operador `false`, también debe definir el operador [true](true.md).

Un tipo no puede sobrecargar directamente los operadores lógicos condicionales [&&](../operators/conditional-and-operator.md) y [&#124;&#124;](../operators/conditional-or-operator.md), pero se consigue un efecto equivalente si se sobrecargan los operadores lógicos normales y los operadores `true` y `false`.

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)  
- [Guía de programación de C#](../../programming-guide/index.md)  
- [Palabras clave de C#](index.md)  
- [Operadores de C#](../operators/index.md)  
- [true](true.md)  