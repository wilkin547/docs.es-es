---
title: "/= (operador) (Referencia de C#) | Microsoft Docs"
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
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (operador de asignación y división) [C#]"
  - "operador de asignación y división (/=) [C#]"
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /= (operador) (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación y división.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `/=`, por ejemplo  
  
```  
x /= y  
```  
  
 es equivalente a  
  
```  
x = x / y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador \/](../../../csharp/language-reference/operators/division-operator.md) está predefinido con la división para tipos numéricos.  
  
 El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \/](../../../csharp/language-reference/operators/division-operator.md) \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.  
  
## Ejemplo  
 [!code-cs[csRefOperators#5](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)