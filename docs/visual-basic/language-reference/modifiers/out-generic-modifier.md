---
title: "Out (Modificador gen&#233;rico) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceOut"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "covarianza, Out (palabra clave) [Visual Basic]"
  - "Out (palabra clave) [Visual Basic]"
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Out (Modificador gen&#233;rico) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En los parámetros de tipo genérico, la palabra clave `Out` especifica que el tipo es covariante.  
  
## Comentarios  
 La covarianza permite usar un tipo más derivado que el especificado por el parámetro genérico.  Esto permite la conversión implícita de las clases que implementan interfaces variantes y de los tipos delegados.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Reglas  
 Puede usar la palabra clave `Out` en delegados e interfaces genéricos.  
  
 En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:  
  
-   El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.  
  
    > [!NOTE]
    >  Hay una excepción para esta regla.  Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado.  Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md) y [Usar la varianza para los delegados genéricos Func y Action](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.  
  
 En un delegado genérico, un parámetro de tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.  
  
 La covarianza y contravarianza son compatibles con los tipos de referencia, pero no con los tipos de valor.  
  
 En Visual Basic, no se pueden declarar eventos en las interfaces covariantes sin especificar el tipo de delegado.  Además, una interfaz covariante no puede tener clases, enumeraciones o estructuras anidadas, pero sí interfaces anidadas.  
  
## Comportamiento  
 Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo.  Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.  
  
 A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante.  También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante.  También se muestra cómo usar la conversión implícita para los tipos de delegado.  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## Vea también  
 [Varianza en interfaces genéricas](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)