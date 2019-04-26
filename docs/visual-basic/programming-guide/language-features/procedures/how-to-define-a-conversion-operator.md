---
title: Procedimiento Definir un operador de conversión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863719"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Procedimiento Definir un operador de conversión (Visual Basic)
Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer`, `Double`, o `String`).  
  
 Definir la conversión de tipos como un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedimiento dentro de la clase o estructura. Todos los procedimientos de conversión deben ser `Public Shared`, y cada uno debe especificar [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) o [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define los operadores de conversión entre una estructura denominada `digit` y un `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Puede probar la estructura `digit` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un operador](./how-to-define-an-operator.md)
- [Cómo: Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Cómo: Usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
