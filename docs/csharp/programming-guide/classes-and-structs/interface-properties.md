---
title: "Propiedades de interfaces (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "interfaces [C#], propiedades"
  - "propiedades [C#], en interfaces"
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Propiedades de interfaces (Gu&#237;a de programaci&#243;n de C#)
Las propiedades se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md).  A continuación se muestra un ejemplo de descriptor de acceso de un indizador de interfaz:  
  
 [!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_1.cs)]  
  
 Un identificador de acceso de una propiedad de interfaz no tiene cuerpo.  Así, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de sólo lectura o de sólo escritura.  
  
## Ejemplo  
 En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de sólo lectura, `Counter`.  La clase `Employee` implementa la interfaz `IEmployee` y utiliza las dos propiedades.  El programa lee el nombre de un empleado nuevo y el número actual de empleados, y muestra como resultado el nombre del empleado y el nuevo número de empleados calculado.  
  
 Se podría utilizar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro.  Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 Esto se denomina [Implementación explícita de interfaz](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas tienen la propiedad `Name`, será necesario implementar explícitamente el miembro de interfaz.  Es decir, la siguiente declaración de propiedad:  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la declaración:  
  
 [!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_3.cs)]  
  
 implementa la propiedad `Name` en la interfaz `ICitizen`.  
  
 [!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## Resultados del ejemplo  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)