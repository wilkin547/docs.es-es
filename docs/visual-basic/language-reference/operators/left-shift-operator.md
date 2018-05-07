---
title: '&lt;&lt; (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: bdec015309526aeac2499bc7b459b6ccab6f1e4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt; (Operador) (Visual Basic)
Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Valor numérico integral. El resultado de desplazar el patrón de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Requerido. Expresión numérica integral. El patrón de bits que se va a desplazar. El tipo de datos debe ser un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Requerido. Expresión numérica. El número de bits para desplazar el patrón de bits. El tipo de datos debe ser `Integer` o amplían `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo. En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits vacantes a la derecha se establecen en cero.  
  
 Para evitar que un cambio más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que se corresponde con el tipo de datos de `pattern`. El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos de `pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y enmascara con la máscara de tamaño adecuado.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
> [!NOTE]
>  El `<<` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `<<` operador para realizar operaciones aritméticas izquierda en valores enteros. El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `result1` es 192 (0000 0000 1100 0000).  
  
-   `result2` es 3072 (0000 1100 0000 0000).  
  
-   `result3` es de -32768 (1000 0000 0000 0000).  
  
-   `result4` es de tipo 384 (0000 0001 1000 0000).  
  
-   `result5` es 0 (se desplaza 15 posiciones a la izquierda).  
  
 La cantidad de desplazamiento para `result4` se calcula como 17 AND 15, lo que es igual a 1.  
  
## <a name="see-also"></a>Vea también  
 [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operador <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
