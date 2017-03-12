---
title: "In (Modificador gen&#233;rico) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceIn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "contravarianza, In (palabra clave) [Visual Basic]"
  - "In (palabra clave) [Visual Basic]"
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# In (Modificador gen&#233;rico) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.  
  
## Comentarios  
 La contravarianza permite usar un tipo menos derivado que el especificado por el parámetro genérico.  Esto permite la conversión implícita de las clases que implementan interfaces variantes y de los tipos delegados.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Reglas  
 Puede usar la palabra clave `In` en delegados e interfaces genéricos.  
  
 Un parámetro de tipo se puede declarar como contravariante en una interfaz o un delegado genérico si solamente se usa como tipo de los argumentos de método y no como tipo devuelto por un método.  Los parámetros `ByRef` no pueden ser covariantes o contravariantes.  
  
 La covarianza y contravarianza son compatibles con los tipos de referencia y no con los tipos de valor.  
  
 En Visual Basic, no se pueden declarar eventos en interfaces contravariantes sin especificar el tipo de delegado.  Además, una interfaz contravariante no puede tener clases, enumeraciones o estructuras anidadas, pero sí interfaces anidadas.  
  
## Comportamiento  
 Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los especificados por el parámetro de tipo de interfaz.  Por ejemplo, dado que en .NET Framework 4, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto del tipo `IComparer(Of Person)` a otro objeto del tipo `IComparer(Of Employee)` sin usar ningún método de conversión especial si `Person` hereda `Employee`.  
  
 A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.  También se muestra cómo se puede usar la conversión implícita para las clases que implementan dicha interfaz.  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/in-generic-modifier_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico contravariante.  También se muestra cómo se puede convertir un tipo de delegado implícitamente.  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/in-generic-modifier_2.vb)]  
  
## Vea también  
 [Varianza en interfaces genéricas](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)