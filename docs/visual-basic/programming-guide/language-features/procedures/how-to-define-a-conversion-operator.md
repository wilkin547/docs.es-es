---
description: 'Más información sobre: Cómo: definir un operador de conversión (Visual Basic)'
title: Procedimiento para definir un operador de conversión
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: c090e183e809974163625c4bfcf33536b1082b66
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481992"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Cómo: Definir un operador de conversión (Visual Basic)

Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer` , `Double` o `String` ).  
  
 Defina la conversión de tipos como un procedimiento de [función ctype](../../../language-reference/functions/ctype-function.md) dentro de la clase o estructura. Todos los procedimientos de conversión deben ser `Public Shared` , y cada uno de ellos debe especificar la [ampliación](../../../language-reference/modifiers/widening.md) o la [restricción](../../../language-reference/modifiers/narrowing.md).  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se definen operadores de conversión entre una estructura denominada `digit` y una `Byte` .  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Puede probar la estructura `digit` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un operador](./how-to-define-an-operator.md)
- [Procedimiento para llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Procedimiento para usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Structure (Instrucción)](../../../language-reference/statements/structure-statement.md)
- [Procedimiento Declaración de estructuras](../data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
