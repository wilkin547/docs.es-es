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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 35d908bde06ef55ba2dc93a73211f7be33b9332c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="d027a-104">Almacenar los resultados de una consulta en memoria</span><span class="sxs-lookup"><span data-stu-id="d027a-104">Store the results of a query in memory</span></span>

<span data-ttu-id="d027a-105">Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar los datos.</span><span class="sxs-lookup"><span data-stu-id="d027a-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="d027a-106">Las consultas se ejecutan de forma diferida, ya que se solicita cada elemento subsiguiente del resultado.</span><span class="sxs-lookup"><span data-stu-id="d027a-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="d027a-107">Cuando se usa `foreach` para iterar los resultados, los elementos se devuelven a medida que se tiene acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="d027a-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="d027a-108">Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:</span><span class="sxs-lookup"><span data-stu-id="d027a-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="d027a-109">Recomendamos que, al almacenar los resultados de consulta, asigne el objeto de colección devuelto a una nueva variable tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d027a-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="d027a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d027a-110">Example</span></span>  
 <span data-ttu-id="d027a-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d027a-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="d027a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d027a-112">See Also</span></span>  
 [<span data-ttu-id="d027a-113">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="d027a-113">LINQ Query Expressions</span></span>](index.md)

