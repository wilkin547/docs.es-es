---
title: Realizar combinaciones externas izquierdas (LINQ en C#)
description: Obtenga información sobre cómo realizar combinaciones externas izquierdas con LINQ en C#.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 329fe9e17640931c5eb39b33b791a7a77a6f7b89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506601"
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="4c15d-103">Realizar operaciones de combinación externa izquierda</span><span class="sxs-lookup"><span data-stu-id="4c15d-103">Perform left outer joins</span></span>

<span data-ttu-id="4c15d-104">Una combinación externa izquierda es una combinación en la que se devuelve cada elemento de la primera colección, independientemente de si tiene elementos correlacionados en la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="4c15d-104">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="4c15d-105">Puede usar LINQ para realizar una combinación externa izquierda llamando al método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="4c15d-105">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>

## <a name="example"></a><span data-ttu-id="4c15d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c15d-106">Example</span></span>

<span data-ttu-id="4c15d-107">En el ejemplo siguiente se muestra cómo usar el método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada para realizar una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="4c15d-107">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>

<span data-ttu-id="4c15d-108">El primer paso para generar una combinación externa izquierda de dos colecciones consiste en realizar una combinación interna usando una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="4c15d-108">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="4c15d-109">(Vea [Realizar combinaciones internas](perform-inner-joins.md) para obtener una explicación de este proceso). En este ejemplo, la lista de objetos de `Person` está unida a la lista de objetos `Pet` basándose en un objeto `Person` que coincide con `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="4c15d-109">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>

<span data-ttu-id="4c15d-110">El segundo paso consiste en incluir cada elemento de la primera colección (izquierda) en el conjunto de resultados, incluso cuando no haya coincidencias en la colección derecha.</span><span class="sxs-lookup"><span data-stu-id="4c15d-110">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="4c15d-111">Esto se realiza llamando a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de elementos coincidentes de la combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="4c15d-111">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="4c15d-112">En este ejemplo, se llama a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de objetos `Pet` coincidentes.</span><span class="sxs-lookup"><span data-stu-id="4c15d-112">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="4c15d-113">El método devuelve una colección que contiene un único, valor predeterminado si la secuencia de objetos `Pet` coincidentes está vacía para cualquier objeto `Person`, con lo que cada objeto `Person` se representa en la colección de resultados.</span><span class="sxs-lookup"><span data-stu-id="4c15d-113">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>

> [!NOTE]
> <span data-ttu-id="4c15d-114">El valor predeterminado para un tipo de referencia es `null`; por consiguiente, el ejemplo busca una referencia NULL antes de tener acceso a cada elemento de cada colección de `Pet`.</span><span class="sxs-lookup"><span data-stu-id="4c15d-114">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a><span data-ttu-id="4c15d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c15d-115">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>  
- <xref:System.Linq.Enumerable.GroupJoin%2A>  
- [<span data-ttu-id="4c15d-116">Realizar combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="4c15d-116">Perform inner joins</span></span>](perform-inner-joins.md)  
- [<span data-ttu-id="4c15d-117">Realizar combinaciones agrupadas</span><span class="sxs-lookup"><span data-stu-id="4c15d-117">Perform grouped joins</span></span>](perform-grouped-joins.md)  
- <span data-ttu-id="4c15d-118">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="4c15d-118">[Anonymous types](../programming-guide/classes-and-structs/anonymous-types.md)</span></span>  