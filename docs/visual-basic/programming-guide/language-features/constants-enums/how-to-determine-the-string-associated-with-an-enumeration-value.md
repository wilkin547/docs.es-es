---
title: "C&#243;mo: Determinar la cadena asociada a un valor de enumeraci&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "enumeraciones [Visual Basic]"
  - "cadenas [Visual Basic], valores de enumeración"
  - "valores, miembros de enumeración"
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Determinar la cadena asociada a un valor de enumeraci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los métodos <xref:System.Enum.GetValues%2A> y <xref:System.Enum.GetNames%2A> permiten determinar las cadenas y los valores asociados a miembros de enumeración.  
  
### Para determinar la cadena asociada a una enumeración  
  
-   Utilice el método <xref:System.Enum.GetNames%2A> para recuperar las cadenas asociadas a los miembros de enumeración.  Este ejemplo declara una enumeración, `flavorEnum`, y utiliza luego el método <xref:System.Enum.GetNames%2A> para mostrar las cadenas asociadas a cada miembro.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## Vea también  
 <xref:System.Enum.GetValues%2A>   
 <xref:System.Enum.GetNames%2A>   
 <xref:System.Enum>   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Cómo: Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Enum \(Instrucción\)](../../../../visual-basic/language-reference/statements/enum-statement.md)