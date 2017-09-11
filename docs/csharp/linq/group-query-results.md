---
title: Agrupar los resultados de consultas
description: "Cómo agrupar los resultados."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1c1639651699afbe5fb768db26b98a9b2d734315
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="group-query-results"></a><span data-ttu-id="d28b0-104">Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="d28b0-104">Group query results</span></span>

<span data-ttu-id="d28b0-105">La agrupación es una de las capacidades más eficaces de LINQ.</span><span class="sxs-lookup"><span data-stu-id="d28b0-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="d28b0-106">Los ejemplos siguientes muestran cómo agrupar datos de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="d28b0-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="d28b0-107">Por una sola propiedad.</span><span class="sxs-lookup"><span data-stu-id="d28b0-107">By a single property.</span></span>  
  
-   <span data-ttu-id="d28b0-108">Por la primera letra de una propiedad de cadena.</span><span class="sxs-lookup"><span data-stu-id="d28b0-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="d28b0-109">Por un intervalo numérico calculado.</span><span class="sxs-lookup"><span data-stu-id="d28b0-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="d28b0-110">Por un predicado booleano u otra expresión.</span><span class="sxs-lookup"><span data-stu-id="d28b0-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="d28b0-111">Por una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="d28b0-111">By a compound key.</span></span>  
  
 <span data-ttu-id="d28b0-112">Además, las dos últimas consultas proyectan sus resultados en un nuevo tipo anónimo que solo contiene el nombre y los apellidos del estudiante.</span><span class="sxs-lookup"><span data-stu-id="d28b0-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="d28b0-113">Para obtener más información, vea la [cláusula group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d28b0-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-114">Example</span></span>  
 <span data-ttu-id="d28b0-115">Todos los ejemplos de este tema usan los siguientes orígenes de datos y clases auxiliares.</span><span class="sxs-lookup"><span data-stu-id="d28b0-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 <span data-ttu-id="d28b0-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-117">Example</span></span>  
 <span data-ttu-id="d28b0-118">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante una propiedad única del elemento como la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="d28b0-118">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="d28b0-119">En este caso, la clave es una `string`, el apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="d28b0-119">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="d28b0-120">También es posible usar una subcadena para la clave.</span><span class="sxs-lookup"><span data-stu-id="d28b0-120">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="d28b0-121">La operación de agrupación usa al comparador de igualdad predeterminado para el tipo.</span><span class="sxs-lookup"><span data-stu-id="d28b0-121">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="d28b0-122">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-122">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="d28b0-123">Cambie la instrucción de llamada en el método `Main` por `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-123">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 <span data-ttu-id="d28b0-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-125">Example</span></span>  
 <span data-ttu-id="d28b0-126">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante algo distinto a una propiedad del objeto para la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="d28b0-126">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="d28b0-127">En este ejemplo, la clave es la primera letra del apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="d28b0-127">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="d28b0-128">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-128">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="d28b0-129">Cambie la instrucción de llamada en el método `Main` por `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-129">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 <span data-ttu-id="d28b0-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-131">Example</span></span>  
 <span data-ttu-id="d28b0-132">En el ejemplo siguiente se muestra cómo agrupar elementos de origen mediante un intervalo numérico como la clave de grupo.</span><span class="sxs-lookup"><span data-stu-id="d28b0-132">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="d28b0-133">Después, la consulta proyecta los resultados en un tipo anónimo que solo contiene el nombre, los apellidos y el intervalo de percentil al que pertenece el alumno.</span><span class="sxs-lookup"><span data-stu-id="d28b0-133">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="d28b0-134">Se usa un tipo anónimo porque no es necesario usar el objeto `Student` completo para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="d28b0-134">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="d28b0-135">`GetPercentile` es una función auxiliar que calcula un percentil basado en la puntuación media del alumno.</span><span class="sxs-lookup"><span data-stu-id="d28b0-135">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="d28b0-136">El método devuelve un entero entre 0 y 10.</span><span class="sxs-lookup"><span data-stu-id="d28b0-136">The method returns an integer between 0 and 10.</span></span>  
  
 <span data-ttu-id="d28b0-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span></span>  
  
 <span data-ttu-id="d28b0-138">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-138">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="d28b0-139">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-139">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 <span data-ttu-id="d28b0-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-141">Example</span></span>  
 <span data-ttu-id="d28b0-142">En el ejemplo siguiente se muestra cómo agrupar elementos de origen usando una expresión de comparación booleana.</span><span class="sxs-lookup"><span data-stu-id="d28b0-142">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="d28b0-143">En este ejemplo, la expresión booleana comprueba si la puntuación media del examen de un alumno es mayor de 75.</span><span class="sxs-lookup"><span data-stu-id="d28b0-143">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="d28b0-144">Como en los ejemplos anteriores, los resultados se proyectan en un tipo anónimo porque el elemento de origen completo no es necesario.</span><span class="sxs-lookup"><span data-stu-id="d28b0-144">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="d28b0-145">Tenga en cuenta que las propiedades del tipo anónimo se convierten en propiedades en el miembro `Key` y puede tener acceso a ellas por nombre cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="d28b0-145">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="d28b0-146">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-146">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="d28b0-147">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-147">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 <span data-ttu-id="d28b0-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28b0-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28b0-149">Example</span></span>  
 <span data-ttu-id="d28b0-150">En el ejemplo siguiente se muestra cómo usar un tipo anónimo para encapsular una clave que contiene varios valores.</span><span class="sxs-lookup"><span data-stu-id="d28b0-150">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="d28b0-151">En este ejemplo, el primer valor de clave es la primera letra del apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="d28b0-151">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="d28b0-152">El segundo valor de clave es un valor booleano que especifica si el alumno obtuvo una nota superior a 85 en el primer examen.</span><span class="sxs-lookup"><span data-stu-id="d28b0-152">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="d28b0-153">Los grupos se pueden ordenar por cualquier propiedad de la clave.</span><span class="sxs-lookup"><span data-stu-id="d28b0-153">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="d28b0-154">Pegue el método siguiente en la clase `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-154">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="d28b0-155">Cambie la instrucción de llamada en el método `Main` por `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="d28b0-155">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 <span data-ttu-id="d28b0-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28b0-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28b0-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="d28b0-157">See also</span></span>  
 <span data-ttu-id="d28b0-158"><xref:System.Linq.Enumerable.GroupBy%2A></span><span class="sxs-lookup"><span data-stu-id="d28b0-158"><xref:System.Linq.Enumerable.GroupBy%2A></span></span>   
 <span data-ttu-id="d28b0-159"><xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="d28b0-159"><xref:System.Linq.IGrouping%602></span></span>   
 <span data-ttu-id="d28b0-160">[Expresiones de consulta LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="d28b0-160">[LINQ Query Expressions](index.md) </span></span>  
 <span data-ttu-id="d28b0-161">[group (Cláusula)](../language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="d28b0-161">[group clause](../language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="d28b0-162">[Tipos anónimos](../programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="d28b0-162">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="d28b0-163">[Realizar una subconsulta en una operación de agrupación](perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="d28b0-163">[Perform a Subquery on a Grouping Operation](perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 <span data-ttu-id="d28b0-164">[Crear un grupo anidado](create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="d28b0-164">[Create a Nested Group](create-a-nested-group.md) </span></span>  
 [<span data-ttu-id="d28b0-165">Agrupación de datos</span><span class="sxs-lookup"><span data-stu-id="d28b0-165">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)

