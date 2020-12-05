---
title: Matrices
description: 'Obtenga información sobre cómo crear y usar matrices en el lenguaje de programación F #.'
ms.date: 08/13/2020
ms.openlocfilehash: 96b0d7eaf10d5afcd9a647681d5c2ef2d2fba335
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739756"
---
# <a name="arrays"></a>Matrices

Las matrices son colecciones mutables de tamaño fijo y de base cero de elementos de datos consecutivos que son del mismo tipo.

## <a name="create-arrays"></a>Crear matrices

Puede crear matrices de varias maneras. Puede crear una matriz pequeña enumerando valores consecutivos entre `[|` y `|]` y separados por punto y coma, tal como se muestra en los ejemplos siguientes.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

También puede colocar cada elemento en una línea independiente, en cuyo caso el separador de punto y coma es opcional.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

El tipo de los elementos de la matriz se deduce de los literales usados y debe ser coherente. El código siguiente produce un error porque 1,0 es float y 2 y 3 son enteros.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

También puede utilizar expresiones de secuencia para crear matrices. A continuación se encuentra un ejemplo que crea una matriz de cuadrados de enteros de 1 a 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

Para crear una matriz en la que todos los elementos se inicializan en cero, use `Array.zeroCreate` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a>Elementos de acceso

Puede tener acceso a los elementos de la matriz mediante un operador punto ( `.` ) y corchetes ( `[` y `]` ).

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

Los índices de matriz comienzan en 0.

También puede tener acceso a los elementos de la matriz mediante la notación de segmentación, que permite especificar un subintervalo de la matriz. A continuación se muestran ejemplos de notación de segmentación.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

Cuando se usa la notación de segmentos, se crea una nueva copia de la matriz.

## <a name="array-types-and-modules"></a>Tipos de matriz y módulos

El tipo de todas las matrices de F # es el tipo de .NET Framework <xref:System.Array?displayProperty=nameWithType> . Por lo tanto, las matrices de F # admiten toda la funcionalidad disponible en <xref:System.Array?displayProperty=nameWithType> .

El [ `Array` módulo](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) admite operaciones en matrices unidimensionales. Los módulos `Array2D` , `Array3D` y `Array4D` contienen funciones que admiten operaciones en matrices de dos, tres y cuatro dimensiones, respectivamente. Puede crear matrices de rango mayores que cuatro mediante <xref:System.Array?displayProperty=nameWithType> .

### <a name="simple-functions"></a>Funciones simples

[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) Obtiene un elemento. [`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) proporciona la longitud de una matriz. [`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) establece un elemento en un valor especificado. En el ejemplo de código siguiente se muestra el uso de estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

La salida es la siguiente.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Funciones que crean matrices

Varias funciones crean matrices sin necesidad de una matriz existente. [`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) crea una nueva matriz que no contiene ningún elemento. [`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) crea una matriz de un tamaño especificado y establece todos los elementos en los valores proporcionados. [`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) crea una matriz, dada una dimensión y una función para generar los elementos. [`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) crea una matriz en la que todos los elementos se inicializan en el valor cero para el tipo de la matriz. En el código siguiente se muestran estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

La salida es la siguiente.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) crea una nueva matriz que contiene los elementos que se copian de una matriz existente. Tenga en cuenta que la copia es una copia superficial, lo que significa que si el tipo de elemento es un tipo de referencia, solo se copia la referencia, no el objeto subyacente. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

La salida del código anterior es la siguiente:

```console
[|Test1; Test2; |]
[|; Test2; |]
```

La cadena `Test1` solo aparece en la primera matriz porque la operación de creación de un nuevo elemento sobrescribe la referencia en `firstArray` pero no afecta a la referencia original a una cadena vacía que todavía está presente en `secondArray` . La cadena `Test2` aparece en ambas matrices porque la `Insert` operación en el <xref:System.Text.StringBuilder?displayProperty=nameWithType> tipo afecta al objeto subyacente <xref:System.Text.StringBuilder?displayProperty=nameWithType> , al que se hace referencia en ambas matrices.

[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) genera una nueva matriz a partir de un subintervalo de una matriz. Para especificar el subintervalo, proporcione el índice de inicio y la longitud. En el código siguiente se muestra cómo usar `Array.sub`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

La salida muestra que la submatriz comienza en el elemento 5 y contiene 10 elementos.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) crea una nueva matriz combinando dos matrices existentes.

En el código siguiente se muestra **array. Append**.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

La salida del código anterior es la siguiente.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) selecciona los elementos de una matriz que se van a incluir en una nueva matriz. En el siguiente código se muestra `Array.choose` . Tenga en cuenta que el tipo de elemento de la matriz no tiene que coincidir con el tipo del valor devuelto en el tipo de opción. En este ejemplo, el tipo de elemento es `int` y la opción es el resultado de una función polinómica, `elem*elem - 1` , como un número de punto flotante.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

