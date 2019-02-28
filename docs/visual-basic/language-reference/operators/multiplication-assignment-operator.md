---
title: '*= (Operador, Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: d672ac147a4d7b2c21f4fcb7ee6cdf91b8b4924b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965337"
---
# <a name="-operator-visual-basic"></a>*= (Operador, Visual Basic)
Multiplica el valor de una propiedad o variable por el valor de una expresión y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `*=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `*=` operador primero multiplica el valor de la expresión (en el lado derecho del operador) por el valor de la variable o propiedad (en el lado izquierdo del operador). El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.  
  
## <a name="overloading"></a>Sobrecarga  
 El [* operador](../../../visual-basic/language-reference/operators/multiplication-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `*` operador afecta al comportamiento de la `*=` operador. Si el código usa `*=` en una clase o estructura que sobrecarga `*`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `*=` operador Multiplicar uno `Integer` variable por un segundo y asigna el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vea también
- [Operador *](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
