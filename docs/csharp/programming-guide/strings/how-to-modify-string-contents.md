---
title: "C&#243;mo: Modificar el contenido de cadenas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cadenas [C#], modificar"
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# C&#243;mo: Modificar el contenido de cadenas (Gu&#237;a de programaci&#243;n de C#)
Dado que las cadenas son *inmutables*, no es posible modificar el valor de un objeto de cadena una vez creado sin utilizar código no seguro.  Sin embargo, existen muchas maneras de modificar el valor de una cadena y almacenar el resultado en un nuevo objeto de cadena.  La clase <xref:System.String?displayProperty=fullName> proporciona métodos que actúan en una cadena de entrada y devuelven un nuevo objeto de cadena.  En muchos casos, puede asignar el nuevo objeto a la variable que contenía la cadena original.  La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> proporciona métodos adicionales que funcionan de manera similar.  La clase <xref:System.Text.StringBuilder?displayProperty=fullName> proporciona un búfer de caracteres que puede modificar "en contexto". Llame al método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> para crear un nuevo objeto de cadena que incluya el contenido actual del búfer.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran varias formas de reemplazar o quitar subcadenas en una cadena especificada.  
  
 [!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## Ejemplo  
 Para obtener acceso a los caracteres individuales de una cadena mediante la notación de matrices, puede utilizar el objeto <xref:System.Text.StringBuilder>, que sobrecarga el operador `[]` para proporcionar acceso a su búfer de caracteres interno.  También puede convertir la cadena en una matriz de caracteres mediante el método <xref:System.String.ToCharArray%2A>.  En el ejemplo siguiente se utiliza `ToCharArray` para crear la matriz.  A continuación, se modifican algunos elementos de esa matriz.  Después, se llama a un constructor de cadena que toma una matriz de caracteres como parámetro de entrada para crear una nueva cadena.  
  
 [!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## Ejemplo  
 El ejemplo siguiente se proporciona para aquellas situaciones poco habituales en las que puede que desee modificar una cadena en contexto mediante código no seguro de forma similar a las matrices de caracteres de estilo de C.  En el ejemplo se muestra cómo obtener acceso a los caracteres individuales "en contexto" mediante la palabra clave fixed.  También se muestra un posible efecto secundario de realizar operaciones no seguras en las cadenas que se produce por la forma en que el compilador de C\# almacena \(confina\) las cadenas internamente.  En general, no debería utilizar esta técnica a menos que sea absolutamente necesario.  
  
 [!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)