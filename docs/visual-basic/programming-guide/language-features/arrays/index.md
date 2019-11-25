---
title: Matrices
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 9dfe7814b00b4d060fa4ab9aa594faa948217d8d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351863"
---
# <a name="arrays-in-visual-basic"></a>Matrices en Visual Basic

An array is a set of values, which are termed *elements*, that are logically related to each other. For example, an array may consist of the number of students in each grade in a grammar school; each element of the array is the number of students in a single grade. Similarly, an array may consist of a student's grades for a class; each element of the array is a single grade.

It is possible individual variables to store each of our data items. For example, if our application analyzes student grades, we can use a separate variable for each student's grade, such as `englishGrade1`, `englishGrade2`, etc. This approach has three major limitations:

- We have to know at design time exactly how many grades we have to handle.
- Handling large numbers of grades quickly becomes unwieldy. This in turn makes an application much more likely to have serious bugs.
- It is difficult to maintain. Each new grade that we add requires that the application be modified, recompiled, and redeployed.

By using an array, you can refer to these related values by the same name, and use a number that’s called an *index* or *subscript* to identify an individual element based on its position in the array. The indexes of an array range from 0 to one less than the total number of elements in the array. When you use Visual Basic syntax to define the size of an array, you specify its highest index, not the total number of elements in the array. You can work with the array as a unit, and the ability to iterate its elements frees you from needing to know exactly how many elements it contains at design time.

Veamos algunos ejemplos rápidos antes de la explicación:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

' Declare a single-dimension array and set its 4 values.
Dim numbers = New Integer() {1, 2, 4, 8}

' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)

' Redefine the size of an existing array and reset the values.
ReDim numbers(15)

' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double

' Declare a 4 x 3 multidimensional array and set array element values.
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}

