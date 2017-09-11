---
title: "Ordenar los resultados de una cláusula join"
description: "Cómo ordenar los resultados de una cláusula join."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6272181647bb200c18231c5fc836e3dd1a2d6d55
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="a84b4-104">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="a84b4-104">Order the results of a join clause</span></span>
<span data-ttu-id="a84b4-105">En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="a84b4-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="a84b4-106">Observe que la ordenación se realiza después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="a84b4-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="a84b4-107">Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a84b4-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="a84b4-108">Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="a84b4-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a84b4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a84b4-109">Example</span></span>  
 <span data-ttu-id="a84b4-110">Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a84b4-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="a84b4-111">Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.</span><span class="sxs-lookup"><span data-stu-id="a84b4-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 <span data-ttu-id="a84b4-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a84b4-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="a84b4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a84b4-113">See also</span></span>  
 <span data-ttu-id="a84b4-114">[Expresiones de consulta LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="a84b4-114">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="a84b4-115">[orderby (Cláusula)](../language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a84b4-115">[orderby clause](../language-reference/keywords/orderby-clause.md) </span></span>  
 [<span data-ttu-id="a84b4-116">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a84b4-116">join clause</span></span>](../language-reference/keywords/join-clause.md) 

