---
title: '>>= (Operador, Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982389"
---
# <a name="-operator-visual-basic"></a>>> = (operador) (Visual Basic)
Realiza un desplazamiento aritmético a la derecha del valor de una propiedad o variable y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Variable o propiedad de tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica de un tipo de datos que se amplía a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `>>=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `>>=` operador primero realiza un desplazamiento aritmético a la derecha del valor de la variable o propiedad. El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits que se desplazan más allá de la posición de bit por la derecha y se propaga el bit situado en las posiciones de bits vacantes a la izquierda. Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacantes se establecen en uno. Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.  
  
## <a name="overloading"></a>Sobrecarga  
 El [>> operador](../../../visual-basic/language-reference/operators/right-shift-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `>>` operador afecta al comportamiento de la `>>=` operador. Si el código usa `>>=` en una clase o estructura que sobrecarga `>>`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `>>=` operador de desplazamiento del patrón de bits de un `Integer` variable directamente por la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- [Operador >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
