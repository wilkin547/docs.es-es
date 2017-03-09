---
title: "C&#243;mo: Hacer referencia al miembro de una enumeraci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "constantes, enumeradas"
  - "miembros de enumeración"
  - "enumeraciones [Visual Basic], hacer referencia"
  - "valores, asociar valores constantes con nombres"
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Hacer referencia al miembro de una enumeraci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y de asociar valores de constantes con nombres.  Por ejemplo, se puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana, y después utilizar los nombres de los días en el código en lugar de sus valores enteros.  
  
 Puede evitar utilizar los nombres completos con la instrucción `Imports`.  Para obtener más información, vea [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### Para hacer referencia a un miembro de una enumeración  
  
-   Califique el nombre de miembro con la enumeración.  Por ejemplo, el ejemplo siguiente asigna el miembro `Saturday` de la enumeración `FirstDayOfWeek` a la variable  `DayValue`.  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#19)]  
  
## Vea también  
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)