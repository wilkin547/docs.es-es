---
title: Comparaciones de valores (Visual Basic)
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
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649612"
---
# <a name="value-comparisons-visual-basic"></a>Comparaciones de valores (Visual Basic)
Operadores de comparación pueden utilizarse para construir expresiones que comparan los valores de variables numéricas. Estas expresiones devuelven un `Boolean` valor en función de si la comparación es true o false. Ejemplos de este tipo de expresión son los siguientes.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La primera expresión se evalúa como `True`, puesto que 45 es mayor que 26. El segundo ejemplo se evalúa como `False`, puesto que 26 no es mayor que 45.  
  
 También puede comparar expresiones numéricas de este modo. Las expresiones que se comparan pueden ser complejas, como en el ejemplo siguiente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Esta expresión compleja incluye literales, variables y llamadas a funciones. Se evalúan las expresiones en ambos lados del operador de comparación y los valores resultantes se comparan mediante el `>=` operador de comparación. Si el valor de la expresión del lado izquierdo es mayor o igual que el valor de la expresión de la derecha, toda la expresión se evalúa como `True`; en caso contrario, se evalúa como `False`.  
  
 Suelen usarse en expresiones que comparen valores `If...Then` construcciones, como en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 La `=` inicio de sesión es un operador de comparación, así como un operador de asignación. Cuando se utiliza como un operador de comparación, evalúa si el valor de la izquierda es igual que el valor de la derecha, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 También puede utilizar una expresión de comparación en cualquier lugar un `Boolean` valor es necesario, como en un `If`, `While`, `Loop`, o `ElseIf` (instrucción), o cuando se asigna o se pasa un valor a un `Boolean` variable. En el ejemplo siguiente, el valor devuelto por la expresión de comparación se asigna a un `Boolean` variable.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Calcular valores numéricos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
