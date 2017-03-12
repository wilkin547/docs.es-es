---
title: "C&#243;mo: Implementar expl&#237;citamente miembros de interfaz (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "interfaces [C#], implementar de forma explícita"
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# C&#243;mo: Implementar expl&#237;citamente miembros de interfaz (Gu&#237;a de programaci&#243;n de C#)
En este ejemplo se declara una [interfaz](../../../csharp/language-reference/keywords/interface.md) `IDimensions` y una clase `Box`, la cual implementa explícitamente los miembros de la interfaz `getLength` y `getWidth`.  El acceso a los miembros se realiza a través de la instancia de interfaz `dimensions`.  
  
## Ejemplo  
 [!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_1_1.cs)]  
  
## Programación eficaz  
  
-   Observe que las siguientes líneas, en el método `Main`, están desactivadas mediante comentarios, ya que producirían errores de compilación.  No se puede obtener acceso desde una instancia de [clase](../../../csharp/language-reference/keywords/class.md) a un miembro de interfaz implementado explícitamente:  
  
     [!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_1_2.cs)]  
  
-   Observe también que las siguientes líneas del método `Main` imprimen correctamente las dimensiones del cuadro, ya que los métodos se invocan desde una instancia de la interfaz:  
  
     [!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_1_3.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [Cómo: Implementar explícitamente miembros de dos interfaces](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)