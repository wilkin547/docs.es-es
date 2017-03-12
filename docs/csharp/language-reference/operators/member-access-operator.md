---
title: "Operador . (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "._CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ". (operador) [C#]"
  - "operador de punto (.) [C#]"
  - "operador de acceso a miembros (.) [C#]"
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Operador . (Referencia de C#)
El operador de punto \(`.`\) se utiliza para el acceso a miembros.  El operador de punto especifica un miembro de un tipo o espacio de nombres.  Por ejemplo, el operador de punto se utiliza para tener acceso a métodos específicos dentro de las bibliotecas de clases de .NET Framework:  
  
 [!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#16)]  
  
 Por ejemplo, considere la siguiente clase:  
  
 [!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#17)]  
  
 [!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#18)]  
  
 La variable `s` tiene dos miembros, `a` y `b`; para tener acceso a ellos, use el operador de punto:  
  
 [!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#19)]  
  
 El punto también se utiliza para formar nombres completos, que son nombres que especifican el espacio de nombres o la interfaz, por ejemplo, a la que pertenecen.  
  
 [!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#20)]  
  
 La directiva using hace que la calificación de nombres sea opcional en algunos casos:  
  
 [!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#21)]  
  
 Sin embargo, un identificador ambiguo debe calificarse:  
  
 [!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#22)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)