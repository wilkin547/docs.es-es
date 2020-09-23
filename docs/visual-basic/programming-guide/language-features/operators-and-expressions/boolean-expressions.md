---
title: Expresiones booleanas
ms.date: 07/20/2015
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
ms.openlocfilehash: 51340bf95795d837c055df796424f3cad912adc7
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085755"
---
# <a name="boolean-expressions-visual-basic"></a>Expresiones booleanas (Visual Basic)

Una *expresión booleana* es una expresión que se evalúa como un valor del [tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md): `True` o `False` . `Boolean` las expresiones pueden tomar varias formas. La más simple es la comparación directa del valor de una `Boolean` variable con un `Boolean` literal, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Dos significados del operador =  

 Observe que la instrucción `newCustomer = True` de asignación tiene el mismo aspecto que la expresión del ejemplo anterior, pero realiza una función diferente y se usa de manera diferente. En el ejemplo anterior, la expresión `newCustomer = True` representa un valor booleano y el `=` signo se interpreta como un operador de comparación. En una instrucción independiente, el `=` signo se interpreta como un operador de asignación y asigna el valor de la derecha a la variable de la izquierda. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Para obtener más información, vea [comparaciones de valores](value-comparisons.md) e [instrucciones](../../../language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Operadores de comparación  

 Los operadores de comparación, como `=` ,, `<` `>` , `<>` , `<=` y `>=` generan Expresiones booleanas comparando la expresión del lado izquierdo del operador con la expresión del lado derecho del operador y evaluando el resultado como `True` o `False` . Esto se ilustra en el siguiente ejemplo:  
  
 `42 < 81`  
  
 Dado que 42 es menor que 81, la expresión booleana en el ejemplo anterior se evalúa como `True` . Para obtener más información sobre este tipo de expresión, vea [comparaciones de valores](value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Operadores de comparación combinados con operadores lógicos  

 Las expresiones de comparación se pueden combinar mediante operadores lógicos para generar Expresiones booleanas más complejas. En el ejemplo siguiente se muestra el uso de operadores de comparación junto con un operador lógico.  
  
 `x > y And x < 1000`  
  
 En el ejemplo anterior, el valor de la expresión general depende de los valores de las expresiones de cada lado del `And` operador. Si ambas expresiones son `True` , la expresión general se evalúa como `True` . Si alguna `False` de las expresiones es, toda la expresión se evalúa como `False` .  
  
## <a name="short-circuiting-operators"></a>Operadores de cortocircuito  

 Los operadores lógicos y el comportamiento de los `AndAlso` `OrElse` exhibes se conocen como cortocircuitos. *short-circuiting* Un operador de cortocircuito evalúa primero el operando izquierdo. Si el operando izquierdo determina el valor de toda la expresión, la ejecución del programa continúa sin evaluar la expresión de la derecha. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 En el ejemplo anterior, el operador evalúa la expresión de la izquierda, `45 < 12` . Dado que la expresión de la izquierda se evalúa como `False` , toda la expresión lógica debe evaluarse como `False` . Así, la ejecución del programa omite la ejecución del código dentro del `If` bloque sin evaluar la expresión de la derecha, `testFunction(3)` . En este ejemplo no se llama a `testFunction()` porque la expresión de la izquierda falsea toda la expresión.  
  
 Del mismo modo, si la expresión de la izquierda en una expresión lógica con `OrElse` se evalúa como `True` , la ejecución continúa en la siguiente línea de código sin evaluar la expresión de la derecha, ya que la expresión de la izquierda ya ha validado toda la expresión.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Comparación con operadores que no son de cortocircuito  

 Por el contrario, los dos lados del operador lógico se evalúan cuando se usan los operadores lógicos `And` y `Or` . Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 En el ejemplo anterior `testFunction()` se llama a, aunque la expresión de la izquierda se evalúe como `False` .  
  
## <a name="parenthetical-expressions"></a>Expresiones entre paréntesis  

 Puede usar paréntesis para controlar el orden de evaluación de las Expresiones booleanas. Las expresiones entre paréntesis se evalúan primero. En el caso de varios niveles de anidamiento, la prioridad se concede a las expresiones más anidadas. Entre paréntesis, la evaluación continúa según las reglas de prioridad de los operadores. Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit en Visual Basic](logical-and-bitwise-operators.md)
- [Comparaciones de valores](value-comparisons.md)
- [Instrucciones](../statements.md)
- [Operadores de comparación](../../../language-reference/operators/comparison-operators.md)
- [Combinación eficaz de operadores](efficient-combination-of-operators.md)
- [Prioridad de operador en Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md)
