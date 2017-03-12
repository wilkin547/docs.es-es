---
title: "C&#243;mo: Crear una cadena a partir de una matriz de caracteres (Visual Basic) | Microsoft Docs"
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
  - "ejemplos [Visual Basic], matrices"
  - "ejemplos [Visual Basic], Char (tipo de datos)"
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# C&#243;mo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo crea la cadena "abcd" a partir de caracteres individuales.  
  
## Ejemplo  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-create-a-string-f_1.vb)]  
  
## Compilar el código  
 Este método no tiene ningún requisito especial.  
  
 Para crear un literal de carácter se utiliza la sintaxis `"a"c`, donde una `c` única sigue a un carácter individual en comillas.  
  
## Programación eficaz  
 Los caracteres Null \(equivalentes a `Chr(0)`\) de la cadena producirán resultados inesperados cuando ésta se utilice.  Aunque el carácter null se incluirá en la cadena, podría ocurrir que los caracteres que lo siguen no aparezcan en algunas situaciones.  
  
## Vea también  
 <xref:System.String>   
 [Char \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)