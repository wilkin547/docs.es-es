---
title: "Operador ^ (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^ (operador) [C#]"
  - "OR (operador exclusivo bit a bit) [C#]"
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operador ^ (Referencia de C#)
Los operadores binarios `^` están predefinidos para tipos enteros y `bool`.  Para los tipos enteros, `^` calcula la operación OR exclusiva bit a bit de sus operandos.  Para los operandos `bool`, `^` calcula la operación OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si, y sólo si, exactamente uno de sus operandos es `true`.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `^` \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#30)]  
  
 El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit con los dos valores binarios siguientes, que corresponden a los valores hexadecimales F8 y 3F:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 El resultado de la operación OR exclusiva es `1100 0111`, que corresponde al valor hexadecimal C7.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)