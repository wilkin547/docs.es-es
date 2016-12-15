---
title: "void (Referencia de C#) | Microsoft Docs"
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
  - "void_CSharpKeyword"
  - "void"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "void (palabra clave) [C#]"
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# void (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando se utiliza como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.  
  
 `void` no se permite en la lista de parámetros de un método.  Un método que no utiliza parámetros y que no devuelve ningún valor se declara del siguiente modo:  
  
```  
public void SampleMethod()  
{  
    // Body of the method.  
}  
  
```  
  
 `void` también se utiliza en un contexto no seguro para declarar un puntero a un tipo desconocido.  Para obtener más información, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
 `void` es un alias para el tipo <xref:System.Void?displayProperty=fullName> de .NET Framework.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)