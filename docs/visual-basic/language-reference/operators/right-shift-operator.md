---
title: '>> Operador (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 8803dc2e25edde756958a243d429dd30c5c78bcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053293"
---
# <a name="-operator-visual-basic"></a>>> (Operador) (Visual Basic)
Realiza un desplazamiento aritmético a la derecha en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor numérico integral. El resultado de desplazar el patrón de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio. Expresión numérica integral. Patrón de bits que se van a desplazar. El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica. El número de bits para desplazar el patrón de bits. El tipo de datos debe ser `Integer` o ampliarse a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits que se desplazan más allá de la posición de bit por la derecha y se propaga el bit más a la izquierda (inicio de sesión) en las posiciones de bits vacantes a la izquierda. Esto significa que si `pattern` tiene un valor negativo, las posiciones vacantes se establecen en uno; de lo contrario, se establecen en cero.  
  
 Tenga en cuenta que los tipos de datos `Byte`, `UShort`, `UInteger`, y `ULong` están firmados, así que no hay ningún bit de signo se propague. Si `pattern` es de cualquier tipo de unsigned, las posiciones vacías siempre se establecen en cero.  
  
 Para evitar que se desplace más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`. La operación AND binario de estos valores se utiliza para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos `pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuado.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="overloading"></a>Sobrecarga  
 El `>>` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `>>` operador para realizar aritméticos desplazamientos a la derecha en los valores enteros. El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `result1` es 2560 (0000 1010 0000 0000).  
  
- `result2` es de 160 (0000 0000 1010 0000).  
  
- `result3` es 2 (0000 0000 0000 0010).  
  
- `result4` es de 640 (0000 0010 1000 0000).  
  
- `result5` es 0 (se desplaza 15 posiciones a la derecha).  
  
 La cantidad de desplazamiento para `result4` se calcula como 18 y 15, que es igual a 2.  
  
 El ejemplo siguiente muestra los desplazamientos aritméticos en un valor negativo.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `negresult1` es -512 (1111 1110 0000 0000).  
  
- `negresult2` es -1 (se propaga el bit de signo).  
  
## <a name="see-also"></a>Vea también

- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operador >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
