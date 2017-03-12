---
title: "C&#243;mo: Usar matrices y variables locales con tipo impl&#237;cito en expresiones de consulta (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "variables locales con asignación implícita de tipos [C#], cómo se utiliza"
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Usar matrices y variables locales con tipo impl&#237;cito en expresiones de consulta (Gu&#237;a de programaci&#243;n de C#)
Puede usar variables locales tipificadas implícitamente siempre que desee que el compilador determine el tipo de una variable local.  Debe usar las variables locales tipificadas implícitamente para almacenar tipos anónimos, que suelen usarse en expresiones de consulta.  En los ejemplos siguientes se muestran los usos opcionales y obligatorios de las variables locales tipificadas implícitamente en las consultas.  
  
 Las variables locales tipificadas implícitamente se declaran usando la palabra clave contextual [var](../../../csharp/language-reference/keywords/var.md).  Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) y [Matrices con tipo implícito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un escenario común en el que se requiere la palabra clave `var`: una expresión de consulta que genera una secuencia de tipos anónimos.  En este escenario, la variable de consulta y la variable de iteración de la instrucción `foreach` deben escribirse implícitamente mediante `var` porque no se tiene acceso a un nombre de tipo del tipo anónimo.  Para obtener más información sobre los tipos anónimos, vea [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#32)]  
  
## Ejemplo  
 En el ejemplo siguiente se usa la palabra clave `var` en una situación similar, pero en la que el uso de `var` es opcional.  Dado que `student.LastName` es una cadena, la ejecución de la consulta devuelve una secuencia de cadenas.  Por tanto, el tipo de `queryID` puede declararse como `System.Collections.Generic.IEnumerable<string>` en lugar de `var`.  La palabra clave `var` se usa para mayor comodidad.  En el ejemplo, la variable de iteración de la instrucción `foreach` se escribe explícitamente como cadena, pero podría declararse usando `var`.  Dado que el tipo de la variable de iteración no es un tipo anónimo, el uso de `var` es opcional, no es obligatorio.  Recuerde que `var` no es un tipo, sino una instrucción para que el compilador infiera y asigne el tipo.  
  
 [!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#33)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)