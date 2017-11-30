---
title: "Cómo: Utilizar una clase que define operadores (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 223b3fc84fe75d1d530cd182c9332e5c663aa519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Cómo: Utilizar una clase que define operadores (Visual Basic)
Si está utilizando una clase o estructura que define sus propios operadores, puede tener acceso a los operadores de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cadena. Use `CType(` *expresión de cadena SQL*, `String)` para convertir una cadena SQL para un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cadena, y `CType(` *expresión de cadena de Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` para convertir en la otra dirección.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 El <xref:System.Data.SqlTypes.SqlString> estructura define un operador de conversión ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md)) desde `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`. La instrucción que asigna `title` a `jobTitle` utiliza el primer operador y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada a la función utiliza el segundo.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea utilizar. No se da por supuesto que la clase o estructura ha definido cada operador disponible para la sobrecarga. Para obtener una lista de operadores disponibles, vea [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Incluir la correspondiente `Imports` instrucción para la cadena SQL al principio del archivo de origen (en este caso <xref:System.Data.SqlTypes>).  
  
 El proyecto debe tener referencias a System.Data y System.XML.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Definir un operador](./how-to-define-an-operator.md)  
 [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)  
 [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
