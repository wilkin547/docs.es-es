---
title: "Operador &gt;&gt; (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">> (operador) [C#]"
  - ">> (operador de desplazamiento a la derecha) [C#]"
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Operador &gt;&gt; (Referencia de C#)
El operador de desplazamiento a la derecha \(`>>`\) desplaza su primer operando a la derecha el número de bits especificado por su segundo operando.  
  
## Comentarios  
 Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) \(cantidad de 32 bits\), los cinco bits de orden inferior del segundo operando proporcionan el valor de desplazamiento \(segundo operando & 0x1f\).  
  
 Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) \(cantidad de 64 bits\), los seis bits de orden inferior del segundo operando proporcionan el valor de desplazamiento \(segundo operando & 0x3f\).  
  
 Si el primer operando es un tipo [int](../../../csharp/language-reference/keywords/int.md)o [long](../../../csharp/language-reference/keywords/long.md), el desplazamiento a la derecha es un desplazamiento aritmético \(los bits vacíos de orden superior toman el bit de signo\).  Si el primer operando es del tipo [uint](../../../csharp/language-reference/keywords/uint.md)o [ulong](../../../csharp/language-reference/keywords/ulong.md), el desplazamiento a la derecha es un desplazamiento lógico \(los bits de orden superior se rellenan con ceros\).  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `>>`; el tipo del primer operando debe ser el tipo definido por el usuario, mientras que el tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md).  Para obtener más información, vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#26)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)