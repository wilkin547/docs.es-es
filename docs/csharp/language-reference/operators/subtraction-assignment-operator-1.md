---
title: "-= Operador (Referencia de C#) | Microsoft Docs"
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
  - "-=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-= (operador de asignación y sustracción) [C#]"
  - "operador de asignación y sustracción (-=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# -= Operador (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación y resta.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `-=`, por ejemplo  
  
```  
x -= y  
```  
  
 es equivalente a  
  
```  
x = x - y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El significado del [operador \-](../../../csharp/language-reference/operators/subtraction-operator.md) depende de los tipos de `x` e `y` \(resta para operandos numéricos, eliminación delegada para operandos delegados, etc.\).  
  
 El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \-](../../../csharp/language-reference/operators/subtraction-operator.md) \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  
  
 El operador \-\= también se usa en C\# para cancelar la suscripción a un evento.  Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## Ejemplo  
 [!code-cs[csRefOperators#6](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-assignment-operator-1_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)