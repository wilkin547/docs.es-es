---
title: '>> Operador'
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
ms.openlocfilehash: cabf8c569435cc0fc98282f5e8f5fd410e6708dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347823"
---
# <a name="-operator-visual-basic"></a>Operador de > de > (Visual Basic)
Realiza un desplazamiento aritmético a la derecha en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor numérico entero. Resultado de desplazar el modelo de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio. Expresión numérica entera. Patrón de bits que se va a desplazar. El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica. Número de bits que se va a desplazar el modelo de bits. El tipo de datos debe `Integer`se o ampliarse a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición del bit más a la derecha y el bit de la izquierda (signo) se propaga a las posiciones de bits que quedan a la izquierda. Esto significa que si `pattern` tiene un valor negativo, las posiciones vacantes se establecen en uno; de lo contrario, se establecen en cero.  
  
 Tenga en cuenta que los tipos de datos `Byte`, `UShort`, `UInteger`y `ULong` no tienen signo, por lo que no hay ningún bit de signo que propagar. Si `pattern` es de cualquier tipo sin signo, las posiciones vacías siempre se establecen en cero.  
  
 Para evitar el desplazamiento por más bits del que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`. El binario y estos valores se usan para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos de `pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="overloading"></a>Sobrecarga  
 El operador de `>>` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `>>` para realizar los desplazamientos aritméticos a la derecha en los valores enteros. El resultado siempre tiene el mismo tipo de datos que la expresión que se está desplazando.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `result1` es 2560 (0000 1010 0000 0000).  
  
- `result2` es 160 (0000 0000 1010 0000).  
  
- `result3` es 2 (0000 0000 0000 0010).  
  
- `result4` es 640 (0000 0010 1000 0000).  
  
- `result5` es 0 (se desplazan 15 posiciones a la derecha).  
  
 La cantidad de desplazamiento de `result4` se calcula como 18 y 15, que es igual a 2.  
  
 En el ejemplo siguiente se muestran los cambios aritméticos en un valor negativo.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `negresult1` es-512 (1111 1110 0000 0000).  
  
- `negresult2` es-1 (el bit de signo se propaga).  
  
## <a name="see-also"></a>Vea también

- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operador >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
