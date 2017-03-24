---
title: "#error (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#error"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#error (directiva) [C#]"
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# #error (Referencia de C#)
`#error` permite generar un error desde una ubicación específica del código.  Por ejemplo:  
  
```  
#error Deprecated code in this method.  
```  
  
## Comentarios  
 `#error` se utiliza normalmente en una directiva condicional.  
  
 También es posible generar una advertencia definida por el usuario mediante [\#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).  
  
## Ejemplo  
  
```  
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)