---
title: "C&#243;mo: Convertir cadenas hexadecimales en n&#250;meros (Visual Basic) | Microsoft Docs"
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
  - "decimales, hexadecimales"
  - "ejemplos [Visual Basic], conversión de cadenas"
  - "hexadecimales, decimales"
  - "números, hexadecimales"
  - "conversión de cadenas, hexadecimales a números"
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# C&#243;mo: Convertir cadenas hexadecimales en n&#250;meros (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este ejemplo se convierte una cadena hexadecimal en un entero utilizando el método <xref:System.Convert.ToInt32%2A>.  
  
### Para convertir una cadena hexadecimal en un número  
  
-   Utilice el método <xref:System.Convert.ToInt32%2A> para convertir el número expresado en base 16 a un entero.  
  
     El primer argumento del método <xref:System.Convert.ToInt32%2A> es la cadena que se va a convertir.  El segundo argumento describe la base en que se expresa el número; el valor hexadecimal es base 16.  
  
     [!code-vb[VbVbalrStrings#62](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:System.Convert.ToInt32%2A>