---
title: "Tipos de m&#233;todos de manipulaci&#243;n de cadenas en Visual Basic | Microsoft Docs"
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
  - "manipulación de cadenas"
  - "cadenas [Visual Basic], manipular [Visual Basic]"
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Tipos de m&#233;todos de manipulaci&#243;n de cadenas en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Existen diferentes formas de analizar y manipular las cadenas.  Algunos métodos forman parte del lenguaje [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], mientras que otros son inherentes a la clase `String`.  
  
## Lenguaje Visual Studio y .NET Framework  
 Los métodos de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] se usan como funciones inherentes del lenguaje.  Pueden utilizarse sin calificación en el código.  En el siguiente ejemplo se muestra el uso habitual de un comando de manipulación de cadenas de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/types-of-string-manipula_1.vb)]  
  
 En este ejemplo, la función `Mid` realiza una operación directa en `aString` y asigna el valor a `bString`.  
  
 Para obtener una lista de los métodos de manipulación de cadenas de Visual Basic, vea [Resumen de manipulación de cadenas](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### Métodos compartidos y métodos de instancia  
 También puede manipular cadenas con los métodos de la clase `String`.  Existen dos tipos de métodos en `String`: métodos *compartidos* y métodos de *instancia*.  
  
#### Métodos compartidos  
 Un método compartido es un método que se deriva de la propia clase `String` y no necesita una instancia de dicha clase para funcionar.  Estos métodos se pueden calificar con el nombre de la clase \(`String`\) en lugar de hacerlo con una instancia de la clase `String`.  Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/types-of-string-manipula_2.vb)]  
  
 En el ejemplo anterior, el método <xref:System.String.Copy%2A?displayProperty=fullName> es un método estático, que actúa sobre una expresión dada y asigna el valor resultante a `bString`.  
  
#### Métodos de instancia  
 En contraste, los métodos de instancia se derivan de una instancia concreta de `String` y deben calificarse con el nombre de la instancia.  Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/types-of-string-manipula_3.vb)]  
  
 En este ejemplo, el método <xref:System.String.Substring%2A?displayProperty=fullName> es un método de la instancia de `String` \(es decir, `aString`\).  Realiza una operación en `aString` y asigna ese valor a `bString`.  
  
 Para obtener más información, vea la documentación de la clase <xref:System.String>.  
  
## Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)