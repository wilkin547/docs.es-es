---
description: 'Más información acerca de: operaciones básicas de consulta (Visual Basic)'
title: Operaciones básicas de consulta
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: 1f8fbda83c21fe9032415d96ff2d7e184083a839
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428693"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="a3872-103">Operaciones básicas de consulta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3872-103">Basic Query Operations (Visual Basic)</span></span>

<span data-ttu-id="a3872-104">En este tema se proporciona una breve introducción a las expresiones de Language-Integrated Query (LINQ) en Visual Basic y a algunos de los tipos de operaciones más habituales que se realizan en una consulta.</span><span class="sxs-lookup"><span data-stu-id="a3872-104">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="a3872-105">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3872-105">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="a3872-106">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3872-106">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="a3872-107">Consultas</span><span class="sxs-lookup"><span data-stu-id="a3872-107">Queries</span></span>](../../../language-reference/queries/index.md)  
  
 [<span data-ttu-id="a3872-108">Tutorial: Escribir consultas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3872-108">Walkthrough: Writing Queries in Visual Basic</span></span>](walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="a3872-109">Especificar el origen de datos (desde)</span><span class="sxs-lookup"><span data-stu-id="a3872-109">Specifying the Data Source (From)</span></span>  

 <span data-ttu-id="a3872-110">En una consulta LINQ, el primer paso es especificar el origen de datos que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="a3872-110">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="a3872-111">Por lo tanto, la `From` cláusula en una consulta siempre aparece primero.</span><span class="sxs-lookup"><span data-stu-id="a3872-111">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="a3872-112">Los operadores de consulta seleccionan y dan forma al resultado en función del tipo de origen.</span><span class="sxs-lookup"><span data-stu-id="a3872-112">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="a3872-113">La `From` cláusula especifica el origen de datos, `customers` , y una *variable de rango*, `cust` .</span><span class="sxs-lookup"><span data-stu-id="a3872-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="a3872-114">La variable de rango es como una variable de iteración de bucle, salvo que en una expresión de consulta no se produce ninguna iteración real.</span><span class="sxs-lookup"><span data-stu-id="a3872-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="a3872-115">Cuando se ejecuta la consulta, a menudo con un `For Each` bucle, la variable de rango sirve como referencia a cada elemento sucesivo en `customers` .</span><span class="sxs-lookup"><span data-stu-id="a3872-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="a3872-116">Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a3872-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="a3872-117">Para obtener ejemplos de consultas escritas con y sin tipos explícitos, vea [relaciones de tipos en operaciones de consulta (Visual Basic)](type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="a3872-118">Para obtener más información sobre cómo usar la `From` cláusula en Visual Basic, consulte [from (cláusula](../../../language-reference/queries/from-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="a3872-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="a3872-119">Filtrar datos (dónde)</span><span class="sxs-lookup"><span data-stu-id="a3872-119">Filtering Data (Where)</span></span>  

 <span data-ttu-id="a3872-120">Probablemente, la operación de consulta más común es aplicar un filtro en forma de expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="a3872-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="a3872-121">A continuación, la consulta devuelve solo los elementos para los que la expresión es verdadera.</span><span class="sxs-lookup"><span data-stu-id="a3872-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="a3872-122">Una `Where` cláusula se usa para realizar el filtrado.</span><span class="sxs-lookup"><span data-stu-id="a3872-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="a3872-123">El filtro especifica los elementos del origen de datos que se van a incluir en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="a3872-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="a3872-124">En el ejemplo siguiente, solo se incluyen los clientes que tienen una dirección en Londres.</span><span class="sxs-lookup"><span data-stu-id="a3872-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a3872-125">Puede utilizar operadores lógicos como `And` y `Or` para combinar expresiones de filtro en una `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="a3872-125">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="a3872-126">Por ejemplo, para devolver solo los clientes que son de Londres y cuyo nombre es Devon, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3872-126">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="a3872-127">Para devolver los clientes de Londres o París, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3872-127">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="a3872-128">Para obtener más información sobre cómo usar la `Where` cláusula en Visual Basic, vea [cláusula WHERE](../../../language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-128">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="a3872-129">Datos de ordenación (order by)</span><span class="sxs-lookup"><span data-stu-id="a3872-129">Ordering Data (Order By)</span></span>  

 <span data-ttu-id="a3872-130">A menudo resulta cómodo ordenar los datos devueltos en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="a3872-130">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="a3872-131">La `Order By` cláusula hará que los elementos de la secuencia devuelta se ordenen en un campo o campos especificados.</span><span class="sxs-lookup"><span data-stu-id="a3872-131">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="a3872-132">Por ejemplo, la siguiente consulta ordena los resultados en función de la `Name` propiedad.</span><span class="sxs-lookup"><span data-stu-id="a3872-132">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="a3872-133">Dado que `Name` es una cadena, los datos devueltos se ordenarán alfabéticamente, de la a A la Z.</span><span class="sxs-lookup"><span data-stu-id="a3872-133">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="a3872-134">Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="a3872-134">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="a3872-135">El valor predeterminado es `Ascending` cuando `Ascending` `Descending` no se especifica ni.</span><span class="sxs-lookup"><span data-stu-id="a3872-135">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="a3872-136">Para obtener más información sobre cómo usar la `Order By` cláusula en Visual Basic, consulte [cláusula order by](../../../language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-136">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="a3872-137">Seleccionar datos (Select)</span><span class="sxs-lookup"><span data-stu-id="a3872-137">Selecting Data (Select)</span></span>  

 <span data-ttu-id="a3872-138">La `Select` cláusula especifica la forma y el contenido de los elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="a3872-138">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="a3872-139">Por ejemplo, puede especificar si los resultados se componen de `Customer` objetos completos, una sola `Customer` propiedad, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún nuevo tipo de resultado basado en un cálculo.</span><span class="sxs-lookup"><span data-stu-id="a3872-139">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="a3872-140">Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.</span><span class="sxs-lookup"><span data-stu-id="a3872-140">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="a3872-141">Para recuperar una colección que consta de `Customer` objetos completos, seleccione la variable de rango en sí:</span><span class="sxs-lookup"><span data-stu-id="a3872-141">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a3872-142">Si una `Customer` instancia es un objeto grande que tiene muchos campos y todo lo que desea recuperar es el nombre, puede seleccionar `cust.Name` , tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3872-142">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="a3872-143">La inferencia de tipo local reconoce que esto cambia el tipo de resultado de una colección de `Customer` objetos a una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a3872-143">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="a3872-144">Para seleccionar varios campos del origen de datos, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="a3872-144">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="a3872-145">En la `Select` cláusula, especifique los campos que desea incluir en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a3872-145">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="a3872-146">El compilador definirá un tipo anónimo que tiene esos campos como sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="a3872-146">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="a3872-147">Para obtener más información, consulte [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).</span><span class="sxs-lookup"><span data-stu-id="a3872-147">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="a3872-148">Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no se puede hacer referencia al tipo por su nombre en ningún lugar del código.</span><span class="sxs-lookup"><span data-stu-id="a3872-148">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="a3872-149">El nombre designado por el compilador para el tipo contiene caracteres que no son válidos en el código de Visual Basic normal.</span><span class="sxs-lookup"><span data-stu-id="a3872-149">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="a3872-150">En el ejemplo siguiente, los elementos de la colección devueltos por la consulta en `londonCusts4` son instancias de un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="a3872-150">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="a3872-151">o bien</span><span class="sxs-lookup"><span data-stu-id="a3872-151">-or-</span></span>  
  
- <span data-ttu-id="a3872-152">Defina un tipo con nombre que contenga los campos concretos que desea incluir en el resultado y cree e inicialice instancias del tipo en la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="a3872-152">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="a3872-153">Utilice esta opción solo si tiene que utilizar resultados individuales fuera de la colección en la que se devuelven, o bien, si tiene que pasarlos como parámetros en las llamadas de método.</span><span class="sxs-lookup"><span data-stu-id="a3872-153">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="a3872-154">El tipo de `londonCusts5` en el ejemplo siguiente es IEnumerable (of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="a3872-154">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="a3872-155">Para obtener más información sobre cómo usar la `Select` cláusula en Visual Basic, consulte [cláusula SELECT](../../../language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-155">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="a3872-156">Combinar datos (combinación y combinación de grupo)</span><span class="sxs-lookup"><span data-stu-id="a3872-156">Joining Data (Join and Group Join)</span></span>  

 <span data-ttu-id="a3872-157">Puede combinar más de un origen de datos en la `From` cláusula de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="a3872-157">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="a3872-158">Por ejemplo, el código siguiente usa dos orígenes de datos y combina implícitamente las propiedades de ambos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a3872-158">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="a3872-159">La consulta selecciona estudiantes cuyos apellidos empiezan por una vocal.</span><span class="sxs-lookup"><span data-stu-id="a3872-159">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="a3872-160">Puede ejecutar este código con la lista de estudiantes creados en [Cómo: crear una lista de elementos](how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-160">You can run this code with the list of students created in [How to: Create a List of Items](how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="a3872-161">La `Join` palabra clave es equivalente a `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="a3872-161">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="a3872-162">Combina dos colecciones en función de los valores de clave coincidentes entre los elementos de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="a3872-162">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="a3872-163">La consulta devuelve todos o parte de los elementos de la colección que tienen valores de clave coincidentes.</span><span class="sxs-lookup"><span data-stu-id="a3872-163">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="a3872-164">Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.</span><span class="sxs-lookup"><span data-stu-id="a3872-164">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="a3872-165">`Group Join` combina colecciones en una sola colección jerárquica, al igual que `LEFT JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="a3872-165">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="a3872-166">Para obtener más información, vea cláusula [join](../../../language-reference/queries/join-clause.md) y Group [join](../../../language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-166">For more information, see [Join Clause](../../../language-reference/queries/join-clause.md) and [Group Join Clause](../../../language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="a3872-167">Agrupar datos (agrupar por)</span><span class="sxs-lookup"><span data-stu-id="a3872-167">Grouping Data (Group By)</span></span>  

 <span data-ttu-id="a3872-168">Puede Agregar una `Group By` cláusula para agrupar los elementos del resultado de una consulta de acuerdo con uno o varios campos de los elementos.</span><span class="sxs-lookup"><span data-stu-id="a3872-168">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="a3872-169">Por ejemplo, el código siguiente agrupa estudiantes por año de clase.</span><span class="sxs-lookup"><span data-stu-id="a3872-169">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="a3872-170">Si ejecuta este código mediante la lista de estudiantes creados en [Cómo: crear una lista de elementos](how-to-create-a-list-of-items.md), la salida de la `For Each` instrucción es:</span><span class="sxs-lookup"><span data-stu-id="a3872-170">If you run this code using the list of students created in [How to: Create a List of Items](how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="a3872-171">Año: Junior</span><span class="sxs-lookup"><span data-stu-id="a3872-171">Year: Junior</span></span>  
  
 <span data-ttu-id="a3872-172">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="a3872-172">Tucker, Michael</span></span>  
  
 <span data-ttu-id="a3872-173">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="a3872-173">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="a3872-174">Garcia, Debra</span><span class="sxs-lookup"><span data-stu-id="a3872-174">Garcia, Debra</span></span>  
  
 <span data-ttu-id="a3872-175">Tucker, lance</span><span class="sxs-lookup"><span data-stu-id="a3872-175">Tucker, Lance</span></span>  
  
 <span data-ttu-id="a3872-176">Año: Senior</span><span class="sxs-lookup"><span data-stu-id="a3872-176">Year: Senior</span></span>  
  
 <span data-ttu-id="a3872-177">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="a3872-177">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="a3872-178">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="a3872-178">Osada, Michiko</span></span>  
  
 <span data-ttu-id="a3872-179">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="a3872-179">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="a3872-180">Feng, Hanying</span><span class="sxs-lookup"><span data-stu-id="a3872-180">Feng, Hanying</span></span>  
  
 <span data-ttu-id="a3872-181">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="a3872-181">Adams, Terry</span></span>  
  
 <span data-ttu-id="a3872-182">Año: actualizado</span><span class="sxs-lookup"><span data-stu-id="a3872-182">Year: Freshman</span></span>  
  
 <span data-ttu-id="a3872-183">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="a3872-183">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="a3872-184">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="a3872-184">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="a3872-185">La variación que se muestra en el código siguiente ordena los años de la clase y, a continuación, ordena los estudiantes de cada año por Apellido.</span><span class="sxs-lookup"><span data-stu-id="a3872-185">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="a3872-186">Para obtener más información sobre `Group By` , vea [cláusula Group by](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-186">For more information about `Group By`, see [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3872-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3872-187">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="a3872-188">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3872-188">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="a3872-189">Consultas</span><span class="sxs-lookup"><span data-stu-id="a3872-189">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="a3872-190">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3872-190">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="a3872-191">LINQ</span><span class="sxs-lookup"><span data-stu-id="a3872-191">LINQ</span></span>](../../language-features/linq/index.md)