' Declare a jagged array
Dim sales()() As Double = New Double(11)() {}
```

## <a name="array-elements-in-a-simple-array"></a>Array elements in a simple array

Let's create an array named `students` to store the number of students in each grade in a grammar school. Los índices de los elementos van del 0 al 6. Using this array is simpler than declaring seven variables.

The following illustration shows the `students` array. Para cada elemento de la matriz:

- El índice del elemento representa el curso (el índice 0 representa la guardería).

- El valor que se encuentra en el elemento representa el número de estudiantes en dicho curso.

![Diagram showing an array of the numbers of students](./media/index/students-array-elements.gif)

The following example contains the Visual Basic code that creates and uses the array:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

The example does three things:

- It declares a `students` array with seven elements. The number `6` in the array declaration indicates the last index in the array; it is one less than the number of elements in the array.
- It assigns values to each element in the array. Array elements are accessed by using the array name and including the index of the individual element in parentheses.
- It lists each value of the array. The example uses a [`For`](../../../language-reference/statements/for-next-statement.md) statement to access each element of the array by its index number.

The `students` array in the preceding example is a one-dimensional array because it uses one index. An array that uses more than one index or subscript is called *multidimensional*. For more information, see the rest of this article and [Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md).

## <a name="creating-an-array"></a>Creating an array

You can define the size of an array in several ways:

- You can specify the size when the array is declared:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- You can use a `New` clause to supply the size of an array when it’s created:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

If you have an existing array, you can redefine its size by using the [`ReDim`](../../../language-reference/statements/redim-statement.md) statement. You can specify that the `ReDim` statement keep the values that are in the array, or you can specify that it create an empty array. El ejemplo siguiente muestra los diferentes usos de la instrucción `ReDim` para modificar el tamaño de una matriz existente.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

For more information, see the [ReDim Statement](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Storing values in an array

Puede tener acceso a cada ubicación en una matriz mediante un índice del tipo `Integer`. Puede almacenar y recuperar los valores en una matriz haciendo referencia a cada ubicación de la matriz usando su índice entre paréntesis. Indexes for multidimensional arrays are separated by commas (,). Necesita un índice para cada dimensión de la matriz.

The following example shows some statements that store and retrieve values in arrays.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Populating an array with array literals

By using an array literal, you can populate an array with an initial set of values at the same time that you create it. Un literal de matriz consta de una lista de valores separados por comas entre llaves (`{}`).

Cuando se crea una matriz mediante un literal de matriz, puede proporcionar el tipo de matriz o usar la inferencia de tipo para determinar el tipo de matriz. The following example shows both options.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

When you use type inference, the type of the array is determined by the *dominant type* in the list of literal values. The dominant type is the type to which all other types in the array can widen. Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que todos los demás tipos de la matriz se pueden restringir. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. Por ejemplo, si la lista de valores que se proporciona al literal de matriz contiene valores de tipo `Integer`, `Long`y `Double`, la matriz resultante es de tipo `Double`. Because `Integer` and `Long` widen only to `Double`, `Double` is the dominant type. Para obtener más información, consulta [Widening and Narrowing Conversions](../../language-features/data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> You can use type inference only for arrays that are defined as local variables in a type member. If an explicit type definition is absent, arrays defined with array literals at the class level are of type `Object[]`. For more information, see [Local type inference](../variables/local-type-inference.md).

Note that the previous example defines `values` as an array of type `Double` even though all the array literals are of type `Integer`. You can create this array because the values in the array literal can widen to `Double` values.

You can also create and populate a multidimensional array by using *nested array literals*. Nested array literals must have a number of dimensions that’s consistent with the resulting array. The following example creates a two-dimensional array of integers by using nested array literals.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

When using nested array literals to create and populate an array, an error occurs if the number of elements in the nested array literals don't match. An error also occurs if you explicitly declare the array variable to have a different number of dimensions than the array literals.

Just as you can for one-dimensional arrays, you can rely on type inference when creating a multidimensional array with nested array literals. The inferred type is the dominant type for all the values in all the array literals for all nesting level. The following example creates a two-dimensional array of type `Double[,]` from values that are of type `Integer` and `Double`.

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Para consultar ejemplos adicionales, vea [Cómo: Inicializar una variable de matriz en Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Iterating through an array

When you iterate through an array, you access each element in the array from the lowest index to the highest or from the highest to the lowest. Typically, use either the [For...Next Statement](../../../language-reference/statements/for-next-statement.md) or the [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md) to iterate through the elements of an array. When you don't know the upper bounds of the array, you can call the <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> method to get the highest value of the index. Although lowest index value is almost always 0, you can call the <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> method to get the lowest value of the index.

The following example iterates through a one-dimensional array by using the [`For...Next`](../../../language-reference/statements/for-next-statement.md) statement.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

The following example iterates through a multidimensional array by using a [`For...Next`](../../../language-reference/statements/for-next-statement.md) statement. El método <xref:System.Array.GetUpperBound%2A> tiene un parámetro que especifica la dimensión. `GetUpperBound(0)` returns the highest index of the first dimension, and `GetUpperBound(1)` returns the highest index of the second dimension.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

The following example uses a [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md)to iterate through a one-dimensional array and a two-dimensional array.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Array size

El tamaño de una matriz es el producto de las longitudes de todas sus dimensiones. Representa el número total de elementos contenidos actualmente en la matriz.  For example, the following example declares a 2-dimensional array with four elements in each dimension. As the output from the example shows, the array's size is 16 (or (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> This discussion of array size does not apply to jagged arrays. For information on jagged arrays and determining the size of a jagged array, see the [Jagged arrays](#jagged-arrays) section.

Puede encontrar el tamaño de una matriz mediante la propiedad <xref:System.Array.Length%2A?displayProperty=nameWithType>. You can find the length of each dimension of a multidimensional array by using the <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.

You can resize an array variable by assigning a new array object to it or by using the [`ReDim` Statement](../../../language-reference/statements/redim-statement.md) statement. The following example uses the `ReDim` statement to change a 100-element array to a 51-element array.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Hay varios aspectos que se deben tener en cuenta cuando se trabaja con el tamaño de una matriz.

|||
|---|---|
|Longitud de la dimensión|The index of each dimension is 0-based, which means it ranges from 0 to its upper bound. Therefore, the length of a given dimension is one greater than the declared upper bound of that dimension.|
|Límites de longitud|The length of every dimension of an array is limited to the maximum value of the `Integer` data type, which is <xref:System.Int32.MaxValue?displayProperty=nameWithType> or (2 ^ 31) - 1. Sin embargo, el tamaño total de una matriz también está limitado por la memoria disponible en el sistema. If you attempt to initialize an array that exceeds the amount of available memory, the runtime throws an <xref:System.OutOfMemoryException>.|
|Tamaño y tamaño de elemento|El tamaño de la matriz es independiente del tipo de datos de sus elementos. The size always represents the total number of elements, not the number of bytes that they consume in memory.|
|Consumo de memoria|No es seguro dar nada por supuesto en lo que respecta al modo de almacenar una matriz en la memoria. El almacenamiento varía en función de las plataformas de diferentes anchos de datos, por lo que la misma matriz puede utilizar más memoria en un sistema de 64 bits que en un sistema de 32 bits. Según la configuración del sistema cuando inicializa una matriz, Common Language Runtime (CLR) puede asignar el almacenamiento para empaquetar los elementos tan juntos como sea posible o para alinearlos todos en los límites naturales del hardware. Asimismo, una matriz requiere una sobrecarga de almacenamiento para obtener su información de control y esta sobrecarga aumenta con cada dimensión agregada.|

## <a name="the-array-type"></a>The array type

Every array has a data type, which differs from the data type of its elements. No existe ningún tipo de datos para todas las matrices. En su lugar, el tipo de datos de una matriz lo determina el número de dimensiones, o *rango*, de la matriz y el tipo de datos de los elementos de la matriz. Two array variables are of the same data type only when they have the same rank and their elements have the same data type. The lengths of the dimensions of an array do not influence the array data type.

Cada matriz hereda la clase <xref:System.Array?displayProperty=nameWithType> y puede declarar una variable del tipo `Array`, pero no puede crear una matriz del tipo `Array`. For example, although the following code declares the `arr` variable to be of type `Array` and calls the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method to instantiate the array, the array's type proves to be Object[].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

Además, la [Instrucción ReDim](../../../language-reference/statements/redim-statement.md) no puede funcionar en una variable declarada de tipo `Array`. For these reasons, and for type safety, it is advisable to declare every array as a specific type.

Puede averiguar el tipo de datos de una matriz o de sus elementos de varias maneras.

- You can call the <xref:System.Object.GetType%2A> method on the variable to get a <xref:System.Type> object that represents the run-time type of the variable. El objeto <xref:System.Type> contiene amplia información en sus propiedades y métodos.
- You can pass the variable to the <xref:Microsoft.VisualBasic.Information.TypeName%2A> function to get a `String` with the name of run-time type.

The following example calls the both the `GetType` method and the `TypeName` function to determine the type of an array. The array type is `Byte(,)`. Note that the <xref:System.Type.BaseType%2A?displayProperty=nameWithType> property also indicates that the base type of the byte array is the <xref:System.Array> class.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Arrays as return values and parameters

Para devolver una matriz desde un procedimiento `Function`, especifique el tipo de datos de matriz y el número de dimensiones como tipo de valor devuelto de la [Instrucción Function](../../../language-reference/statements/function-statement.md). Dentro de la función, declare una variable de matriz local con el mismo tipo de datos y número de dimensiones. En la [Instrucción Return](../../../language-reference/statements/return-statement.md), incluya la variable de matriz local sin paréntesis.

Para especificar una matriz como parámetro para un procedimiento `Sub` o `Function` , defina el parámetro como una matriz con un tipo de datos especificado y el número de dimensiones. In the call to the procedure, pass an array variable with the same data type and number of dimensions.

In the following example, the `GetNumbers` function returns an `Integer()`, a one-dimensional array of type `Integer`. El procedimiento `ShowNumbers` acepta un argumento `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

