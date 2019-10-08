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
ms.openlocfilehash: 8eab7db00515f55b086b5e1beddd149f966cb27a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72001937"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="da68c-102">Join (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da68c-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="da68c-103">Combina dos colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="da68c-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="da68c-104">La operación de combinación se basa en las claves coincidentes y utiliza el operador `Equals`.</span><span class="sxs-lookup"><span data-stu-id="da68c-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da68c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da68c-105">Syntax</span></span>  
  
```vb  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="da68c-106">Elementos</span><span class="sxs-lookup"><span data-stu-id="da68c-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="da68c-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="da68c-107">Required.</span></span> <span data-ttu-id="da68c-108">Variable de control de la colección que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="da68c-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="da68c-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="da68c-109">Required.</span></span> <span data-ttu-id="da68c-110">Colección que se va a combinar con la colección identificada en el lado izquierdo del operador `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="da68c-111">Una cláusula `Join` puede estar anidada en otra cláusula `Join` o en una cláusula `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="da68c-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="da68c-112">Optional.</span></span> <span data-ttu-id="da68c-113">Una o más cláusulas `Join` adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="da68c-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="da68c-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="da68c-114">Optional.</span></span> <span data-ttu-id="da68c-115">Una o más cláusulas `Group Join` adicionales para restringir aún más la consulta.</span><span class="sxs-lookup"><span data-stu-id="da68c-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="da68c-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="da68c-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="da68c-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="da68c-117">Required.</span></span> <span data-ttu-id="da68c-118">Identifica las claves para las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="da68c-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="da68c-119">Debe usar el operador `Equals` para comparar las claves de las colecciones que se están combinando.</span><span class="sxs-lookup"><span data-stu-id="da68c-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="da68c-120">Puede combinar condiciones de combinación mediante el operador `And` para identificar varias claves.</span><span class="sxs-lookup"><span data-stu-id="da68c-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="da68c-121">`key1` debe ser de la colección del lado izquierdo del operador `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="da68c-122">`key2` debe ser de la colección del lado derecho del operador `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="da68c-123">Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="da68c-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="da68c-124">Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.</span><span class="sxs-lookup"><span data-stu-id="da68c-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da68c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da68c-125">Remarks</span></span>  
 <span data-ttu-id="da68c-126">La cláusula `Join` combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="da68c-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="da68c-127">La colección resultante puede contener cualquier combinación de valores de la colección identificada en el lado izquierdo del operador `Join` y la colección identificada en la cláusula `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="da68c-128">La consulta devolverá solo los resultados para los que se cumple la condición especificada por el operador `Equals`.</span><span class="sxs-lookup"><span data-stu-id="da68c-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="da68c-129">Esto es equivalente a un `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="da68c-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="da68c-130">Puede usar varias cláusulas `Join` en una consulta para combinar dos o más colecciones en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="da68c-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="da68c-131">Puede realizar una combinación implícita para combinar colecciones sin la cláusula `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="da68c-132">Para ello, incluya varias cláusulas `In` en la cláusula `From` y especifique una cláusula `Where` que identifique las claves que desea usar para la combinación.</span><span class="sxs-lookup"><span data-stu-id="da68c-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="da68c-133">Puede usar la cláusula `Group Join` para combinar colecciones en una sola colección jerárquica.</span><span class="sxs-lookup"><span data-stu-id="da68c-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="da68c-134">Esto es como un `LEFT OUTER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="da68c-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da68c-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da68c-135">Example</span></span>  
 <span data-ttu-id="da68c-136">En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.</span><span class="sxs-lookup"><span data-stu-id="da68c-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="da68c-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da68c-137">Example</span></span>  
 <span data-ttu-id="da68c-138">En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join`.</span><span class="sxs-lookup"><span data-stu-id="da68c-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 <span data-ttu-id="da68c-139">Este ejemplo generará una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="da68c-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="da68c-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da68c-140">Example</span></span>  
 <span data-ttu-id="da68c-141">En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join` con dos columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="da68c-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 <span data-ttu-id="da68c-142">En el ejemplo se producirá una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="da68c-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="da68c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="da68c-143">See also</span></span>

- [<span data-ttu-id="da68c-144">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da68c-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="da68c-145">Consultas</span><span class="sxs-lookup"><span data-stu-id="da68c-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="da68c-146">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="da68c-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="da68c-147">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="da68c-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="da68c-148">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="da68c-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="da68c-149">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="da68c-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
