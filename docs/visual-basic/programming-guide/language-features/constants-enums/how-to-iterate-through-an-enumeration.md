---
title: "Cómo: Recorrer en iteración una enumeración en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Cómo: Recorrer en iteración una enumeración en Visual Basic
Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres. Para recorrer en iteración una enumeración, se puede mover a una matriz mediante el <xref:System.Enum.GetValues%2A> método. También puede iterar a través de una enumeración con un `For...Each` (instrucción), con el <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> método para extraer el valor de cadena o numérica.  
  
### <a name="to-iterate-through-an-enumeration"></a>Para recorrer en iteración una enumeración  
  
-   Declarar una matriz y convierta la enumeración en ella con el <xref:System.Enum.GetValues%2A> método antes de pasar la matriz como haría cualquier otra variable. En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> tal y como se recorre en iteración la enumeración.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
