---
title: "C&#243;mo: Recorrer en iteraci&#243;n una enumeraci&#243;n en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], iterar"
  - "enumeraciones [Visual Basic], iterar"
  - "ListBox (control) [Windows Forms], rellenar a partir de una enumeración"
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# C&#243;mo: Recorrer en iteraci&#243;n una enumeraci&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y de asociar valores de constantes con nombres.  Para recorrer en iteración una enumeración, puede moverla a una matriz mediante el método <xref:System.Enum.GetValues%2A>.  También puede recorrer en iteración una enumeración mediante una instrucción `For...Each`, mediante un método <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> para extraer la cadena o valor numérico.  
  
### Para recorrer en iteración una enumeración  
  
-   Declare una matriz y convierta la enumeración en ella con el método <xref:System.Enum.GetValues%2A> antes de pasar la matriz como haría con cualquier otra variable.  En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> cuando la recorre en iteración.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#7)]  
  
## Vea también  
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Cómo: Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Cómo: Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)