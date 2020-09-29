---
title: 'Interfaces genéricas: Guía de programación de C#'
description: Aprenda a usar interfaces genéricas en C#. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: ec86395a41baea75694572b59b2c76cbde24fedf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170394"
---
# <a name="generic-interfaces-c-programming-guide"></a>Interfaces genéricas (Guía de programación de C#)

A menudo es útil definir interfaces para las clases de colección genéricas o para las clases genéricas que representan los elementos de la colección. Lo preferible para las clases genéricas es usar interfaces genéricas, como <xref:System.IComparable%601> en lugar de <xref:System.IComparable>, para evitar las operaciones de conversión boxing y unboxing en los tipos de valor. En la biblioteca de clases de .NET se definen varias interfaces genéricas para usarlas con las clases de colección del espacio de nombres <xref:System.Collections.Generic>.  
  
 Cuando una interfaz se especifica como restricción en un parámetro de tipo, solo se pueden usar los tipos que implementan la interfaz. El ejemplo de código siguiente muestra una clase `SortedList<T>` derivada de la clase `GenericList<T>`. Para obtener más información, vea [Introducción a los genéricos](./index.md). `SortedList<T>` agrega la restricción `where T : IComparable<T>`. Esto permite al método `BubbleSort` de `SortedList<T>` usar el método <xref:System.IComparable%601.CompareTo%2A> genérico con los elementos de lista. En este ejemplo, los elementos de lista son una clase simple, `Person`, que implementa `IComparable<Person>`.  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 Se pueden especificar varias interfaces como restricciones en un solo tipo, de la siguiente manera:  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 Una interfaz puede definir más de un parámetro de tipo, de la siguiente manera:  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 Las reglas de herencia que se aplican a las clases también se aplican a las interfaces:  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 Las interfaces genéricas pueden heredar de interfaces no genéricas si son contravariantes, lo que significa que solo usan su parámetro de tipo como valor devuelto. En la biblioteca de clases de .NET, <xref:System.Collections.Generic.IEnumerable%601> hereda de <xref:System.Collections.IEnumerable> porque <xref:System.Collections.Generic.IEnumerable%601> solo usa `T` en el valor devuelto de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> y en el captador de propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Las clases concretas pueden implementar interfaces construidas cerradas, de la siguiente manera:  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 Las clases genéricas pueden implementar interfaces genéricas o interfaces construidas cerradas siempre que la lista de parámetros de la clase suministre todos los argumentos que necesita la interfaz, de la siguiente manera:  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 Las reglas que controlan la sobrecarga de métodos son las mismas para los métodos incluidos en las clases genéricas, los structs genéricos o las interfaces genéricas. Para obtener más información, vea [Métodos genéricos](./generic-methods.md).  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Introducción a los genéricos](./index.md)
- [interface](../../language-reference/keywords/interface.md)
- [Genéricos](../../../standard/generics/index.md)
