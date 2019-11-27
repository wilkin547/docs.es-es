---
title: Operador <<=
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
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350953"
---
# <a name="-operator-visual-basic"></a>\<\<= operador (Visual Basic)
Realiza un desplazamiento aritmético a la izquierda en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Variable o propiedad de un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica de un tipo de datos que se amplía a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 El elemento del lado izquierdo del operador `<<=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador `<<=` primero realiza un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad. A continuación, el operador asigna de nuevo el resultado de la operación a esa variable o propiedad.  
  
 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.  
  
## <a name="overloading"></a>Sobrecarga  
 Se puede *sobrecargar*el [operador < <](../../../visual-basic/language-reference/operators/left-shift-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del operador `<<` afecta al comportamiento del operador `<<=`. Si el código usa `<<=` en una clase o estructura que sobrecarga `<<`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `<<=` para desplazar el modelo de bits de una variable de `Integer` a la izquierda en la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Vea también

- [Operador <<](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
