---
title: Operadores y expresiones en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: a0f6d026714f8e933dc75dbb7c3a5e6e8e1bd795
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805453"
---
# <a name="operators-and-expressions-in-visual-basic"></a>Operadores y expresiones en Visual Basic
Un *operador* es un elemento de código que realiza una operación en uno o más elementos de código que contienen valores. Los elementos de valor incluyen variables, constantes, literales, propiedades, devoluciones de procedimientos `Function` y `Operator` y expresiones.  
  
 Una *expresión* es una serie de elementos de valor combinados con operadores, lo que produce un nuevo valor. Los operadores actúan en los elementos de valor mediante cálculos, comparaciones y otras operaciones.  
  
## <a name="types-of-operators"></a>Tipos de operadores  
 Visual Basic proporciona los siguientes tipos de operadores:  
  
-   Los [operadores aritméticos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) realizan cálculos familiares en valores numéricos, incluido el desplazamiento de los patrones de bits.  
  
-   Los [operadores de comparación](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) comparan dos expresiones y devuelven un valor `Boolean` que representa el resultado de la comparación.  
  
-   Los [operadores de concatenación](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) unen varias cadenas en una sola.  
  
-   Los [operadores lógicos y bit a bit de Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combinan valores `Boolean` o numéricos y devuelven un resultado del mismo tipo de datos que los valores.  
  
 Los elementos de valor que se combinan con un operador se denominan *operandos* de ese operador. Los operadores combinados con elementos de valor forman expresiones, salvo el operador de asignación, que forma una *instrucción*. Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
## <a name="evaluation-of-expressions"></a>Evaluación de expresiones  
 El resultado final de una expresión representa un valor, que suele ser de un tipo de datos conocido, como un tipo `Boolean`, `String` o numérico.  
  
 A continuación se muestran ejemplos de expresiones.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Varios operadores pueden realizar acciones en una sola expresión o instrucción, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 En el ejemplo anterior, Visual Basic realiza las operaciones en la expresión del lado derecho del operador de asignación (`=`), a continuación, asigna el valor resultante a la variable `x` a la izquierda. No hay ningún límite práctico al número de operadores que se pueden combinar en una expresión, pero es necesario conocer la [prioridad de operadores en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) para asegurarse de que se obtienen los resultados esperados.  
  
 Para obtener más información y ejemplos, vea [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx) (Sobrecarga de operadores en Visual Basic 2005).  
  
## <a name="see-also"></a>Vea también  
 [Operadores](../../../../visual-basic/language-reference/operators/index.md)  
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)
