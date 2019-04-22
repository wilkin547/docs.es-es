---
title: Operaciones básicas de consulta (Visual Basic)
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
ms.openlocfilehash: ed5ed56366911c3676c4413711207ac0a8f85765
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826202"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="3aafc-102">Operaciones básicas de consulta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aafc-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="3aafc-103">Este tema proporciona una breve introducción a [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expresiones en Visual Basic y algunos de los tipos de operaciones que se realizan en una consulta.</span><span class="sxs-lookup"><span data-stu-id="3aafc-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="3aafc-104">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3aafc-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="3aafc-105">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aafc-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="3aafc-106">Consultas</span><span class="sxs-lookup"><span data-stu-id="3aafc-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="3aafc-107">Tutorial: Escribir consultas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aafc-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="3aafc-108">Especificar el origen de datos (desde)</span><span class="sxs-lookup"><span data-stu-id="3aafc-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="3aafc-109">En un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta, el primer paso es especificar el origen de datos que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="3aafc-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="3aafc-110">Por lo tanto, el `From` cláusula en una consulta siempre va primero.</span><span class="sxs-lookup"><span data-stu-id="3aafc-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="3aafc-111">Operadores de consulta seleccione y el resultado según el tipo del origen de la forma.</span><span class="sxs-lookup"><span data-stu-id="3aafc-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="3aafc-112">El `From` cláusula especifica el origen de datos, `customers`y un *variable de rango*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="3aafc-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="3aafc-113">La variable de rango es como una variable de iteración del bucle, excepto que en una expresión de consulta, se produce ninguna iteración real.</span><span class="sxs-lookup"><span data-stu-id="3aafc-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="3aafc-114">Cuando se ejecuta la consulta, a menudo mediante el uso de un `For Each` bucle, la variable de rango actúa como una referencia a cada elemento sucesivo de `customers`.</span><span class="sxs-lookup"><span data-stu-id="3aafc-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="3aafc-115">Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="3aafc-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="3aafc-116">Para obtener ejemplos de las consultas escritas con y sin tipos explícitos, consulte [relaciones entre tipos en operaciones de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="3aafc-117">Para obtener más información sobre cómo usar el `From` cláusula en Visual Basic, vea [la cláusula From](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="3aafc-118">Filtrar datos (dónde)</span><span class="sxs-lookup"><span data-stu-id="3aafc-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="3aafc-119">Probablemente la operación de consulta más común es aplicar un filtro en forma de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="3aafc-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="3aafc-120">La consulta, a continuación, devuelve sólo los elementos para que la expresión es verdadera.</span><span class="sxs-lookup"><span data-stu-id="3aafc-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="3aafc-121">Un `Where` cláusula se usa para realizar el filtrado.</span><span class="sxs-lookup"><span data-stu-id="3aafc-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="3aafc-122">El filtro especifica qué elementos del origen de datos para incluir en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="3aafc-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="3aafc-123">En el ejemplo siguiente, se incluyen sólo aquellos clientes que tienen una dirección en Londres.</span><span class="sxs-lookup"><span data-stu-id="3aafc-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="3aafc-124">Puede usar operadores lógicos, como `And` y `Or` para combinar expresiones de filtro en un `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="3aafc-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="3aafc-125">Por ejemplo, para devolver a sólo los clientes de Londres y cuyo nombre es Devon, utilice el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="3aafc-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="3aafc-126">Para devolver a los clientes de Londres o París, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3aafc-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="3aafc-127">Para obtener más información sobre cómo usar el `Where` cláusula en Visual Basic, vea [cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="3aafc-128">Ordenar datos (Order By)</span><span class="sxs-lookup"><span data-stu-id="3aafc-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="3aafc-129">A menudo es conveniente ordenar los datos devueltos en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="3aafc-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="3aafc-130">El `Order By` cláusula hará que los elementos de la secuencia devuelta se ordene en un campo o campos especificados.</span><span class="sxs-lookup"><span data-stu-id="3aafc-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="3aafc-131">Por ejemplo, la siguiente consulta ordena los resultados según el `Name` propiedad.</span><span class="sxs-lookup"><span data-stu-id="3aafc-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="3aafc-132">Dado que `Name` es una cadena, los datos devueltos se ordenarán alfabéticamente, de la A Z.</span><span class="sxs-lookup"><span data-stu-id="3aafc-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="3aafc-133">Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="3aafc-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="3aafc-134">El valor predeterminado es `Ascending` cuando ninguna de ellas `Ascending` ni `Descending` se especifica.</span><span class="sxs-lookup"><span data-stu-id="3aafc-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="3aafc-135">Para obtener más información sobre cómo usar el `Order By` cláusula en Visual Basic, vea [cláusula Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="3aafc-136">Selección de datos (Select)</span><span class="sxs-lookup"><span data-stu-id="3aafc-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="3aafc-137">El `Select` cláusula especifica la forma y el contenido de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="3aafc-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="3aafc-138">Por ejemplo, puede especificar si sus resultados estarán compuestos de complete `Customer` objetos, solo uno `Customer` propiedad, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún tipo de resultado nuevo basado en un cálculo.</span><span class="sxs-lookup"><span data-stu-id="3aafc-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="3aafc-139">Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.</span><span class="sxs-lookup"><span data-stu-id="3aafc-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="3aafc-140">Para recuperar una colección formada por completo `Customer` objetos, seleccione la variable de rango:</span><span class="sxs-lookup"><span data-stu-id="3aafc-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="3aafc-141">Si un `Customer` instancia es un objeto grande que tiene muchos campos, y todo lo que van a recuperar es el nombre, puede seleccionar `cust.Name`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3aafc-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="3aafc-142">Inferencia de tipos local reconoce que se cambia el tipo de resultado de una colección de `Customer` objetos a una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3aafc-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="3aafc-143">Para seleccionar varios campos del origen de datos, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="3aafc-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="3aafc-144">En el `Select` cláusula, especificar los campos que van a incluir en el resultado.</span><span class="sxs-lookup"><span data-stu-id="3aafc-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="3aafc-145">El compilador definirá un tipo anónimo que tiene esos campos como sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="3aafc-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="3aafc-146">Para más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="3aafc-147">Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no se puede consultar el tipo por su nombre en otro lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="3aafc-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="3aafc-148">El nombre designado por el compilador para el tipo contiene caracteres que no son válidos en el código de Visual Basic normal.</span><span class="sxs-lookup"><span data-stu-id="3aafc-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="3aafc-149">En el ejemplo siguiente, los elementos de la colección devuelta por la consulta en `londonCusts4` son instancias de un tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="3aafc-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="3aafc-150">-o bien-</span><span class="sxs-lookup"><span data-stu-id="3aafc-150">-or-</span></span>  
  
-   <span data-ttu-id="3aafc-151">Definir un tipo con nombre que contenga los campos concretos que desea incluir en el resultado y crear e inicializar instancias del tipo en el `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="3aafc-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="3aafc-152">Use esta opción solo si tiene que utilizar fuera de la colección en el que se devuelven los resultados individuales, o si tiene que pasarlos como parámetros en las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="3aafc-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="3aafc-153">El tipo de `londonCusts5` en el ejemplo siguiente es IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="3aafc-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="3aafc-154">Para obtener más información sobre cómo usar el `Select` cláusula en Visual Basic, vea [cláusula Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="3aafc-155">Datos de combinación (Join y Group Join)</span><span class="sxs-lookup"><span data-stu-id="3aafc-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="3aafc-156">Puede combinar más de un origen de datos en el `From` cláusula de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="3aafc-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="3aafc-157">Por ejemplo, el código siguiente utiliza dos orígenes de datos y combina implícitamente las propiedades de ambos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="3aafc-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="3aafc-158">La consulta selecciona los alumnos cuyos apellidos comiencen con una vocal.</span><span class="sxs-lookup"><span data-stu-id="3aafc-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  <span data-ttu-id="3aafc-159">Puede ejecutar este código con la lista de estudiantes creada en [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="3aafc-160">El `Join` palabra clave es equivalente a un `INNER JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="3aafc-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="3aafc-161">Combina dos colecciones basadas en valores de clave coincidentes entre los elementos de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="3aafc-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="3aafc-162">La consulta devuelve todo o parte de los elementos de colección que tienen valores de clave coincidentes.</span><span class="sxs-lookup"><span data-stu-id="3aafc-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="3aafc-163">Por ejemplo, el siguiente código duplica la acción de la combinación implícita anterior.</span><span class="sxs-lookup"><span data-stu-id="3aafc-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="3aafc-164">`Group Join` combina las colecciones en una sola colección jerárquica, igual que un `LEFT JOIN` en SQL.</span><span class="sxs-lookup"><span data-stu-id="3aafc-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="3aafc-165">Para obtener más información, consulte [cláusula Join](../../../../visual-basic/language-reference/queries/join-clause.md) y [Group (cláusula) Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="3aafc-166">Agrupar datos (Agrupar por)</span><span class="sxs-lookup"><span data-stu-id="3aafc-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="3aafc-167">Puede agregar un `Group By` cláusula para agrupar los elementos de un resultado de consulta según uno o más campos de los elementos.</span><span class="sxs-lookup"><span data-stu-id="3aafc-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="3aafc-168">Por ejemplo, el siguiente código agrupa los estudiantes por año de la clase.</span><span class="sxs-lookup"><span data-stu-id="3aafc-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="3aafc-169">Si ejecuta este código utilizando la lista de estudiantes creada en [Cómo: Crear una lista de elementos de](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), el resultado de la `For Each` instrucción es:</span><span class="sxs-lookup"><span data-stu-id="3aafc-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="3aafc-170">Año: "Junior"</span><span class="sxs-lookup"><span data-stu-id="3aafc-170">Year: Junior</span></span>  
  
 <span data-ttu-id="3aafc-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="3aafc-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="3aafc-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="3aafc-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="3aafc-173">García, Gustavo</span><span class="sxs-lookup"><span data-stu-id="3aafc-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="3aafc-174">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="3aafc-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="3aafc-175">Año: Senior</span><span class="sxs-lookup"><span data-stu-id="3aafc-175">Year: Senior</span></span>  
  
 <span data-ttu-id="3aafc-176">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="3aafc-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="3aafc-177">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="3aafc-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="3aafc-178">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="3aafc-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="3aafc-179">Feng, Hanying</span><span class="sxs-lookup"><span data-stu-id="3aafc-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="3aafc-180">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="3aafc-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="3aafc-181">Año: Freshman</span><span class="sxs-lookup"><span data-stu-id="3aafc-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="3aafc-182">Maldonado Guerra, Sven</span><span class="sxs-lookup"><span data-stu-id="3aafc-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="3aafc-183">Garcia, Cesar</span><span class="sxs-lookup"><span data-stu-id="3aafc-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="3aafc-184">La variación que se muestra en el código siguiente ordena los años de clase y, a continuación, ordena los estudiantes de cada año por apellido.</span><span class="sxs-lookup"><span data-stu-id="3aafc-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="3aafc-185">Para obtener más información acerca de `Group By`, consulte [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3aafc-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aafc-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aafc-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="3aafc-187">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aafc-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="3aafc-188">Consultas</span><span class="sxs-lookup"><span data-stu-id="3aafc-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3aafc-189">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aafc-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="3aafc-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="3aafc-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
