---
title: "C&#243;mo: Escribir un constructor Copy (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Lenguaje C#, copy (constructor)"
  - "copy (constructor) [C#]"
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# C&#243;mo: Escribir un constructor Copy (Gu&#237;a de programaci&#243;n de C#)
C\# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.  
  
## Ejemplo  
 En el ejemplo siguiente, `Person` [clase](../../../csharp/language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.  Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.  El código contiene un constructor de copias alternativo que envía las propiedades de `Name` y de `Age` de la instancia que desea copiar al constructor de instancia de la clase.  
  
 [!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## Vea también  
 <xref:System.ICloneable>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)