---
title: "implicit (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "implicit"
  - "implicit_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "implicit (palabra clave) [C#]"
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# implicit (Referencia de C#)
La palabra clave `implicit` se utiliza para declarar un operador de conversión de tipo implícito definido por el usuario.  Utilícela para permitir conversiones implícitas entre un tipo definido por el usuario y otro tipo, si existen garantías de que la conversión no provocará la pérdida de datos.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/csharp/implicit_1.cs)]  
  
 Si se eliminan las conversiones de tipo explícitas innecesarias y se utilizan conversiones implícitas, la legibilidad del código mejora.  Sin embargo, como las conversiones implícitas no requieren que los programadores conviertan explícitamente un tipo en otro, deben tomarse las medidas adecuadas para impedir que se produzcan resultados imprevistos.  En general, los operadores de conversión implícita nunca deberían producir excepciones ni pérdida de información, de modo que puedan utilizarse de forma segura sin intervención del programador.  Si un operador de conversión no cumple esos criterios, debería marcarse como `explicit`.  Para obtener más información, vea [Utilizar operadores de conversión \(Guía de programación de C\#\)](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [explícita](../../../csharp/language-reference/keywords/explicit.md)   
 [operador](../../../csharp/language-reference/keywords/operator.md)   
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)