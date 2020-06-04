---
title: Cláusula Join
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
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359779"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="f8286-102">Join (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8286-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="f8286-103">Combina dos colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="f8286-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="f8286-104">La operación de combinación se basa en las claves coincidentes y utiliza el `Equals` operador.</span><span class="sxs-lookup"><span data-stu-id="f8286-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8286-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8286-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="f8286-106">Partes</span><span class="sxs-lookup"><span data-stu-id="f8286-106">Parts</span></span>

<span data-ttu-id="f8286-107">`element` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8286-107">`element` Required.</span></span> <span data-ttu-id="f8286-108">Variable de control de la colección que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="f8286-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="f8286-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f8286-109">Required.</span></span> <span data-ttu-id="f8286-110">Colección que se va a combinar con la colección identificada en el lado izquierdo del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="f8286-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="f8286-111">Una `Join` cláusula se puede anidar en otra `Join` cláusula o en una `Group Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f8286-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="f8286-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f8286-112">Optional.</span></span> <span data-ttu-id="f8286-113">Una o más `Join` cláusulas adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="f8286-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="f8286-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f8286-114">Optional.</span></span> <span data-ttu-id="f8286-115">Una o más `Group Join` cláusulas adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="f8286-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="f8286-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="f8286-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="f8286-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f8286-117">Required.</span></span> <span data-ttu-id="f8286-118">Identifica las claves para las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="f8286-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="f8286-119">Debe utilizar el `Equals` operador para comparar las claves de las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="f8286-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="f8286-120">Puede combinar condiciones de combinación mediante el `And` operador para identificar varias claves.</span><span class="sxs-lookup"><span data-stu-id="f8286-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="f8286-121">`key1`debe ser de la colección en el lado izquierdo del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="f8286-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="f8286-122">`key2`debe ser de la colección del lado derecho del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="f8286-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="f8286-123">Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="f8286-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="f8286-124">Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.</span><span class="sxs-lookup"><span data-stu-id="f8286-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8286-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8286-125">Remarks</span></span>

<span data-ttu-id="f8286-126">La `Join` cláusula combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="f8286-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="f8286-127">La colección resultante puede contener cualquier combinación de valores de la colección identificada en el lado izquierdo del `Join` operador y la colección identificada en la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f8286-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="f8286-128">La consulta devolverá solo los resultados para los que se cumple la condición especificada por el `Equals` operador.</span><span class="sxs-lookup"><span data-stu-id="f8286-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="f8286-129">Esto es equivalente a `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="f8286-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="f8286-130">Puede usar varias `Join` cláusulas en una consulta para combinar dos o más colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="f8286-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="f8286-131">Puede realizar una combinación implícita para combinar colecciones sin la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f8286-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="f8286-132">Para ello, incluya varias `In` cláusulas en la `From` cláusula y especifique una `Where` cláusula que identifique las claves que desea usar para la combinación.</span><span class="sxs-lookup"><span data-stu-id="f8286-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="f8286-133">Puede usar la `Group Join` cláusula para combinar colecciones en una sola colección jerárquica.</span><span class="sxs-lookup"><span data-stu-id="f8286-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="f8286-134">Es como un `LEFT OUTER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="f8286-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="f8286-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8286-135">Example</span></span>

<span data-ttu-id="f8286-136">En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.</span><span class="sxs-lookup"><span data-stu-id="f8286-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="f8286-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8286-137">Example</span></span>

<span data-ttu-id="f8286-138">En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f8286-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="f8286-139">Este ejemplo generará una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8286-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="f8286-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8286-140">Example</span></span>

<span data-ttu-id="f8286-141">En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula con dos columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="f8286-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="f8286-142">En el ejemplo se producirá una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8286-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="f8286-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8286-143">See also</span></span>

- [<span data-ttu-id="f8286-144">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8286-144">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f8286-145">Consultas</span><span class="sxs-lookup"><span data-stu-id="f8286-145">Queries</span></span>](index.md)
- [<span data-ttu-id="f8286-146">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f8286-146">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="f8286-147">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="f8286-147">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="f8286-148">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="f8286-148">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="f8286-149">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="f8286-149">Where Clause</span></span>](where-clause.md)
