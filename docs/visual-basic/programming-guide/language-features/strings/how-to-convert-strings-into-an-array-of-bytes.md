---
title: "C&#243;mo: Convertir cadenas en una matriz de bytes en Visual Basic | Microsoft Docs"
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
  - "matrices [Visual Basic], matrices de bytes"
  - "matrices [Visual Basic], convertir cadenas en"
  - "matrices de bytes"
  - "ejemplos [Visual Basic], conversión de cadenas"
  - "conversión de cadenas, matrices"
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Convertir cadenas en una matriz de bytes en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este tema se muestra cómo convertir una cadena en una matriz de bytes.  
  
## Ejemplo  
 Este ejemplo utiliza el método <xref:System.Text.Encoding.GetBytes%2A> de la clase de codificación <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> para convertir una cadena en una matriz de bytes.  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 Puede elegir varias opciones de codificación para convertir una cadena en una matriz de bytes:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: Obtiene una codificación para el juego de caracteres ASCII \(7 bits\).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-16 utilizando el orden de bytes big\-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-16 utilizando el orden de bytes little\-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-32 utilizando el orden de bytes little\-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-8.  
  
## Vea también  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetBytes%2A>   
 [Cómo: Convertir una matriz de bytes en una cadena en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)