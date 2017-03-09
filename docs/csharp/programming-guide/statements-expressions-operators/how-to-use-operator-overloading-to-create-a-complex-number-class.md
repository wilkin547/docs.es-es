---
title: "C&#243;mo: Utilizar la sobrecarga de operadores para crear una clase de n&#250;meros complejos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "clases [C#], sobrecarga de operadores"
  - "números complejos [C#]"
  - "sobrecarga de operadores [C#], números complejos"
  - "sobrecarga de operadores [C#], utilizar para crear clases"
  - "operadores [C#], reemplazar para crear una clase de números complejos"
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Utilizar la sobrecarga de operadores para crear una clase de n&#250;meros complejos (Gu&#237;a de programaci&#243;n de C#)
Este ejemplo muestra cómo utilizar la sobrecarga de operadores para crear una clase de números complejos `Complex` que define la suma compleja.  El programa muestra las partes real e imaginaria de los números y el resultado de la suma mediante un método sustituto del método `ToString`.  
  
## Ejemplo  
 [!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-use-operator-over_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [operador](../../../csharp/language-reference/keywords/operator.md)   
 [Why are overloaded operators always static in C\#?](http://go.microsoft.com/fwlink/?LinkId=112383)