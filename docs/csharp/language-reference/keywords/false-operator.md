---
title: false (Operador, Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f9761fb49e2c7f6e4a7615e64cec9fed88318c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="false-operator-c-reference"></a>false (Operador, Referencia de C#)
Devuelve el valor [bool](../../../csharp/language-reference/keywords/bool.md) `true` para indicar que un operando es `false` y devuelve `false` en caso contrario.  
  
 Antes de C# 2.0, los operadores `true` y `false` se usaban para crear tipos de valor que aceptan valores NULL definidos por el usuario que eran compatibles con tipos como `SqlBool`. Pero ahora este lenguaje proporciona compatibilidad integrada para tipos de valor que aceptan valores NULL y, siempre que sea posible, deben usarse en lugar de sobrecargar los operadores `true` y `false`. Para obtener más información, vea [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#]).  
  
 Con valores booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)` porque es posible que uno o los dos valores sean NULL. Debe sobrecargar los operadores `true` y `false` por separado para controlar correctamente los valores NULL en la expresión. En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 Un tipo que sobrecarga los operadores `true` y `false` puede usarse para la expresión de control en instrucciones [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) y [for](../../../csharp/language-reference/keywords/for.md), y en [expresiones condicionales](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Si un tipo define el operador `false`, también debe definir el operador [true](../../../csharp/language-reference/keywords/true.md).  
  
 Un tipo no puede sobrecargar directamente los operadores lógicos condicionales [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), pero se consigue un efecto equivalente si se sobrecargan los operadores lógicos normales y los operadores `true` y `false`.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [true](../../../csharp/language-reference/keywords/true.md)
