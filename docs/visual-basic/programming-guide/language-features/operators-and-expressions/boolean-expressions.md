---
title: Expresiones booleanas (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 48071c6833f9841fa42311dda59d6959c0645ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-expressions-visual-basic"></a>Expresiones booleanas (Visual Basic)
A *expresión booleana* es una expresión que se evalúa como un valor de la [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` o `False`. `Boolean`las expresiones pueden tener varias formas. La más simple es la comparación directa del valor de un `Boolean` variable a un `Boolean` literal, tal como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>Dos significados de los = (operador)  
 Tenga en cuenta que la instrucción de asignación `newCustomer = True` tenga la misma apariencia que la expresión en el ejemplo anterior, pero realiza funciones diferentes y se utiliza de manera diferente. En el ejemplo anterior, la expresión `newCustomer = True` representa un valor booleano y la `=` inicio de sesión se interpreta como un operador de comparación. En una instrucción independiente, el `=` se interpreta como un operador de asignación de inicio de sesión y asigna el valor de la derecha a la variable de la izquierda. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Para obtener más información, consulte [comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) y [instrucciones](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Operadores de comparación  
 Operadores de comparación, como `=`, `<`, `>`, `<>`, `<=`, y `>=` producen expresiones booleanas, compara la expresión en el lado izquierdo del operador con la expresión situada a la derecha del operador y evaluar el resultado como `True` o `False`. Esto se ilustra en el siguiente ejemplo:  
  
 `42 < 81`  
  
 Dado que 42 es menor que 81, la expresión booleana en el ejemplo anterior se evalúa como `True`. Para obtener más información sobre este tipo de expresión, vea [comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Operadores de comparación combinados con operadores lógicos  
 Expresiones de comparación se pueden combinar con operadores lógicos para producir expresiones booleanas más complejas. En el ejemplo siguiente se muestra el uso de operadores de comparación junto con un operador lógico.  
  
 `x > y And x < 1000`  
  
 En el ejemplo anterior, el valor de toda la expresión depende de los valores de las expresiones especificadas a cada lado de la `And` operador. Si ambas expresiones son `True`, a continuación, toda la expresión se evalúa como `True`. Si ambas expresiones son `False`, a continuación, toda la expresión se evalúa como `False`.  
  
## <a name="short-circuiting-operators"></a>Operadores de evaluación "cortocircuitada"  
 Los operadores lógicos `AndAlso` y `OrElse` exhiben un comportamiento conocido como *evaluación "cortocircuitada"*. Un operador de evaluación "cortocircuitada" evalúa primero el operando izquierdo. Si el operando izquierdo determina el valor de la expresión completa, la ejecución del programa continúa sin evaluar la expresión derecha. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 En el ejemplo anterior, el operador evalúa la expresión de la izquierda, `45 < 12`. Dado que la expresión de la izquierda se evalúa como `False`, toda la expresión lógica debe evaluar como `False`. Ejecución del programa, por tanto, omite la ejecución del código dentro de la `If` bloque sin evaluar la expresión de la derecha, `testFunction(3)`. En este ejemplo no llama a `testFunction()` porque la expresión izquierda falsea toda la expresión.  
  
 De forma similar, si la expresión izquierda de una expresión lógica con `OrElse` se evalúa como `True`, la ejecución prosigue con la siguiente línea de código sin evaluar la expresión de la derecha, porque la expresión izquierda ya ha validado toda la matriz expresión.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Comparación con operadores no cortocircuitan  
 Por el contrario, se evalúan los dos lados del operador lógico cuando los operadores lógicos `And` y `Or` se usan. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 El ejemplo anterior se llama `testFunction()` incluso si la expresión izquierda se evalúa como `False`.  
  
## <a name="parenthetical-expressions"></a>Expresiones entre paréntesis  
 Puede usar paréntesis para controlar el orden de evaluación de expresiones booleanas. Expresiones entre paréntesis se evalúan primero. Para varios niveles de anidamiento, se garantiza la prioridad a las expresiones más profundamente anidadas. Entre paréntesis, la evaluación continúa según las reglas de prioridad de operador. Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Instrucciones](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Boolean (tipo de datos)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
