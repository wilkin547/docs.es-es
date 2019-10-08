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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004783"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="53b26-102">From (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53b26-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="53b26-103">Especifica una o varias variables de rango y una colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="53b26-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53b26-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="53b26-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="53b26-105">Parts</span></span>  
  
|<span data-ttu-id="53b26-106">Término</span><span class="sxs-lookup"><span data-stu-id="53b26-106">Term</span></span>|<span data-ttu-id="53b26-107">Definición</span><span class="sxs-lookup"><span data-stu-id="53b26-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="53b26-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="53b26-108">Required.</span></span> <span data-ttu-id="53b26-109">Una *variable de rango* que se usa para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="53b26-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="53b26-110">Una variable de rango se usa para hacer referencia a cada miembro del `collection`, ya que la consulta recorre en iteración el `collection`.</span><span class="sxs-lookup"><span data-stu-id="53b26-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="53b26-111">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="53b26-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="53b26-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="53b26-112">Optional.</span></span> <span data-ttu-id="53b26-113">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="53b26-113">The type of `element`.</span></span> <span data-ttu-id="53b26-114">Si no se especifica `type`, el tipo de `element` se deduce de `collection`.</span><span class="sxs-lookup"><span data-stu-id="53b26-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="53b26-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="53b26-115">Required.</span></span> <span data-ttu-id="53b26-116">Hace referencia a la colección que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="53b26-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="53b26-117">Debe ser un tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="53b26-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b26-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53b26-118">Remarks</span></span>  
 <span data-ttu-id="53b26-119">La cláusula `From` se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="53b26-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="53b26-120">Estas variables se denominan *variables de rango*.</span><span class="sxs-lookup"><span data-stu-id="53b26-120">These variables are called *range variables*.</span></span> <span data-ttu-id="53b26-121">La cláusula `From` es necesaria para una consulta, excepto cuando se usa la cláusula `Aggregate` para identificar una consulta que devuelve solo resultados agregados.</span><span class="sxs-lookup"><span data-stu-id="53b26-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="53b26-122">Para obtener más información, vea [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="53b26-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="53b26-123">Puede especificar varias cláusulas `From` en una consulta para identificar varias colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="53b26-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="53b26-124">Cuando se especifican varias colecciones, se recorren en iteración de forma independiente o puede combinarlas si están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="53b26-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="53b26-125">Puede combinar las colecciones implícitamente mediante la cláusula `Select`, o explícitamente mediante las cláusulas `Join` o `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="53b26-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="53b26-126">Como alternativa, puede especificar varias colecciones y variables de rango en una sola cláusula `From`, con cada variable de rango relacionada y colección separadas de las otras por una coma.</span><span class="sxs-lookup"><span data-stu-id="53b26-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="53b26-127">En el ejemplo de código siguiente se muestran las dos opciones de sintaxis para la cláusula `From`.</span><span class="sxs-lookup"><span data-stu-id="53b26-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="53b26-128">La cláusula `From` define el ámbito de una consulta, que es similar al ámbito de un bucle `For`.</span><span class="sxs-lookup"><span data-stu-id="53b26-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="53b26-129">Por lo tanto, cada variable de rango `element` en el ámbito de una consulta debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="53b26-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="53b26-130">Dado que puede especificar varias cláusulas `From` para una consulta, las cláusulas de `From` subsiguientes pueden hacer referencia a las variables de rango de la cláusula `From` o pueden hacer referencia a las variables de rango de una cláusula `From` anterior.</span><span class="sxs-lookup"><span data-stu-id="53b26-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="53b26-131">Por ejemplo, en el ejemplo siguiente se muestra una cláusula anidada `From` en la que la colección de la segunda cláusula se basa en una propiedad de la variable de rango de la primera cláusula.</span><span class="sxs-lookup"><span data-stu-id="53b26-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="53b26-132">Cada cláusula `From` puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="53b26-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="53b26-133">Puede refinar la consulta de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="53b26-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="53b26-134">Combine varias colecciones implícitamente mediante el uso de las cláusulas `From` y `Select`, o explícitamente mediante las cláusulas `Join` o `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="53b26-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="53b26-135">Utilice la cláusula `Where` para filtrar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="53b26-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="53b26-136">Ordene el resultado mediante la cláusula `Order By`.</span><span class="sxs-lookup"><span data-stu-id="53b26-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="53b26-137">Agrupe resultados similares juntos mediante la cláusula `Group By`.</span><span class="sxs-lookup"><span data-stu-id="53b26-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="53b26-138">Utilice la cláusula `Aggregate` para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="53b26-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="53b26-139">Utilice la cláusula `Let` para introducir una variable de iteración cuyo valor se determina mediante una expresión en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="53b26-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="53b26-140">Utilice la cláusula `Distinct` para omitir los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="53b26-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="53b26-141">Identifique las partes del resultado que se van a devolver mediante las cláusulas `Skip`, `Take`, `Skip While` y `Take While`.</span><span class="sxs-lookup"><span data-stu-id="53b26-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b26-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53b26-142">Example</span></span>  
 <span data-ttu-id="53b26-143">La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` para cada objeto `Customer` en la colección `customers`.</span><span class="sxs-lookup"><span data-stu-id="53b26-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="53b26-144">La cláusula `Where` usa la variable de rango para restringir la salida a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="53b26-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="53b26-145">El bucle `For Each` muestra el nombre de la compañía para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="53b26-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="53b26-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b26-146">See also</span></span>

- [<span data-ttu-id="53b26-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="53b26-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="53b26-148">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53b26-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="53b26-149">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="53b26-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="53b26-150">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="53b26-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="53b26-151">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="53b26-152">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="53b26-153">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="53b26-154">Distinct (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="53b26-155">Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="53b26-156">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="53b26-157">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="53b26-158">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="53b26-159">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="53b26-160">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="53b26-161">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="53b26-162">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53b26-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
