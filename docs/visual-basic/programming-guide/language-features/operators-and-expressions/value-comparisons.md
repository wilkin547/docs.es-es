---
description: 'Más información sobre: comparaciones de valores (Visual Basic)'
title: Comparaciones de valores
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: b5d2228b5bb6be18aecebcd0247a1e29e29df9ec
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472714"
---
# <a name="value-comparisons-visual-basic"></a>Comparaciones de valores (Visual Basic)

Los operadores de comparación se pueden usar para construir expresiones que comparen los valores de variables numéricas. Estas expresiones devuelven un `Boolean` valor en función de si la comparación es true o false. Los ejemplos de estas expresiones son los siguientes.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La primera expresión se evalúa como `True` , porque 45 es mayor que 26. El segundo ejemplo se evalúa como `False` , porque 26 no es mayor que 45.  
  
 También puede comparar expresiones numéricas de este modo. Las expresiones que se comparan pueden ser expresiones complejas, como en el ejemplo siguiente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 La expresión compleja anterior incluye literales, variables y llamadas de función. Se evalúan las expresiones en ambos lados del operador de comparación y los valores resultantes se comparan mediante el `>=` operador de comparación. Si el valor de la expresión del lado izquierdo es mayor o igual que el valor de la expresión de la derecha, toda la expresión se evalúa como; de `True` lo contrario, se evalúa como `False` .  
  
 Las expresiones que comparan valores se usan normalmente en `If...Then` construcciones, como en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 El `=` signo es un operador de comparación y un operador de asignación. Cuando se utiliza como un operador de comparación, evalúa si el valor de la izquierda es igual al valor de la derecha, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 También puede utilizar una expresión de comparación en cualquier parte en la `Boolean` que se necesite un valor, como en una `If` `While` instrucción,, `Loop` o `ElseIf` , o al asignar o pasar un valor a una `Boolean` variable. En el ejemplo siguiente, el valor devuelto por la expresión de comparación se asigna a una `Boolean` variable.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Consulte también

- [Expresiones booleanas](boolean-expressions.md)
- [Operadores y expresiones](index.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Procedimiento para calcular valores numéricos](how-to-calculate-numeric-values.md)
- [Prioridad de operador en Visual Basic](../../../language-reference/operators/operator-precedence.md)
