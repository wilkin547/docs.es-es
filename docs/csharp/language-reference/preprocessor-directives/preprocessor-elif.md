---
title: "#elif (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#elif"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#elif (directiva) [C#]"
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# #elif (Referencia de C#)
`#elif` permite crear una directiva condicional compuesta.  La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o `#elif` \(opcional\) precedentes se evalúan como `true`.  Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional.  Por ejemplo:  
  
```  
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 Se pueden usar los operadores `==` \(igualdad\), `!=` \(desigualdad\), `&&` \(y\), así como `||` \(o\), para evaluar varios símbolos.  Es posible agrupar símbolos y operadores mediante paréntesis.  
  
## Comentarios  
 `#elif` equivale a usar:  
  
```  
#else  
#if  
```  
  
 El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.  
  
 Vea [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)