---
title: << (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: e11dbc453934f1aac4a8092cdc6539ec11f0cc21
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663180"
---
# <a name="-operator-visual-basic"></a>\<\< Operador (Visual Basic)
Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor numérico integral. El resultado de desplazar el patrón de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio. Expresión numérica integral. Patrón de bits que se van a desplazar. El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica. El número de bits para desplazar el patrón de bits. El tipo de datos debe ser `Integer` o ampliarse a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo. En un desplazamiento aritmético a la izquierda, se descartan los bits que se desplazan más allá del intervalo del tipo de datos del resultado y las posiciones de bits vacantes en la parte derecha se establecen en cero.  
  
 Para evitar que un cambio más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que se corresponde con el tipo de datos de `pattern`. La operación AND binario de estos valores se utiliza para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos `pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuado.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
> [!NOTE]
>  El `<<` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que comprende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `<<` operador para realizar operaciones aritméticas izquierda en los valores enteros. El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `result1` es 192 (0000 0000 0000 de 1100).  
  
- `result2` es 3072 (0000 1100 0000 0000).  
  
- `result3` es de -32768 (1000 0000 0000 0000).  
  
- `result4` es de tipo 384 (0000 0001 1000 0000).  
  
- `result5` es 0 (se desplaza 15 posiciones a la izquierda).  
  
 La cantidad de desplazamiento para `result4` se calcula como 17 y 15, que es igual a 1.  
  
## <a name="see-also"></a>Vea también

- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operador <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
