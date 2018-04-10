---
title: '&gt;&gt;(Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4eb0ed817c95905a679de5026bf6494eb72df078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;(Operador) (Visual Basic)
Realiza un desplazamiento aritmético a la derecha en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor numérico integral. El resultado de desplazar el patrón de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio. Expresión numérica integral. El patrón de bits que se va a desplazar. El tipo de datos debe ser un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica. El número de bits para desplazar el patrón de bits. El tipo de datos debe ser `Integer` o amplían `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit de la derecha y el bit de la izquierda (inicio de sesión) se propaga a las posiciones de bits vacantes a la izquierda. Esto significa que si `pattern` tiene un valor negativo, las posiciones vacantes se establecen en uno; en caso contrario se establece en cero.  
  
 Tenga en cuenta que los tipos de datos `Byte`, `UShort`, `UInteger`, y `ULong` están firmados, así que no hay ningún bit de signo para propagar. Si `pattern` es de cualquier tipo sin signo, las posiciones vacías siempre se establecen en cero.  
  
 Para evitar que se desplace más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`. El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos de`pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y enmascara con la máscara de tamaño adecuado.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="overloading"></a>Sobrecarga  
 El `>>` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `>>` operador que se va a realizar desplazamientos aritméticos a la derecha en valores enteros. El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `result1`es 2560 (0000 1010 0000 0000).  
  
-   `result2`es de 160 (0000 0000 1010 0000).  
  
-   `result3`es 2 (0000 0000 0000 0010).  
  
-   `result4`es 640 (0000 0010 1000 0000).  
  
-   `result5`es 0 (se desplaza 15 posiciones a la derecha).  
  
 La cantidad de desplazamiento para `result4` se calcula como 18 AND 15, lo que es igual a 2.  
  
 El ejemplo siguiente muestra los desplazamientos aritméticos en un valor negativo.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `negresult1`es -512 (1111 1110 0000 0000).  
  
-   `negresult2`es -1 (se propaga el bit de signo).  
  
## <a name="see-also"></a>Vea también  
 [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operador >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
