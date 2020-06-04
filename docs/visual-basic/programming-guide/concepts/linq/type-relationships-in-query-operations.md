---
title: Relaciones entre tipos en las operaciones de consulta LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 73a287541ddf115510bf6ab5c830eafac370cc3a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406734"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="5fe24-102">Relaciones entre tipos en operaciones de consulta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fe24-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="5fe24-103">Las variables que se usan en las operaciones de consulta de Language-Integrated Query (LINQ) están fuertemente tipadas y deben ser compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="5fe24-103">Variables used in Language-Integrated Query (LINQ) query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="5fe24-104">El establecimiento de tipos seguros se usa en el origen de datos, en la propia consulta y en la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="5fe24-105">En la ilustración siguiente se identifican los términos que se usan para describir una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="5fe24-105">The following illustration identifies terms used to describe a LINQ query.</span></span> <span data-ttu-id="5fe24-106">Para obtener más información acerca de las partes de una consulta, consulte [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5fe24-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](basic-query-operations.md).</span></span>

![Captura de pantalla que muestra una consulta de pseudocódigo con elementos resaltados.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="5fe24-108">El tipo de la variable de rango de la consulta debe ser compatible con el tipo de los elementos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe24-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="5fe24-109">El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5fe24-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="5fe24-110">Por último, el tipo de los elementos de la secuencia también debe ser compatible con el tipo de la variable de control de bucle que se usa en la `For Each` instrucción que ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="5fe24-111">Este fuertemente tipado facilita la identificación de los errores de tipo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5fe24-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="5fe24-112">Visual Basic hace que el establecimiento de tipos seguros sea conveniente implementando la inferencia de tipo local, también conocida como *tipos implícitos*.</span><span class="sxs-lookup"><span data-stu-id="5fe24-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="5fe24-113">Esa característica se usa en el ejemplo anterior y la verá utilizada en los ejemplos y la documentación de LINQ.</span><span class="sxs-lookup"><span data-stu-id="5fe24-113">That feature is used in the previous example, and you will see it used throughout the LINQ samples and documentation.</span></span> <span data-ttu-id="5fe24-114">En Visual Basic, la inferencia de tipo de variable local se realiza simplemente mediante una `Dim` instrucción sin una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5fe24-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="5fe24-115">En el ejemplo siguiente, `city` está fuertemente tipado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="5fe24-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="5fe24-116">La inferencia de tipo local solo funciona cuando `Option Infer` se establece en `On` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="5fe24-117">Para obtener más información, vea [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5fe24-117">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="5fe24-118">Sin embargo, incluso si utiliza la inferencia de tipo de variable local en una consulta, las mismas relaciones de tipo están presentes entre las variables en el origen de datos, la variable de consulta y el bucle de ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="5fe24-119">Resulta útil tener un conocimiento básico de estas relaciones de tipo al escribir consultas LINQ o al trabajar con los ejemplos y ejemplos de código de la documentación.</span><span class="sxs-lookup"><span data-stu-id="5fe24-119">It is useful to have a basic understanding of these type relationships when you are writing LINQ queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="5fe24-120">Es posible que tenga que especificar un tipo explícito para una variable de rango que no coincida con el tipo devuelto desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe24-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="5fe24-121">Puede especificar el tipo de la variable de rango mediante el uso de una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5fe24-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="5fe24-122">Sin embargo, esto genera un error si la conversión es una [conversión de restricción](../../language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` está establecida en `On` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-122">However, this results in an error if the conversion is a [narrowing conversion](../../language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="5fe24-123">Por lo tanto, se recomienda realizar la conversión en los valores recuperados del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe24-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="5fe24-124">Puede convertir los valores del origen de datos al tipo de variable de rango explícito mediante el <xref:System.Linq.Enumerable.Cast%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5fe24-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="5fe24-125">También puede convertir los valores seleccionados en la `Select` cláusula en un tipo explícito distinto del tipo de la variable de rango.</span><span class="sxs-lookup"><span data-stu-id="5fe24-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="5fe24-126">Estos puntos se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fe24-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="5fe24-127">Consultas que devuelven elementos completos de los datos de origen</span><span class="sxs-lookup"><span data-stu-id="5fe24-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="5fe24-128">En el ejemplo siguiente se muestra una operación de consulta LINQ que devuelve una secuencia de elementos seleccionados a partir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="5fe24-128">The following example shows a LINQ query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="5fe24-129">El origen, `names` , contiene una matriz de cadenas y el resultado de la consulta es una secuencia que contiene cadenas que comienzan por la letra M.</span><span class="sxs-lookup"><span data-stu-id="5fe24-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="5fe24-130">Esto es equivalente al código siguiente, pero es mucho más corto y más fácil de escribir.</span><span class="sxs-lookup"><span data-stu-id="5fe24-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="5fe24-131">La dependencia de la inferencia de tipo local en las consultas es el estilo preferido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe24-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="5fe24-132">Las siguientes relaciones existen en los dos ejemplos de código anteriores, tanto si los tipos se determinan implícita o explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5fe24-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="5fe24-133">El tipo de los elementos del origen de datos, `names` , es el tipo de la variable de rango, `name` , en la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="5fe24-134">El tipo del objeto que está seleccionado, `name` , determina el tipo de la variable de consulta, `mNames` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="5fe24-135">Esta `name` es una cadena, por lo que la variable de consulta es IEnumerable (of String) en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe24-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="5fe24-136">La consulta definida en `mNames` se ejecuta en el `For Each` bucle.</span><span class="sxs-lookup"><span data-stu-id="5fe24-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="5fe24-137">El bucle recorre en iteración el resultado de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="5fe24-138">Dado `mNames` que, cuando se ejecuta, devolverá una secuencia de cadenas, la variable de iteración del bucle, `nm` , también es una cadena.</span><span class="sxs-lookup"><span data-stu-id="5fe24-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="5fe24-139">Consultas que devuelven un campo de los elementos seleccionados</span><span class="sxs-lookup"><span data-stu-id="5fe24-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="5fe24-140">En el ejemplo siguiente se muestra una [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operación de consulta que devuelve una secuencia que contiene solo una parte de cada elemento seleccionado del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fe24-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="5fe24-141">La consulta toma una colección de `Customer` objetos como origen de datos y proyecta solo la `Name` propiedad en el resultado.</span><span class="sxs-lookup"><span data-stu-id="5fe24-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="5fe24-142">Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como salida.</span><span class="sxs-lookup"><span data-stu-id="5fe24-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

<span data-ttu-id="5fe24-143">Las relaciones entre las variables son similares a las del ejemplo más sencillo.</span><span class="sxs-lookup"><span data-stu-id="5fe24-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="5fe24-144">El tipo de los elementos del origen de datos, `customers` , es el tipo de la variable de rango, `cust` , en la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="5fe24-145">En este ejemplo, ese tipo es `Customer` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="5fe24-146">La `Select` instrucción devuelve la `Name` propiedad de cada `Customer` objeto en lugar de todo el objeto.</span><span class="sxs-lookup"><span data-stu-id="5fe24-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="5fe24-147">Dado `Name` que es una cadena, la variable de consulta, `custNames` , volverá a ser IEnumerable (de cadena), no de `Customer` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="5fe24-148">Dado que `custNames` representa una secuencia de cadenas, la `For Each` variable de iteración del bucle, `custName` , debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="5fe24-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="5fe24-149">Sin la inferencia de tipo local, el ejemplo anterior sería más complicado de escribir y comprender, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fe24-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="5fe24-150">Consultas que requieren tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="5fe24-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="5fe24-151">En el ejemplo siguiente se muestra una situación más compleja.</span><span class="sxs-lookup"><span data-stu-id="5fe24-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="5fe24-152">En el ejemplo anterior, no era conveniente especificar explícitamente los tipos para todas las variables.</span><span class="sxs-lookup"><span data-stu-id="5fe24-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="5fe24-153">En este ejemplo, es imposible.</span><span class="sxs-lookup"><span data-stu-id="5fe24-153">In this example, it is impossible.</span></span> <span data-ttu-id="5fe24-154">En lugar de seleccionar `Customer` elementos completos del origen de datos, o un único campo de cada elemento, la `Select` cláusula de esta consulta devuelve dos propiedades del objeto original `Customer` : `Name` y `City` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="5fe24-155">En respuesta a la `Select` cláusula, el compilador define un tipo anónimo que contiene esas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="5fe24-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="5fe24-156">El resultado de ejecutar `nameCityQuery` en el `For Each` bucle es una colección de instancias del nuevo tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="5fe24-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="5fe24-157">Dado que el tipo anónimo no tiene ningún nombre utilizable, no se puede especificar el tipo de `nameCityQuery` o `custInfo` explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5fe24-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="5fe24-158">Es decir, con un tipo anónimo, no hay ningún nombre de tipo para usar en lugar de `String` en `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="5fe24-159">Para obtener más información, vea [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="5fe24-159">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

<span data-ttu-id="5fe24-160">Aunque no es posible especificar tipos para todas las variables en el ejemplo anterior, las relaciones siguen siendo las mismas.</span><span class="sxs-lookup"><span data-stu-id="5fe24-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="5fe24-161">El tipo de los elementos del origen de datos es de nuevo el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="5fe24-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="5fe24-162">En este ejemplo, `cust` es una instancia de `Customer` .</span><span class="sxs-lookup"><span data-stu-id="5fe24-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="5fe24-163">Dado `Select` que la instrucción genera un tipo anónimo, la variable de consulta, `nameCityQuery` , debe escribirse implícitamente como un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="5fe24-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="5fe24-164">Un tipo anónimo no tiene ningún nombre utilizable y, por lo tanto, no se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5fe24-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="5fe24-165">El tipo de la variable de iteración en el `For Each` bucle es el tipo anónimo creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="5fe24-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="5fe24-166">Dado que el tipo no tiene ningún nombre utilizable, el tipo de la variable de iteración del bucle se debe determinar de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5fe24-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fe24-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fe24-167">See also</span></span>

- [<span data-ttu-id="5fe24-168">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fe24-168">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="5fe24-169">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="5fe24-169">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="5fe24-170">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="5fe24-170">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5fe24-171">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fe24-171">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5fe24-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="5fe24-172">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="5fe24-173">Consultas</span><span class="sxs-lookup"><span data-stu-id="5fe24-173">Queries</span></span>](../../../language-reference/queries/index.md)
