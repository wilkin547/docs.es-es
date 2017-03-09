---
title: "Par&#225;metros de tipos gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], parámetros de tipo"
  - "parámetros de tipo [C#]"
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Par&#225;metros de tipos gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
En una definición de tipo o método genérico, un parámetro de tipo es un marcador para un tipo especificado por un cliente al crear una instancia de una variable del tipo genérico.  Una clase genérica, como `GenericList<T>`, que se muestra en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md), no se puede utilizar tal cual, porque no es realmente un tipo, sino el plano de un tipo.  Para utilizar `GenericList<T>`, el código de cliente debe declarar y crear una instancia de un tipo construido especificando un argumento de tipo dentro de los corchetes angulares.  El argumento de tipo para esta clase determinada puede ser cualquier tipo reconocido por el compilador.  Se puede crear cualquier número de instancias del tipo construido, cada una de ellas con un argumento de tipo diferente, de la forma siguiente:  
  
 [!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-type-parameters_1.cs)]  
  
 En cada una de estas instancias de `GenericList<T>`, cada aparición de `T` en la clase se sustituirá en tiempo de ejecución con el argumento de tipo.  Mediante esta sustitución, hemos creado tres objetos independientes y eficaces con seguridad de tipos utilizando una sola definición de clase.  Para obtener más información sobre cómo el CLR realiza esta sustitución, vea [Genéricos en el motor en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## Instrucciones de nomenclatura de parámetros de tipo  
  
-   **Denomine** los parámetros de tipo genérico con nombres descriptivos, a menos que un nombre de una sola letra sea muy fácil de entender y un nombre descriptivo no agregue ningún valor.  
  
     [!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-type-parameters_2.cs)]  
  
-   **Considere** el uso de T como nombre del parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.  
  
     [!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-type-parameters_3.cs)]  
  
-   **Añada** el prefijo "T" a los nombres de parámetros de tipo descriptivos.  
  
     [!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-type-parameters_4.cs)]  
  
-   **Considere** indicar las restricciones de un parámetro de tipo en el nombre del parámetro.  Por ejemplo, un parámetro restringido a `ISession` se puede denominar `TSession`.  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Diferencias entre plantillas de C\+\+ y tipos genéricos de C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)