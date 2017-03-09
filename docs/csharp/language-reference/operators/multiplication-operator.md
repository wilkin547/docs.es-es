---
title: "Operador * (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* (operador) [C#]"
  - "* (operador de multiplicación) [C#]"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Operador * (Referencia de C#)
Operador de multiplicación \(`*`\) que calcula el producto de sus operandos.  Además, operador de desreferenciación que permite leer y escribir en un puntero.  
  
## Comentarios  
 Todos los tipos numéricos poseen operadores de multiplicación predefinidos.  
  
 El operador `*` también se utiliza para declarar los tipos de puntero y para desreferenciar los punteros.  Este operador sólo se puede utilizar en contextos no seguros, indicados por el uso de la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), y que requieren la opción del compilador [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  El operador de desreferenciación también se conoce como el operador de direccionamiento indirecto.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#50)]  
  
## Ejemplo  
 [!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#51)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)