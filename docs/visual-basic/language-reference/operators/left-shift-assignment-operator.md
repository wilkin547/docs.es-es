---
title: << = (operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: da2b5ca0b7538d77c3c8d8bc7d45712d656ce63a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768321"
---
# <a name="-operator-visual-basic"></a>\<\<= (Operador) (Visual Basic)
Realiza un desplazamiento aritmético a la izquierda en el valor de una propiedad o variable y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Variable o propiedad de tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica de un tipo de datos que se amplía a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `<<=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `<<=` operador primero realiza un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad. El operador, a continuación, asigna el resultado de esa operación a esa variable o propiedad.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo. En un desplazamiento aritmético a la izquierda, se descartan los bits que se desplazan más allá del intervalo del tipo de datos del resultado y las posiciones de bits vacantes en la parte derecha se establecen en cero.  
  
## <a name="overloading"></a>Sobrecarga  
 El [<< operador](../../../visual-basic/language-reference/operators/left-shift-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `<<` operador afecta al comportamiento de la `<<=` operador. Si el código usa `<<=` en una clase o estructura que sobrecarga `<<`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `<<=` operador de desplazamiento del patrón de bits de un `Integer` variable de la izquierda la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Vea también

- [Operador <<](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
