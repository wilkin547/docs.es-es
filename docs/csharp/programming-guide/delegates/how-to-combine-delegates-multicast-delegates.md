---
title: "C&#243;mo: Combinar delegados (delegados de multidifusi&#243;n) (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegados [C#], combinar"
  - "delegados de multidifusión [C#]"
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# C&#243;mo: Combinar delegados (delegados de multidifusi&#243;n) (Gu&#237;a de programaci&#243;n de C#)
En este ejemplo se muestra cómo se crean delegados de multidifusión.  Una propiedad útil de los objetos [delegate](../../../csharp/language-reference/keywords/delegate.md) es que se pueden asignar varios objetos a una única instancia del delegado con el operador `+`.  El delegado de multidifusión contiene una lista de los delegados asignados.  Cuando se llama al delegado de multidifusión, este invoca los delegados de la lista, en orden.  Solo pueden combinarse delegados del mismo tipo.  
  
 El operador `-` se puede usar para quitar un delegado componente de un delegado de multidifusión.  
  
## Ejemplo  
 [!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#11)]  
  
## Vea también  
 <xref:System.MulticastDelegate>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)