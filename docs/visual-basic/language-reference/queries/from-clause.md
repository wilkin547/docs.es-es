---
description: 'Más información sobre: cláusula FROM (Visual Basic)'
title: Cláusula From
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
ms.openlocfilehash: e35188412deb7fd9f2d8306c85057d050a60d030
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700564"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="958cd-103">From (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="958cd-103">From Clause (Visual Basic)</span></span>

<span data-ttu-id="958cd-104">Especifica una o varias variables de rango y una colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="958cd-104">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="958cd-105">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="958cd-106">Partes</span><span class="sxs-lookup"><span data-stu-id="958cd-106">Parts</span></span>  
  
|<span data-ttu-id="958cd-107">Término</span><span class="sxs-lookup"><span data-stu-id="958cd-107">Term</span></span>|<span data-ttu-id="958cd-108">Definición</span><span class="sxs-lookup"><span data-stu-id="958cd-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="958cd-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="958cd-109">Required.</span></span> <span data-ttu-id="958cd-110">Una *variable de rango* que se usa para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="958cd-110">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="958cd-111">Una variable de rango se utiliza para hacer referencia a cada miembro de `collection` , ya que la consulta recorre en iteración la `collection` .</span><span class="sxs-lookup"><span data-stu-id="958cd-111">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="958cd-112">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="958cd-112">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="958cd-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="958cd-113">Optional.</span></span> <span data-ttu-id="958cd-114">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="958cd-114">The type of `element`.</span></span> <span data-ttu-id="958cd-115">Si no `type` se especifica, el tipo de `element` se deduce de `collection` .</span><span class="sxs-lookup"><span data-stu-id="958cd-115">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="958cd-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="958cd-116">Required.</span></span> <span data-ttu-id="958cd-117">Hace referencia a la colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="958cd-117">Refers to the collection to be queried.</span></span> <span data-ttu-id="958cd-118">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="958cd-118">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="958cd-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="958cd-119">Remarks</span></span>  

 <span data-ttu-id="958cd-120">La `From` cláusula se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="958cd-120">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="958cd-121">Estas variables se denominan *variables de rango*.</span><span class="sxs-lookup"><span data-stu-id="958cd-121">These variables are called *range variables*.</span></span> <span data-ttu-id="958cd-122">La `From` cláusula es necesaria para una consulta, excepto cuando `Aggregate` se usa la cláusula para identificar una consulta que devuelve solo resultados agregados.</span><span class="sxs-lookup"><span data-stu-id="958cd-122">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="958cd-123">Para obtener más información, vea [cláusula Aggregate](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="958cd-123">For more information, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="958cd-124">Puede especificar varias `From` cláusulas en una consulta para identificar varias colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="958cd-124">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="958cd-125">Cuando se especifican varias colecciones, se recorren en iteración de forma independiente o puede combinarlas si están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="958cd-125">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="958cd-126">Puede combinar las colecciones implícitamente mediante la `Select` cláusula o explícitamente mediante las `Join` `Group Join` cláusulas o.</span><span class="sxs-lookup"><span data-stu-id="958cd-126">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="958cd-127">Como alternativa, puede especificar varias colecciones y variables de rango en una sola `From` cláusula, con cada variable de rango relacionada y colección separadas de las otras mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="958cd-127">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="958cd-128">En el ejemplo de código siguiente se muestran ambas opciones de sintaxis para la `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="958cd-128">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="958cd-129">La `From` cláusula define el ámbito de una consulta, que es similar al ámbito de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="958cd-129">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="958cd-130">Por lo tanto, cada `element` variable de rango en el ámbito de una consulta debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="958cd-130">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="958cd-131">Dado que puede especificar varias `From` cláusulas para una consulta, las `From` cláusulas posteriores pueden hacer referencia a las variables de rango de la `From` cláusula o pueden hacer referencia a las variables de rango de una `From` cláusula anterior.</span><span class="sxs-lookup"><span data-stu-id="958cd-131">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="958cd-132">Por ejemplo, en el ejemplo siguiente se muestra una cláusula anidada en la `From` que la colección de la segunda cláusula se basa en una propiedad de la variable de rango de la primera cláusula.</span><span class="sxs-lookup"><span data-stu-id="958cd-132">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="958cd-133">Cada `From` cláusula puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="958cd-133">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="958cd-134">Puede refinar la consulta de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="958cd-134">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="958cd-135">Combine varias colecciones implícitamente mediante el uso de las `From` `Select` cláusulas y, o explícitamente mediante el uso de las `Join` `Group Join` cláusulas o.</span><span class="sxs-lookup"><span data-stu-id="958cd-135">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="958cd-136">Utilice la `Where` cláusula para filtrar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="958cd-136">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="958cd-137">Ordene el resultado mediante la `Order By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="958cd-137">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="958cd-138">Agrupe resultados similares juntos mediante la `Group By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="958cd-138">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="958cd-139">Utilice la `Aggregate` cláusula para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="958cd-139">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="958cd-140">Utilice la `Let` cláusula para introducir una variable de iteración cuyo valor se determina mediante una expresión en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="958cd-140">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="958cd-141">Utilice la `Distinct` cláusula para omitir los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="958cd-141">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="958cd-142">Identifique las partes del resultado que se van a devolver mediante las `Skip` `Take` `Skip While` cláusulas,, y `Take While` .</span><span class="sxs-lookup"><span data-stu-id="958cd-142">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="958cd-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="958cd-143">Example</span></span>  

 <span data-ttu-id="958cd-144">La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para cada `Customer` objeto de la `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="958cd-144">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="958cd-145">La `Where` cláusula usa la variable de rango para restringir la salida a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="958cd-145">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="958cd-146">El `For Each` bucle muestra el nombre de la compañía para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="958cd-146">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="958cd-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="958cd-147">See also</span></span>

- [<span data-ttu-id="958cd-148">Consultas</span><span class="sxs-lookup"><span data-stu-id="958cd-148">Queries</span></span>](index.md)
- [<span data-ttu-id="958cd-149">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="958cd-149">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="958cd-150">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="958cd-150">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="958cd-151">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="958cd-151">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="958cd-152">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="958cd-152">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="958cd-153">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="958cd-153">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="958cd-154">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="958cd-154">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="958cd-155">Cláusula Distinct</span><span class="sxs-lookup"><span data-stu-id="958cd-155">Distinct Clause</span></span>](distinct-clause.md)
- [<span data-ttu-id="958cd-156">Cláusula Join</span><span class="sxs-lookup"><span data-stu-id="958cd-156">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="958cd-157">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="958cd-157">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="958cd-158">Cláusula order by</span><span class="sxs-lookup"><span data-stu-id="958cd-158">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="958cd-159">Cláusula Let</span><span class="sxs-lookup"><span data-stu-id="958cd-159">Let Clause</span></span>](let-clause.md)
- [<span data-ttu-id="958cd-160">Cláusula Skip</span><span class="sxs-lookup"><span data-stu-id="958cd-160">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="958cd-161">Cláusula Take</span><span class="sxs-lookup"><span data-stu-id="958cd-161">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="958cd-162">Cláusula Skip While</span><span class="sxs-lookup"><span data-stu-id="958cd-162">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="958cd-163">Cláusula Take While</span><span class="sxs-lookup"><span data-stu-id="958cd-163">Take While Clause</span></span>](take-while-clause.md)
