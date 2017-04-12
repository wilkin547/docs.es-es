---
title: "Cómo: utilizar una clase que define operadores (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b1db7c0b2a6fd8160baa48892b5f2214df24674e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Cómo: Utilizar una clase que define operadores (Visual Basic)
Si utiliza una clase o estructura que define sus propios operadores, puede tener acceso a los operadores de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se tiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cadena.</xref:System.Data.SqlTypes.SqlString> Utilice `CType(` *expresión de cadena SQL*, `String)` para convertir una cadena SQL a un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cadena, y `CType(` *expresión de cadena de Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` para convertir en la otra dirección.</xref:System.Data.SqlTypes.SqlString>  
  
 [!code-vb[VbVbcnProcedures Nº&30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 El <xref:System.Data.SqlTypes.SqlString>estructura define un operador de conversión ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md)) desde `String` a <xref:System.Data.SqlTypes.SqlString>y otro de <xref:System.Data.SqlTypes.SqlString>a `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> La instrucción que asigna `title` a `jobTitle` utiliza el primer operador y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>llamada de función utiliza el segundo.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea utilizar. No suponga que la clase o estructura ha definido cada operador disponible para la sobrecarga. Para obtener una lista de operadores disponibles, vea [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Incluir adecuado `Imports` instrucción para la cadena SQL al principio de su archivo de origen (en este caso <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes>  
  
 El proyecto debe tener referencias a System.Data y System.XML.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de operadores](./operator-procedures.md)   
 [Cómo: definir un operador](./how-to-define-an-operator.md)   
 [Cómo: definir un operador de conversión](./how-to-define-a-conversion-operator.md)   
 [Cómo: llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)   
 [De ampliación](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [De restricción](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Cómo: declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
