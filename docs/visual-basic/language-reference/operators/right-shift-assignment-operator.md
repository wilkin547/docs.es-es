---
title: '&gt;&gt;= (Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;= (Operador) (Visual Basic)
Realiza un desplazamiento aritmético a la derecha en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Variable o propiedad de un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obligatorio. Expresión numérica de un tipo de datos que se amplíe a `Integer`.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `>>=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `>>=` operador primero realiza un desplazamiento aritmético a la derecha en el valor de la variable o propiedad. El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit de la derecha y el bit de la izquierda se propaga a las posiciones de bits vacantes a la izquierda. Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacantes se establecen en uno. Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.  
  
## <a name="overloading"></a>Sobrecarga  
 El [>> operador](../../../visual-basic/language-reference/operators/right-shift-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecarga de la `>>` operador afecta al comportamiento de la `>>=` operador. Si el código usa `>>=` en una clase o estructura que sobrecarga `>>`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `>>=` operador de desplazamiento del patrón de bits de un `Integer` variable derecha por la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Operador >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operadores de desplazamiento de bits](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
