---
title: "Operador += (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+= (operador) [C#]"
  - "+= (operador de asignación y suma) [C#]"
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Operador += (Referencia de C#)
El operador de asignación y suma.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `+=`, por ejemplo  
  
```  
x += y  
```  
  
 es equivalente a  
  
```  
x = x + y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El significado del [operador \+](../../../csharp/language-reference/operators/addition-operator.md) depende de los tipos de `x` e `y` \(suma para operandos numéricos, concatenación para operandos de tipo cadena, etc.\).  
  
 El operador `+=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \+](../../../csharp/language-reference/operators/addition-operator.md) \(vea [operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
 El operador `+=` se utiliza también para especificar un método al que se llama en respuesta a un evento; estos métodos se denominan controladores de eventos.  El uso del operador `+=` en este contexto se denomina *suscribirse a un evento*.  Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  y [Delegados](../../../csharp/programming-guide/delegates/index.md).  
  
## Ejemplo  
 [!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#35)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)