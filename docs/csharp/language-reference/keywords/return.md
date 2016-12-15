---
title: "return (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "return_CSharpKeyword"
  - "return"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "return (palabra clave) [C#]"
  - "return (instrucción) [C#]"
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# return (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método que realizó la llamada.  También puede devolver un valor opcional.  Si el método es del tipo `void`, la instrucción `return` se puede omitir.  
  
 Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.  
  
## Ejemplo  
 En el siguiente ejemplo, el método `A()` devuelve la variable `Area` como un valor de tipo [double](../../../csharp/language-reference/keywords/double.md).  
  
 [!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [return \(Instrucción\)](/visual-cpp/cpp/return-statement-cpp)   
 [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)