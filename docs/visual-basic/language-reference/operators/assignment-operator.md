---
title: = (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874826"
---
# <a name="-operator-visual-basic"></a>= (Operador, Visual Basic)

Asigna un valor a una variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Partes  

 `variableorproperty`  
 Cualquier variable que se pueda escribir o cualquier propiedad.  
  
 `value`  
 Cualquier literal, constante o expresión.  
  
## <a name="remarks"></a>Comentarios  

 El elemento del lado izquierdo del signo igual ( `=` ) puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md). El `=` operador asigna el valor de su derecha a la variable o propiedad de su izquierda.  
  
> [!NOTE]
> El `=` operador también se usa como operador de comparación. Para obtener más información, vea [operadores de comparación](comparison-operators.md).  
  
## <a name="overloading"></a>Sobrecarga  

 El `=` operador solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra el operador de asignación. El valor de la derecha se asigna a la variable de la izquierda.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Consulte también

- [&= (operador)](and-assignment-operator.md)
- [* = (Operador)](multiplication-assignment-operator.md)
- [Operador + =](addition-assignment-operator.md)
- [-= (Operador) (Visual Basic)](subtraction-assignment-operator.md)
- [/= (Operador) (Visual Basic)](floating-point-division-assignment-operator.md)
- [\\= (Operador)](integer-division-assignment-operator.md)
- [Operador ^ =](exponentiation-assignment-operator.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
- [Operadores de comparación](comparison-operators.md)
- [ReadOnly](../modifiers/readonly.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
