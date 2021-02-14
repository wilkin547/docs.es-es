---
description: 'Más información acerca de cómo: combinar datos con LINQ mediante combinaciones (Visual Basic)'
title: Procedimiento para combinar datos con LINQ mediante cláusulas Join
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 69cf0bcfb8d9241afdd0616621f35d7ca93bbb9e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422749"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="9c1d8-103">Cómo: Combinar datos con LINQ usando cláusulas Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-103">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>

<span data-ttu-id="9c1d8-104">Visual Basic proporciona las `Join` `Group Join` cláusulas de consulta y para que pueda combinar el contenido de varias colecciones en función de los valores comunes entre las colecciones.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-104">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="9c1d8-105">Estos valores se conocen como valores de *clave* .</span><span class="sxs-lookup"><span data-stu-id="9c1d8-105">These values are known as *key* values.</span></span> <span data-ttu-id="9c1d8-106">Los desarrolladores familiarizados con los conceptos de bases de datos relacionales reconocerán la `Join` cláusula como una combinación interna y la `Group Join` cláusula como, efectivamente, una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-106">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="9c1d8-107">En los ejemplos de este tema se muestran algunas maneras de combinar datos con las `Join` `Group Join` cláusulas de consulta y.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-107">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="9c1d8-108">Crear un proyecto y agregar datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c1d8-108">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="9c1d8-109">Para crear un proyecto que contenga datos y tipos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c1d8-109">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="9c1d8-110">Para ejecutar los ejemplos de este tema, abra Visual Studio y agregue un nuevo proyecto de aplicación de consola de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-110">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="9c1d8-111">Haga doble clic en el archivo Module1. VB creado por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-111">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="9c1d8-112">Los ejemplos de este tema usan los `Person` `Pet` tipos y y los datos del ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-112">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="9c1d8-113">Copie este código en el `Module1` módulo predeterminado creado por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-113">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="9c1d8-114">Realizar una combinación interna mediante la cláusula join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-114">Perform an Inner Join by Using the Join Clause</span></span>  

 <span data-ttu-id="9c1d8-115">Una combinación interna combina datos de dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-115">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="9c1d8-116">Se incluyen los elementos para los que coinciden los valores de clave especificados.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-116">Items for which the specified key values match are included.</span></span> <span data-ttu-id="9c1d8-117">Se excluyen todos los elementos de cualquier colección que no tengan un elemento coincidente en la otra colección.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-117">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="9c1d8-118">En Visual Basic, LINQ proporciona dos opciones para realizar una combinación interna: una combinación implícita y una combinación explícita.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-118">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="9c1d8-119">Una combinación implícita especifica las colecciones que se van a combinar en una `From` cláusula e identifica los campos de clave coincidentes en una `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-119">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="9c1d8-120">Visual Basic combina implícitamente las dos colecciones basándose en los campos de clave especificados.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-120">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="9c1d8-121">Puede especificar una combinación explícita mediante la `Join` cláusula cuando quiera ser específica de qué campos clave usar en la combinación.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-121">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="9c1d8-122">En este caso, `Where` todavía se puede usar una cláusula para filtrar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-122">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="9c1d8-123">Para realizar una combinación interna mediante la cláusula join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-123">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="9c1d8-124">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación interna implícita y explícita.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-124">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="9c1d8-125">Realizar una combinación externa izquierda mediante la cláusula Group join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-125">Perform a Left Outer Join by Using the Group Join Clause</span></span>  

 <span data-ttu-id="9c1d8-126">Una combinación externa izquierda incluye todos los elementos de la colección del lado izquierdo de la combinación y solo los valores coincidentes de la colección del lado derecho de la combinación.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-126">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="9c1d8-127">Los elementos de la colección del lado derecho de la combinación que no tienen un elemento coincidente en la colección del lado izquierdo se excluyen del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-127">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="9c1d8-128">La `Group Join` cláusula realiza una combinación externa izquierda, en efecto.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-128">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="9c1d8-129">La diferencia entre lo que se conoce normalmente como una combinación externa izquierda y lo que `Group Join` devuelve la cláusula es que la `Group Join` cláusula agrupa los resultados de la colección del lado derecho de la combinación de cada elemento de la colección del lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-129">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="9c1d8-130">En una base de datos relacional, una combinación externa izquierda devuelve un resultado no agrupado en el que cada elemento del resultado de la consulta contiene elementos coincidentes de ambas colecciones en la combinación.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-130">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="9c1d8-131">En este caso, los elementos de la colección del lado izquierdo de la combinación se repiten para cada elemento coincidente de la colección del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-131">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="9c1d8-132">Verá el aspecto que tendrá cuando complete el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-132">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="9c1d8-133">Puede recuperar los resultados de una `Group Join` consulta como un resultado no agrupado extendiendo la consulta para devolver un elemento para cada resultado de la consulta agrupada.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-133">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="9c1d8-134">Para ello, debe asegurarse de que consulta en el `DefaultIfEmpty` método de la colección agrupada.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-134">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="9c1d8-135">Esto garantiza que los elementos de la colección del lado izquierdo de la combinación todavía se incluyen en el resultado de la consulta, incluso si no tienen resultados coincidentes de la colección del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-135">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="9c1d8-136">Puede agregar código a la consulta para proporcionar un valor de resultado predeterminado cuando no haya ningún valor coincidente en la colección del lado derecho de la combinación.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-136">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="9c1d8-137">Para realizar una combinación externa izquierda mediante la cláusula Group join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-137">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="9c1d8-138">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación externa izquierda agrupada y una combinación externa izquierda no agrupada.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-138">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="9c1d8-139">Realizar una combinación mediante una clave compuesta</span><span class="sxs-lookup"><span data-stu-id="9c1d8-139">Perform a Join by Using a Composite Key</span></span>  

 <span data-ttu-id="9c1d8-140">Puede usar la `And` palabra clave en una `Join` `Group Join` cláusula o para identificar varios campos clave que se usarán al buscar valores coincidentes de las colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-140">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="9c1d8-141">La `And` palabra clave especifica que todos los campos de clave especificados deben coincidir con los elementos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-141">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="9c1d8-142">Para realizar una combinación mediante una clave compuesta</span><span class="sxs-lookup"><span data-stu-id="9c1d8-142">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="9c1d8-143">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación que usa una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-143">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="9c1d8-144">ejecutar el código</span><span class="sxs-lookup"><span data-stu-id="9c1d8-144">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="9c1d8-145">Para agregar código para ejecutar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="9c1d8-145">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="9c1d8-146">Reemplace `Sub Main` en el `Module1` módulo del proyecto por el código siguiente para ejecutar los ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-146">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="9c1d8-147">Presione F5 para ejecutar los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-147">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c1d8-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c1d8-148">See also</span></span>

- [<span data-ttu-id="9c1d8-149">LINQ</span><span class="sxs-lookup"><span data-stu-id="9c1d8-149">LINQ</span></span>](index.md)
- [<span data-ttu-id="9c1d8-150">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c1d8-150">Introduction to LINQ in Visual Basic</span></span>](introduction-to-linq.md)
- [<span data-ttu-id="9c1d8-151">Cláusula Join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-151">Join Clause</span></span>](../../../language-reference/queries/join-clause.md)
- [<span data-ttu-id="9c1d8-152">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="9c1d8-152">Group Join Clause</span></span>](../../../language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="9c1d8-153">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="9c1d8-153">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="9c1d8-154">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="9c1d8-154">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="9c1d8-155">Consultas</span><span class="sxs-lookup"><span data-stu-id="9c1d8-155">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="9c1d8-156">Transformaciones de datos con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-156">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
