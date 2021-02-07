---
description: 'Más información acerca de: operador de  << (Visual Basic)'
title: Operador <<
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 079af61e5c4ce3834db0877feace724c74c8169c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665632"
---
# <a name="-operator-visual-basic"></a>\<\< Operador (Visual Basic)

Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a>Partes  

 `result`  
 Necesario. Valor numérico entero. Resultado de desplazar el modelo de bits. El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio. Expresión numérica integral. Modelo de bits que se va a desplazar. El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica. Número de bits que se va a desplazar el modelo de bits. El tipo de datos debe ser `Integer` o ampliarse a `Integer`.  
  
## <a name="remarks"></a>Observaciones  

 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.  
  
 Para evitar que un desplazamiento entre más bits que el resultado pueda contener, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que corresponde al tipo de datos de `pattern` . El binario y estos valores se usan para la cantidad de desplazamiento. Las máscaras de tamaño son las siguientes:  
  
|Tipo de datos de `pattern`|Máscara de tamaño (decimal)|Máscara de tamaño (hexadecimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern` . Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
> [!NOTE]
> El `<<` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `<<` operador para realizar los desplazamientos aritméticos a la izquierda en valores enteros. El resultado siempre tiene el mismo tipo de datos que la expresión que se está desplazando.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
- `result1` es 192 (0000 0000 1100 0000).  
  
- `result2` es 3072 (0000 1100 0000 0000).  
  
- `result3` es-32768 (1000 0000 0000 0000).  
  
- `result4` es 384 (0000 0001 1000 0000).  
  
- `result5` es 0 (se desplazan 15 posiciones hacia la izquierda).  
  
 La cantidad de desplazamiento de `result4` se calcula como 17 y 15, que es igual a 1.  
  
## <a name="see-also"></a>Vea también

- [Operadores de desplazamiento de bits](bit-shift-operators.md)
- [Operadores de asignación](assignment-operators.md)
- [<<= (operador)](left-shift-assignment-operator.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
