---
title: "Operador != (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "!=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "!= (operador) [C#]"
  - "!= (operador de desigualdad) [C#]"
  - "!= (operador de desigualdad) [C#]"
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Operador != (Referencia de C#)
El operador de desigualdad \(`!=`\) devuelve false si sus dos operandos son iguales; en caso contrario, devuelve true.  Los operadores de desigualdad están predefinidos para todos los tipos, incluidos string y object.  Los tipos definidos por el usuario pueden sobrecargar el operador `!=`  
  
## Comentarios  
 Para los tipos de valor predefinidos, el operador de desigualdad \(`!=`\) devuelve true si los valores de sus operandos son diferentes, y false en caso contrario.  Para los tipos de referencia, excepto `string`, `!=` devuelve true si sus dos operandos se refieren a objetos diferentes.  Para el tipo `string`, `!=` compara los valores de las cadenas.  
  
 Los tipos de valor definidos por el usuario pueden sobrecargar el operador `!=` \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  También pueden hacerlo los tipos de referencia definidos por el usuario, aunque, de forma predeterminada, `!=` se comporta como se ha descrito anteriormente tanto para los tipos de referencia predefinidos como para los definidos por el usuario.  Si se sobrecarga `!=`, también se debe sobrecargar [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)