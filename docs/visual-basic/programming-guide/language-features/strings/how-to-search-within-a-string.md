---
title: "C&#243;mo: Buscar en una cadena (Visual Basic) | Microsoft Docs"
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
  - "ejemplos [Visual Basic], cadenas"
  - "cadenas [Visual Basic], buscar"
  - "cadenas [Visual Basic], buscar"
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Buscar en una cadena (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este ejemplo se llama al método <xref:System.String.IndexOf%2A> de un objeto <xref:System.String> para informar del índice de la primera aparición de una subcadena.  
  
## Ejemplo  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una instrucción `Imports` que especifica el espacio de nombres <xref:System>.  Para obtener más información, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Programación eficaz  
 El método <xref:System.String.IndexOf%2A> informa de la ubicación del primer carácter de la primera aparición de la subcadena.  El índice es de base 0, lo que significa que el índice del primer carácter de una cadena es 0.  
  
 Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve \-1.  
  
 El método <xref:System.String.IndexOf%2A> distingue entre mayúsculas y minúsculas y utiliza la referencia cultural actual.  
  
 Para un control óptimo de errores, sería recomendable incluir la búsqueda de cadenas en el bloque `Try` de una construcción [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Vea también  
 <xref:System.String.IndexOf%2A>   
 [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)