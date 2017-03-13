---
title: "() (operador) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "()_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "() (operador) [C#]"
  - "operador de conversión [C#]"
  - "conversión de tipos [C#], operador ()"
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# () (operador) (Referencia de C#)
Además de usarlos para especificar el orden de las operaciones en una expresión, los paréntesis se utilizan para realizar las siguientes tareas:  
  
1.  Especificar conversiones o conversiones de tipo.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Invocar métodos o delegados.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## Comentarios  
 Una conversión de tipos invoca explícitamente el operador de conversión de un tipo a otro; se producirá un error en la conversión si no se ha definido ese operador.  Para definir un operador de conversión, vea [explicit \(Referencia de C\#\)](../../../csharp/language-reference/keywords/explicit.md) e [implicit \(Referencia de C\#\)](../../../csharp/language-reference/keywords/implicit.md).  
  
 El operador `()` no se puede sobrecargar.  
  
 Para obtener más información, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Una expresión de conversión podría llevar a una sintaxis ambigua.  Por ejemplo, la expresión `(x)–y` puede interpretarse como una expresión de conversión \(una conversión del tipo –y al tipo x\) o como una expresión de suma combinada con una expresión entre paréntesis, que calcula el valor de x – y.  
  
 Para obtener más información sobre las llamadas a métodos, vea [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)