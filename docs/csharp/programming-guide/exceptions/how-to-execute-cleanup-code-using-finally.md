---
title: "C&#243;mo: Ejecutar c&#243;digo de limpieza mediante finally (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "control de excepciones [C#], bloque Try/Finally"
  - "excepciones [C#], bloque Try/Finally"
  - "try/finally (bloques) [C#]"
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# C&#243;mo: Ejecutar c&#243;digo de limpieza mediante finally (Gu&#237;a de programaci&#243;n de C#)
El propósito de una instrucción `finally` es asegurarse de que la limpieza necesaria de objetos, por lo general objetos que contienen recursos externos, se realiza inmediatamente, incluso cuando se produce una excepción.  Un ejemplo de esta limpieza es llamar a <xref:System.IO.Stream.Close%2A> en <xref:System.IO.FileStream> inmediatamente después de su uso en lugar de esperar que el objeto sea recolectado como elemento no utilizado por Common Language Runtime, de la siguiente manera:  
  
 [!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## Ejemplo  
 Para convertir el código anterior en una instrucción `try-catch-finally`, el código de limpieza está separado del código activo como se muestra a continuación.  
  
 [!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 Dado que una excepción puede producirse dentro del bloque `try` en cualquier momento antes de llamar a `OpenWrite()` o que puede producirse un error en la propia llamada a `OpenWrite()`, no hay garantías de que el archivo esté abierto al intentar cerrarlo.  El bloque `finally` agrega una comprobación que garantiza que el objeto <xref:System.IO.FileStream> no es `null` antes de llamar al método <xref:System.IO.Stream.Close%2A>.  Sin la comprobación de `null`, el bloque `finally` podría iniciar su propia excepción <xref:System.NullReferenceException>, pero debería evitarse en lo posible producir excepciones en los bloques `finally`.  
  
 Una conexión de base de datos también es un elemento que debería cerrarse en un bloque `finally`.  Dado que el número de conexiones permitidas a un servidor de bases de datos en ocasiones es limitado, las conexiones de base de datos deben cerrarse tan rápido como sea posible.  Si se produjera una excepción antes de poder cerrar la conexión, se trataría de otro caso en el que sería preferible utilizar el bloque `finally` a esperar a la recolección de elementos no utilizados.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)