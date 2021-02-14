---
description: 'Más información sobre: Cómo: definir un operador (Visual Basic)'
title: Procedimiento para definir un operador
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
ms.openlocfilehash: ead96a302426c6f5b1667bb030aab56afe3284c8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462716"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Cómo: Definir un operador (Visual Basic)

Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*` , `<>` o `And` ) cuando uno o los dos operandos son del tipo de la clase o estructura.  
  
 Defina el operador estándar como procedimiento de operador dentro de la clase o estructura. Todos los procedimientos de operador deben ser `Public` `Shared` .  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se define el `+` operador para una estructura denominada `height` . La estructura utiliza altos medidos en pies y pulgadas. Una *pulgada* es 2,54 centímetros y un *pie* es 12 pulgadas. Para garantizar valores normalizados (pulgadas < 12,0), el constructor realiza la aritmética de *módulo* 12. El `+` operador usa el constructor para generar valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Puede probar la estructura `height` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Consulte también

- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Procedimiento para llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Procedimiento para usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Structure (Instrucción)](../../../language-reference/statements/structure-statement.md)
- [Procedimiento Declaración de estructuras](../data-types/how-to-declare-a-structure.md)
- [Mod (Operador)](../../../language-reference/operators/mod-operator.md)
