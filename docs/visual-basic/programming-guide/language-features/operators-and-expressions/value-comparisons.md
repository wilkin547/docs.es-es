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
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864396"
---
# <a name="value-comparisons-visual-basic"></a>Comparaciones de valores (Visual Basic)
Operadores de comparación pueden usarse para construir expresiones que comparen los valores de variables numéricas. Estas expresiones devuelven un `Boolean` valor en función de si la comparación es true o false. Ejemplos de este tipo de expresión son los siguientes.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La primera expresión se evalúa como `True`, ya que es mayor que 26 45. El segundo ejemplo se evalúa como `False`, ya que no es mayor que 45 26.  
  
 También puede comparar expresiones numéricas de esta manera. Las expresiones que compara pueden ser compleja, como en el ejemplo siguiente.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Expresión compleja incluye literales, variables y las llamadas de función. Se evalúan las expresiones en ambos lados del operador de comparación y los valores resultantes se comparan mediante el `>=` operador de comparación. Si el valor de la expresión en el lado izquierdo es mayor o igual que el valor de la expresión de la derecha, toda la expresión se evalúa como `True`; en caso contrario, se evalúa como `False`.  
  
 Suelen usarse en expresiones que comparen valores `If...Then` construcciones, como en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 El `=` inicio de sesión es un operador de comparación, así como un operador de asignación. Cuando se usa como un operador de comparación, evalúa si el valor de la izquierda es igual al valor de la derecha, tal como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 También puede usar una expresión de comparación en cualquier lugar un `Boolean` valor es necesario, como en un `If`, `While`, `Loop`, o `ElseIf` instrucción, o cuando se asigna o se pasa un valor a un `Boolean` variable. En el ejemplo siguiente, el valor devuelto por la expresión de comparación se asigna a un `Boolean` variable.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Vea también

- [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Cómo: Calcular valores numéricos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
