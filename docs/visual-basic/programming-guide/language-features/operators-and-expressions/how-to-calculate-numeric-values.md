---
title: Procedimiento Calcular valores numéricos (Visual Basic)
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
ms.openlocfilehash: 33184d9be275f5e777ffd79c6dd4e3182d865de7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864687"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Procedimiento Calcular valores numéricos (Visual Basic)
Puede calcular valores numéricos mediante el uso de expresiones numéricas. Un *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.  
  
## <a name="calculating-numeric-values"></a>Calcular valores numéricos  
  
#### <a name="to-calculate-a-numeric-value"></a>Para calcular un valor numérico  
  
-   Combinar uno o más literales numéricos, constantes y variables en una expresión numérica. El ejemplo siguiente muestra algunas expresiones numéricas válidas.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Las tres primeras líneas muestran un literal, una constante y variable. Cada uno forma una expresión numérica válida por sí mismo. La última línea muestra una combinación de una variable con dos literales.  
  
     Tenga en cuenta que una expresión numérica no forma una instrucción completa de Visual Basic por sí mismo. Debe usar la expresión como parte de una instrucción completa.  
  
#### <a name="to-store-a-numeric-value"></a>Para almacenar un valor numérico  
  
-   Puede usar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual (`=`) se asigna a la variable `j` en el lado izquierdo del operador, por lo que `j` se evalúa como 276.  
  
     Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Operadores varios  
 Si la expresión numérica contiene más de un operador, el orden en que se evalúan viene determinada por las reglas de precedencia de operadores. Para invalidar las reglas de precedencia de operadores, encerrar expresiones entre paréntesis, como se muestra en el ejemplo anterior; las expresiones se evalúan primero.  
  
#### <a name="to-override-normal-operator-precedence"></a>Para invalidar la prioridad de operador  
  
-   Utilice paréntesis para indicar las operaciones que desee que se ejecute primero. El ejemplo siguiente muestra dos resultados diferentes con los mismos operandos y operadores.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     En el ejemplo anterior, el cálculo de `j` realiza el operador de suma (`+`) primera porque los paréntesis que rodean `(67 + i)` invalidar la prioridad normal y el valor asignado a `j` es 276 (4 veces 69). El cálculo para `k` realiza los operadores con su prioridad normal (`*` antes `+`) y el valor asignado a `k` es 270 (268 más 2).  
  
     Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vea también

- [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)
- [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
