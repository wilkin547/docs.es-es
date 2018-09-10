---
title: Devolver una consulta de un método
description: Cómo devolver una consulta.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1c5fa534f3f39f8201d93b986e687d85bb303736
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510792"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="54a92-103">Cómo: Devolver una consulta desde un método (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="54a92-103">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="54a92-104">En este ejemplo se muestra cómo devolver una consulta desde un método como un valor devuelto y como un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="54a92-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="54a92-105">Los objetos de consulta admiten composición, lo que significa que puede devolver una consulta desde un método.</span><span class="sxs-lookup"><span data-stu-id="54a92-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="54a92-106">Los objetos que representan consultas no almacenan la colección resultante, sino los pasos para generar los resultados cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="54a92-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="54a92-107">La ventaja de devolver objetos de consulta desde métodos es que se pueden componer o modificar todavía más.</span><span class="sxs-lookup"><span data-stu-id="54a92-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="54a92-108">Por lo tanto, cualquier valor devuelto o parámetro `out` de un método que devuelve una consulta también debe tener ese tipo.</span><span class="sxs-lookup"><span data-stu-id="54a92-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="54a92-109">Si un método materializa una consulta en un tipo concreto <xref:System.Collections.Generic.List%601> o <xref:System.Array>, se considera que está devolviendo los resultados de la consulta en lugar de la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="54a92-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="54a92-110">Una variable de consulta que se devuelve desde un método sigue pudiendo componerse o modificarse.</span><span class="sxs-lookup"><span data-stu-id="54a92-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54a92-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54a92-111">Example</span></span>  
 <span data-ttu-id="54a92-112">En el ejemplo siguiente, el primer método devuelve una consulta como un valor devuelto y el segundo método devuelve una consulta como un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="54a92-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="54a92-113">Tenga en cuenta que, en ambos casos, se trata de una consulta que se devuelve, no de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="54a92-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="54a92-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="54a92-114">See Also</span></span>

- [<span data-ttu-id="54a92-115">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="54a92-115">Language Integrated Query (LINQ)</span></span>](index.md)
