---
title: Operadores lógicos y bit a bit en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operadores lógicos y bit a bit en Visual Basic
Los operadores lógicos comparan `Boolean` expresiones y devuelven un `Boolean` resultado. El `And`, `Or`, `AndAlso`, `OrElse`, y `Xor` operadores son *binario* porque toman dos operandos, mientras el `Not` operador es *unario* porque toma un solo operando. Algunos de estos operadores también pueden realizar operaciones lógicas bit a bit de valores enteros.  
  
## <a name="unary-logical-operator"></a>Operador lógico unario  
 El [Not (operador)](../../../../visual-basic/language-reference/operators/not-operator.md) realiza lógico *negación* en un `Boolean` expresión. Produce el contrario lógico de su operando. Si la expresión se evalúa como `True`, a continuación, `Not` devuelve `False`; si la expresión se evalúa como `False`, a continuación, `Not` devuelve `True`. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a>Operadores lógicos binarios  
 El [operador y](../../../../visual-basic/language-reference/operators/and-operator.md) realiza lógico *junto* con dos `Boolean` expresiones. Si ambas expresiones se evalúan como `True`, a continuación, `And` devuelve `True`. Si al menos una de las expresiones se evalúa como `False`, a continuación, `And` devuelve `False`.  
  
 El [operador o](../../../../visual-basic/language-reference/operators/or-operator.md) realiza lógico *disyunción* o *inclusión* con dos `Boolean` expresiones. Si alguna de las expresiones se evalúa como `True`, o ambos se evalúan en `True`, a continuación, `Or` devuelve `True`. Si ninguna de las expresiones se evalúa como `True`, `Or` devuelve `False`.  
  
 El [XOR (operador)](../../../../visual-basic/language-reference/operators/xor-operator.md) realiza lógico *exclusión* con dos `Boolean` expresiones. Si una expresión se evalúa como `True`, pero no a ambos, `Xor` devuelve `True`. Si ambas expresiones se evalúan como `True` o ambos se evalúan en `False`, `Xor` devuelve `False`.  
  
 En el ejemplo siguiente se muestra la `And`, `Or`, y `Xor` operadores.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a>Operaciones lógicas evaluación "cortocircuitada"  
 El [AndAlso (operador)](../../../../visual-basic/language-reference/operators/andalso-operator.md) es muy similar a la `And` (operador), ya que también realiza la conjunción lógica en dos `Boolean` expresiones. La diferencia clave entre los dos es que `AndAlso` exhibe *evaluación "cortocircuitada"* comportamiento. Si la primera expresión en una `AndAlso` expresión se evalúa como `False`, no se evalúa la segunda expresión ya que no puede modificar el resultado final, y `AndAlso` devuelve `False`.  
  
 De forma similar, el [OrElse (operador)](../../../../visual-basic/language-reference/operators/orelse-operator.md) realiza la evaluación "cortocircuitada" disyunción lógica entre dos `Boolean` expresiones. Si la primera expresión en una `OrElse` expresión se evalúa como `True`, no se evalúa la segunda expresión ya que no puede modificar el resultado final, y `OrElse` devuelve `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Ventajas y desventajas de evaluación "cortocircuitada"  
 Evaluación "cortocircuitada" puede mejorar el rendimiento mediante la evaluación no de una expresión que no se puede modificar el resultado de la operación lógica. Sin embargo, si esa expresión realiza acciones adicionales, evaluación "cortocircuitada" omite esas acciones. Por ejemplo, si la expresión incluye una llamada a un `Function` procedimiento, que el procedimiento no se llama si la expresión se cortocircuita y ningún código adicional contenida en el `Function` no se ejecuta. Por lo tanto, la función puede ejecutarse sólo ocasionalmente y no se pueden probar correctamente. O podría dependen de la lógica del programa en el código en el `Function`.  
  
 En el ejemplo siguiente se muestra la diferencia entre `And`, `Or`y sus homólogos de evaluación "cortocircuitada".  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 En el ejemplo anterior, tenga en cuenta que parte de código importante dentro de `checkIfValid()` no se ejecuta cuando se cortocircuita la llamada. La primera `If` instrucción llama `checkIfValid()` aunque `12 > 45` devuelve `False`, porque `And` no cortocircuita. El segundo `If` no llama la instrucción `checkIfValid()`, porque cuando `12 > 45` devuelve `False`, `AndAlso` cortocircuita la segunda expresión. La tercera `If` instrucción llama `checkIfValid()` aunque `12 < 45` devuelve `True`, porque `Or` no cortocircuita. El cuarto `If` no llama la instrucción `checkIfValid()`, porque cuando `12 < 45` devuelve `True`, `OrElse` cortocircuita la segunda expresión.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  
 Operaciones bit a bit evalúan dos valores enteros en formato binario (base 2). Se comparan los bits en las posiciones correspondientes y, a continuación, asignan valores basados en la comparación. En el ejemplo siguiente se muestra el `And` operador.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 En el ejemplo anterior se establece el valor de `x` en 1. Esto ocurre por las razones siguientes:  
  
-   Los valores se tratan como binarios:  
  
     3 en formato binario = 011  
  
     5 en formato binario = 101  
  
-   El `And` operador compara las representaciones binarias, una posición binaria (bit) a la vez. Si ambos bits en una posición determinada son 1, 1 se coloca en esa posición en el resultado. Si cualquiera de los bits es 0, entonces se coloca un 0 en esa posición en el resultado. En el ejemplo anterior se resuelve como sigue:  
  
     011 (3 en formato binario)  
  
     101 (5 en formato binario)  
  
     001 (el resultado, en formato binario)  
  
-   El resultado se trata como decimal. El valor 001 es la representación binaria de 1, por lo que `x` = 1.  
  
 Bit a bit `Or` operación es similar, salvo que se asigna un 1 al bit de resultado si uno o ambos de los bits comparados es 1. `Xor` asigna un 1 al bit de resultado si exactamente uno de los bits comparados (no ambos) es 1. `Not` toma un solo operando, invierte todos los bits, incluido el bit de signo y asigna ese valor al resultado. Esto significa que para números con signo positivos, `Not` siempre devuelve un valor negativo y para los números negativos, `Not` siempre devuelve el valor cero o positivo.  
  
 El `AndAlso` y `OrElse` operadores no admiten operaciones bit a bit.  
  
> [!NOTE]
>  Operaciones bit a bit pueden realizarse en solo tipos enteros. Valores de punto flotante se deben convertir a tipos enteros para que pueda continuar la operación bit a bit.  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos y bit a bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
