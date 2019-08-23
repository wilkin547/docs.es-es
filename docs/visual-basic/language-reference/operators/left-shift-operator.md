---
title: Operador de < de < (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: d6b186ad519bcd7cf82cce12523f2d75e09317cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966883"
---
# <a name="-operator-visual-basic"></a>\<\<Operador (Visual Basic)
Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Valor numérico entero. Resultado de desplazar el modelo de bits. El tipo de datos es el mismo que el `pattern`de.  
  
 `pattern`  
 Necesario. Expresión numérica entera. Patrón de bits que se va a desplazar. El tipo de datos debe ser un tipo entero`SByte`( `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Necesario. Expresión numérica. Número de bits que se va a desplazar el modelo de bits. El tipo de datos debe `Integer` ser o ampliarse a. `Integer`  
  
## <a name="remarks"></a>Comentarios  
 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.  
  
 Para evitar que un desplazamiento entre más bits que el resultado pueda contener, Visual Basic enmascara el valor `amount` de con una máscara de tamaño que corresponde al tipo de `pattern`datos de. El binario y estos valores se usan para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos de`pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`. Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
> [!NOTE]
> El `<<` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `<<` usa el operador para realizar los desplazamientos aritméticos a la izquierda en valores enteros. El resultado siempre tiene el mismo tipo de datos que la expresión que se está desplazando.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `result1`es 192 (0000 0000 1100 0000).  
  
- `result2`es 3072 (0000 1100 0000 0000).  
  
- `result3`es-32768 (1000 0000 0000 0000).  
  
- `result4`es 384 (0000 0001 1000 0000).  
  
- `result5`es 0 (se desplazan 15 posiciones hacia la izquierda).  
  
 La cantidad de desplazamiento `result4` de se calcula como 17 y 15, que es igual a 1.  
  
## <a name="see-also"></a>Vea también

- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operador <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
