---
title: 'Cómo: Definir un operador'
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
ms.openlocfilehash: b99af8ff4d5428f1749bfc1a4c51a136f12405ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344876"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Cómo: Definir un operador (Visual Basic)
Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*`, `<>`o `And`) cuando uno o los dos operandos son del tipo de la clase o estructura.  
  
 Defina el operador estándar como procedimiento de operador dentro de la clase o estructura. Todos los procedimientos de operador deben estar `Public` `Shared`.  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define el operador de `+` para una estructura denominada `height`. La estructura utiliza altos medidos en pies y pulgadas. Una *pulgada* es 2,54 centímetros y un *pie* es 12 pulgadas. Para garantizar valores normalizados (pulgadas < 12,0), el constructor realiza la aritmética de *módulo* 12. El operador `+` usa el constructor para generar valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Puede probar la estructura `height` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md)
