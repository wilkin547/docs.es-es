---
title: "#warning (Referencia de C#) | Microsoft Docs"
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
  - "#warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#warning (directiva) [C#]"
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #warning (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#warning` permite generar una advertencia de nivel uno desde una ubicación específica del código.  Por ejemplo:  
  
```  
#warning Deprecated code in this method.  
```  
  
## Comentarios  
 `#warning` se utiliza normalmente en una directiva condicional.  También es posible generar un error definido por el usuario mediante [\#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).  
  
## Ejemplo  
  
```  
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)