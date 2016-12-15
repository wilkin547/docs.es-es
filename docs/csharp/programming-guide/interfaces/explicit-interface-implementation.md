---
title: "Implementaci&#243;n de interfaz expl&#237;cita (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "interfaces explícitas [C#]"
  - "interfaces [C#], explícitas"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Implementaci&#243;n de interfaz expl&#237;cita (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Si una [clase](../../../csharp/language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, la implementación de ese miembro en la clase hará que ambas interfaces usen ese miembro como implementación.  En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.  
  
 [!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 Sin embargo, s los miembros de dos [interfaces](../../../csharp/language-reference/keywords/interface.md) no realizan la misma función, esto puede llevar a una implementación incorrecta de una o ambas interfaces.  Es posible implementar un miembro de interfaz explícitamente, creando un miembro de clase que sólo se llama a través de la interfaz y es específico de ésta.  Esto se puede llevar a cabo asignando al miembro de clase el nombre de la interfaz y un punto.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 El miembro de clase `IControl.Paint` sólo está disponible a través de la interfaz `IControl`, mientras que `ISurface.Paint` sólo está disponible a través de `ISurface`.  Ambas implementaciones de método son independientes y ninguna está directamente disponible en la clase.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 La implementación explícita también se usa para resolver casos donde cada una de las dos interfaces declara miembros diferentes del mismo nombre como propiedad y método:  
  
 [!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Para implementar ambas interfaces, una clase tiene que utilizar implementación explícita, ya sea para la propiedad P, el método P o ambos, con el fin de evitar un error del compilador.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)