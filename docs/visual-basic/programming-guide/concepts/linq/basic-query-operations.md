---
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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266383"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="56451-102">Operaciones básicas de consulta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56451-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="56451-103">En este tema se proporciona una breve introducción a las expresiones de Language-Integrated Query (LINQ) en Visual Basic y a algunos de los tipos típicos de operaciones que se realizan en una consulta.</span><span class="sxs-lookup"><span data-stu-id="56451-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="56451-104">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="56451-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="56451-105">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56451-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="56451-106">Consultas</span><span class="sxs-lookup"><span data-stu-id="56451-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="56451-107">Tutorial: Escribir consultas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56451-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="56451-108">Especificación del origen de datos (desde)</span><span class="sxs-lookup"><span data-stu-id="56451-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="56451-109">En una consulta LINQ, el primer paso es especificar el origen de datos que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="56451-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="56451-110">Por lo `From` tanto, la cláusula de una consulta siempre es lo primero.</span><span class="sxs-lookup"><span data-stu-id="56451-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="56451-111">Los operadores de consulta seleccionan y dan forma al resultado en función del tipo de origen.</span><span class="sxs-lookup"><span data-stu-id="56451-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="56451-112">La `From` cláusula especifica el `customers`origen de datos `cust`, y una variable de *rango*, .</span><span class="sxs-lookup"><span data-stu-id="56451-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="56451-113">La variable de rango es como una variable de iteración de bucle, excepto que en una expresión de consulta, no se produce ninguna iteración real.</span><span class="sxs-lookup"><span data-stu-id="56451-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="56451-114">Cuando se ejecuta la consulta, `For Each` a menudo mediante un bucle, la `customers`variable de rango sirve como referencia a cada elemento sucesivo en .</span><span class="sxs-lookup"><span data-stu-id="56451-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="56451-115">Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="56451-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="56451-116">Para obtener ejemplos de consultas escritas con y sin escritura explícita, vea Relaciones de tipo en operaciones de [consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="56451-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="56451-117">Para obtener más información `From` acerca de cómo usar la cláusula en Visual Basic, vea [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="56451-118">Filtrado de datos (dónde)</span><span class="sxs-lookup"><span data-stu-id="56451-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="56451-119">Probablemente la operación de consulta más común es aplicar un filtro en forma de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="56451-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="56451-120">A continuación, la consulta devuelve solo los elementos para los que la expresión es true.</span><span class="sxs-lookup"><span data-stu-id="56451-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="56451-121">Se `Where` utiliza una cláusula para realizar el filtrado.</span><span class="sxs-lookup"><span data-stu-id="56451-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="56451-122">El filtro especifica qué elementos del origen de datos se incluirán en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="56451-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="56451-123">En el ejemplo siguiente, solo se incluyen los clientes que tienen una dirección en Londres.</span><span class="sxs-lookup"><span data-stu-id="56451-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="56451-124">Puede utilizar operadores `And` lógicos como y `Or` `Where` combinar expresiones de filtro en una cláusula.</span><span class="sxs-lookup"><span data-stu-id="56451-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="56451-125">Por ejemplo, para devolver solo aquellos clientes que son de Londres y cuyo nombre es Devon, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="56451-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="56451-126">Para devolver clientes de Londres o París, utilice el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="56451-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="56451-127">Para obtener más información `Where` acerca de cómo usar la cláusula en Visual Basic, vea [Cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="56451-128">Datos de pedido (pedido por)</span><span class="sxs-lookup"><span data-stu-id="56451-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="56451-129">A menudo es conveniente ordenar los datos devueltos en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="56451-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="56451-130">La `Order By` cláusula hará que los elementos de la secuencia devuelta se ordenen en un campo o campos especificados.</span><span class="sxs-lookup"><span data-stu-id="56451-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="56451-131">Por ejemplo, la siguiente consulta ordena `Name` los resultados en función de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="56451-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="56451-132">Dado `Name` que es una cadena, los datos devueltos se ordenarán alfabéticamente, de la A a la Z.</span><span class="sxs-lookup"><span data-stu-id="56451-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="56451-133">Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="56451-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="56451-134">El valor `Ascending` predeterminado `Ascending` `Descending` es cuando no se especifica ni se especifica.</span><span class="sxs-lookup"><span data-stu-id="56451-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="56451-135">Para obtener más información `Order By` acerca de cómo usar la cláusula en Visual Basic, vea [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="56451-136">Selección de datos (Seleccionar)</span><span class="sxs-lookup"><span data-stu-id="56451-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="56451-137">La `Select` cláusula especifica el formulario y el contenido de los elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="56451-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="56451-138">Por ejemplo, puede especificar si los `Customer` resultados consistirán `Customer` en objetos completos, una sola propiedad, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún nuevo tipo de resultado basado en un cálculo.</span><span class="sxs-lookup"><span data-stu-id="56451-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="56451-139">Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.</span><span class="sxs-lookup"><span data-stu-id="56451-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="56451-140">Para recuperar una colección `Customer` que consta de objetos completos, seleccione la propia variable de rango:</span><span class="sxs-lookup"><span data-stu-id="56451-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="56451-141">Si `Customer` una instancia es un objeto grande que tiene muchos campos y todo `cust.Name`lo que desea recuperar es el nombre, puede seleccionar , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="56451-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="56451-142">La inferencia de tipo local reconoce que esto `Customer` cambia el tipo de resultado de una colección de objetos a una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="56451-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="56451-143">Para seleccionar varios campos del origen de datos, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="56451-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="56451-144">En `Select` la cláusula, especifique los campos que desea incluir en el resultado.</span><span class="sxs-lookup"><span data-stu-id="56451-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="56451-145">El compilador definirá un tipo anónimo que tiene esos campos como sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="56451-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="56451-146">Para obtener más información, consulte [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).</span><span class="sxs-lookup"><span data-stu-id="56451-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="56451-147">Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no puede hacer referencia al tipo por nombre en otro lugar del código.</span><span class="sxs-lookup"><span data-stu-id="56451-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="56451-148">El nombre designado por el compilador para el tipo contiene caracteres que no son válidos en el código normal de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56451-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="56451-149">En el ejemplo siguiente, los elementos de la `londonCusts4` colección devueltos por la consulta son instancias de un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="56451-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="56451-150">O bien</span><span class="sxs-lookup"><span data-stu-id="56451-150">-or-</span></span>  
  
- <span data-ttu-id="56451-151">Defina un tipo con nombre que contenga los campos concretos que desea incluir en `Select` el resultado y cree e inicialice instancias del tipo en la cláusula.</span><span class="sxs-lookup"><span data-stu-id="56451-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="56451-152">Utilice esta opción solo si tiene que usar resultados individuales fuera de la colección en la que se devuelven, o si tiene que pasarlos como parámetros en las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="56451-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="56451-153">El tipo `londonCusts5` de en el ejemplo siguiente es IEnumerable(Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="56451-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="56451-154">Para obtener más información `Select` acerca de cómo usar la cláusula en Visual Basic, vea [Seleccionar cláusula](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="56451-155">Unirdatos (unirse y unirse a grupos)</span><span class="sxs-lookup"><span data-stu-id="56451-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="56451-156">Puede combinar más de un `From` origen de datos en la cláusula de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="56451-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="56451-157">Por ejemplo, el código siguiente utiliza dos orígenes de datos y combina implícitamente propiedades de ambos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="56451-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="56451-158">La consulta selecciona los alumnos cuyos apellidos comienzan con una vocal.</span><span class="sxs-lookup"><span data-stu-id="56451-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="56451-159">Puede ejecutar este código con la lista de alumnos creados en [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="56451-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="56451-160">La `Join` palabra clave `INNER JOIN` es equivalente a un en SQL.</span><span class="sxs-lookup"><span data-stu-id="56451-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="56451-161">Combina dos colecciones basadas en valores de clave coincidentes entre los elementos de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="56451-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="56451-162">La consulta devuelve todos o parte de los elementos de colección que tienen valores de clave coincidentes.</span><span class="sxs-lookup"><span data-stu-id="56451-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="56451-163">Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.</span><span class="sxs-lookup"><span data-stu-id="56451-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="56451-164">`Group Join`combina colecciones en una única colección jerárquica, al igual que una `LEFT JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="56451-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="56451-165">Para obtener más información, consulte Cláusula de [unión](../../../../visual-basic/language-reference/queries/join-clause.md) y Cláusula de [unión de grupo](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="56451-166">Agrupar datos (Agrupar por)</span><span class="sxs-lookup"><span data-stu-id="56451-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="56451-167">Puede agregar `Group By` una cláusula para agrupar los elementos de un resultado de consulta según uno o varios campos de los elementos.</span><span class="sxs-lookup"><span data-stu-id="56451-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="56451-168">Por ejemplo, el código siguiente agrupa a los alumnos por año de clase.</span><span class="sxs-lookup"><span data-stu-id="56451-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="56451-169">Si ejecuta este código utilizando la lista de alumnos creados en `For Each` [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), la salida de la instrucción es:</span><span class="sxs-lookup"><span data-stu-id="56451-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="56451-170">Año: Junior</span><span class="sxs-lookup"><span data-stu-id="56451-170">Year: Junior</span></span>  
  
 <span data-ttu-id="56451-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="56451-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="56451-172">García, Hugo</span><span class="sxs-lookup"><span data-stu-id="56451-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="56451-173">García, Debra</span><span class="sxs-lookup"><span data-stu-id="56451-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="56451-174">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="56451-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="56451-175">Año: Senior</span><span class="sxs-lookup"><span data-stu-id="56451-175">Year: Senior</span></span>  
  
 <span data-ttu-id="56451-176">Omelchenko</span><span class="sxs-lookup"><span data-stu-id="56451-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="56451-177">Osada</span><span class="sxs-lookup"><span data-stu-id="56451-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="56451-178">Fakhouri</span><span class="sxs-lookup"><span data-stu-id="56451-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="56451-179">Feng</span><span class="sxs-lookup"><span data-stu-id="56451-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="56451-180">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="56451-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="56451-181">Año: Primer año</span><span class="sxs-lookup"><span data-stu-id="56451-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="56451-182">Mortensen</span><span class="sxs-lookup"><span data-stu-id="56451-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="56451-183">García, Cesar</span><span class="sxs-lookup"><span data-stu-id="56451-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="56451-184">La variación que se muestra en el código siguiente ordena los años de clase y, a continuación, ordena a los alumnos dentro de cada año por apellido.</span><span class="sxs-lookup"><span data-stu-id="56451-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="56451-185">Para obtener `Group By`más información acerca de , consulte [Agrupar por cláusula](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56451-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56451-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56451-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="56451-187">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56451-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="56451-188">Consultas</span><span class="sxs-lookup"><span data-stu-id="56451-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="56451-189">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56451-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="56451-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="56451-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
