---
title: Join (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499430"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="fb5b3-102">Join (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb5b3-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="fb5b3-103">Combina dos colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="fb5b3-104">La operación de combinación se basa en claves coincidentes y usa el `Equals` operador.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb5b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb5b3-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="fb5b3-106">Elementos</span><span class="sxs-lookup"><span data-stu-id="fb5b3-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="fb5b3-107">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-107">Required.</span></span> <span data-ttu-id="fb5b3-108">La variable de control para la colección que se está combina.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="fb5b3-109">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-109">Required.</span></span> <span data-ttu-id="fb5b3-110">La colección para combinar con la colección identificado en el lado izquierdo de la `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="fb5b3-111">Un `Join` cláusula puede estar anidada en otro `Join` cláusula, o en un `Group Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="fb5b3-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-112">Optional.</span></span> <span data-ttu-id="fb5b3-113">Uno o más adicionales `Join` cláusulas aún más refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="fb5b3-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-114">Optional.</span></span> <span data-ttu-id="fb5b3-115">Uno o más adicionales `Group Join` cláusulas aún más refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="fb5b3-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="fb5b3-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="fb5b3-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-117">Required.</span></span> <span data-ttu-id="fb5b3-118">Identifica las claves para las colecciones que se están combina.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="fb5b3-119">Debe usar el `Equals` operador para comparar las claves de las colecciones que se están combina.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="fb5b3-120">Puede combinar condiciones de combinación utilizando el `And` operador para identificar varias claves.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="fb5b3-121">`key1` debe ser de la colección en el lado izquierdo de la `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="fb5b3-122">`key2` debe ser de la colección en el lado derecho de la `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="fb5b3-123">Las claves usadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="fb5b3-124">Sin embargo, cada expresión de clave solo puede contener elementos de su colección respectiva.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb5b3-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb5b3-125">Remarks</span></span>  
 <span data-ttu-id="fb5b3-126">El `Join` cláusula combina dos colecciones basadas en valores de clave de las colecciones que se están combinando coincidentes.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="fb5b3-127">La colección resultante puede contener cualquier combinación de valores de la colección identificado en el lado izquierdo de la `Join` operador y la colección identificado en el `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="fb5b3-128">La consulta devolverá solo los resultados para el que la condición especificada por el `Equals` operador se cumple.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="fb5b3-129">Esto es equivalente a un `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="fb5b3-130">Puede usar varios `Join` cláusulas en una consulta para combinar dos o más colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="fb5b3-131">Puede realizar una combinación implícita para combinar colecciones sin el `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="fb5b3-132">Para ello, incluyen varias `In` cláusulas en su `From` cláusula y especifique un `Where` cláusula que identifica las claves que desee usar para la combinación.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="fb5b3-133">Puede usar el `Group Join` cláusula para combinar colecciones en una sola colección jerárquica.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="fb5b3-134">Esto es similar a un `LEFT OUTER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb5b3-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb5b3-135">Example</span></span>  
 <span data-ttu-id="fb5b3-136">El ejemplo de código siguiente realiza una combinación implícita para combinar una lista de clientes con sus pedidos.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="fb5b3-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb5b3-137">Example</span></span>  
 <span data-ttu-id="fb5b3-138">El ejemplo de código siguiente combina dos colecciones mediante el uso de la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="fb5b3-139">En este ejemplo genera una salida similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb5b3-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="fb5b3-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb5b3-140">Example</span></span>  
 <span data-ttu-id="fb5b3-141">El ejemplo de código siguiente combina dos colecciones mediante el uso de la `Join` cláusula con dos columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="fb5b3-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="fb5b3-142">En el ejemplo se genera una salida similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb5b3-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="fb5b3-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb5b3-143">See Also</span></span>  
 [<span data-ttu-id="fb5b3-144">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb5b3-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="fb5b3-145">Consultas</span><span class="sxs-lookup"><span data-stu-id="fb5b3-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="fb5b3-146">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="fb5b3-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="fb5b3-147">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="fb5b3-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="fb5b3-148">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="fb5b3-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="fb5b3-149">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="fb5b3-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