In the following example, the `GetNumbersMultiDim` function returns an `Integer(,)`, a two-dimensional array of type `Integer`.  El procedimiento `ShowNumbersMultiDim` acepta un argumento `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Matrices escalonadas

A veces la estructura de datos de la aplicación es bidimensional pero no rectangular. For example, you might use an array to store data about the high temperature of each day of the month. The first dimension of the array represents the month, but the second dimension represents the number of days, and the number of days in a month is not uniform. A *jagged array*, which is also called an *array of arrays*, is designed for such scenarios. A jagged array is an array whose elements are also arrays. Una matriz escalonada y cada elemento de una matriz escalonada pueden tener una o más dimensiones.

The following example uses an array of months, each element of which is an array of days. The example uses a jagged array because different months have different numbers of days.  The example shows how to create a jagged array, assign values to it, and retrieve and display its values.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

The previous example assigns values to the jagged array on an element-by-element basis by using a `For...Next` loop. You can also assign values to the elements of a jagged array by using nested array literals. However, the attempt to use nested array literals (for example, `Dim valuesjagged = {{1, 2}, {2, 3, 4}}`) generates compiler error [BC30568](../../../,,/../misc/bc30568.md). To correct the error, enclose the inner array literals in parentheses. The parentheses force the array literal expression to be evaluated, and the resulting values are used with the outer array literal, as the following example shows.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

A jagged array is a one-dimensional array whose elements contain arrays. Therefore, the <xref:System.Array.Length%2A?displayProperty=nameWithType> property and the `Array.GetLength(0)` method return the number of elements in the one-dimensional array, and `Array.GetLength(1)` throws an <xref:System.IndexOutOfRangeException> because a jagged array is not multidimensional. You determine the number of elements in each subarray by retrieving the value of each subarray's <xref:System.Array.Length%2A?displayProperty=nameWithType> property. The following example illustrates how to determine the number of elements in a jagged array.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Zero-length arrays

Visual Basic differentiates between a uninitialized array (an array whose value is `Nothing`) and a *zero-length array* or empty array (an array that has no elements.) An uninitialized array is one that has not been dimensioned or had any values assigned to it. Por ejemplo:

```vb
Dim arr() As String
```

A zero-length array is declared with a dimension of -1. Por ejemplo:

```vb
Dim arrZ(-1) As String
```

Puede que tenga que crear una matriz de longitud cero en las circunstancias siguientes:

- Without risking a <xref:System.NullReferenceException> exception, your code must access members of the <xref:System.Array> class, such as <xref:System.Array.Length%2A> or <xref:System.Array.Rank%2A>, or call a Visual Basic function such as <xref:Microsoft.VisualBasic.Information.UBound%2A>.

- You want to keep your code simple by not having to check for `Nothing` as a special case.

- El código interactúa con una interfaz de programación de aplicaciones (API) que requiere pasar una matriz de longitud cero a uno o más procedimientos o que devuelve una matriz de longitud cero desde uno o más procedimientos.

## <a name="splitting-an-array"></a>Splitting an array

In some cases, you may need to split a single array into multiple arrays. This involves identifying the point or points at which the array is to be split, and then spitting the array into two or more separate arrays.

> [!NOTE]
> This section does not discuss splitting a single string into a string array based on some delimiter. For information on splitting a string, see the <xref:System.String.Split%2A?displayProperty=nameWithType> method.

The most common criteria for splitting an array are:

- Número de elementos de la matriz. For example, you might want to split an array of more than a specified number of elements into a number of approximately equal parts. For this purpose, you can use the value returned by either the <xref:System.Array.Length%2A?displayProperty=nameWithType> or <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.

- The value of an element, which serves as a delimiter that indicates where the array should be split. You can search for a specific value by calling the <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> and <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> methods.

Once you've determined the index or indexes at which the array should be split, you can then create the individual arrays by calling the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.

The following example splits an array into two arrays of approximately equal size. (If the total number of array elements is odd, the first array has one more element than the second.)

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

The following example splits a string array into two arrays based on the presence of an element whose value is "zzz", which serves as the array delimiter. The new arrays do not include the element that contains the delimiter.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Joining arrays

You can also combine a number of arrays into a single larger array. To do this, you also use the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.

> [!NOTE]
> This section does not discuss joining a string array into a single string. For information on joining a string array, see the <xref:System.String.Join%2A?displayProperty=nameWithType> method.

Before copying the elements of each array into the new array, you must first ensure that you have initialized the array so that it is large enough to accommodate the new array. Hay dos maneras de hacerlo:

- Use the [`ReDim Preserve`](../../../language-reference/statements/redim-statement.md) statement to dynamically expand the array before adding new elements to it. This is the easiest technique, but it can result in performance degradation and excessive memory consumption when you are copying large arrays.
- Calculate the total number of elements needed for the new large array, then add the elements of each source array to it.

The following example uses the second approach to add four arrays with ten elements each to a single array.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Since in this case the source arrays are all small, we can also dynamically expand the array as we add the elements of each new array to it. En el siguiente ejemplo se realiza esto.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Collections as an alternative to arrays

Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados. Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. Unlike arrays, which require that you explicitly change the size of an array with the [`ReDim` Statement](../../../language-reference/statements/redim-statement.md), collections grow and shrink dynamically as the needs of an application change.

When you use `ReDim` to redimension an array, Visual Basic creates a new array and releases the previous one. Esto requiere tiempo de ejecución. Therefore, if the number of items you are working with changes frequently, or you cannot predict the maximum number of items you need, you'll usually obtain better performance by using a collection.

Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.

Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>. Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella.

Para más información sobre las colecciones, vea [Colecciones](../../concepts/collections.md).

## <a name="related-topics"></a>Temas relacionados

|Término|de esquema JSON|
|----------|----------------|
|[Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md)|Explica el rango y las dimensiones de las matrices.|
|[Cómo: Inicializar una variable de matriz en Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md)|Describe cómo se llenan las matrices con valores iniciales.|
|[Cómo: Ordenar una matriz en Visual Basic](../../language-features/arrays/how-to-sort-an-array.md)|Muestra cómo ordenar alfabéticamente los elementos de una matriz.|
|[Asignar una matriz a otra](../../language-features/arrays/how-to-assign-one-array-to-another-array.md)|Describe las reglas y los pasos para asignar una matriz a otra variable de matriz.|
|[Solución de problemas de matrices](../../language-features/arrays/troubleshooting-arrays.md)|Describe algunos problemas comunes que surgen al trabajar con matrices.|

## <a name="see-also"></a>Vea también

- <xref:System.Array?displayProperty=nameWithType>
- [Dim (instrucción)](../../../language-reference/statements/dim-statement.md)
- [ReDim (instrucción)](../../../language-reference/statements/redim-statement.md)
