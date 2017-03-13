---
title: "C&#243;mo: Buscar cadenas mediante expresiones regulares (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "buscar cadenas [C#]"
  - "cadenas [C#], buscar con RegEx"
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Buscar cadenas mediante expresiones regulares (Gu&#237;a de programaci&#243;n de C#)
La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> se puede utilizar para buscar cadenas.  Estas búsquedas pueden tener distinta complejidad, desde ser muy sencillas hasta hacer un gran uso de expresiones regulares.  A continuación se ofrecen dos ejemplos de búsqueda de cadenas utilizando la clase <xref:System.Text.RegularExpressions.Regex>.  Para obtener más información, vea [Expresiones regulares de .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md).  
  
## Ejemplo  
 El código siguiente es una aplicación de consola que realiza una búsqueda simple de cadenas sin distinción entre mayúsculas y minúsculas en una matriz.  El método estático <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> realiza la búsqueda a partir de la cadena de búsqueda y de una cadena que contiene el modelo de búsqueda.  En este caso, se utiliza un tercer argumento para indicar que no se debe distinguir entre mayúsculas y minúsculas.  Para obtener más información, vea <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## Ejemplo  
 El código siguiente es una aplicación de consola que utiliza expresiones regulares para validar el formato de cada cadena de una matriz.  La validación requiere que cada cadena tenga la forma de un número de teléfono en el que tres grupos de dígitos se separan por guiones. Los dos primeros grupos contienen tres dígitos, y el tercero, cuatro.  Para ello, se utiliza la expresión regular `^\\d{3}-\\d{3}-\\d{4}$`.  Para obtener más información, vea [Lenguaje de expresiones regulares \- Referencia rápida](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## Vea también  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [Expresiones regulares de .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Lenguaje de expresiones regulares \- Referencia rápida](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md)