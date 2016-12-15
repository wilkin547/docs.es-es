---
title: "C&#243;mo: Utilizar una clase que define operadores (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ejemplos [Visual Basic], CType"
  - "sobrecarga de operadores"
  - "procedimientos de operadores, llamar"
  - "operadores [Visual Basic], sobrecargar"
  - "procedimientos, llamar"
  - "procedimientos, operador"
  - "valores devueltos, procedimientos de operadores"
  - "sintaxis, procedimientos de operadores"
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Utilizar una clase que define operadores (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Si está utilizando una clase o una estructura que define sus propios operadores, puede tener acceso a estos operadores desde [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 La definición de un operador de una clase o estructura también se denomina *sobrecarga* del operador.  
  
## Ejemplo  
 En el ejemplo siguiente se tiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión \([CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md)\) entre una cadena SQL y una cadena de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y viceversa.  Use `CType(`*expresión de cadena SQL*, `String)` para convertir una cadena SQL en una cadena de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y `CType(`*expresión de cadena de Visual Basic*, <xref:System.Data.SqlTypes.SqlString>`)` para convertir en la dirección inversa.  
  
 [!code-vb[VbVbcnProcedures#30](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 La estructura <xref:System.Data.SqlTypes.SqlString> define un operador de conversión \([CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md)\) de `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`.  La instrucción que asigna `title` a `jobTitle` utiliza el primer operador y la llamada a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> utiliza el segundo.  
  
## Compilar el código  
 Asegúrese de que la clase o la estructura que está utilizando define el operador que desea utilizar.  No debe presuponer que la clase o la estructura ha definido cada operador disponible para su sobrecarga.  Para obtener una lista de los operadores disponibles, vea [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Incluya la instrucción `Imports` apropiada en la cadena SQL al comienzo de su archivo de código fuente \(en este caso <xref:System.Data.SqlTypes>\).  
  
 El proyecto debe tener referencias a System.Data y System.XML.  
  
## Vea también  
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Cómo: Llamar a un procedimiento de operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)