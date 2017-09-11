---
title: "Realizar operaciones de combinación externa izquierda"
description: "Cómo realizar operaciones de combinación externa izquierda."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d81f6e9df228dc6eec985253f53b70a95493ed42
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="ec52c-104">Realizar operaciones de combinación externa izquierda</span><span class="sxs-lookup"><span data-stu-id="ec52c-104">Perform left outer joins</span></span>
<span data-ttu-id="ec52c-105">Una combinación externa izquierda es una combinación en la que se devuelve cada elemento de la primera colección, independientemente de si tiene elementos correlacionados en la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="ec52c-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="ec52c-106">Puede usar LINQ para realizar una combinación externa izquierda llamando al método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="ec52c-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec52c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec52c-107">Example</span></span>  
 <span data-ttu-id="ec52c-108">En el ejemplo siguiente se muestra cómo usar el método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada para realizar una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="ec52c-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="ec52c-109">El primer paso para generar una combinación externa izquierda de dos colecciones consiste en realizar una combinación interna usando una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="ec52c-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="ec52c-110">(Vea [Realizar combinaciones internas](perform-inner-joins.md) para obtener una explicación de este proceso). En este ejemplo, la lista de objetos de `Person` está unida a la lista de objetos `Pet` basándose en un objeto `Person` que coincide con `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="ec52c-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="ec52c-111">El segundo paso consiste en incluir cada elemento de la primera colección (izquierda) en el conjunto de resultados, incluso cuando no haya coincidencias en la colección derecha.</span><span class="sxs-lookup"><span data-stu-id="ec52c-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="ec52c-112">Esto se realiza llamando a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de elementos coincidentes de la combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="ec52c-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="ec52c-113">En este ejemplo, se llama a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de objetos `Pet` coincidentes.</span><span class="sxs-lookup"><span data-stu-id="ec52c-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="ec52c-114">El método devuelve una colección que contiene un único, valor predeterminado si la secuencia de objetos `Pet` coincidentes está vacía para cualquier objeto `Person`, con lo que cada objeto `Person` se representa en la colección de resultados.</span><span class="sxs-lookup"><span data-stu-id="ec52c-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec52c-115">El valor predeterminado para un tipo de referencia es `null`; por consiguiente, el ejemplo busca una referencia NULL antes de tener acceso a cada elemento de cada colección de `Pet`.</span><span class="sxs-lookup"><span data-stu-id="ec52c-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 <span data-ttu-id="ec52c-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec52c-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="ec52c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec52c-117">See also</span></span>  
 <span data-ttu-id="ec52c-118"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="ec52c-118"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="ec52c-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="ec52c-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="ec52c-120">[Realizar combinaciones internas](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="ec52c-120">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="ec52c-121">[Realizar combinaciones agrupadas](perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="ec52c-121">[Perform grouped joins](perform-grouped-joins.md) </span></span>  
 [<span data-ttu-id="ec52c-122">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="ec52c-122">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)   
 

