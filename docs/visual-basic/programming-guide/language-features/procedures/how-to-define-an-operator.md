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
ms.openlocfilehash: 14aa25de78eb357f8474d3828aa45e48e7a4f9c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126118"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Filtrar Definir un operador (Visual Basic)
Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*`, `<>`, o `And`) cuando uno o ambos de los operandos es del tipo de la clase o estructura.  
  
 Definir el operador estándar como un procedimiento de operador dentro de la clase o estructura. Todos los procedimientos de operador deben ser `Public` `Shared`.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define la `+` operador para una estructura denominada `height`. La estructura utiliza altos que se miden en metros. Una *pulgadas* es 2,54 centímetros y uno *foot* 12 pulgadas. Para garantizar que los valores normalizados (pulgadas < 12.0), el constructor realiza *módulo* 12 aritmético. El `+` operador utiliza el constructor para generar los valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Puede probar la estructura `height` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Vea también

- [Procedimientos de operador](./operator-procedures.md)
- [Filtrar para definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Filtrar para llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Filtrar para usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (Instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Filtrar Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod (Operador)](../../../../visual-basic/language-reference/operators/mod-operator.md)