La salida del código anterior es la siguiente.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) ejecuta una función especificada en cada elemento de matriz de una matriz existente y, a continuación, recopila los elementos generados por la función y los combina en una nueva matriz. En el siguiente código se muestra `Array.collect` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

La salida del código anterior es la siguiente.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) toma una secuencia de matrices y las combina en una sola matriz. En el siguiente código se muestra `Array.concat` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

La salida del código anterior es la siguiente.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) toma una función de condición booleana y genera una nueva matriz que contiene solo los elementos de la matriz de entrada para los que la condición es true. En el siguiente código se muestra `Array.filter` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

La salida del código anterior es la siguiente.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) genera una nueva matriz invirtiendo el orden de una matriz existente. En el siguiente código se muestra `Array.rev` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

La salida del código anterior es la siguiente.

```console
"Hello world!"
```

Puede combinar fácilmente funciones en el módulo de matriz que transforman matrices mediante el operador de canalización ( `|>` ), tal como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

El resultado es

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Matrices multidimensionales

Se puede crear una matriz multidimensional, pero no hay ninguna sintaxis para escribir un literal de matriz multidimensional. Use el operador [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) para crear una matriz a partir de una secuencia de secuencias de elementos de matriz. Las secuencias pueden ser literales de matriz o lista. Por ejemplo, el código siguiente crea una matriz bidimensional.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

También puede usar la función [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) para inicializar matrices de dos dimensiones, y las funciones similares están disponibles para las matrices de tres y cuatro dimensiones. Estas funciones toman una función que se utiliza para crear los elementos. Para crear una matriz bidimensional que contenga elementos establecidos en un valor inicial en lugar de especificar una función, use la [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) función, que también está disponible para matrices de hasta cuatro dimensiones. En el ejemplo de código siguiente se muestra primero cómo crear una matriz de matrices que contienen los elementos deseados y, a continuación, `Array2D.init` se usa para generar la matriz bidimensional deseada.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

La sintaxis de indización y segmentación de matrices es compatible con matrices hasta el rango 4. Cuando se especifica un índice en varias dimensiones, se usan comas para separar los índices, tal y como se muestra en el ejemplo de código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

El tipo de una matriz bidimensional se escribe como `<type>[,]` (por ejemplo, `int[,]` , `double[,]` ) y el tipo de una matriz tridimensional se escribe como `<type>[,,]` y así sucesivamente para las matrices de dimensiones superiores.

Solo hay disponible un subconjunto de las funciones disponibles para las matrices unidimensionales para las matrices multidimensionales.

### <a name="array-slicing-and-multidimensional-arrays"></a>Segmentación de matrices y matrices multidimensionales

En una matriz bidimensional (matriz), puede extraer una submatriz especificando los intervalos y usando un carácter comodín ( `*` ) para especificar filas o columnas completas.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

Puede descomponer una matriz multidimensional en submatrices de la misma dimensión o en una inferior. Por ejemplo, puede obtener un vector de una matriz especificando una sola fila o columna.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

Puede utilizar esta sintaxis de segmentación para los tipos que implementan los operadores de acceso a elementos y los métodos sobrecargados `GetSlice` . Por ejemplo, el código siguiente crea un tipo de matriz que contiene la matriz 2D de F #, implementa una propiedad Item para proporcionar compatibilidad con la indización de matrices e implementa tres versiones de `GetSlice` . Si puede usar este código como plantilla para los tipos de matriz, puede usar todas las operaciones de segmentación que se describen en esta sección.

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn $"{submatrix}"

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn $"{firstCol}"
```

### <a name="boolean-functions-on-arrays"></a>Funciones booleanas en matrices

Las funciones [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) y [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) los elementos de prueba de una o dos matrices, respectivamente. Estas funciones toman una función de prueba y devuelven `true` si hay un elemento (o par de elementos para `Array.exists2` ) que cumple la condición.

En el código siguiente se muestra el uso de `Array.exists` y `Array.exists2` . En estos ejemplos, se crean nuevas funciones aplicando solo uno de los argumentos, en estos casos, el argumento de la función.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

La salida del código anterior es la siguiente.

```console
true
false
false
true
```

Del mismo modo, la función [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) prueba una matriz para determinar si todos los elementos satisfacen una condición booleana. La variación [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) hace lo mismo mediante el uso de una función booleana que implica elementos de dos matrices de igual longitud. En el código siguiente se muestra el uso de estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

La salida de estos ejemplos es la siguiente.

```console
false
true
true
false
```

### <a name="search-arrays"></a>Buscar matrices

[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) toma una función booleana y devuelve el primer elemento para el que devuelve la función `true` , o produce una <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> si no se encuentra ningún elemento que cumpla la condición. [`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) es como `Array.find` , excepto que devuelve el índice del elemento en lugar del propio elemento.

