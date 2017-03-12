---
title: "C&#243;mo: Convertir una matriz de bytes en una cadena en Visual Basic | Microsoft Docs"
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
  - "matrices [Visual Basic], convertir a cadenas"
  - "matrices de bytes, convertir a cadenas"
  - "ejemplos [Visual Basic], cadenas"
  - "conversión de cadenas, matrices"
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# C&#243;mo: Convertir una matriz de bytes en una cadena en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.  
  
## Ejemplo  
 Este ejemplo utiliza el método <xref:System.Text.Encoding.GetString%2A> de la clase de codificación <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> para convertir todos los bytes de una matriz de bytes en una cadena.  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-convert-an-array-_1.vb)]  
  
 Puede elegir varias opciones de codificación para convertir una matriz de bytes en una cadena:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>: Obtiene una codificación para el juego de caracteres ASCII \(7 bits\).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-16 utilizando el orden de bytes big\-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-16 utilizando el orden de bytes little\-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-32 utilizando el orden de bytes little\-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>: Obtiene una codificación para el formato UTF\-8.  
  
## Vea también  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetString%2A>   
 [Cómo: Convertir cadenas en una matriz de bytes en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)