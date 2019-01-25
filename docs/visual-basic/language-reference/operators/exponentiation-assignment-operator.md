---
title: ^= (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 73705df376284edd9d8f20baaf4306c41b1d3943
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699732"
---
# <a name="-operator-visual-basic"></a>^= (Operador, Visual Basic)
Eleva el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `^=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `^=` operador genera el valor de la variable o propiedad (en el lado izquierdo del operador) en primer lugar a la potencia del valor de la expresión (en el lado derecho del operador). El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.  
  
 Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md). Operandos de cualquier otro tipo se convierten en `Double`, y el resultado es siempre `Double`.  
  
 El valor de `expression` puede ser fraccionario, negativo o ambos.  
  
## <a name="overloading"></a>Sobrecarga  
 El [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `^` operador afecta al comportamiento de la `^=` operador. Si el código usa `^=` en una clase o estructura que sobrecarga `^`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `^=` operador para generar el valor de uno `Integer` variable a la potencia de una segunda variable y asigna el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Operador ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
