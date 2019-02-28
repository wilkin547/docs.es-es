---
title: Filtrar Definir un operador (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 1e7d767b1ba370ac7303abfd8aa3606a43c33de9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973293"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Procedimiento Definir un operador (Visual Basic)
Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*`, `<>`, o `And`) cuando uno o ambos de los operandos es del tipo de la clase o estructura.  
  
 Definir el operador estándar como un procedimiento de operador dentro de la clase o estructura. Todos los procedimientos de operador deben ser `Public` `Shared`.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define la `+` operador para una estructura denominada `height`. La estructura utiliza altos que se miden en metros. Una *pulgadas* es 2,54 centímetros y uno *foot* 12 pulgadas. Para garantizar que los valores normalizados (pulgadas < 12.0), el constructor realiza *módulo* 12 aritmético. El `+` operador utiliza el constructor para generar los valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Puede probar la estructura `height` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  
  
  
## <a name="see-also"></a>Vea también
- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Cómo: Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Cómo: Usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md)
