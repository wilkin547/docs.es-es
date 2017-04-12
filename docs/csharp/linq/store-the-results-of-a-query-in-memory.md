---
title: Almacenar los resultados de una consulta en memoria
description: "Cómo almacenar resultados."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 644db94bc739d0ae465e28315f0ec43ef6ac241e
ms.lasthandoff: 03/13/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a>Almacenar los resultados de una consulta en memoria

Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar los datos. Las consultas se ejecutan de forma diferida, ya que se solicita cada elemento subsiguiente del resultado. Cuando se usa `foreach` para iterar los resultados, los elementos se devuelven a medida que se tiene acceso a ellos. Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Recomendamos que, al almacenar los resultados de consulta, asigne el objeto de colección devuelto a una nueva variable tal como se muestra en el ejemplo siguiente:  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
