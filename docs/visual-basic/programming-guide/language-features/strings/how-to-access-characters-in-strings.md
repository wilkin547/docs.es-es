---
title: "C&#243;mo: Obtener acceso a caracteres de cadenas en Visual Basic | Microsoft Docs"
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
  - "caracteres [Visual Basic], obtener acceso en cadenas"
  - "cadenas [Visual Basic], obtener acceso a caracteres"
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# C&#243;mo: Obtener acceso a caracteres de cadenas en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo muestra cómo utilizar la propiedad <xref:System.String.Chars%2A> para tener acceso al carácter situado en la ubicación especificada en una cadena.  
  
## Ejemplo  
 En ocasiones es útil tener información sobre los caracteres de una cadena y de su posición dentro de la misma.  Una cadena se puede considerar como una matriz de caracteres \(instancias `Char`\); se puede recuperar un carácter concreto haciendo referencia al índice de dicho carácter a través de la propiedad <xref:System.String.Chars%2A>.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 El parámetro `index` de la propiedad <xref:System.String.Chars%2A> está basado en cero.  
  
## Programación eficaz  
 La propiedad <xref:System.String.Chars%2A> devuelve el carácter situado en la posición especificada.  Sin embargo, algunos caracteres Unicode se pueden representar con más de un carácter.  Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La propiedad <xref:System.String.Chars%2A> produce una excepción <xref:System.IndexOutOfRangeException> si el parámetro `index` es mayor o igual que la longitud de la cadena, o si es menor que cero.  
  
## Vea también  
 <xref:System.String.Chars%2A>   
 [Cómo: Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)   
 [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)