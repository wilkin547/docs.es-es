---
title: '\= Operador (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842543"
---
# <a name="-operator"></a>\\= Operador
Divide el valor de una propiedad o variable por el valor de una expresión y asigna el resultado entero a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `\=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `\=` operador divide el valor de una variable o propiedad a su izquierda por el valor de su derecha y asigna el resultado entero a la variable o propiedad a su izquierda.  
  
 Para obtener más información sobre la división de enteros, vea [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `\` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `\` operador afecta al comportamiento de la `\=` operador. Si el código usa `\=` en una clase o estructura que sobrecarga `\`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `\=` operador dividir una `Integer` variable por segundo y asignar el entero como resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vea también

- [\ (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
