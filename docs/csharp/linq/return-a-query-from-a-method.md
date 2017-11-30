---
title: "Devolver una consulta de un método"
description: "Cómo devolver una consulta."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="43aca-104">Cómo: Devolver una consulta desde un método (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="43aca-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="43aca-105">En este ejemplo se muestra cómo devolver una consulta desde un método como un valor devuelto y como un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="43aca-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="43aca-106">Los objetos de consulta admiten composición, lo que significa que puede devolver una consulta desde un método.</span><span class="sxs-lookup"><span data-stu-id="43aca-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="43aca-107">Los objetos que representan consultas no almacenan la colección resultante, sino los pasos para generar los resultados cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="43aca-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="43aca-108">La ventaja de devolver objetos de consulta desde métodos es que se pueden componer o modificar todavía más.</span><span class="sxs-lookup"><span data-stu-id="43aca-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="43aca-109">Por lo tanto, cualquier valor devuelto o parámetro `out` de un método que devuelve una consulta también debe tener ese tipo.</span><span class="sxs-lookup"><span data-stu-id="43aca-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="43aca-110">Si un método materializa una consulta en un tipo concreto <xref:System.Collections.Generic.List%601> o <xref:System.Array>, se considera que está devolviendo los resultados de la consulta en lugar de la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="43aca-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="43aca-111">Una variable de consulta que se devuelve desde un método sigue pudiendo componerse o modificarse.</span><span class="sxs-lookup"><span data-stu-id="43aca-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43aca-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43aca-112">Example</span></span>  
 <span data-ttu-id="43aca-113">En el ejemplo siguiente, el primer método devuelve una consulta como un valor devuelto y el segundo método devuelve una consulta como un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="43aca-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="43aca-114">Tenga en cuenta que, en ambos casos, se trata de una consulta que se devuelve, no de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="43aca-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="43aca-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="43aca-115">See Also</span></span>  
 [<span data-ttu-id="43aca-116">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="43aca-116">LINQ Query Expressions</span></span>](index.md)
