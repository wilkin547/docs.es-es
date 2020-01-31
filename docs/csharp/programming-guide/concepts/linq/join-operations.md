---
title: Operaciones Join (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: d4bf9fe76238d8824c5255df8910c1000503dcdf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746960"
---
# <a name="opno-locjoin-operations-c"></a><span data-ttu-id="09788-102">Operaciones [!OP.NO-LOC(Join)] (C#)</span><span class="sxs-lookup"><span data-stu-id="09788-102">[!OP.NO-LOC(Join)] Operations (C#)</span></span>
<span data-ttu-id="09788-103">Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="09788-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="09788-104">La combinación es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se puede seguir directamente.</span><span class="sxs-lookup"><span data-stu-id="09788-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="09788-105">En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="09788-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="09788-106">Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente.</span><span class="sxs-lookup"><span data-stu-id="09788-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="09788-107">Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.</span><span class="sxs-lookup"><span data-stu-id="09788-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="09788-108">Los métodos de combinación que se han proporcionado en el marco de LINQ son <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> y <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A>.</span><span class="sxs-lookup"><span data-stu-id="09788-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> and <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A>.</span></span> <span data-ttu-id="09788-109">Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves.</span><span class="sxs-lookup"><span data-stu-id="09788-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="09788-110">(Para comparar, Transact-SQL admite otros operadores de combinación aparte de 'igual', por ejemplo, 'menor que'). En términos de base de datos relacional, <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> implementa una combinación interna, un tipo de combinación en la que solo se devuelven los objetos que tienen una correspondencia en el otro conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="09788-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="09788-111">El método <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A> no tiene equivalente directo en términos de bases de datos relacionales; pero implementa un superconjunto de combinaciones internas y combinaciones externas izquierdas.</span><span class="sxs-lookup"><span data-stu-id="09788-111">The <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="09788-112">Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="09788-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="09788-113">En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="09788-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Dos círculos superpuestos en los que se muestra el interior y el exterior.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="09788-115">Métodos</span><span class="sxs-lookup"><span data-stu-id="09788-115">Methods</span></span>  
  
|<span data-ttu-id="09788-116">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="09788-116">Method Name</span></span>|<span data-ttu-id="09788-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="09788-117">Description</span></span>|<span data-ttu-id="09788-118">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="09788-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="09788-119">Más información</span><span class="sxs-lookup"><span data-stu-id="09788-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="09788-120">Combina dos secuencias según las funciones de selector de claves y extrae pares de valores.</span><span class="sxs-lookup"><span data-stu-id="09788-120">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="09788-121">Combina dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="09788-121">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="09788-122">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="09788-122">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="09788-123">En el ejemplo siguiente se usa la cláusula `join … in … on … equals …` para combinar dos secuencias en función de un valor específico:</span><span class="sxs-lookup"><span data-stu-id="09788-123">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="09788-124">En el ejemplo siguiente se usa la cláusula `join … in … on … equals … into …` para combinar dos secuencias en función de un valor específico y se agrupan las coincidencias resultantes de cada elemento:</span><span class="sxs-lookup"><span data-stu-id="09788-124">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="09788-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="09788-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="09788-126">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="09788-126">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="09788-127">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="09788-127">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="09788-128">Formulación de combinaciones y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="09788-128">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="09788-129">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="09788-129">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- <span data-ttu-id="09788-130">[Join usando claves compuestas](../../../linq/join-by-using-composite-keys.md)</span><span class="sxs-lookup"><span data-stu-id="09788-130">[Join by using composite keys](../../../linq/join-by-using-composite-keys.md)</span></span>
- [<span data-ttu-id="09788-131">Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="09788-131">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="09788-132">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="09788-132">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="09788-133">Realizar operaciones de combinación personalizadas</span><span class="sxs-lookup"><span data-stu-id="09788-133">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="09788-134">Realizar combinaciones agrupadas</span><span class="sxs-lookup"><span data-stu-id="09788-134">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="09788-135">Realizar combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="09788-135">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="09788-136">Realizar operaciones de combinación externa izquierda</span><span class="sxs-lookup"><span data-stu-id="09788-136">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="09788-137">Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="09788-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
