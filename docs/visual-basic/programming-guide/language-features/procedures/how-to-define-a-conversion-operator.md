---
title: 'Cómo: Definir un operador de conversión'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344900"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Cómo: Definir un operador de conversión (Visual Basic)
Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer`, `Double`o `String`).  
  
 Defina la conversión de tipos como un procedimiento de [función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md) dentro de la clase o estructura. Todos los procedimientos de conversión deben ser `Public Shared`, y cada uno de ellos debe especificar la [ampliación](../../../../visual-basic/language-reference/modifiers/widening.md) o la [restricción](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se definen operadores de conversión entre una estructura denominada `digit` y una `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Puede probar la estructura `digit` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un operador](./how-to-define-an-operator.md)
- [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
