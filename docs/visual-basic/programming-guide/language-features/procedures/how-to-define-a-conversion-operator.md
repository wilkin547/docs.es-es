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
If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).  
  
 Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure. All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Defining an operator on a class or structure is also called *overloading* the operator.  
  
## <a name="example"></a>Ejemplo  
 The following example defines conversion operators between a structure called `digit` and a `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 You can test the structure `digit` with the following code.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un operador](./how-to-define-an-operator.md)
- [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
- [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
