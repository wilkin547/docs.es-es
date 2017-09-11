---
title: "Realizar una subconsulta en una operación de agrupación"
description: "Cómo realizar una subconsulta en una operación de agrupación."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68acc07e0c33d042123d3cd403a73d58a7c3d245
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="68bf1-104">Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="68bf1-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="68bf1-105">En este tema se muestran dos maneras diferentes de crear una consulta que ordena los datos de origen en grupos y, luego, realiza una subconsulta en cada grupo individualmente.</span><span class="sxs-lookup"><span data-stu-id="68bf1-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="68bf1-106">La técnica básica de cada ejemplo consiste en agrupar los elementos de origen usando una *continuación* denominada `newGroup` y después generar una nueva subconsulta en `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="68bf1-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="68bf1-107">Esta subconsulta se ejecuta en cada uno de los nuevos grupos creados por la consulta externa.</span><span class="sxs-lookup"><span data-stu-id="68bf1-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="68bf1-108">Tenga en cuenta que en este ejemplo concreto el resultado final no es un grupo, sino una secuencia plana de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="68bf1-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="68bf1-109">Para obtener más información sobre cómo agrupar, consulte [group clause](../language-reference/keywords/group-clause.md) (Cláusula group).</span><span class="sxs-lookup"><span data-stu-id="68bf1-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="68bf1-110">Para obtener más información sobre continuaciones, consulte [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="68bf1-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="68bf1-111">En el ejemplo siguiente se usa una estructura de datos en memoria como origen de datos, pero se aplican los mismos principios para cualquier tipo de origen de datos LINQ.</span><span class="sxs-lookup"><span data-stu-id="68bf1-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68bf1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68bf1-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="68bf1-113">Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).</span><span class="sxs-lookup"><span data-stu-id="68bf1-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 <span data-ttu-id="68bf1-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="68bf1-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span></span>  
   
## <a name="see-also"></a><span data-ttu-id="68bf1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="68bf1-115">See also</span></span>  
 [<span data-ttu-id="68bf1-116">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="68bf1-116">LINQ Query Expressions</span></span>](index.md)

