---
title: Realizar una subconsulta en una operación de agrupación (LINQ en C#)
description: Obtenga información sobre cómo realizar una subconsulta en una operación de agrupación con LINQ en C#.
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: a3757a7d358a310dd1404f85e34178f6e561bcb9
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857442"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="4287a-103">Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="4287a-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="4287a-104">En este artículo se muestran dos maneras diferentes de crear una consulta que ordena los datos de origen en grupos y, luego, realiza una subconsulta en cada grupo de forma individual.</span><span class="sxs-lookup"><span data-stu-id="4287a-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="4287a-105">La técnica básica de cada ejemplo consiste en agrupar los elementos de origen usando una *continuación* denominada `newGroup` y después generar una nueva subconsulta en `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="4287a-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="4287a-106">Esta subconsulta se ejecuta en cada uno de los nuevos grupos creados por la consulta externa.</span><span class="sxs-lookup"><span data-stu-id="4287a-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="4287a-107">Tenga en cuenta que en este ejemplo concreto el resultado final no es un grupo, sino una secuencia plana de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="4287a-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="4287a-108">Para obtener más información sobre cómo agrupar, consulte [Cláusula group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4287a-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="4287a-109">Para obtener más información sobre continuaciones, consulte [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="4287a-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="4287a-110">En el ejemplo siguiente se usa una estructura de datos en memoria como origen de datos, pero se aplican los mismos principios para cualquier tipo de origen de datos LINQ.</span><span class="sxs-lookup"><span data-stu-id="4287a-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4287a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4287a-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="4287a-112">Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).</span><span class="sxs-lookup"><span data-stu-id="4287a-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)] 

<span data-ttu-id="4287a-113">La consulta del fragmento de código anterior también se puede escribir con la sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="4287a-113">The query in the snippet above can also be written using method syntax.</span></span> <span data-ttu-id="4287a-114">El siguiente fragmento de código tiene una consulta semánticamente equivalente escrita con sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="4287a-114">The following code snippet has a semantically equivalent query written using method syntax.</span></span>

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a><span data-ttu-id="4287a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4287a-115">See also</span></span>

- [<span data-ttu-id="4287a-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4287a-116">Language Integrated Query (LINQ)</span></span>](index.md)
