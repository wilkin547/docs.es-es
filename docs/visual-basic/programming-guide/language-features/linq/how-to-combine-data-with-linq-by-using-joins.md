---
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
ms.openlocfilehash: ebda8d3b7fa2e712c337ed2c1fadc580bed7fe61
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075075"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="a8e25-102">Cómo: Combinar datos con LINQ usando cláusulas Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8e25-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>

<span data-ttu-id="a8e25-103">Visual Basic proporciona las `Join` `Group Join` cláusulas de consulta y para que pueda combinar el contenido de varias colecciones en función de los valores comunes entre las colecciones.</span><span class="sxs-lookup"><span data-stu-id="a8e25-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="a8e25-104">Estos valores se conocen como valores de *clave* .</span><span class="sxs-lookup"><span data-stu-id="a8e25-104">These values are known as *key* values.</span></span> <span data-ttu-id="a8e25-105">Los desarrolladores familiarizados con los conceptos de bases de datos relacionales reconocerán la `Join` cláusula como una combinación interna y la `Group Join` cláusula como, efectivamente, una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="a8e25-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="a8e25-106">En los ejemplos de este tema se muestran algunas maneras de combinar datos con las `Join` `Group Join` cláusulas de consulta y.</span><span class="sxs-lookup"><span data-stu-id="a8e25-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="a8e25-107">Crear un proyecto y agregar datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8e25-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="a8e25-108">Para crear un proyecto que contenga datos y tipos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8e25-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="a8e25-109">Para ejecutar los ejemplos de este tema, abra Visual Studio y agregue un nuevo proyecto de aplicación de consola de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8e25-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="a8e25-110">Haga doble clic en el archivo Module1. VB creado por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8e25-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="a8e25-111">Los ejemplos de este tema usan los `Person` `Pet` tipos y y los datos del ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8e25-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="a8e25-112">Copie este código en el `Module1` módulo predeterminado creado por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8e25-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="a8e25-113">Realizar una combinación interna mediante la cláusula join</span><span class="sxs-lookup"><span data-stu-id="a8e25-113">Perform an Inner Join by Using the Join Clause</span></span>  

 <span data-ttu-id="a8e25-114">Una combinación interna combina datos de dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="a8e25-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="a8e25-115">Se incluyen los elementos para los que coinciden los valores de clave especificados.</span><span class="sxs-lookup"><span data-stu-id="a8e25-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="a8e25-116">Se excluyen todos los elementos de cualquier colección que no tengan un elemento coincidente en la otra colección.</span><span class="sxs-lookup"><span data-stu-id="a8e25-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="a8e25-117">En Visual Basic, LINQ proporciona dos opciones para realizar una combinación interna: una combinación implícita y una combinación explícita.</span><span class="sxs-lookup"><span data-stu-id="a8e25-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="a8e25-118">Una combinación implícita especifica las colecciones que se van a combinar en una `From` cláusula e identifica los campos de clave coincidentes en una `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="a8e25-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="a8e25-119">Visual Basic combina implícitamente las dos colecciones basándose en los campos de clave especificados.</span><span class="sxs-lookup"><span data-stu-id="a8e25-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="a8e25-120">Puede especificar una combinación explícita mediante la `Join` cláusula cuando quiera ser específica de qué campos clave usar en la combinación.</span><span class="sxs-lookup"><span data-stu-id="a8e25-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="a8e25-121">En este caso, `Where` todavía se puede usar una cláusula para filtrar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8e25-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="a8e25-122">Para realizar una combinación interna mediante la cláusula join</span><span class="sxs-lookup"><span data-stu-id="a8e25-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="a8e25-123">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación interna implícita y explícita.</span><span class="sxs-lookup"><span data-stu-id="a8e25-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="a8e25-124">Realizar una combinación externa izquierda mediante la cláusula Group join</span><span class="sxs-lookup"><span data-stu-id="a8e25-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  

 <span data-ttu-id="a8e25-125">Una combinación externa izquierda incluye todos los elementos de la colección del lado izquierdo de la combinación y solo los valores coincidentes de la colección del lado derecho de la combinación.</span><span class="sxs-lookup"><span data-stu-id="a8e25-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="a8e25-126">Los elementos de la colección del lado derecho de la combinación que no tienen un elemento coincidente en la colección del lado izquierdo se excluyen del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8e25-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="a8e25-127">La `Group Join` cláusula realiza una combinación externa izquierda, en efecto.</span><span class="sxs-lookup"><span data-stu-id="a8e25-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="a8e25-128">La diferencia entre lo que se conoce normalmente como una combinación externa izquierda y lo que `Group Join` devuelve la cláusula es que la `Group Join` cláusula agrupa los resultados de la colección del lado derecho de la combinación de cada elemento de la colección del lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a8e25-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="a8e25-129">En una base de datos relacional, una combinación externa izquierda devuelve un resultado no agrupado en el que cada elemento del resultado de la consulta contiene elementos coincidentes de ambas colecciones en la combinación.</span><span class="sxs-lookup"><span data-stu-id="a8e25-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="a8e25-130">En este caso, los elementos de la colección del lado izquierdo de la combinación se repiten para cada elemento coincidente de la colección del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="a8e25-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="a8e25-131">Verá el aspecto que tendrá cuando complete el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8e25-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="a8e25-132">Puede recuperar los resultados de una `Group Join` consulta como un resultado no agrupado extendiendo la consulta para devolver un elemento para cada resultado de la consulta agrupada.</span><span class="sxs-lookup"><span data-stu-id="a8e25-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="a8e25-133">Para ello, debe asegurarse de que consulta en el `DefaultIfEmpty` método de la colección agrupada.</span><span class="sxs-lookup"><span data-stu-id="a8e25-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="a8e25-134">Esto garantiza que los elementos de la colección del lado izquierdo de la combinación todavía se incluyen en el resultado de la consulta, incluso si no tienen resultados coincidentes de la colección del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="a8e25-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="a8e25-135">Puede agregar código a la consulta para proporcionar un valor de resultado predeterminado cuando no haya ningún valor coincidente en la colección del lado derecho de la combinación.</span><span class="sxs-lookup"><span data-stu-id="a8e25-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="a8e25-136">Para realizar una combinación externa izquierda mediante la cláusula Group join</span><span class="sxs-lookup"><span data-stu-id="a8e25-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="a8e25-137">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación externa izquierda agrupada y una combinación externa izquierda no agrupada.</span><span class="sxs-lookup"><span data-stu-id="a8e25-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="a8e25-138">Realizar una combinación mediante una clave compuesta</span><span class="sxs-lookup"><span data-stu-id="a8e25-138">Perform a Join by Using a Composite Key</span></span>  

 <span data-ttu-id="a8e25-139">Puede usar la `And` palabra clave en una `Join` `Group Join` cláusula o para identificar varios campos clave que se usarán al buscar valores coincidentes de las colecciones que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="a8e25-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="a8e25-140">La `And` palabra clave especifica que todos los campos de clave especificados deben coincidir con los elementos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="a8e25-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="a8e25-141">Para realizar una combinación mediante una clave compuesta</span><span class="sxs-lookup"><span data-stu-id="a8e25-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="a8e25-142">Agregue el código siguiente al `Module1` módulo del proyecto para ver ejemplos de una combinación que usa una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="a8e25-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="a8e25-143">ejecutar el código</span><span class="sxs-lookup"><span data-stu-id="a8e25-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="a8e25-144">Para agregar código para ejecutar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e25-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="a8e25-145">Reemplace `Sub Main` en el `Module1` módulo del proyecto por el código siguiente para ejecutar los ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="a8e25-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="a8e25-146">Presione F5 para ejecutar los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a8e25-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e25-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e25-147">See also</span></span>

- [<span data-ttu-id="a8e25-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="a8e25-148">LINQ</span></span>](index.md)
- [<span data-ttu-id="a8e25-149">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8e25-149">Introduction to LINQ in Visual Basic</span></span>](introduction-to-linq.md)
- [<span data-ttu-id="a8e25-150">Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a8e25-150">Join Clause</span></span>](../../../language-reference/queries/join-clause.md)
- [<span data-ttu-id="a8e25-151">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="a8e25-151">Group Join Clause</span></span>](../../../language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="a8e25-152">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="a8e25-152">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="a8e25-153">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="a8e25-153">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="a8e25-154">Consultas</span><span class="sxs-lookup"><span data-stu-id="a8e25-154">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="a8e25-155">Transformaciones de datos con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a8e25-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
