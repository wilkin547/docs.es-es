---
description: 'Más información sobre: tipos de relaciones en operaciones de consulta (Visual Basic)'
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
ms.openlocfilehash: b6a59308e76afdcf1aaf7084904b9925cd5bef14
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428225"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="25b18-103">Relaciones entre tipos en operaciones de consulta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25b18-103">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="25b18-104">Las variables usadas en las operaciones de consulta de Language-Integrated (LINQ) están fuertemente tipadas y deben ser compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="25b18-104">Variables used in Language-Integrated Query (LINQ) query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="25b18-105">El establecimiento de tipos seguros se usa en el origen de datos, en la propia consulta y en la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-105">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="25b18-106">En la ilustración siguiente se identifican los términos que se usan para describir una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="25b18-106">The following illustration identifies terms used to describe a LINQ query.</span></span> <span data-ttu-id="25b18-107">Para obtener más información acerca de las partes de una consulta, consulte [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="25b18-107">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](basic-query-operations.md).</span></span>

![Captura de pantalla que muestra una consulta de pseudocódigo con elementos resaltados.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="25b18-109">El tipo de la variable de rango de la consulta debe ser compatible con el tipo de los elementos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b18-109">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="25b18-110">El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="25b18-110">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="25b18-111">Por último, el tipo de los elementos de la secuencia también debe ser compatible con el tipo de la variable de control de bucle que se usa en la `For Each` instrucción que ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-111">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="25b18-112">Este fuertemente tipado facilita la identificación de los errores de tipo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="25b18-112">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="25b18-113">Visual Basic hace que el establecimiento de tipos seguros sea conveniente implementando la inferencia de tipo local, también conocida como *tipos implícitos*.</span><span class="sxs-lookup"><span data-stu-id="25b18-113">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="25b18-114">Esa característica se usa en el ejemplo anterior y la verá utilizada en los ejemplos y la documentación de LINQ.</span><span class="sxs-lookup"><span data-stu-id="25b18-114">That feature is used in the previous example, and you will see it used throughout the LINQ samples and documentation.</span></span> <span data-ttu-id="25b18-115">En Visual Basic, la inferencia de tipo de variable local se realiza simplemente mediante una `Dim` instrucción sin una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="25b18-115">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="25b18-116">En el ejemplo siguiente, `city` está fuertemente tipado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="25b18-116">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="25b18-117">La inferencia de tipo local solo funciona cuando `Option Infer` se establece en `On` .</span><span class="sxs-lookup"><span data-stu-id="25b18-117">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="25b18-118">Para obtener más información, vea [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25b18-118">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="25b18-119">Sin embargo, incluso si utiliza la inferencia de tipo de variable local en una consulta, las mismas relaciones de tipo están presentes entre las variables en el origen de datos, la variable de consulta y el bucle de ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-119">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="25b18-120">Resulta útil tener un conocimiento básico de estas relaciones de tipo al escribir consultas LINQ o al trabajar con los ejemplos y ejemplos de código de la documentación.</span><span class="sxs-lookup"><span data-stu-id="25b18-120">It is useful to have a basic understanding of these type relationships when you are writing LINQ queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="25b18-121">Es posible que tenga que especificar un tipo explícito para una variable de rango que no coincida con el tipo devuelto desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b18-121">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="25b18-122">Puede especificar el tipo de la variable de rango mediante el uso de una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="25b18-122">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="25b18-123">Sin embargo, esto genera un error si la conversión es una [conversión de restricción](../../language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` está establecida en `On` .</span><span class="sxs-lookup"><span data-stu-id="25b18-123">However, this results in an error if the conversion is a [narrowing conversion](../../language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="25b18-124">Por lo tanto, se recomienda realizar la conversión en los valores recuperados del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b18-124">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="25b18-125">Puede convertir los valores del origen de datos al tipo de variable de rango explícito mediante el <xref:System.Linq.Enumerable.Cast%2A> método.</span><span class="sxs-lookup"><span data-stu-id="25b18-125">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="25b18-126">También puede convertir los valores seleccionados en la `Select` cláusula en un tipo explícito distinto del tipo de la variable de rango.</span><span class="sxs-lookup"><span data-stu-id="25b18-126">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="25b18-127">Estos puntos se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="25b18-127">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="25b18-128">Consultas que devuelven elementos completos de los datos de origen</span><span class="sxs-lookup"><span data-stu-id="25b18-128">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="25b18-129">En el ejemplo siguiente se muestra una operación de consulta LINQ que devuelve una secuencia de elementos seleccionados a partir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="25b18-129">The following example shows a LINQ query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="25b18-130">El origen, `names` , contiene una matriz de cadenas y el resultado de la consulta es una secuencia que contiene cadenas que comienzan por la letra M.</span><span class="sxs-lookup"><span data-stu-id="25b18-130">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="25b18-131">Esto es equivalente al código siguiente, pero es mucho más corto y más fácil de escribir.</span><span class="sxs-lookup"><span data-stu-id="25b18-131">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="25b18-132">La dependencia de la inferencia de tipo local en las consultas es el estilo preferido en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="25b18-132">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="25b18-133">Las siguientes relaciones existen en los dos ejemplos de código anteriores, tanto si los tipos se determinan implícita o explícitamente.</span><span class="sxs-lookup"><span data-stu-id="25b18-133">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="25b18-134">El tipo de los elementos del origen de datos, `names` , es el tipo de la variable de rango, `name` , en la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-134">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="25b18-135">El tipo del objeto que está seleccionado, `name` , determina el tipo de la variable de consulta, `mNames` .</span><span class="sxs-lookup"><span data-stu-id="25b18-135">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="25b18-136">Esta `name` es una cadena, por lo que la variable de consulta es IEnumerable (of String) en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="25b18-136">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="25b18-137">La consulta definida en `mNames` se ejecuta en el `For Each` bucle.</span><span class="sxs-lookup"><span data-stu-id="25b18-137">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="25b18-138">El bucle recorre en iteración el resultado de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-138">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="25b18-139">Dado `mNames` que, cuando se ejecuta, devolverá una secuencia de cadenas, la variable de iteración del bucle, `nm` , también es una cadena.</span><span class="sxs-lookup"><span data-stu-id="25b18-139">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="25b18-140">Consultas que devuelven un campo de los elementos seleccionados</span><span class="sxs-lookup"><span data-stu-id="25b18-140">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="25b18-141">En el ejemplo siguiente se muestra una [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operación de consulta que devuelve una secuencia que contiene solo una parte de cada elemento seleccionado del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b18-141">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="25b18-142">La consulta toma una colección de `Customer` objetos como origen de datos y proyecta solo la `Name` propiedad en el resultado.</span><span class="sxs-lookup"><span data-stu-id="25b18-142">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="25b18-143">Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como salida.</span><span class="sxs-lookup"><span data-stu-id="25b18-143">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

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

<span data-ttu-id="25b18-144">Las relaciones entre las variables son similares a las del ejemplo más sencillo.</span><span class="sxs-lookup"><span data-stu-id="25b18-144">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="25b18-145">El tipo de los elementos del origen de datos, `customers` , es el tipo de la variable de rango, `cust` , en la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-145">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="25b18-146">En este ejemplo, ese tipo es `Customer` .</span><span class="sxs-lookup"><span data-stu-id="25b18-146">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="25b18-147">La `Select` instrucción devuelve la `Name` propiedad de cada `Customer` objeto en lugar de todo el objeto.</span><span class="sxs-lookup"><span data-stu-id="25b18-147">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="25b18-148">Dado `Name` que es una cadena, la variable de consulta, `custNames` , volverá a ser IEnumerable (de cadena), no de `Customer` .</span><span class="sxs-lookup"><span data-stu-id="25b18-148">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="25b18-149">Dado que `custNames` representa una secuencia de cadenas, la `For Each` variable de iteración del bucle, `custName` , debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="25b18-149">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="25b18-150">Sin la inferencia de tipo local, el ejemplo anterior sería más complicado de escribir y comprender, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="25b18-150">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

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

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="25b18-151">Consultas que requieren tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="25b18-151">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="25b18-152">En el ejemplo siguiente se muestra una situación más compleja.</span><span class="sxs-lookup"><span data-stu-id="25b18-152">The following example shows a more complex situation.</span></span> <span data-ttu-id="25b18-153">En el ejemplo anterior, no era conveniente especificar explícitamente los tipos para todas las variables.</span><span class="sxs-lookup"><span data-stu-id="25b18-153">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="25b18-154">En este ejemplo, es imposible.</span><span class="sxs-lookup"><span data-stu-id="25b18-154">In this example, it is impossible.</span></span> <span data-ttu-id="25b18-155">En lugar de seleccionar `Customer` elementos completos del origen de datos, o un único campo de cada elemento, la `Select` cláusula de esta consulta devuelve dos propiedades del objeto original `Customer` : `Name` y `City` .</span><span class="sxs-lookup"><span data-stu-id="25b18-155">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="25b18-156">En respuesta a la `Select` cláusula, el compilador define un tipo anónimo que contiene esas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="25b18-156">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="25b18-157">El resultado de ejecutar `nameCityQuery` en el `For Each` bucle es una colección de instancias del nuevo tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="25b18-157">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="25b18-158">Dado que el tipo anónimo no tiene ningún nombre utilizable, no se puede especificar el tipo de `nameCityQuery` o `custInfo` explícitamente.</span><span class="sxs-lookup"><span data-stu-id="25b18-158">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="25b18-159">Es decir, con un tipo anónimo, no hay ningún nombre de tipo para usar en lugar de `String` en `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="25b18-159">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="25b18-160">Para obtener más información, consulte [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).</span><span class="sxs-lookup"><span data-stu-id="25b18-160">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

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

<span data-ttu-id="25b18-161">Aunque no es posible especificar tipos para todas las variables en el ejemplo anterior, las relaciones siguen siendo las mismas.</span><span class="sxs-lookup"><span data-stu-id="25b18-161">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="25b18-162">El tipo de los elementos del origen de datos es de nuevo el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="25b18-162">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="25b18-163">En este ejemplo, `cust` es una instancia de `Customer` .</span><span class="sxs-lookup"><span data-stu-id="25b18-163">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="25b18-164">Dado `Select` que la instrucción genera un tipo anónimo, la variable de consulta, `nameCityQuery` , debe escribirse implícitamente como un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="25b18-164">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="25b18-165">Un tipo anónimo no tiene ningún nombre utilizable y, por lo tanto, no se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="25b18-165">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="25b18-166">El tipo de la variable de iteración en el `For Each` bucle es el tipo anónimo creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="25b18-166">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="25b18-167">Dado que el tipo no tiene ningún nombre utilizable, el tipo de la variable de iteración del bucle se debe determinar de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="25b18-167">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="25b18-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25b18-168">See also</span></span>

- [<span data-ttu-id="25b18-169">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25b18-169">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="25b18-170">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="25b18-170">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="25b18-171">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="25b18-171">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="25b18-172">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25b18-172">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="25b18-173">LINQ</span><span class="sxs-lookup"><span data-stu-id="25b18-173">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="25b18-174">Consultas</span><span class="sxs-lookup"><span data-stu-id="25b18-174">Queries</span></span>](../../../language-reference/queries/index.md)
