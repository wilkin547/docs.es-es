---
title: "Tipos de datos de caracteres (Visual Basic) | Microsoft Docs"
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
  - "Char (tipo de datos), tipos de datos de caracteres"
  - "tipos de datos de caracteres [Visual Basic]"
  - "tipos de datos [Visual Basic], caracteres"
  - "tipos de datos [Visual Basic], elegir"
  - "String (tipo de datos), tipos de datos de caracteres"
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Tipos de datos de caracteres (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona *tipos de datos de caracteres* para trabajar con caracteres que se pueden mostrar e imprimir.  Aunque ambos tipos utilizan caracteres Unicode, `Char` contiene un único carácter, mientras que `String` contiene un número indefinido de caracteres.  
  
 Para obtener una tabla que muestra una comparación en paralelo de los tipos de datos de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Tipo Char  
 El tipo de datos `Char` es un único carácter Unicode de dos bytes \(16 bits\).  Si una variable siempre almacena exactamente un carácter, declárela como `Char`.  Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/character-data-types_1.vb)]  
  
 Cada valor posible en una variable `Char` o `String` es un *punto de código* o código de carácter en el juego de caracteres Unicode.  Los caracteres Unicode incluyen el juego de caracteres ASCII básico, diversas letras del alfabeto, acentos, símbolos de moneda, fracciones, signos diacríticos y símbolos matemáticos y técnicos.  
  
> [!NOTE]
>  El juego de caracteres Unicode reserva los puntos de código de D800 a DFFF \(de 55296 a 55551 decimales\) para *pares suplentes* que exigen dos valores de 16 bits que representen un punto de código único.  Una variable `Char` no puede contener un par suplente y `String` utiliza dos posiciones para contener este tipo de par.  
  
 Para obtener más información, vea [Char \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## Tipo String  
 El tipo de datos `String` es una secuencia de cero o más caracteres Unicode de dos bytes \(16 bits\).  Si una variable puede contener un número de caracteres indefinido, declárela como `String`.  Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/character-data-types_2.vb)]  
  
 Para obtener más información, vea [String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## Vea también  
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)