---
title: Almacenar los resultados de una consulta en memoria
description: Cómo almacenar resultados.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 52d502a841c428bd90a26c803ba577e76c17197c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404306"
---
# <a name="store-the-results-of-a-query-in-memory"></a>Almacenar los resultados de una consulta en memoria

Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar los datos. Las consultas se ejecutan de forma diferida, ya que se solicita cada elemento subsiguiente del resultado. Cuando se usa `foreach` para iterar los resultados, los elementos se devuelven a medida que se tiene acceso a ellos. Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 Recomendamos que, al almacenar los resultados de consulta, asigne el objeto de colección devuelto a una nueva variable tal como se muestra en el ejemplo siguiente:

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a>Vea también

[Language-Integrated Query (LINQ)](index.md)