---
title: "in (Modificador gen&#233;rico) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "contravarianza, in (palabra clave) [C#]"
  - "in (palabra clave) [C#]"
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# in (Modificador gen&#233;rico) (Referencia de C#)
En los parámetros de tipo genérico, la palabra clave `in` especifica que el parámetro de tipo es contravariante.  Puede usar la palabra clave `in` en delegados e interfaces genéricos.  
  
 La contravarianza permite usar un tipo menos derivado que el especificado por el parámetro genérico.  Esto permite la conversión implícita de las clases que implementan interfaces variantes y de los tipos delegados.  La covarianza y contravarianza en los parámetros de tipo genérico son compatibles con los tipos de referencia, pero no con los tipos de valor.  
  
 Un tipo se puede declarar como contravariante en una interfaz o un delegado genérico si solamente se usa solamente como tipo de los argumentos de método y no como tipo devuelto por un método.  Los parámetros `Ref` y `out` no pueden ser variantes.  
  
 Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los especificados por el parámetro de tipo de interfaz.  Por ejemplo, dado que en .NET Framework 4, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto del tipo `IComparer(Of Person)` a otro objeto del tipo `IComparer(Of Employee)` sin usar ningún método de conversión especial si `Employee` hereda `Person`.  
  
 A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.  También se muestra cómo se puede usar la conversión implícita para las clases que implementan dicha interfaz.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/csharp/in-generic-modifier_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico contravariante.  También se muestra cómo se puede convertir un tipo de delegado implícitamente.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/csharp/in-generic-modifier_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)