---
title: "Especificar dinámicamente filtros con predicado en tiempo de ejecución"
description: "Cómo especificar dinámicamente filtros con predicado en tiempo de ejecución."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8b9ad2603a9c57855f9a8ebd7ff3f5261aa44157
ms.lasthandoff: 03/13/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a>Especificar dinámicamente filtros con predicado en tiempo de ejecución

En algunos casos no se conoce cuántos predicados hay que aplicar a los elementos de origen de la cláusula `where` hasta el tiempo de ejecución. Una forma de especificar dinámicamente varios filtros con predicado es usar el método <xref:System.Linq.Enumerable.Contains%2A>, como se muestra en el ejemplo siguiente. El ejemplo se construye de dos maneras. En primer lugar, el proyecto se ejecuta al filtrar por los valores proporcionados en el programa. Luego se vuelve a ejecutar mediante la entrada proporcionada en tiempo de ejecución.  
  
## <a name="to-filter-by-using-the-contains-method"></a>Para filtrar mediante el método Contains  
  
1.  Abra una nueva aplicación de consola y denomínela `PredicateFilters`.  
  
2.  Copie la clase `StudentClass` desde [Consultar una colección de objetos](query-a-collection-of-objects.md) y péguela en el espacio de nombres `PredicateFilters` debajo de la clase `Program`. `StudentClass` proporciona una lista de objetos `Student`.  
  
3.  Comente el método `Main` de `StudentClass`.  
  
4.  Sustituya la clase `Program` por el siguiente código.  
  
     [!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  Agregue la siguiente línea al método `Main` de la clase `DynamicPredicates`, debajo de la declaración de `ids`.  
  
     ```csharp
     QueryById(ids);
     ```

6.  Ejecute el proyecto.  
  
7.  El resultado siguiente se muestra en una ventana de la consola:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  El siguiente paso es volver a ejecutar el proyecto, esta vez mediante la entrada especificada en tiempo de ejecución en lugar de la matriz `ids`. Cambie `QueryByID(ids)` por `QueryByID(args)` en el método `Main`.  
  
9. Ejecute el proyecto con los argumentos de la línea de comandos `122 117 120 115`. Una vez ejecutado el proyecto, esos valores se convierten en elementos de `args`, el parámetro del método `Main`.  
  
10. El resultado siguiente se muestra en una ventana de la consola:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
## <a name="to-filter-by-using-a-switch-statement"></a>Para filtrar mediante una instrucción switch  
  
1.  Puede usar una instrucción `switch` para seleccionar entre consultas alternativas predeterminadas. En el ejemplo siguiente, `studentQuery` usa otra cláusula `where` en función de qué curso, o año, se especifique en tiempo de ejecución.  
  
2.  Copie el método siguiente y péguelo en la clase `DynamicPredicates`.  
  
     [!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  En el método `Main`, sustituya la llamada a `QueryByID` por la siguiente llamada, que envía el primer elemento de la matriz `args` como su argumento: `QueryByYear(args[0])`.  
  
4.  Ejecute el proyecto con un argumento de la línea de comandos de un valor entero entre 1 y 4.  
  
 
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)   
 [where (cláusula)](../language-reference/keywords/where-clause.md)
