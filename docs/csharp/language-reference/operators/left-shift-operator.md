---
title: "Operador &lt;&lt; (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<< (operador) [C#]"
  - "<<= (operador de desplazamiento a la izquierda) [C#]"
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Operador &lt;&lt; (Referencia de C#)
El operador de desplazamiento a la izquierda \(`<<`\) desplaza su primer operando a la izquierda el número de bits especificado por su segundo operando.  El tipo del segundo operando debe ser un [int](../../../csharp/language-reference/keywords/int.md) o un tipo que tiene una conversión numérica implícita predefinida en `int`.  
  
## Comentarios  
 Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) \(cantidad de 32 bits\), los cinco bits de orden inferior del segundo operando proporcionan el valor de desplazamiento.  Es decir, el recuento de desplazamiento real es de 0 a 31 bits.  
  
 Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) \(cantidad de 64 bits\), los seis bits de orden inferior del segundo operando proporcionan el valor de desplazamiento.  Es decir, el recuento de desplazamiento real es de 0 a 63 bits.  
  
 Los bits de orden superior que no están contenidos en el intervalo del tipo del primer operando después del desplazamiento se descartan y los bits vacíos de orden inferior se rellenan con ceros.  Las operaciones de desplazamiento nunca producen desbordamientos.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `<<` \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\); el tipo del primer operando debe ser el tipo definido por el usuario, mientras que el tipo del segundo operando debe ser `int`.  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#14)]  
  
## Comentarios  
 Observe que `i<<1` e `i<<33` dan el mismo resultado, ya que 1 y 33 tienen los mismos cinco bits de orden inferior.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)