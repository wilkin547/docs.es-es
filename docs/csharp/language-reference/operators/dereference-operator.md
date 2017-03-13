---
title: "-&gt; (operador) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "->_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-> (operador) [C#]"
  - "operador de acceso a miembro (->) [C#]"
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# -&gt; (operador) (Referencia de C#)
El operador `->` combina la desreferenciación de un puntero y el acceso a un miembro.  
  
## Comentarios  
 Una expresión de la forma  
  
```  
x->y  
```  
  
 \(donde `x` es un puntero de tipo `T*` e `y` es un miembro de `T`\) equivale a  
  
```  
(*x).y  
```  
  
 El operador `->` sólo puede utilizarse en código marcado como [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
 El operador `->` no se puede sobrecargar.  
  
## Ejemplo  
 [!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)