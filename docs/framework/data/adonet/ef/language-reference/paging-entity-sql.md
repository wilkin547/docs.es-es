---
description: 'Más información acerca de: paginación (Entity SQL)'
title: Paginación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: c32474b772be359dbf2ffd46e5489cc0b4b2abb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791860"
---
# <a name="paging-entity-sql"></a><span data-ttu-id="85d75-103">Paginación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="85d75-103">Paging (Entity SQL)</span></span>

<span data-ttu-id="85d75-104">La paginación física se puede realizar mediante las subcláusulas [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="85d75-104">Physical paging can be performed by using the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="85d75-105">Para llevar a cabo la paginación física de forma determinista, debe usar SKIP y LIMIT.</span><span class="sxs-lookup"><span data-stu-id="85d75-105">To perform physical paging deterministically, you should use SKIP and LIMIT.</span></span> <span data-ttu-id="85d75-106">Si solo desea restringir el número de filas del resultado de forma no determinista, debe utilizar [Top](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="85d75-106">If you only want to restrict the number of rows in the result in a non-deterministic way, you should use [TOP](top-entity-sql.md).</span></span> <span data-ttu-id="85d75-107">TOP y SKIP/LIMIT se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="85d75-107">TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="top-overview"></a><span data-ttu-id="85d75-108">Introducción a TOP</span><span class="sxs-lookup"><span data-stu-id="85d75-108">TOP Overview</span></span>  

 <span data-ttu-id="85d75-109">La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="85d75-109">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="85d75-110">La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="85d75-110">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span> <span data-ttu-id="85d75-111">Para obtener más información, vea [Top](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="85d75-111">For more information, see [TOP](top-entity-sql.md).</span></span>  
  
## <a name="skip-and-limit-overview"></a><span data-ttu-id="85d75-112">Introducción a SKIP y LIMIT</span><span class="sxs-lookup"><span data-stu-id="85d75-112">SKIP And LIMIT Overview</span></span>  

 <span data-ttu-id="85d75-113">SKIP y LIMIT son parte de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="85d75-113">SKIP and LIMIT are part of the ORDER BY clause.</span></span> <span data-ttu-id="85d75-114">Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP.</span><span class="sxs-lookup"><span data-stu-id="85d75-114">If a SKIP expression sub-clause is present in a ORDER BY clause, the results will be sorted according to the sort specification and the result set will include row(s) starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="85d75-115">Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.</span><span class="sxs-lookup"><span data-stu-id="85d75-115">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span> <span data-ttu-id="85d75-116">Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="85d75-116">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="85d75-117">Por ejemplo, LIMIT 5 restringirá el conjunto de resultados a cinco instancias o filas.</span><span class="sxs-lookup"><span data-stu-id="85d75-117">For instance, LIMIT 5 will restrict the result set to five instances or rows.</span></span> <span data-ttu-id="85d75-118">SKIP y LIMIT no tienen que usarse conjuntamente; se puede usar solo una de ellas con la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="85d75-118">SKIP and LIMIT do not have to be used together; you can use just SKIP or just LIMIT with ORDER BY clause.</span></span> <span data-ttu-id="85d75-119">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="85d75-119">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="85d75-120">IRÁ</span><span class="sxs-lookup"><span data-stu-id="85d75-120">SKIP</span></span>](skip-entity-sql.md)  
  
- [<span data-ttu-id="85d75-121">ILIMITADO</span><span class="sxs-lookup"><span data-stu-id="85d75-121">LIMIT</span></span>](limit-entity-sql.md)  
  
- [<span data-ttu-id="85d75-122">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="85d75-122">ORDER BY</span></span>](order-by-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="85d75-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="85d75-123">See also</span></span>

- [<span data-ttu-id="85d75-124">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="85d75-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="85d75-125">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="85d75-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
- <span data-ttu-id="85d75-126">[Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="85d75-126">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
