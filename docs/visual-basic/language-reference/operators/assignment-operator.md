---
title: = (Operador, Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 47b69a908f12ec36daf2848da6ee4b04895fd3a4
ms.lasthandoff: 03/13/2017

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
 El elemento en el lado izquierdo del signo igual (`=`) puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). El `=` operador asigna el valor situado a su derecha a la variable o propiedad de su izquierda.  
  
> [!NOTE]
>  El `=` operador también se utiliza como un operador de comparación. Para obtener más información, consulte [operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `=` operador se puede sobrecargar sólo como un operador de comparación relacional, no como un operador de asignación. Para obtener más información, consulte [procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el operador de asignación. El valor de la derecha se asigna a la variable de la izquierda.  
  
 [!code-vb[VbVbalrOperators&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Aspecto = (operador)](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [* = (Operador)](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [+= (Operador)](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [-= (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [/ = (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\= (Operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [^ = (Operador)](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Sólo lectura](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

