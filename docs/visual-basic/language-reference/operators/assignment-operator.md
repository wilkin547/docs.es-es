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
ms.openlocfilehash: 58dcdfd21fd8701c6ac391672e768819f696aab9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643561"
---
# <a name="-operator-visual-basic"></a>= (Operador, Visual Basic)
Asigna un valor a una variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Cualquier variable de lectura o de cualquier propiedad.  
  
 `value`  
 Cualquier literal, constante o expresión.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo del signo igual (`=`) puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). El `=` operador asigna el valor de su derecho de la variable o propiedad a su izquierda.  
  
> [!NOTE]
>  El `=` operador también se utiliza como un operador de comparación. Para obtener más información, consulte [operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `=` operador se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra el operador de asignación. El valor de la derecha se asigna a la variable de la izquierda.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Operador &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operador *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [-= (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\\= Operador](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operador ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
- [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
