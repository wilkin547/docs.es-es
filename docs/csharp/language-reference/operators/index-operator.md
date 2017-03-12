---
title: "Operador (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "operador de subíndice [C#]"
  - "[] (corchetes, operador) [C#]"
  - "[] (operador) [C#]"
  - "operador de indización [C#]"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Operador (Referencia de C#)
Los corchetes \(`[]`\) se utilizan para matrices, indizadores y atributos.  También se pueden utilizar con punteros.  
  
## Comentarios  
 Un tipo de matriz es un tipo seguido de `[]`:  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#43)]  
  
 Para obtener acceso a un elemento de la matriz, el índice del elemento deseado se encierra entre corchetes:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#44)]  
  
 Se produce una excepción si el índice de la matriz está fuera del intervalo declarado.  
  
 El operador de indización de la matriz no se puede sobrecargar; no obstante, los tipos pueden definir indizadores y propiedades que aceptan uno o varios parámetros.  Los parámetros de indizador van entre corchetes, como los índices de matriz, pero en los primeros se puede declarar cualquier tipo de parámetro, mientras que los índices de matriz deben ser de tipo integral.  
  
 Por ejemplo, .NET Framework define un tipo `Hashtable` que asocia claves y valores de tipo arbitrario:  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#45)]  
  
 Los corchetes también se utilizan para especificar [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md):  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#46)]  
  
 Puede utilizar los corchetes para indizar fuera de un puntero:  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#47)]  
  
 No obstante, tenga en cuenta que no se realiza una comprobación de los límites del índice.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)