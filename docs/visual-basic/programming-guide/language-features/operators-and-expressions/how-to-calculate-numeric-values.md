---
title: 'Cómo: Calcular valores numéricos (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649791"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Cómo: Calcular valores numéricos (Visual Basic)
Puede calcular valores numéricos mediante el uso de expresiones numéricas. A *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.  
  
## <a name="calculating-numeric-values"></a>Calcular valores numéricos  
  
#### <a name="to-calculate-a-numeric-value"></a>Para calcular un valor numérico  
  
-   Combinar uno o más literales numéricos, constantes y variables en una expresión numérica. El ejemplo siguiente muestra algunas expresiones numéricas válidas.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Las tres primeras líneas muestran un literal, una constante y una variable. Cada uno forma una expresión numérica válida por sí mismo. La línea final muestra una combinación de una variable con dos literales.  
  
     Tenga en cuenta que una expresión numérica no forma una instrucción de Visual Basic completa por sí misma. Debe usar la expresión como parte de una instrucción completa.  
  
#### <a name="to-store-a-numeric-value"></a>Para almacenar un valor numérico  
  
-   Puede utilizar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual (`=`) se asigna a la variable `j` en el lado izquierdo del operador, por lo que `j` se evalúa como 276.  
  
     Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Operadores varios  
 Si la expresión numérica contiene más de un operador, se determina el orden en que se evalúan las reglas de precedencia de operadores. Para invalidar las reglas de prioridad de operador, las expresiones se escriben entre paréntesis, como en el ejemplo anterior; las expresiones se evalúan primero.  
  
#### <a name="to-override-normal-operator-precedence"></a>Para invalidar la prioridad de operador  
  
-   Utilice paréntesis para indicar las operaciones que desea efectuar en primer lugar. El ejemplo siguiente muestra dos resultados diferentes con los mismos operandos y operadores.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     En el ejemplo anterior, el cálculo de `j` realiza el operador de suma (`+`) primera porque los paréntesis que rodean `(67 + i)` invalidar la prioridad normal y el valor asignado a `j` es 276 (4 veces 69). El cálculo de `k` lleva a cabo los operadores con su prioridad normal (`*` antes de `+`) y el valor asignado a `k` es 270 (268 más 2).  
  
     Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vea también  
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)  
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
