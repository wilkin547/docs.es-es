---
title: Paginación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 42f685e0b84109f3099b501b2a75e681af1ea1bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177480"
---
# <a name="paging-entity-sql"></a><span data-ttu-id="11a97-102">Paginación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="11a97-102">Paging (Entity SQL)</span></span>

<span data-ttu-id="11a97-103">La paginación física se puede realizar mediante las subcláusulas [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="11a97-103">Physical paging can be performed by using the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="11a97-104">Para llevar a cabo la paginación física de forma determinista, debe usar SKIP y LIMIT.</span><span class="sxs-lookup"><span data-stu-id="11a97-104">To perform physical paging deterministically, you should use SKIP and LIMIT.</span></span> <span data-ttu-id="11a97-105">Si solo desea restringir el número de filas del resultado de forma no determinista, debe utilizar [Top](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="11a97-105">If you only want to restrict the number of rows in the result in a non-deterministic way, you should use [TOP](top-entity-sql.md).</span></span> <span data-ttu-id="11a97-106">TOP y SKIP/LIMIT se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="11a97-106">TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="top-overview"></a><span data-ttu-id="11a97-107">Introducción a TOP</span><span class="sxs-lookup"><span data-stu-id="11a97-107">TOP Overview</span></span>  

 <span data-ttu-id="11a97-108">La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="11a97-108">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="11a97-109">La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="11a97-109">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span> <span data-ttu-id="11a97-110">Para obtener más información, vea [Top](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="11a97-110">For more information, see [TOP](top-entity-sql.md).</span></span>  
  
## <a name="skip-and-limit-overview"></a><span data-ttu-id="11a97-111">Introducción a SKIP y LIMIT</span><span class="sxs-lookup"><span data-stu-id="11a97-111">SKIP And LIMIT Overview</span></span>  

 <span data-ttu-id="11a97-112">SKIP y LIMIT son parte de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="11a97-112">SKIP and LIMIT are part of the ORDER BY clause.</span></span> <span data-ttu-id="11a97-113">Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP.</span><span class="sxs-lookup"><span data-stu-id="11a97-113">If a SKIP expression sub-clause is present in a ORDER BY clause, the results will be sorted according to the sort specification and the result set will include row(s) starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="11a97-114">Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.</span><span class="sxs-lookup"><span data-stu-id="11a97-114">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span> <span data-ttu-id="11a97-115">Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="11a97-115">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="11a97-116">Por ejemplo, LIMIT 5 restringirá el conjunto de resultados a cinco instancias o filas.</span><span class="sxs-lookup"><span data-stu-id="11a97-116">For instance, LIMIT 5 will restrict the result set to five instances or rows.</span></span> <span data-ttu-id="11a97-117">SKIP y LIMIT no tienen que usarse conjuntamente; se puede usar solo una de ellas con la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="11a97-117">SKIP and LIMIT do not have to be used together; you can use just SKIP or just LIMIT with ORDER BY clause.</span></span> <span data-ttu-id="11a97-118">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="11a97-118">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="11a97-119">IRÁ</span><span class="sxs-lookup"><span data-stu-id="11a97-119">SKIP</span></span>](skip-entity-sql.md)  
  
- [<span data-ttu-id="11a97-120">ILIMITADO</span><span class="sxs-lookup"><span data-stu-id="11a97-120">LIMIT</span></span>](limit-entity-sql.md)  
  
- [<span data-ttu-id="11a97-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="11a97-121">ORDER BY</span></span>](order-by-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="11a97-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11a97-122">See also</span></span>

- [<span data-ttu-id="11a97-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="11a97-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="11a97-124">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="11a97-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- <span data-ttu-id="11a97-125">[Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11a97-125">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
