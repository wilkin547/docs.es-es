---
title: 'Cómo: Utilizar una clase que define operadores'
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
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347892"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Cómo: Utilizar una clase que define operadores (Visual Basic)
Si usa una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene acceso a la estructura de SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena Visual Basic. Use `CType(`*expresión de cadena SQL*, `String)` para convertir una cadena SQL en una cadena Visual Basic y `CType(`*Visual Basic expresión de cadena*, <xref:System.Data.SqlTypes.SqlString>`)` para convertirla en la otra dirección.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 La estructura <xref:System.Data.SqlTypes.SqlString> define un operador de conversión ([función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md)) de `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`. La instrucción que asigna `title` a `jobTitle` usa el primer operador y la llamada a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> usa el segundo.  
  
## <a name="compile-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar. No suponga que la clase o la estructura ha definido todos los operadores disponibles para la sobrecarga. Para obtener una lista de operadores disponibles, vea [Operator (instrucción](../../../../visual-basic/language-reference/statements/operator-statement.md)).  
  
 Incluya la instrucción `Imports` adecuada para la cadena SQL al principio del archivo de código fuente (en este caso <xref:System.Data.SqlTypes>).  
  
 El proyecto debe tener referencias a System. Data y System. XML.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un operador](./how-to-define-an-operator.md)
- [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
