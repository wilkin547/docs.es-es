---
title: "Delegados con m&#233;todos con nombre y delegados con m&#233;todos an&#243;nimos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "delegados [C#], con métodos con nombre y con métodos anónimos"
  - "métodos [C#], en delegados"
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Delegados con m&#233;todos con nombre y delegados con m&#233;todos an&#243;nimos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se puede asociar un [delegado](../../../csharp/language-reference/keywords/delegate.md) a un método con nombre.  Cuando se crean instancias de un delegado mediante un método con nombre, el método se pasa como parámetro; por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 Esto se denomina utilizar un método con nombre.  Los delegados creados con un método con nombre pueden encapsular un método [estático](../../../csharp/language-reference/keywords/static.md) o un método de instancia.  Los métodos con nombre son la única forma de crear instancias de un delegado en versiones anteriores de C\#.  Sin embargo, en una situación en la que crear un método nuevo constituye una sobrecarga no deseada, C\# permite crear instancias de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se le llame.  El bloque puede contener una expresión lambda o un método anónimo.  Para obtener más información, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Comentarios  
 El método, que se pasa como parámetro de delegado, debe tener la misma firma que la declaración de delegado.  
  
 La instancia de un delegado puede encapsular un método estático o de instancia.  
  
 Aunque el delegado puede utilizar un parámetro [out](../../../csharp/language-reference/keywords/out.md), no se recomienda su uso con delegados de eventos de multidifusión porque no se puede saber a qué delegado se va a llamar.  
  
## Ejemplo 1  
 El siguiente es un ejemplo sencillo de declaración y uso de un delegado.  Observe que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## Ejemplo 2  
 En el siguiente ejemplo, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno de ellos.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [Cómo: Combinar delegados \(delegados de multidifusión\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)