---
title: "Operador ~ (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "~_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ [C#], bit a bit (operador de complemento)"
  - "~ (operador) [C#]"
  - "bit a bit (operador de complemento) [C#]"
  - "tilde (~) (operador de complemento de uno) [C#]"
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Operador ~ (Referencia de C#)
El operador `~` realiza una operación de complemento bit a bit en su operando, lo que tiene el efecto de invertir cada bit.  Los operadores de complemento bit a bit están predefinidos para [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) y [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  El símbolo `~` también se usa para declarar destructores.  Para obtener más información, vea [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `~`  Para obtener más información, vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#25)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)