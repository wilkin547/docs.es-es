---
title: "out (Modificador gen&#233;rico) (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "covarianza, out (palabra clave) [C#]"
  - "out (palabra clave) [C#]"
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# out (Modificador gen&#233;rico) (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En los parámetros de tipo genérico, la palabra clave `out` especifica que el parámetro de tipo es covariante.  Puede usar la palabra clave `out` en delegados e interfaces genéricos.  
  
 La covarianza permite usar un tipo más derivado que el especificado por el parámetro genérico.  Esto permite la conversión implícita de las clases que implementan interfaces variantes y de los tipos delegados.  La covarianza y contravarianza son compatibles con los tipos de referencia, pero no con los tipos de valor.  
  
 Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo.  Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.  
  
 A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante.  También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.  
  
 [!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:  
  
-   El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.  
  
    > [!NOTE]
    >  Hay una excepción para esta regla.  Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado.  Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md) y [Usar la varianza para los delegados genéricos Func y Action](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante.  También se muestra cómo convertir implícitamente los tipos de delegado.  
  
 [!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 En un delegado genérico, un tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Varianza en interfaces genéricas](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [in](../../../csharp/language-reference/keywords/in-generic-modifier.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)