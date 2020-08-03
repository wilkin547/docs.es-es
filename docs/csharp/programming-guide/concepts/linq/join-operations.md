---
title: Operaciones Join (C#)
description: Una combinación de dos orígenes de datos asocia objetos con objetos que comparten un atributo en los orígenes de datos. Obtenga información sobre los métodos de combinación en el marco de LINQ en C#.
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165687"
---
# <a name="no-locjoin-operations-c"></a><span data-ttu-id="ddf70-104">Operaciones Join (C#)</span><span class="sxs-lookup"><span data-stu-id="ddf70-104">Join Operations (C#)</span></span>

<span data-ttu-id="ddf70-105">Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ddf70-105">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="ddf70-106">La combinación Join es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se pueden seguir directamente.</span><span class="sxs-lookup"><span data-stu-id="ddf70-106">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="ddf70-107">En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="ddf70-107">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="ddf70-108">Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente.</span><span class="sxs-lookup"><span data-stu-id="ddf70-108">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="ddf70-109">Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.</span><span class="sxs-lookup"><span data-stu-id="ddf70-109">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="ddf70-110">Los métodos de combinación que se han proporcionado en el marco de LINQ son <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="ddf70-110">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="ddf70-111">Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves.</span><span class="sxs-lookup"><span data-stu-id="ddf70-111">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="ddf70-112">(Para comparar, Transact-SQL admite otros operadores de combinación aparte de 'igual', por ejemplo, 'menor que'). En términos de base de datos relacional, <xref:System.Linq.Enumerable.Join%2A> implementa una combinación interna, un tipo de combinación en la que solo se devuelven los objetos que tienen una correspondencia en el otro conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ddf70-112">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="ddf70-113">El método <xref:System.Linq.Enumerable.GroupJoin%2A> no tiene equivalente directo en términos de bases de datos relacionales; pero implementa un superconjunto de combinaciones internas y combinaciones externas izquierdas.</span><span class="sxs-lookup"><span data-stu-id="ddf70-113">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="ddf70-114">Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ddf70-114">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="ddf70-115">En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="ddf70-115">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Dos círculos superpuestos en los que se muestra el interior y el exterior.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="ddf70-117">Métodos</span><span class="sxs-lookup"><span data-stu-id="ddf70-117">Methods</span></span>  
  
|<span data-ttu-id="ddf70-118">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="ddf70-118">Method Name</span></span>|<span data-ttu-id="ddf70-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddf70-119">Description</span></span>|<span data-ttu-id="ddf70-120">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="ddf70-120">C# Query Expression Syntax</span></span>|<span data-ttu-id="ddf70-121">Más información</span><span class="sxs-lookup"><span data-stu-id="ddf70-121">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="ddf70-122">Combina mediante Join dos secuencias según las funciones de selector de claves y extrae pares de valores.</span><span class="sxs-lookup"><span data-stu-id="ddf70-122">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="ddf70-123">Combina mediante Join dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="ddf70-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ddf70-124">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="ddf70-124">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="ddf70-125">En el ejemplo siguiente se usa la cláusula `join … in … on … equals …` para combinar dos secuencias en función de un valor específico:</span><span class="sxs-lookup"><span data-stu-id="ddf70-125">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="ddf70-126">En el ejemplo siguiente se usa la cláusula `join … in … on … equals … into …` para combinar dos secuencias en función de un valor específico y se agrupan las coincidencias resultantes de cada elemento:</span><span class="sxs-lookup"><span data-stu-id="ddf70-126">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="ddf70-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddf70-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ddf70-128">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="ddf70-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="ddf70-129">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="ddf70-129">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="ddf70-130">Formular combinaciones Join y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="ddf70-130">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="ddf70-131">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddf70-131">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="ddf70-132">Join usando claves compuestas</span><span class="sxs-lookup"><span data-stu-id="ddf70-132">Join by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="ddf70-133">Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ddf70-133">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="ddf70-134">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="ddf70-134">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="ddf70-135">Realizar operaciones de combinación personalizadas</span><span class="sxs-lookup"><span data-stu-id="ddf70-135">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="ddf70-136">Realizar combinaciones agrupadas</span><span class="sxs-lookup"><span data-stu-id="ddf70-136">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="ddf70-137">Realizar combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="ddf70-137">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="ddf70-138">Realizar operaciones de combinación externa izquierda</span><span class="sxs-lookup"><span data-stu-id="ddf70-138">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="ddf70-139">Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ddf70-139">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
