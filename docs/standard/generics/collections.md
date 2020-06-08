---
title: Colecciones genéricas en .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: 5767bac0bb1e3ae9e586e9a10d8452d421519447
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287576"
---
# <a name="generic-collections-in-net"></a>Colecciones genéricas en .NET

 La biblioteca de clases de .NET ofrece varias clases de colección genéricas en los espacios de nombres <xref:System.Collections.Generic> y <xref:System.Collections.ObjectModel>. Para obtener información más detallada sobre estas clases, vea [Tipos de colección utilizados normalmente](../collections/commonly-used-collection-types.md).  
  
## <a name="systemcollectionsgeneric"></a>System.Collections.Generic

 Muchos de los tipos de colección genéricos son análogos directos de tipos no genéricos. <xref:System.Collections.Generic.Dictionary%602> es una versión genérica de <xref:System.Collections.Hashtable>; usa la estructura genérica <xref:System.Collections.Generic.KeyValuePair%602> para la enumeración en lugar de <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> es una versión genérica de <xref:System.Collections.ArrayList>. Hay clases <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601> genéricas que se corresponden con las versiones no genéricas.  
  
 Hay versiones genéricas y no genéricas de <xref:System.Collections.Generic.SortedList%602>. Ambas versiones son híbridos de un diccionario y una lista. La clase genérica <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario puro y no tiene ninguna homóloga no genérica.  
  
 La clase genérica <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada genuina. No tiene ninguna homóloga no genérica.  
  
## <a name="systemcollectionsobjectmodel"></a>System.Collections.ObjectModel

 La clase genérica <xref:System.Collections.ObjectModel.Collection%601> proporciona una clase base para derivar sus propios tipos de colección genéricos. La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> proporciona una manera sencilla de generar una colección de solo lectura de cualquier tipo que implementa la interfaz genérica <xref:System.Collections.Generic.IList%601>. La clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> proporciona una manera de almacenar objetos que contienen sus propias claves.  
  
## <a name="other-generic-types"></a>Otros tipos genéricos

 La estructura genérica <xref:System.Nullable%601> permite usar tipos de valor como si se les pudiera asignar el valor `null`. Esto puede ser útil para trabajar con consultas de base de datos en las que pueden faltar campos que contienen tipos de valor. El parámetro de tipo genérico puede ser cualquier tipo de valor.  
  
> [!NOTE]
> En C# y Visual Basic no hay que usar <xref:System.Nullable%601> explícitamente porque el lenguaje tiene sintaxis para tipos que aceptan valores NULL. Consulte [Tipos de valor que admiten un valor NULL (referencia de C#)](../../csharp/language-reference/builtin-types/nullable-value-types.md) y [Tipos de valor que admiten un valor NULL (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).
  
 La estructura genérica <xref:System.ArraySegment%601> proporciona una manera de delimitar un intervalo de elementos en una matriz unidimensional basada en cero de cualquier tipo. El parámetro de tipo genérico es el tipo de los elementos de la matriz.  
  
 El delegado genérico <xref:System.EventHandler%601> elimina la necesidad de declarar un tipo de delegado para controlar los eventos, siempre que el evento siga el patrón de control de eventos que usa .NET Framework. Por ejemplo, supongamos que ha creado una clase `MyEventArgs`, derivada de <xref:System.EventArgs>, para contener los datos del evento. Puede declarar el evento de la siguiente manera:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Genéricos](index.md)
- [Delegados genéricos para manipular matrices y listas](delegates-for-manipulating-arrays-and-lists.md)
- [Interfaces genéricas](interfaces.md)
