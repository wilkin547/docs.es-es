---
description: 'Más información sobre: Cómo: utilizar una clase que define operadores (Visual Basic)'
title: Procedimiento para usar una clase que define operadores
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
ms.openlocfilehash: 4bf5321fbf1868ad0214d0f4781df30dc8f92ac9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455748"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Cómo: Utilizar una clase que define operadores (Visual Basic)

Si usa una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se tiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString> , que define los operadores de conversión ([función ctype](../../../language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena de Visual Basic. Use `CType(` la *expresión de cadena de SQL* para `String)` convertir una cadena de SQL en una cadena de Visual Basic y `CType(` *Visual Basic expresión de cadena*, <xref:System.Data.SqlTypes.SqlString> `)` para convertirla en la otra dirección.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 La <xref:System.Data.SqlTypes.SqlString> estructura define un operador de conversión ([función ctype](../../../language-reference/functions/ctype-function.md)) de `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String` . La instrucción que asigna `title` a `jobTitle` hace uso del primer operador y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada de función utiliza el segundo.  
  
## <a name="compile-the-code"></a>Compilar el código  

 Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar. No suponga que la clase o la estructura ha definido todos los operadores disponibles para la sobrecarga. Para obtener una lista de operadores disponibles, vea [Operator (instrucción](../../../language-reference/statements/operator-statement.md)).  
  
 Incluya la `Imports` instrucción adecuada para la cadena SQL al principio del archivo de código fuente (en este caso <xref:System.Data.SqlTypes> ).  
  
 El proyecto debe tener referencias a System. Data y System.XML.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un operador](./how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Procedimiento para llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Structure (Instrucción)](../../../language-reference/statements/structure-statement.md)
- [Procedimiento Declaración de estructuras](../data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
