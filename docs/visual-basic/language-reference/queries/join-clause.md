---
description: 'Más información acerca de: cláusula join (Visual Basic)'
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
ms.openlocfilehash: 69d808e68a32b3f8799dabbbc8abc53acae42b57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700447"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="d52b8-103">Join (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d52b8-103">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="d52b8-104">Combina dos colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="d52b8-104">Combines two collections into a single collection.</span></span> <span data-ttu-id="d52b8-105">La operación de combinación se basa en las claves coincidentes y utiliza el `Equals` operador.</span><span class="sxs-lookup"><span data-stu-id="d52b8-105">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="d52b8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d52b8-106">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="d52b8-107">Partes</span><span class="sxs-lookup"><span data-stu-id="d52b8-107">Parts</span></span>

<span data-ttu-id="d52b8-108">`element` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d52b8-108">`element` Required.</span></span> <span data-ttu-id="d52b8-109">Variable de control de la colección que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="d52b8-109">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="d52b8-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d52b8-110">Required.</span></span> <span data-ttu-id="d52b8-111">Colección que se va a combinar con la colección identificada en el lado izquierdo del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="d52b8-111">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="d52b8-112">Una `Join` cláusula se puede anidar en otra `Join` cláusula o en una `Group Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d52b8-112">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="d52b8-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d52b8-113">Optional.</span></span> <span data-ttu-id="d52b8-114">Una o más `Join` cláusulas adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="d52b8-114">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="d52b8-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d52b8-115">Optional.</span></span> <span data-ttu-id="d52b8-116">Una o más `Group Join` cláusulas adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="d52b8-116">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="d52b8-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="d52b8-117">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="d52b8-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d52b8-118">Required.</span></span> <span data-ttu-id="d52b8-119">Identifica las claves para las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="d52b8-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="d52b8-120">Debe utilizar el `Equals` operador para comparar las claves de las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="d52b8-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="d52b8-121">Puede combinar condiciones de combinación mediante el `And` operador para identificar varias claves.</span><span class="sxs-lookup"><span data-stu-id="d52b8-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="d52b8-122">`key1` debe ser de la colección en el lado izquierdo del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="d52b8-122">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="d52b8-123">`key2` debe ser de la colección del lado derecho del `Join` operador.</span><span class="sxs-lookup"><span data-stu-id="d52b8-123">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="d52b8-124">Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="d52b8-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="d52b8-125">Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.</span><span class="sxs-lookup"><span data-stu-id="d52b8-125">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="d52b8-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d52b8-126">Remarks</span></span>

<span data-ttu-id="d52b8-127">La `Join` cláusula combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="d52b8-127">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="d52b8-128">La colección resultante puede contener cualquier combinación de valores de la colección identificada en el lado izquierdo del `Join` operador y la colección identificada en la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d52b8-128">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="d52b8-129">La consulta devolverá solo los resultados para los que se cumple la condición especificada por el `Equals` operador.</span><span class="sxs-lookup"><span data-stu-id="d52b8-129">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="d52b8-130">Esto es equivalente a `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="d52b8-130">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="d52b8-131">Puede usar varias `Join` cláusulas en una consulta para combinar dos o más colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="d52b8-131">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="d52b8-132">Puede realizar una combinación implícita para combinar colecciones sin la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d52b8-132">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="d52b8-133">Para ello, incluya varias `In` cláusulas en la `From` cláusula y especifique una `Where` cláusula que identifique las claves que desea usar para la combinación.</span><span class="sxs-lookup"><span data-stu-id="d52b8-133">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="d52b8-134">Puede usar la `Group Join` cláusula para combinar colecciones en una sola colección jerárquica.</span><span class="sxs-lookup"><span data-stu-id="d52b8-134">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="d52b8-135">Es como un `LEFT OUTER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="d52b8-135">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="d52b8-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d52b8-136">Example</span></span>

<span data-ttu-id="d52b8-137">En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.</span><span class="sxs-lookup"><span data-stu-id="d52b8-137">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="d52b8-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d52b8-138">Example</span></span>

<span data-ttu-id="d52b8-139">En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d52b8-139">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="d52b8-140">Este ejemplo generará una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d52b8-140">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="d52b8-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d52b8-141">Example</span></span>

<span data-ttu-id="d52b8-142">En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula con dos columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="d52b8-142">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="d52b8-143">En el ejemplo se producirá una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d52b8-143">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="d52b8-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="d52b8-144">See also</span></span>

- [<span data-ttu-id="d52b8-145">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d52b8-145">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d52b8-146">Consultas</span><span class="sxs-lookup"><span data-stu-id="d52b8-146">Queries</span></span>](index.md)
- [<span data-ttu-id="d52b8-147">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="d52b8-147">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="d52b8-148">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="d52b8-148">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="d52b8-149">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="d52b8-149">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="d52b8-150">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="d52b8-150">Where Clause</span></span>](where-clause.md)
