---
title: "#undef (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#undef"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#undef (directiva) [C#]"
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #undef (Referencia de C#)
La directiva `#undef` permite anular la definición de un símbolo, de tal modo que si se utiliza como expresión de una directiva [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `false`.  
  
 Un símbolo se puede definir mediante la directiva [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) o la opción [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador.  La directiva `#undef` debe aparecer en el archivo antes de cualquier instrucción que no sea una directiva.  
  
## Ejemplo  
  
```  
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
  **DEBUG no está definido**   
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)