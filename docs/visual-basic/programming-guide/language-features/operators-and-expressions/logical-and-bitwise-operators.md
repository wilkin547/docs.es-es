---
title: Operadores lógicos y bit a bit
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
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343592"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operadores lógicos y bit a bit en Visual Basic
Los operadores lógicos comparan expresiones `Boolean` y devuelven un resultado `Boolean`. Los operadores `And`, `Or`, `AndAlso`, `OrElse`y `Xor` son *binarios* porque toman dos operandos, mientras que el operador `Not` es *unario* porque toma un solo operando. Algunos de estos operadores también pueden realizar operaciones lógicas bit a bit en valores enteros.  
  
## <a name="unary-logical-operator"></a>Operador lógico unario  
 El [operador not](../../../../visual-basic/language-reference/operators/not-operator.md) realiza una *negación* lógica en una expresión `Boolean`. Produce el contrario lógico de su operando. Si la expresión se evalúa como `True`, `Not` devuelve `False`; Si la expresión se evalúa como `False`, `Not` devuelve `True`. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operadores lógicos binarios  
 El [operador and](../../../../visual-basic/language-reference/operators/and-operator.md) realiza una *conjunción* lógica entre dos expresiones `Boolean`. Si ambas expresiones se evalúan como `True`, `And` devuelve `True`. Si al menos una de las expresiones se evalúa como `False`, `And` devuelve `False`.  
  
 El [operador OR](../../../../visual-basic/language-reference/operators/or-operator.md) realiza una *disyunción* lógica o una *inclusión* en dos expresiones `Boolean`. Si alguna de las expresiones se evalúa como `True`, o ambos se evalúan como `True`, `Or` devuelve `True`. Si ninguna de las expresiones se evalúa como `True`, `Or` devuelve `False`.  
  
 El [operador XOR](../../../../visual-basic/language-reference/operators/xor-operator.md) realiza una *exclusión* lógica en dos expresiones `Boolean`. Si exactamente una expresión se evalúa como `True`, pero no ambos, `Xor` devuelve `True`. Si ambas expresiones se evalúan como `True` o ambos se evalúan como `False`, `Xor` devuelve `False`.  
  
 En el ejemplo siguiente se muestran los operadores `And`, `Or`y `Xor`.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Operaciones lógicas de cortocircuito  
 El [operador AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) es muy similar al operador `And`, ya que también realiza una conjunción lógica de dos expresiones `Boolean`. La diferencia clave entre ambos es que `AndAlso` exhibe *un comportamiento de cortocircuito* . Si la primera expresión de una expresión `AndAlso` se evalúa como `False`, la segunda expresión no se evalúa porque no puede modificar el resultado final y `AndAlso` devuelve `False`.  
  
 Del mismo modo, el [operador OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) realiza una disyunción lógica de cortocircuito en dos expresiones `Boolean`. Si la primera expresión de una expresión `OrElse` se evalúa como `True`, la segunda expresión no se evalúa porque no puede modificar el resultado final y `OrElse` devuelve `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Equilibrio de cortocircuito  
 El cortocircuito puede mejorar el rendimiento al no evaluar una expresión que no pueda modificar el resultado de la operación lógica. Sin embargo, si esa expresión realiza acciones adicionales, el cortocircuito omite esas acciones. Por ejemplo, si la expresión incluye una llamada a un procedimiento de `Function`, no se llama a ese procedimiento si la expresión se cortocircuita y no se ejecuta ningún código adicional incluido en el `Function`. Por lo tanto, la función puede ejecutarse solo ocasionalmente y no se puede probar correctamente. O la lógica del programa podría depender del código del `Function`.  
  
 En el ejemplo siguiente se muestra la diferencia entre `And`, `Or`y sus homólogos de cortocircuito.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 En el ejemplo anterior, tenga en cuenta que algunos códigos importantes dentro de `checkIfValid()` no se ejecutan cuando la llamada se cortocircuita. La primera instrucción `If` llama a `checkIfValid()` aunque `12 > 45` devuelva `False`, porque `And` no cortocircuita. La segunda instrucción `If` no llama a `checkIfValid()`, porque cuando `12 > 45` devuelve `False`, `AndAlso` cortocircuita la segunda expresión. La tercera `If` instrucción llama a `checkIfValid()` aunque `12 < 45` devuelva `True`, porque `Or` no cortocircuita. La cuarta instrucción `If` no llama a `checkIfValid()`, porque cuando `12 < 45` devuelve `True`, `OrElse` cortocircuita la segunda expresión.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  
 Las operaciones bit a bit evalúan dos valores enteros en formato binario (base 2). Comparan los bits en las posiciones correspondientes y, a continuación, asignan valores basados en la comparación. En el ejemplo siguiente se muestra el operador `And`.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 En el ejemplo anterior se establece el valor de `x` en 1. Esto sucede por los siguientes motivos:  
  
- Los valores se tratan como binarios:  
  
     3 en formato binario = 011  
  
     5 en formato binario = 101  
  
- El operador `And` compara las representaciones binarias, una posición binaria (bit) a la vez. Si los dos bits de una posición determinada son 1, se coloca un 1 en esa posición en el resultado. Si alguno de los bits es 0, se coloca un 0 en esa posición en el resultado. En el ejemplo anterior, esto funciona de la siguiente manera:  
  
     011 (3 en formato binario)  
  
     101 (5 en formato binario)  
  
     001 (el resultado, en formato binario)  
  
- El resultado se trata como decimal. El valor 001 es la representación binaria de 1, por lo que `x` = 1.  
  
 La operación de `Or` bit a bit es similar, salvo que se asigna 1 al bit de resultado si uno de los bits comparados es 1 o ambos. `Xor` asigna un 1 al bit de resultado si exactamente uno de los bits comparados (no ambos) es 1. `Not` toma un solo operando e invierte todos los bits, incluido el bit de signo, y asigna ese valor al resultado. Esto significa que para los números positivos con signo, `Not` siempre devuelve un valor negativo, y para los números negativos, `Not` siempre devuelve un valor positivo o cero.  
  
 Los operadores `AndAlso` y `OrElse` no admiten las operaciones bit a bit.  
  
> [!NOTE]
> Las operaciones bit a bit solo se pueden realizar en tipos enteros. Los valores de punto flotante se deben convertir en tipos enteros antes de que pueda continuar la operación bit a bit.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
