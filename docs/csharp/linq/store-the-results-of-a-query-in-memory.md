---
title: Almacenar los resultados de una consulta en memoria
description: Cómo almacenar resultados.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 66a7a95c74db4062e76c54d4339ccb7343f44067
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633565"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="cf75c-103">Almacenar los resultados de una consulta en memoria</span><span class="sxs-lookup"><span data-stu-id="cf75c-103">Store the results of a query in memory</span></span>

<span data-ttu-id="cf75c-104">Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar los datos.</span><span class="sxs-lookup"><span data-stu-id="cf75c-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="cf75c-105">Las consultas se ejecutan de forma diferida, ya que se solicita cada elemento subsiguiente del resultado.</span><span class="sxs-lookup"><span data-stu-id="cf75c-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="cf75c-106">Cuando se usa `foreach` para iterar los resultados, los elementos se devuelven a medida que se tiene acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="cf75c-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="cf75c-107">Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:</span><span class="sxs-lookup"><span data-stu-id="cf75c-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="cf75c-108">Recomendamos que, al almacenar los resultados de consulta, asigne el objeto de colección devuelto a una nueva variable tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf75c-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="cf75c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf75c-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="cf75c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf75c-110">See also</span></span>

- [<span data-ttu-id="cf75c-111">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cf75c-111">Language Integrated Query (LINQ)</span></span>](index.md)
