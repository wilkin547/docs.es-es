---
title: Filtrar Usar una clase que define operadores (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: bd512adf2f06ed0fbd3d36ed3175a0928bf1c57c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829413"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Filtrar Usar una clase que define operadores (Visual Basic)
Si utiliza una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se obtiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena de Visual Basic. Use `CType(` *expresión de cadena SQL*, `String)` para convertir una cadena SQL en una cadena de Visual Basic y `CType(` *expresión de cadena de Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` para convertir en la otra dirección.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 El <xref:System.Data.SqlTypes.SqlString> estructura define un operador de conversión ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) desde `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`. La instrucción que asigna `title` a `jobTitle` usa el primer operador y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada de función usa la segunda.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea usar. No suponga que la clase o estructura ha definido todos los operadores disponibles para la sobrecarga. Para obtener una lista de operadores disponibles, vea [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Incluir adecuado `Imports` instrucción para la cadena SQL al principio del archivo de origen (en este caso <xref:System.Data.SqlTypes>).  
  
 El proyecto debe tener referencias a System.Data y System.XML.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un operador](./how-to-define-an-operator.md)
- [Cómo: Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Cómo: Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
