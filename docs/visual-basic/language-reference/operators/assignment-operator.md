---
title: = (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603605"
---
# <a name="-operator-visual-basic"></a>= (Operador, Visual Basic)
Asigna un valor a una variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Cualquier variable de escritura o cualquier propiedad.  
  
 `value`  
 Cualquier literal, una constante o una expresión.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo del signo igual (`=`) puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). El `=` operador asigna el valor de su derecha a la variable o propiedad de su izquierda.  
  
> [!NOTE]
>  El `=` operador también se utiliza como un operador de comparación. Para obtener más información, consulte [operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `=` operador se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el operador de asignación. El valor de la derecha se asigna a la variable de la izquierda.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Operador &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Operador *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [-= (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\= (Operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [Operador ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