En el código siguiente `Array.find` se usa y `Array.findIndex` para buscar un número que sea un cuadrado perfecto y un cubo perfecto.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

La salida es la siguiente.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) es como `Array.find` , excepto que su resultado es un tipo de opción y devuelve `None` si no se encuentra ningún elemento. `Array.tryFind` se debe usar en lugar de `Array.find` cuando no se sabe si un elemento coincidente está en la matriz. Del mismo modo, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) es como, `Array.findIndex` excepto que el tipo de opción es el valor devuelto. Si no se encuentra ningún elemento, la opción es `None` .

En el código siguiente se muestra cómo usar `Array.tryFind`. Este código depende del código anterior.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

La salida es la siguiente.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

Use [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) cuando necesite transformar un elemento además de encontrarlo. El resultado es el primer elemento para el que la función devuelve el elemento transformado como un valor de opción, o `None` si no se encuentra dicho elemento.

En el código siguiente se muestra el uso de `Array.tryPick`. En este caso, en lugar de una expresión lambda, se definen varias funciones auxiliares locales para simplificar el código.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

La salida es la siguiente.

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a>Realizar cálculos en matrices

La [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) función devuelve el promedio de cada elemento de una matriz. Se limita a los tipos de elemento que admiten la división exacta mediante un entero, que incluye los tipos de punto flotante, pero no los tipos enteros. La [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) función devuelve el promedio de los resultados de llamar a una función en cada elemento. Para una matriz de tipo entero, puede usar `Array.averageBy` y hacer que la función convierta cada elemento en un tipo de punto flotante para el cálculo.

Use [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) o [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) para obtener el elemento máximo o mínimo, si el tipo de elemento lo admite. De forma similar, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) y [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) permiten que una función se ejecute en primer lugar, quizás para realizar la transformación en un tipo que admita la comparación.

[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) agrega los elementos de una matriz y [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) llama a una función en cada elemento y agrega los resultados juntos.

Para ejecutar una función en cada elemento de una matriz sin almacenar los valores devueltos, use [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) . Para una función que implique dos matrices de igual longitud, use [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) . Si también necesita mantener una matriz de los resultados de la función, use [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) o [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) , que opera en dos matrices a la vez.

Las variaciones [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) y [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) permiten que el índice del elemento esté implicado en el cálculo; lo mismo sucede con [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) y [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2) .

Las funciones,,,, [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) y [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) ejecutan algoritmos que implican todos los elementos de una matriz. Del mismo modo, las variaciones [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) y [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) realizan cálculos en dos matrices.

Estas funciones para realizar cálculos se corresponden con las funciones del mismo nombre en el [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Para obtener ejemplos de uso, vea [listas](lists.md).

### <a name="modify-arrays"></a>Modificar matrices

[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) establece un elemento en un valor especificado. [`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) establece un intervalo de elementos de una matriz en un valor especificado. En el código siguiente se proporciona un ejemplo de `Array.fill` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

La salida es la siguiente.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Puede usar [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) para copiar una subsección de una matriz en otra matriz.

### <a name="convert-to-and-from-other-types"></a>Conversión a y desde otros tipos

[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) crea una matriz a partir de una lista. [`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) crea una matriz a partir de una secuencia. [`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) y [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) se convierten en estos otros tipos de colección del tipo de matriz.

### <a name="sort-arrays"></a>Ordenar matrices

Use [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) para ordenar una matriz utilizando la función de comparación genérica. Utilice [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) para especificar una función que genera un valor, al que se hace referencia como *clave*, para ordenar mediante la función de comparación genérica de la clave. Use [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) si desea proporcionar una función de comparación personalizada. `Array.sort`, `Array.sortBy` y `Array.sortWith` devuelven la matriz ordenada como una nueva matriz. Las variaciones [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace) , [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) y [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) modifican la matriz existente en lugar de devolver una nueva.

### <a name="arrays-and-tuples"></a>Matrices y tuplas

Las funciones [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) y [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) convierten matrices de pares de tupla en tuplas de matrices y viceversa. [`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) y [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) son similares, salvo que funcionan con tuplas de tres elementos o tuplas de tres matrices.

## <a name="parallel-computations-on-arrays"></a>Cálculos paralelos en matrices

El módulo [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) contiene funciones para realizar cálculos paralelos en matrices. Este módulo no está disponible en las aplicaciones que tienen como destino versiones de .NET Framework anteriores a la versión 4.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
