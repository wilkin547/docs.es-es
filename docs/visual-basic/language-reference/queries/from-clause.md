---
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
ms.openlocfilehash: 120ba6da11bffc3a0e81873d1fd606633724723d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875255"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="9e5d4-102">From (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e5d4-102">From Clause (Visual Basic)</span></span>

<span data-ttu-id="9e5d4-103">Especifica una o varias variables de rango y una colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e5d4-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="9e5d4-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9e5d4-105">Parts</span></span>  
  
|<span data-ttu-id="9e5d4-106">Término</span><span class="sxs-lookup"><span data-stu-id="9e5d4-106">Term</span></span>|<span data-ttu-id="9e5d4-107">Definición</span><span class="sxs-lookup"><span data-stu-id="9e5d4-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="9e5d4-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-108">Required.</span></span> <span data-ttu-id="9e5d4-109">Una *variable de rango* que se usa para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="9e5d4-110">Una variable de rango se utiliza para hacer referencia a cada miembro de `collection` , ya que la consulta recorre en iteración la `collection` .</span><span class="sxs-lookup"><span data-stu-id="9e5d4-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="9e5d4-111">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="9e5d4-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-112">Optional.</span></span> <span data-ttu-id="9e5d4-113">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-113">The type of `element`.</span></span> <span data-ttu-id="9e5d4-114">Si no `type` se especifica, el tipo de `element` se deduce de `collection` .</span><span class="sxs-lookup"><span data-stu-id="9e5d4-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="9e5d4-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-115">Required.</span></span> <span data-ttu-id="9e5d4-116">Hace referencia a la colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="9e5d4-117">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e5d4-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e5d4-118">Remarks</span></span>  

 <span data-ttu-id="9e5d4-119">La `From` cláusula se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="9e5d4-120">Estas variables se denominan *variables de rango*.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-120">These variables are called *range variables*.</span></span> <span data-ttu-id="9e5d4-121">La `From` cláusula es necesaria para una consulta, excepto cuando `Aggregate` se usa la cláusula para identificar una consulta que devuelve solo resultados agregados.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="9e5d4-122">Para obtener más información, vea [cláusula Aggregate](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9e5d4-122">For more information, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="9e5d4-123">Puede especificar varias `From` cláusulas en una consulta para identificar varias colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="9e5d4-124">Cuando se especifican varias colecciones, se recorren en iteración de forma independiente o puede combinarlas si están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="9e5d4-125">Puede combinar las colecciones implícitamente mediante la `Select` cláusula o explícitamente mediante las `Join` `Group Join` cláusulas o.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="9e5d4-126">Como alternativa, puede especificar varias colecciones y variables de rango en una sola `From` cláusula, con cada variable de rango relacionada y colección separadas de las otras mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="9e5d4-127">En el ejemplo de código siguiente se muestran ambas opciones de sintaxis para la `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="9e5d4-128">La `From` cláusula define el ámbito de una consulta, que es similar al ámbito de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="9e5d4-129">Por lo tanto, cada `element` variable de rango en el ámbito de una consulta debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="9e5d4-130">Dado que puede especificar varias `From` cláusulas para una consulta, las `From` cláusulas posteriores pueden hacer referencia a las variables de rango de la `From` cláusula o pueden hacer referencia a las variables de rango de una `From` cláusula anterior.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="9e5d4-131">Por ejemplo, en el ejemplo siguiente se muestra una cláusula anidada en la `From` que la colección de la segunda cláusula se basa en una propiedad de la variable de rango de la primera cláusula.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="9e5d4-132">Cada `From` cláusula puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="9e5d4-133">Puede refinar la consulta de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="9e5d4-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="9e5d4-134">Combine varias colecciones implícitamente mediante el uso de las `From` `Select` cláusulas y, o explícitamente mediante el uso de las `Join` `Group Join` cláusulas o.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="9e5d4-135">Utilice la `Where` cláusula para filtrar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="9e5d4-136">Ordene el resultado mediante la `Order By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="9e5d4-137">Agrupe resultados similares juntos mediante la `Group By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="9e5d4-138">Utilice la `Aggregate` cláusula para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="9e5d4-139">Utilice la `Let` cláusula para introducir una variable de iteración cuyo valor se determina mediante una expresión en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="9e5d4-140">Utilice la `Distinct` cláusula para omitir los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="9e5d4-141">Identifique las partes del resultado que se van a devolver mediante las `Skip` `Take` `Skip While` cláusulas,, y `Take While` .</span><span class="sxs-lookup"><span data-stu-id="9e5d4-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e5d4-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e5d4-142">Example</span></span>  

 <span data-ttu-id="9e5d4-143">La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para cada `Customer` objeto de la `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="9e5d4-144">La `Where` cláusula usa la variable de rango para restringir la salida a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="9e5d4-145">El `For Each` bucle muestra el nombre de la compañía para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e5d4-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="9e5d4-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e5d4-146">See also</span></span>

- [<span data-ttu-id="9e5d4-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="9e5d4-147">Queries</span></span>](index.md)
- [<span data-ttu-id="9e5d4-148">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e5d4-148">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9e5d4-149">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="9e5d4-149">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="9e5d4-150">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="9e5d4-150">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="9e5d4-151">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="9e5d4-151">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9e5d4-152">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="9e5d4-152">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="9e5d4-153">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="9e5d4-153">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="9e5d4-154">Cláusula Distinct</span><span class="sxs-lookup"><span data-stu-id="9e5d4-154">Distinct Clause</span></span>](distinct-clause.md)
- [<span data-ttu-id="9e5d4-155">Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="9e5d4-155">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="9e5d4-156">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="9e5d4-156">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="9e5d4-157">Cláusula order by</span><span class="sxs-lookup"><span data-stu-id="9e5d4-157">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="9e5d4-158">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="9e5d4-158">Let Clause</span></span>](let-clause.md)
- [<span data-ttu-id="9e5d4-159">Cláusula Skip</span><span class="sxs-lookup"><span data-stu-id="9e5d4-159">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="9e5d4-160">Cláusula Take</span><span class="sxs-lookup"><span data-stu-id="9e5d4-160">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="9e5d4-161">Cláusula Skip While</span><span class="sxs-lookup"><span data-stu-id="9e5d4-161">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="9e5d4-162">Cláusula Take While</span><span class="sxs-lookup"><span data-stu-id="9e5d4-162">Take While Clause</span></span>](take-while-clause.md)
