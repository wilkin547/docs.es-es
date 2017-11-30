---
title: Agrupar los resultados de consultas
description: "Cómo agrupar los resultados."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: ca68cf96a2c27bbd1999d5445c14fc93e8e2566c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="group-query-results"></a><span data-ttu-id="feedf-104">Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="feedf-104">Group query results</span></span>

<span data-ttu-id="feedf-105">La agrupación es una de las capacidades más eficaces de LINQ.</span><span class="sxs-lookup"><span data-stu-id="feedf-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="feedf-106">Los ejemplos siguientes muestran cómo agrupar datos de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="feedf-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="feedf-107">Por una sola propiedad.</span><span class="sxs-lookup"><span data-stu-id="feedf-107">By a single property.</span></span>  
  
-   <span data-ttu-id="feedf-108">Por la primera letra de una propiedad de cadena.</span><span class="sxs-lookup"><span data-stu-id="feedf-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="feedf-109">Por un intervalo numérico calculado.</span><span class="sxs-lookup"><span data-stu-id="feedf-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="feedf-110">Por un predicado booleano u otra expresión.</span><span class="sxs-lookup"><span data-stu-id="feedf-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="feedf-111">Por una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="feedf-111">By a compound key.</span></span>  
  
 <span data-ttu-id="feedf-112">Además, las dos últimas consultas proyectan sus resultados en un nuevo tipo anónimo que solo contiene el nombre y los apellidos del estudiante.</span><span class="sxs-lookup"><span data-stu-id="feedf-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="feedf-113">Para obtener más información, vea la [cláusula group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="feedf-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="feedf-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-114">Example</span></span>  
 <span data-ttu-id="feedf-115">Todos los ejemplos de este tema usan los siguientes orígenes de datos y clases auxiliares.</span><span class="sxs-lookup"><span data-stu-id="feedf-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="feedf-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-116">Example</span></span>  
 <span data-ttu-id="feedf-117">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante una propiedad única del elemento como la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="feedf-117">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="feedf-118">En este caso, la clave es una `string`, el apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="feedf-118">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="feedf-119">También es posible usar una subcadena para la clave.</span><span class="sxs-lookup"><span data-stu-id="feedf-119">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="feedf-120">La operación de agrupación usa al comparador de igualdad predeterminado para el tipo.</span><span class="sxs-lookup"><span data-stu-id="feedf-120">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="feedf-121">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="feedf-121">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="feedf-122">Cambie la instrucción de llamada en el método `Main` por `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="feedf-122">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="feedf-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-123">Example</span></span>  
 <span data-ttu-id="feedf-124">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante algo distinto a una propiedad del objeto para la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="feedf-124">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="feedf-125">En este ejemplo, la clave es la primera letra del apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="feedf-125">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="feedf-126">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="feedf-126">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="feedf-127">Cambie la instrucción de llamada en el método `Main` por `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="feedf-127">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="feedf-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-128">Example</span></span>  
 <span data-ttu-id="feedf-129">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante un intervalo numérico como la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="feedf-129">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="feedf-130">Después, la consulta proyecta los resultados en un tipo anónimo que solo contiene el nombre, los apellidos y el intervalo de percentil al que pertenece el alumno.</span><span class="sxs-lookup"><span data-stu-id="feedf-130">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="feedf-131">Se usa un tipo anónimo porque no es necesario usar el objeto `Student` completo para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="feedf-131">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="feedf-132">`GetPercentile` es una función auxiliar que calcula un percentil basado en la puntuación media del alumno.</span><span class="sxs-lookup"><span data-stu-id="feedf-132">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="feedf-133">El método devuelve un entero entre 0 y 10.</span><span class="sxs-lookup"><span data-stu-id="feedf-133">The method returns an integer between 0 and 10.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]  
  
 <span data-ttu-id="feedf-134">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="feedf-134">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="feedf-135">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="feedf-135">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="feedf-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-136">Example</span></span>  
 <span data-ttu-id="feedf-137">En el ejemplo siguiente se muestra cómo agrupar elementos de origen usando una expresión de comparación booleana.</span><span class="sxs-lookup"><span data-stu-id="feedf-137">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="feedf-138">En este ejemplo, la expresión booleana comprueba si la puntuación media del examen de un alumno es mayor de 75.</span><span class="sxs-lookup"><span data-stu-id="feedf-138">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="feedf-139">Como en los ejemplos anteriores, los resultados se proyectan en un tipo anónimo porque el elemento de origen completo no es necesario.</span><span class="sxs-lookup"><span data-stu-id="feedf-139">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="feedf-140">Tenga en cuenta que las propiedades del tipo anónimo se convierten en propiedades en el miembro `Key` y puede tener acceso a ellas por nombre cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="feedf-140">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="feedf-141">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="feedf-141">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="feedf-142">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="feedf-142">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="feedf-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feedf-143">Example</span></span>  
 <span data-ttu-id="feedf-144">En el ejemplo siguiente se muestra cómo usar un tipo anónimo para encapsular una clave que contiene varios valores.</span><span class="sxs-lookup"><span data-stu-id="feedf-144">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="feedf-145">En este ejemplo, el primer valor de clave es la primera letra del apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="feedf-145">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="feedf-146">El segundo valor de clave es un valor booleano que especifica si el alumno obtuvo una nota superior a 85 en el primer examen.</span><span class="sxs-lookup"><span data-stu-id="feedf-146">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="feedf-147">Los grupos se pueden ordenar por cualquier propiedad de la clave.</span><span class="sxs-lookup"><span data-stu-id="feedf-147">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="feedf-148">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="feedf-148">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="feedf-149">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="feedf-149">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="feedf-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="feedf-150">See also</span></span>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.IGrouping%602>  
 [<span data-ttu-id="feedf-151">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="feedf-151">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="feedf-152">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="feedf-152">group clause</span></span>](../language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="feedf-153">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="feedf-153">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="feedf-154">Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="feedf-154">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="feedf-155">Crear grupos anidados</span><span class="sxs-lookup"><span data-stu-id="feedf-155">Create a Nested Group</span></span>](create-a-nested-group.md)  
 [<span data-ttu-id="feedf-156">Agrupación de datos</span><span class="sxs-lookup"><span data-stu-id="feedf-156">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
