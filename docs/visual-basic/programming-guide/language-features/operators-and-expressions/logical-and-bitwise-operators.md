---
description: 'Más información sobre: operadores lógicos y bit a bit en Visual Basic'
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
ms.openlocfilehash: 55d9567813a9114573e1e3f70fe181cb8621b350
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472727"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operadores lógicos y bit a bit en Visual Basic

Los operadores lógicos comparan `Boolean` expresiones y devuelven un `Boolean` resultado. Los `And` `Or` operadores,, `AndAlso` , `OrElse` y `Xor` son *binarios* porque toman dos operandos, mientras que el `Not` operador es *unario* porque toma un solo operando. Algunos de estos operadores también pueden realizar operaciones lógicas bit a bit en valores enteros.  
  
## <a name="unary-logical-operator"></a>Operador lógico unario  

 El [operador not](../../../language-reference/operators/not-operator.md) realiza una *negación* lógica en una `Boolean` expresión. Produce el contrario lógico de su operando. Si la expresión se evalúa como `True` , `Not` devuelve `False` ; si la expresión se evalúa como `False` , entonces `Not` devuelve `True` . Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operadores lógicos binarios  

 El [operador and](../../../language-reference/operators/and-operator.md) realiza una *conjunción* lógica entre dos `Boolean` expresiones. Si ambas expresiones se evalúan como `True` , `And` devuelve `True` . Si al menos una de las expresiones se evalúa como `False` , entonces `And` devuelve `False` .  
  
 El [operador OR](../../../language-reference/operators/or-operator.md) realiza una *disyunción* lógica o una *inclusión* en dos `Boolean` expresiones. Si una de las expresiones se evalúa como `True` , o ambos se evalúan como `True` , entonces `Or` devuelve `True` . Si ninguna de las expresiones se evalúa como `True` , `Or` devuelve `False` .  
  
 El [operador XOR](../../../language-reference/operators/xor-operator.md) realiza una *exclusión* lógica en dos `Boolean` expresiones. Si exactamente una expresión se evalúa como `True` , pero no ambos, `Xor` devuelve `True` . Si ambas expresiones se evalúan como `True` o se evalúan como `False` , `Xor` devuelve `False` .  
  
 En el ejemplo siguiente se muestran `And` los `Or` operadores, y `Xor` .  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Short-Circuiting operaciones lógicas  

 El [operador AndAlso](../../../language-reference/operators/andalso-operator.md) es muy similar al `And` operador, ya que también realiza una conjunción lógica de dos `Boolean` expresiones. La diferencia clave entre ambos es que `AndAlso` exhibe *un comportamiento de cortocircuito* . Si la primera expresión de una `AndAlso` expresión se evalúa como `False` , la segunda expresión no se evalúa porque no puede modificar el resultado final y `AndAlso` devuelve `False` .  
  
 Del mismo modo, el [operador OrElse](../../../language-reference/operators/orelse-operator.md) realiza una disyunción lógica de cortocircuito en dos `Boolean` expresiones. Si la primera expresión de una `OrElse` expresión se evalúa como `True` , la segunda expresión no se evalúa porque no puede modificar el resultado final y `OrElse` devuelve `True` .  
  
### <a name="short-circuiting-trade-offs"></a>Short-Circuiting Trade-Offs  

 El cortocircuito puede mejorar el rendimiento al no evaluar una expresión que no pueda modificar el resultado de la operación lógica. Sin embargo, si esa expresión realiza acciones adicionales, el cortocircuito omite esas acciones. Por ejemplo, si la expresión incluye una llamada a un `Function` procedimiento, no se llama a ese procedimiento si la expresión se cortocircuita y no se ejecuta ningún código adicional incluido en `Function` . Por lo tanto, la función puede ejecutarse solo ocasionalmente y no se puede probar correctamente. O la lógica del programa podría depender del código del `Function` .  
  
 En el ejemplo siguiente se muestra la diferencia entre `And` , `Or` y sus homólogos de cortocircuito.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 En el ejemplo anterior, tenga en cuenta que algunos códigos importantes `checkIfValid()` de no se ejecutan cuando la llamada está en cortocircuito. La primera `If` instrucción llama a `checkIfValid()` aunque `12 > 45` devuelve `False` , porque `And` no cortocircuita. La segunda `If` instrucción no llama a `checkIfValid()` porque, cuando `12 > 45` devuelve `False` , `AndAlso` cortocircuita la segunda expresión. La tercera `If` instrucción llama a `checkIfValid()` aunque `12 < 45` devuelve `True` , porque `Or` no cortocircuita. La cuarta `If` instrucción no llama a `checkIfValid()` porque, cuando `12 < 45` devuelve `True` , `OrElse` cortocircuita la segunda expresión.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  

 Las operaciones bit a bit evalúan dos valores enteros en formato binario (base 2). Comparan los bits en las posiciones correspondientes y, a continuación, asignan valores basados en la comparación. En el siguiente ejemplo se muestra el `And` operador.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 En el ejemplo anterior se establece el valor de `x` en 1. Esto sucede por los siguientes motivos:  
  
- Los valores se tratan como binarios:  
  
     3 en formato binario = 011  
  
     5 en formato binario = 101  
  
- El `And` operador compara las representaciones binarias, una posición binaria (bit) a la vez. Si los dos bits de una posición determinada son 1, se coloca un 1 en esa posición en el resultado. Si alguno de los bits es 0, se coloca un 0 en esa posición en el resultado. En el ejemplo anterior, esto funciona de la siguiente manera:  
  
     011 (3 en formato binario)  
  
     101 (5 en formato binario)  
  
     001 (el resultado, en formato binario)  
  
- El resultado se trata como decimal. El valor 001 es la representación binaria de 1, por lo que `x` = 1.  
  
 La `Or` operación bit a bit es similar, salvo que se asigna 1 al bit de resultado si uno de los bits comparados es 1 o ambos. `Xor` asigna un 1 al bit de resultado si exactamente uno de los bits comparados (no ambos) es 1. `Not` toma un solo operando e invierte todos los bits, incluido el bit de signo, y asigna ese valor al resultado. Esto significa que para los números positivos con signo, `Not` siempre devolverá un valor negativo y, en el caso de números negativos, `Not` siempre devolverá un valor positivo o cero.  
  
 Los `AndAlso` `OrElse` operadores y no admiten las operaciones bit a bit.  
  
> [!NOTE]
> Las operaciones bit a bit solo se pueden realizar en tipos enteros. Los valores de punto flotante se deben convertir en tipos enteros antes de que pueda continuar la operación bit a bit.  
  
## <a name="see-also"></a>Consulte también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Expresiones booleanas](boolean-expressions.md)
- [Operadores aritméticos en Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operadores de concatenación en Visual Basic](concatenation-operators.md)
- [Combinación eficaz de operadores](efficient-combination-of-operators.md)
