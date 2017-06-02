---
title: "Delegados gen&#233;ricos para manipular matrices y listas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "matrices [.NET Framework], delegados genéricos"
  - "encadenar delegados"
  - "delegados [.NET Framework], delegados genéricos"
  - "delegados genéricos [.NET Framework]"
  - "genéricos [.NET Framework], delegados"
  - "listas [.NET Framework], delegados genéricos"
ms.assetid: 416be383-cc61-4102-9b1b-88b51adb963e
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Delegados gen&#233;ricos para manipular matrices y listas
En este tema se ofrece una introducción a los delegados genéricos para conversiones, predicados de búsqueda y acciones realizadas en los elementos de una matriz o colección.  
  
## Delegados genéricos para manipular matrices y listas  
 El delegado genérico <xref:System.Action%601> representa un método que realiza alguna acción en un elemento del tipo especificado.  Puede crear un método que realiza la acción deseada en el elemento, crear una instancia del delegado <xref:System.Action%601> para que represente ese método y, después, pasar la matriz y el delegado al método genérico estático <xref:System.Array.ForEach%2A?displayProperty=fullName>.  Se llama al método para cada elemento de la matriz.  
  
 La clase genérica <xref:System.Collections.Generic.List%601> también proporciona un método <xref:System.Collections.Generic.List%601.ForEach%2A> que usa el delegado <xref:System.Action%601>.  Este método no es genérico.  
  
> [!NOTE]
>  Este es un aspecto interesante de los tipos y métodos genéricos.  El método <xref:System.Array.ForEach%2A?displayProperty=fullName> debe ser estático \(`Shared` en Visual Basic\) y genérico porque <xref:System.Array> no es un tipo genérico; la única razón por la que se puede especificar un tipo para que <xref:System.Array.ForEach%2A?displayProperty=fullName> opere sobre él es que el método tiene su propia lista de parámetros de tipo.  Por el contrario, el método no genérico <xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=fullName> pertenece a la clase genérica <xref:System.Collections.Generic.List%601>, por lo que simplemente utiliza el parámetro de tipo de su clase.  La clase está fuertemente tipada, por lo que el método puede ser un método de instancia.  
  
 El delegado genérico <xref:System.Predicate%601> representa un método que determina si un determinado elemento cumple los criterios definidos.  Puede usar los siguientes métodos genéricos estáticos de <xref:System.Array> para buscar un elemento o un conjunto de elementos: <xref:System.Array.Exists%2A>, <xref:System.Array.Find%2A>, <xref:System.Array.FindAll%2A>, <xref:System.Array.FindIndex%2A>, <xref:System.Array.FindLast%2A>, <xref:System.Array.FindLastIndex%2A> y <xref:System.Array.TrueForAll%2A>.  
  
 <xref:System.Predicate%601> también trabaja con los correspondientes métodos de instancia no genéricos de la clase genérica <xref:System.Collections.Generic.List%601>.  
  
 El delegado genérico <xref:System.Comparison%601> permite proporcionar un criterio de ordenación para los elementos de la matriz o la lista que no tienen un criterio de ordenación nativo, o para reemplazar el criterio de ordenación nativo.  Cree un método que realice la comparación, cree una instancia del delegado <xref:System.Comparison%601> para representar el método y, después, pase la matriz y el delegado al método genérico estático [Array.Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29?displayProperty=fullName>.  La clase genérica <xref:System.Collections.Generic.List%601> proporciona una sobrecarga del método de instancia correspondiente, <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29?displayProperty=fullName>.  
  
 El delegado genérico <xref:System.Converter%602> permite definir una conversión entre dos tipos y convertir una matriz de un tipo en una matriz del otro, o convertir una lista de un tipo a una lista del otro.  Cree un método que convierta los elementos de la lista existente a un nuevo tipo, cree una instancia de delegado para representar el método y use el método estático genérico <xref:System.Array.ConvertAll%2A?displayProperty=fullName> para producir una matriz del nuevo tipo a partir de la matriz original, o el método de instancia genérico <xref:System.Collections.Generic.List%601.ConvertAll%2A?displayProperty=fullName> para producir una lista del nuevo tipo a partir de la lista original.  
  
### Encadenar delegados  
 Muchos de los métodos que usan estos delegados devuelven una matriz o una lista, que se puede pasar a otro método.  Por ejemplo, si quiere seleccionar determinados elementos de una matriz, convertirlos a un nuevo tipo y guardarlos en una nueva matriz, puede pasar la matriz devuelta por el método genérico <xref:System.Array.FindAll%2A> al método genérico <xref:System.Array.ConvertAll%2A>.  Si el nuevo tipo de elemento carece de un criterio de ordenación natural, puede pasar la matriz devuelta por el método genérico <xref:System.Array.ConvertAll%2A> al método genérico [Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29>.  
  
## Vea también  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [Genéricos](../../../docs/standard/generics/index.md)   
 [Colecciones genéricas en .NET Framework](../../../docs/standard/generics/collections.md)   
 [Interfaces genéricas](../../../docs/standard/generics/interfaces.md)   
 [Covarianza y contravarianza](../../../docs/standard/generics/covariance-and-contravariance.md)