---
title: "Operador == (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "==_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "== (operador) [C#]"
  - "operador de igualdad [C#]"
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Operador == (Referencia de C#)
Para los tipo de valor predefinidos, el operador de igualdad \(`==`\) devuelve true si los valores de sus operandos son iguales y `false` en caso contrario.  Para los tipos de referencia, excepto [string](../../../csharp/language-reference/keywords/string.md), `==` devuelve `true` si sus dos operandos se refieren al mismo objeto.  Para el tipo `string`, `==` compara los valores de las cadenas.  
  
## Comentarios  
 Los tipos de valor definidos por el usuario pueden sobrecargar el operador `==` \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  También pueden hacerlo los tipos de referencia definidos por el usuario, aunque, de forma predeterminada, `==` se comporta como se ha descrito anteriormente tanto para los tipos de referencia predefinidos como para los definidos por el usuario.  Si se sobrecarga `==`, también se debe sobrecargar [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#36)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)