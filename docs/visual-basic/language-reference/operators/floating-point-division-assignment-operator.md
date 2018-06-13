---
title: /= (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 642307bc531e7d9ce21a932b112795b35e7b3182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604099"
---
# <a name="-operator-visual-basic"></a>/= (Operador, Visual Basic)
Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Requerido. Cualquier propiedad o variable numérica.  
  
 `expression`  
 Requerido. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `/=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `/=` operador divide primero el valor de la variable o propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador). El operador, a continuación, asigna el resultado de esa operación de punto flotante a la variable o propiedad.  
  
 Esta instrucción asigna un `Double` valor a la variable o propiedad de la izquierda. Si `Option Strict` es `On`, `variableorproperty` debe ser un `Double`. Si `Option Strict` es `Off`, Visual Basic realiza una conversión implícita y asigna el valor resultante al `variableorproperty`, con un posible error en tiempo de ejecución. Para obtener más información, consulte [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecarga de la `/` operador afecta al comportamiento de la `/=` operador. Si el código usa `/=` en una clase o estructura que sobrecarga `/`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `/=` operador que se va a dividir uno `Integer` variable por un segundo y asignar el cociente a la primera variable.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [/ (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [\\= (Operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
