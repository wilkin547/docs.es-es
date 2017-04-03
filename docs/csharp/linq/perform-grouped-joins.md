---
title: Realizar combinaciones agrupadas
description: "Cómo realizar combinaciones agrupadas."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ee055b8e65f8aa48f1211871719b9e638e71ed1
ms.lasthandoff: 03/13/2017

---
# <a name="perform-grouped-joins"></a>Realizar combinaciones agrupadas

La combinación agrupada resulta útil para generar estructuras de datos jerárquicas. Empareja cada elemento de la primera colección con un conjunto de elementos correlacionados de la segunda colección.  
  
 Por ejemplo, una clase o una tabla de base de datos relacional denominada `Student` podría contener dos campos: `Id` y `Name`. Una segunda clase o tabla de base de datos relacional denominada `Course` podría contener dos campos: `StudentId` y `CourseTitle`. Una combinación agrupada de estos dos orígenes de datos, basada en la combinación de `Student.Id` y `Course.StudentId`, agruparía cada `Student` con una colección de objetos `Course` (que podrían estar vacíos).  
  
> [!NOTE]
>  Cada elemento de la primera colección aparece en el conjunto de resultados de una combinación agrupada, independientemente de si se encuentran elementos correlacionados en la segunda colección. En el caso de que no se encuentren elementos correlacionados, la secuencia de elementos correlacionados para ese elemento estaría vacía. Por consiguiente, el selector de resultados tiene acceso a cada uno de los elementos de la primera colección. Esto difiere del selector de resultados en una combinación no agrupada, que no puede acceder a los elementos de la primera colección que no tienen ninguna coincidencia en la segunda colección.  
  
 En el primer ejemplo de este tema se muestra cómo realizar una combinación agrupada. En el segundo ejemplo se muestra cómo usar una combinación agrupada para crear elementos XML.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="group-join-example"></a>Ejemplo de combinación agrupada  
 En el ejemplo siguiente se realiza una combinación agrupada de objetos de tipo `Person` y `Pet` basada en la coincidencia de `Person` con la propiedad `Pet.Owner`. A diferencia de una combinación no agrupada, que generaría un par de elementos para cada coincidencia, la combinación agrupada produce un único objeto resultante para cada elemento de la primera colección, que en este ejemplo es un objeto `Person`. Los elementos correspondientes de la segunda colección, que en este ejemplo son objetos `Pet`, se agrupan en una colección. Por último, la función de selector de resultados crea un tipo anónimo para cada coincidencia formada por `Person.FirstName` y una colección de objetos `Pet`.  
  
 [!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="group-join-to-create-xml-example"></a>Ejemplo de combinación agrupada para crear XML  
 Las combinaciones agrupadas resultan ideales para crear XML con LINQ to XML. El siguiente ejemplo es similar al anterior, pero en lugar de crear tipos anónimos, la función de selector de resultados crea elementos XML que representan los objetos combinados.  
  
 [!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Realizar combinaciones internas](perform-inner-joins.md)   
 [Perform left outer joins](perform-left-outer-joins.md)  (Realizar operaciones de combinación externa izquierda)  
 [Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])   
 
