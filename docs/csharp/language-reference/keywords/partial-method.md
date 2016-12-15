---
title: "M&#233;todo parcial (Referencia de C#) | Microsoft Docs"
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
  - "partialmethod_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "métodos parciales [C#]"
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# M&#233;todo parcial (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo.  Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no.  Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación.  Se aplican las siguientes condiciones a los métodos parciales:  
  
-   Las signaturas de ambas partes del tipo parcial deben coincidir.  
  
-   El método debe devolver el valor void.  
  
-   No se permiten modificadores de acceso.  Los métodos parciales son privados implícitamente.  
  
 En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:  
  
 [!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Para obtener más información, vea [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [partial \(Tipos\)](../../../csharp/language-reference/keywords/partial-type.md)