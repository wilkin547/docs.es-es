---
title: "goto (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "goto_CSharpKeyword"
  - "goto"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "goto (palabra clave) [C#]"
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# goto (Referencia de C#)
La instrucción `goto` transfiere el control del programa directamente a una instrucción identificada por una etiqueta.  
  
 Un uso habitual de `goto` consiste en transferir el control a una etiqueta switch\-case específica o a la etiqueta predeterminada de una instrucción `switch`.  
  
 La instrucción `goto` también es útil para salir de bucles de varios niveles de anidamiento.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar `goto` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/csharp/goto_1.cs)]  
  
## Ejemplo  
 El siguiente ejemplo muestra el uso de `goto` para salir de un conjunto de bucles anidados.  
  
 [!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/csharp/goto_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [goto \(Instrucción\)](/visual-cpp/cpp/goto-statement-cpp)   
 [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)