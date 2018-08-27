---
title: From (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932493"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="ddfc3-102">From (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="ddfc3-103">Especifica uno o más variables de rango y una colección a la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddfc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddfc3-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ddfc3-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ddfc3-105">Parts</span></span>  
  
|<span data-ttu-id="ddfc3-106">Término</span><span class="sxs-lookup"><span data-stu-id="ddfc3-106">Term</span></span>|<span data-ttu-id="ddfc3-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ddfc3-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="ddfc3-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-108">Required.</span></span> <span data-ttu-id="ddfc3-109">Un *variable de rango* utiliza para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="ddfc3-110">Una variable de rango se usa para referirse a cada miembro de la `collection` como la consulta se recorre el `collection`.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="ddfc3-111">Debe ser un tipo enumerable.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="ddfc3-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-112">Optional.</span></span> <span data-ttu-id="ddfc3-113">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-113">The type of `element`.</span></span> <span data-ttu-id="ddfc3-114">Si no hay ningún `type` se especifica, el tipo de `element` se deduce del `collection`.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="ddfc3-115">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-115">Required.</span></span> <span data-ttu-id="ddfc3-116">Hace referencia a la colección que se van a consultar.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="ddfc3-117">Debe ser un tipo enumerable.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddfc3-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddfc3-118">Remarks</span></span>  
 <span data-ttu-id="ddfc3-119">El `From` cláusula se usa para identificar los datos de origen para una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="ddfc3-120">Estas variables se denominan *las variables de rango*.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-120">These variables are called *range variables*.</span></span> <span data-ttu-id="ddfc3-121">El `From` cláusula se requiere para una consulta, excepto cuando la `Aggregate` cláusula se usa para identificar una consulta que devuelve resultados agregados solo.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="ddfc3-122">Para obtener más información, consulte [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ddfc3-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="ddfc3-123">Puede especificar varios `From` cláusulas en una consulta para identificar varias colecciones a unirse.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="ddfc3-124">Cuando se especifican varias colecciones, se iteran en forma independiente o combinarlas si están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="ddfc3-125">Puede combinar colecciones implícitamente mediante el uso de la `Select` cláusula, o explícitamente mediante la `Join` o `Group Join` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="ddfc3-126">Como alternativa, puede especificar varias variables de rango y colecciones en una sola `From` cláusula con cada variable de rango relacionado y la colección separados de los demás por una coma.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="ddfc3-127">El ejemplo de código siguiente muestra ambas opciones de sintaxis para el `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="ddfc3-128">El `From` cláusula define el ámbito de una consulta, que es similar al ámbito de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="ddfc3-129">Por lo tanto, cada uno de ellos `element` variable de rango en el ámbito de una consulta debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="ddfc3-130">Dado que puede especificar varios `From` cláusulas para una consulta, posteriores `From` cláusulas pueden hacer referencia a las variables de rango en la `From` cláusula, o bien pueden hacer referencia a las variables de rango en una anterior `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="ddfc3-131">Por ejemplo, en el ejemplo siguiente se muestra un anidada `From` cláusula donde la colección en la segunda cláusula se basa en una propiedad de la variable de rango en la primera cláusula.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="ddfc3-132">Cada `From` cláusula puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="ddfc3-133">Puede refinar la consulta de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="ddfc3-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="ddfc3-134">Combinar varias colecciones implícitamente mediante la `From` y `Select` cláusulas, o explícitamente mediante la `Join` o `Group Join` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="ddfc3-135">Use el `Where` cláusula para filtrar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="ddfc3-136">Ordenar el resultado mediante la `Order By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="ddfc3-137">Agrupar resultados similares mediante el uso de la `Group By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="ddfc3-138">Use el `Aggregate` cláusula para identificar las funciones de agregado que se evalúa para el resultado de toda la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="ddfc3-139">Use el `Let` cláusula para introducir una variable de iteración cuyo valor viene determinado por una expresión en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="ddfc3-140">Use el `Distinct` cláusula para pasar por alto los resultados de consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="ddfc3-141">Identificar las partes del resultado para devolver mediante el uso de la `Skip`, `Take`, `Skip While`, y `Take While` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddfc3-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddfc3-142">Example</span></span>  
 <span data-ttu-id="ddfc3-143">Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="ddfc3-144">El `Where` cláusula usa la variable de rango para restringir los resultados a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="ddfc3-145">El `For Each` bucle muestra el nombre de la empresa para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddfc3-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ddfc3-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddfc3-146">See Also</span></span>  
 [<span data-ttu-id="ddfc3-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="ddfc3-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="ddfc3-148">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddfc3-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="ddfc3-149">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="ddfc3-150">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="ddfc3-151">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="ddfc3-152">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="ddfc3-153">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="ddfc3-154">Distinct (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="ddfc3-155">Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="ddfc3-156">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="ddfc3-157">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="ddfc3-158">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="ddfc3-159">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="ddfc3-160">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="ddfc3-161">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="ddfc3-162">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ddfc3-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
