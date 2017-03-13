---
title: "Operador &amp; (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "AND (operador bit a bit) [C#]"
  - "& (operador y comercial) [C#]"
  - "& (operador) [C#]"
  - "& (operador AND) [C#]"
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operador &amp; (Referencia de C#)
El operador & puede funcionar como operador unario o binario.  
  
## Comentarios  
 El operador & unario devuelve la dirección de memoria de su operando \(requiere un contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\).  
  
 Los operadores & binarios están predefinidos para los tipos enteros y `bool`.  Para tipos enteros, & calcula la operación AND bit a bit lógica de sus operandos.  Para operandos de tipo `bool`, & calcula la operación lógica AND de sus operandos; es decir, el resultado es `true` si, y sólo si ambos operandos son `true`.  
  
 El operador `&` evalúa ambos operadores sin tener en cuenta el valor del primero.  Por ejemplo:  
  
 [!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador binario `&` \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)