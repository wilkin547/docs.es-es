---
title: "Interfaces gen&#233;ricas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, interfaces genéricas"
  - "genéricos [C#], interfaces"
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Interfaces gen&#233;ricas (Gu&#237;a de programaci&#243;n de C#)
A menudo es útil definir interfaces para las clases de colección genéricas o para las clases genéricas que representan los elementos de la colección.  Lo preferible para las clases genéricas es utilizar interfaces genéricas, como <xref:System.IComparable%601> en lugar de <xref:System.IComparable>, para evitar las operaciones de conversión boxing y unboxing en los tipos de valor.  La biblioteca de clases de .NET Framework define varias interfaces genéricas para utilizarlas con las clases de colección del espacio de nombres <xref:System.Collections.Generic>.  
  
 Cuando una interfaz se especifica como restricción en un parámetro de tipo, sólo se pueden utilizar los tipos que implementan la interfaz.  El ejemplo de código siguiente muestra una clase `SortedList<T>` derivada de la clase `GenericList<T>`.  Para obtener más información, vea [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md).  `SortedList<T>` agrega la restricción `where T : IComparable<T>`.  Esto permite al método `BubbleSort` de `SortedList<T>` utilizar el método <xref:System.IComparable%601.CompareTo%2A> genérico con los elementos de lista.  En este ejemplo, los elementos de lista son una clase simple, `Person`, que implementa `IComparable<Person>`.  
  
 [!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_1.cs)]  
  
 Se pueden especificar varias interfaces como restricciones en un solo tipo, de la siguiente manera:  
  
 [!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_2.cs)]  
  
 Una interfaz puede definir más de un parámetro de tipo, de la siguiente manera:  
  
 [!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_3.cs)]  
  
 Las reglas de herencia que se aplican a las clases también se aplican a las interfaces:  
  
 [!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_4.cs)]  
  
 Las interfaces genéricas pueden heredar de interfaces no genéricas si son contra\-variantes, lo que significa que sólo utilizan su parámetro de tipo como valor devuelto.  En la biblioteca de clases de .NET Framework, <xref:System.Collections.Generic.IEnumerable%601> hereda de <xref:System.Collections.IEnumerable> porque <xref:System.Collections.Generic.IEnumerable%601> sólo utiliza `T` en el valor devuelto de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> y en el captador de propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Las clases concretas pueden implementar interfaces construidas cerradas, de la siguiente manera:  
  
 [!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_5.cs)]  
  
 Las clases genéricas pueden implementar interfaces genéricas o interfaces construidas cerradas siempre que la lista de parámetros de la clase suministre todos los argumentos que necesita la interfaz, de la siguiente manera:  
  
 [!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-interfaces_6.cs)]  
  
 Las reglas que controlan la sobrecarga de métodos son las mismas para los métodos incluidos en las clases genéricas, los structs genéricos o las interfaces genéricas.  Para obtener más información, vea [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [interfaz](../../../csharp/language-reference/keywords/interface.md)   
 [Genéricos](../Topic/Generics%20in%20the%20.NET%20Framework.md)