---
title: "interface (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "interface_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "interface (palabra clave) [C#]"
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# interface (Referencia de C#)
Una interfaz contiene solo las signaturas de [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [eventos](../../../csharp/programming-guide/events/index.md) o [indizadores](../../../csharp/programming-guide/indexers/index.md).  Una clase o struct que implemente la interfaz debe implementar los miembros de la interfaz que se especifican en la definición de interfaz.  En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.  
  
 Para obtener más información y ejemplos, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).  
  
## Ejemplo  
 [!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 Una interfaz puede ser miembro de un espacio de nombres o de una clase, y puede contener signaturas de los siguientes miembros:  
  
-   [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Indizadores](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Eventos](../../../csharp/language-reference/keywords/event.md)  
  
 Una interfaz puede heredar de una o varias interfaces base.  
  
 Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.  
  
 Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz.  A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.  
  
 Para obtener información más detallada y ejemplos de código de la implementación de interfaces explícita, vea [Implementación explícita de interfaz](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la implementación de una interfaz.  En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación.  Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.  
  
 [!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Utilizar indizadores](../../../csharp/programming-guide/indexers/using-indexers.md)   
 [clase](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)