---
title: '&amp;= (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: fa009168be3781c727cd5a9cb6976b8c16fb2843
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967495"
---
# <a name="amp-operator-visual-basic"></a>&amp;= (Operador) (Visual Basic)
Concatena una `String` expresión a un `String` variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier `String` variable o propiedad.  
  
 `expression`  
 Obligatorio. Cualquier expresión `String` .  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `&=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). El `&=` operador concatena el `String` expresión en su derecho de la `String` variable o propiedad a su izquierda y asigna el resultado a la variable o propiedad a su izquierda.  
  
## <a name="overloading"></a>Sobrecarga  
 El [& operador](../../../visual-basic/language-reference/operators/concatenation-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `&` operador afecta al comportamiento de la `&=` operador. Si el código usa `&=` en una clase o estructura que sobrecarga `&`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `&=` para concatenar dos `String` variables y asigna el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también
- [Operador &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
