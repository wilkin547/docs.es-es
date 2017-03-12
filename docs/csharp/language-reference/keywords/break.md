---
title: "break (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "break"
  - "break_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "break (palabra clave) [C#]"
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# break (Referencia de C#)
La instrucción `break` permite terminar el bucle envolvente más cercano o la instrucción [switch](../../../csharp/language-reference/keywords/switch.md) en la cual aparece.  El control se transfiere a la instrucción que sigue a la instrucción terminada, si existe alguna.  
  
## Ejemplo  
 En este ejemplo, la instrucción condicional contiene un contador preparado para contar de 1 a 100; sin embargo, la instrucción `break` termina el bucle tras 4 iteraciones.  
  
 [!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/csharp/break_1.cs)]  
  
## Ejemplo  
 En este ejemplo, se usa la instrucción `break` para interrumpir la ejecución de un bucle anidado interno y devolver el control al bucle externo.  
  
 [!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/csharp/break_2.cs)]  
  
## Ejemplo  
 Este ejemplo muestra el uso de `break` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/csharp/break_3.cs)]  
  
 Si se escribió `4`, el resultado sería:  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)