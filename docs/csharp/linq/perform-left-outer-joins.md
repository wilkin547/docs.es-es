---
title: "Realizar operaciones de combinación externa izquierda"
description: "Cómo realizar operaciones de combinación externa izquierda."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 0c28c85bf933a411403aefcb91801d28fe1c268e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="aa859-104">Realizar operaciones de combinación externa izquierda</span><span class="sxs-lookup"><span data-stu-id="aa859-104">Perform left outer joins</span></span>
<span data-ttu-id="aa859-105">Una combinación externa izquierda es una combinación en la que se devuelve cada elemento de la primera colección, independientemente de si tiene elementos correlacionados en la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="aa859-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="aa859-106">Puede usar LINQ para realizar una combinación externa izquierda llamando al método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="aa859-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa859-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa859-107">Example</span></span>  
 <span data-ttu-id="aa859-108">En el ejemplo siguiente se muestra cómo usar el método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada para realizar una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="aa859-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="aa859-109">El primer paso para generar una combinación externa izquierda de dos colecciones consiste en realizar una combinación interna usando una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="aa859-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="aa859-110">(Vea [Realizar combinaciones internas](perform-inner-joins.md) para obtener una explicación de este proceso). En este ejemplo, la lista de objetos de `Person` está unida a la lista de objetos `Pet` basándose en un objeto `Person` que coincide con `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="aa859-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="aa859-111">El segundo paso consiste en incluir cada elemento de la primera colección (izquierda) en el conjunto de resultados, incluso cuando no haya coincidencias en la colección derecha.</span><span class="sxs-lookup"><span data-stu-id="aa859-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="aa859-112">Esto se realiza llamando a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de elementos coincidentes de la combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="aa859-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="aa859-113">En este ejemplo, se llama a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de objetos `Pet` coincidentes.</span><span class="sxs-lookup"><span data-stu-id="aa859-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="aa859-114">El método devuelve una colección que contiene un único, valor predeterminado si la secuencia de objetos `Pet` coincidentes está vacía para cualquier objeto `Person`, con lo que cada objeto `Person` se representa en la colección de resultados.</span><span class="sxs-lookup"><span data-stu-id="aa859-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa859-115">El valor predeterminado para un tipo de referencia es `null`; por consiguiente, el ejemplo busca una referencia NULL antes de tener acceso a cada elemento de cada colección de `Pet`.</span><span class="sxs-lookup"><span data-stu-id="aa859-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="aa859-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa859-116">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="aa859-117">Realizar combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="aa859-117">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="aa859-118">Realizar combinaciones agrupadas</span><span class="sxs-lookup"><span data-stu-id="aa859-118">Perform grouped joins</span></span>](perform-grouped-joins.md)  
 <span data-ttu-id="aa859-119">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="aa859-119">[Anonymous types](../programming-guide/classes-and-structs/anonymous-types.md)</span></span>  
 
