---
title: Matrices
description: 'Obtenga información sobre cómo crear y usar matrices en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f95ca3274e098fda044973a48205cb591ec30b27
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855613"
---
# <a name="arrays"></a>Matrices

Las matrices son colecciones mutables de tamaño fijo y de base cero de elementos de datos consecutivos que son del mismo tipo.

> [!NOTE]
> La referencia de la API de docs.microsoft.com para F # no está completa. Si encuentra vínculos rotos, consulte la [documentación de la biblioteca básica de F #](https://fsharp.github.io/fsharp-core-docs/) .

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

El módulo de biblioteca [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) admite operaciones en matrices unidimensionales. Los módulos `Array2D` , `Array3D` y `Array4D` contienen funciones que admiten operaciones en matrices de dos, tres y cuatro dimensiones, respectivamente. Puede crear matrices de rango mayores que cuatro mediante <xref:System.Array?displayProperty=nameWithType> .

### <a name="simple-functions"></a>Funciones simples

[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc)Obtiene un elemento. [`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f)proporciona la longitud de una matriz. [`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)establece un elemento en un valor especificado. En el ejemplo de código siguiente se muestra el uso de estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

La salida es la siguiente.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Funciones que crean matrices

Varias funciones crean matrices sin necesidad de una matriz existente. [`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32)crea una nueva matriz que no contiene ningún elemento. [`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be)crea una matriz de un tamaño especificado y establece todos los elementos en los valores proporcionados. [`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665)crea una matriz, dada una dimensión y una función para generar los elementos. [`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)crea una matriz en la que todos los elementos se inicializan en el valor cero para el tipo de la matriz. En el código siguiente se muestran estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

La salida es la siguiente.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f)crea una nueva matriz que contiene los elementos que se copian de una matriz existente. Tenga en cuenta que la copia es una copia superficial, lo que significa que si el tipo de elemento es un tipo de referencia, solo se copia la referencia, no el objeto subyacente. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

La salida del código anterior es la siguiente:

```console
[|Test1; Test2; |]
[|; Test2; |]
```

La cadena `Test1` solo aparece en la primera matriz porque la operación de creación de un nuevo elemento sobrescribe la referencia en `firstArray` pero no afecta a la referencia original a una cadena vacía que todavía está presente en `secondArray` . La cadena `Test2` aparece en ambas matrices porque la `Insert` operación en el <xref:System.Text.StringBuilder?displayProperty=nameWithType> tipo afecta al objeto subyacente <xref:System.Text.StringBuilder?displayProperty=nameWithType> , al que se hace referencia en ambas matrices.

[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d)genera una nueva matriz a partir de un subintervalo de una matriz. Para especificar el subintervalo, proporcione el índice de inicio y la longitud. En el código siguiente se muestra cómo usar `Array.sub`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

La salida muestra que la submatriz comienza en el elemento 5 y contiene 10 elementos.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911)crea una nueva matriz combinando dos matrices existentes.

En el código siguiente se muestra **array. Append**.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

La salida del código anterior es la siguiente.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09)selecciona los elementos de una matriz que se van a incluir en una nueva matriz. En el siguiente código se muestra `Array.choose` . Tenga en cuenta que el tipo de elemento de la matriz no tiene que coincidir con el tipo del valor devuelto en el tipo de opción. En este ejemplo, el tipo de elemento es `int` y la opción es el resultado de una función polinómica, `elem*elem - 1` , como un número de punto flotante.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

La salida del código anterior es la siguiente.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a)ejecuta una función especificada en cada elemento de matriz de una matriz existente y, a continuación, recopila los elementos generados por la función y los combina en una nueva matriz. En el siguiente código se muestra `Array.collect` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

La salida del código anterior es la siguiente.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302)toma una secuencia de matrices y las combina en una sola matriz. En el siguiente código se muestra `Array.concat` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

La salida del código anterior es la siguiente.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede)toma una función de condición booleana y genera una nueva matriz que contiene solo los elementos de la matriz de entrada para los que la condición es true. En el siguiente código se muestra `Array.filter` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

La salida del código anterior es la siguiente.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709)genera una nueva matriz invirtiendo el orden de una matriz existente. En el siguiente código se muestra `Array.rev` .

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

Se puede crear una matriz multidimensional, pero no hay ninguna sintaxis para escribir un literal de matriz multidimensional. Use el operador [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) para crear una matriz a partir de una secuencia de secuencias de elementos de matriz. Las secuencias pueden ser literales de matriz o lista. Por ejemplo, el código siguiente crea una matriz bidimensional.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

También puede usar la función [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) para inicializar matrices de dos dimensiones, y las funciones similares están disponibles para las matrices de tres y cuatro dimensiones. Estas funciones toman una función que se utiliza para crear los elementos. Para crear una matriz bidimensional que contenga elementos establecidos en un valor inicial en lugar de especificar una función, use la [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) función, que también está disponible para matrices de hasta cuatro dimensiones. En el ejemplo de código siguiente se muestra primero cómo crear una matriz de matrices que contienen los elementos deseados y, a continuación, `Array2D.init` se usa para generar la matriz bidimensional deseada.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

La sintaxis de indización y segmentación de matrices es compatible con matrices hasta el rango 4. Cuando se especifica un índice en varias dimensiones, se usan comas para separar los índices, tal y como se muestra en el ejemplo de código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

El tipo de una matriz bidimensional se escribe como `<type>[,]` (por ejemplo, `int[,]` , `double[,]` ) y el tipo de una matriz tridimensional se escribe como `<type>[,,]` y así sucesivamente para las matrices de dimensiones superiores.

Solo hay disponible un subconjunto de las funciones disponibles para las matrices unidimensionales para las matrices multidimensionales. Para obtener más información, vea [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d) ,, [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d) [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d) y [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d) .

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

A partir de F # 3,1, puede descomponer una matriz multidimensional en submatrices de la misma dimensión o inferior. Por ejemplo, puede obtener un vector de una matriz especificando una sola fila o columna.

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
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a>Funciones booleanas en matrices

Las funciones [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) y [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) los elementos de prueba de una o dos matrices, respectivamente. Estas funciones toman una función de prueba y devuelven `true` si hay un elemento (o par de elementos para `Array.exists2` ) que cumple la condición.

En el código siguiente se muestra el uso de `Array.exists` y `Array.exists2` . En estos ejemplos, se crean nuevas funciones aplicando solo uno de los argumentos, en estos casos, el argumento de la función.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

La salida del código anterior es la siguiente.

```console
true
false
false
true
```

Del mismo modo, la función [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) prueba una matriz para determinar si todos los elementos satisfacen una condición booleana. La variación [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) hace lo mismo mediante el uso de una función booleana que implica elementos de dos matrices de igual longitud. En el código siguiente se muestra el uso de estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

La salida de estos ejemplos es la siguiente.

```console
false
true
true
false
```

### <a name="search-arrays"></a>Buscar matrices

[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33)toma una función booleana y devuelve el primer elemento para el que devuelve la función `true` , o produce una <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> si no se encuentra ningún elemento que cumpla la condición. [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f)es como `Array.find` , excepto que devuelve el índice del elemento en lugar del propio elemento.

En el código siguiente `Array.find` se usa y `Array.findIndex` para buscar un número que sea un cuadrado perfecto y un cubo perfecto.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

La salida es la siguiente.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9)es como `Array.find` , excepto que su resultado es un tipo de opción y devuelve `None` si no se encuentra ningún elemento. `Array.tryFind`se debe usar en lugar de `Array.find` cuando no se sabe si un elemento coincidente está en la matriz. Del mismo modo, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) es como, [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) excepto que el tipo de opción es el valor devuelto. Si no se encuentra ningún elemento, la opción es `None` .

En el código siguiente se muestra cómo usar `Array.tryFind`. Este código depende del código anterior.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

La salida es la siguiente.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) cuando necesite transformar un elemento además de encontrarlo. El resultado es el primer elemento para el que la función devuelve el elemento transformado como un valor de opción, o `None` si no se encuentra dicho elemento.

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

La [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) función devuelve el promedio de cada elemento de una matriz. Se limita a los tipos de elemento que admiten la división exacta mediante un entero, que incluye los tipos de punto flotante, pero no los tipos enteros. La [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) función devuelve el promedio de los resultados de llamar a una función en cada elemento. Para una matriz de tipo entero, puede usar `Array.averageBy` y hacer que la función convierta cada elemento en un tipo de punto flotante para el cálculo.

Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) o [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) para obtener el elemento máximo o mínimo, si el tipo de elemento lo admite. De forma similar, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) y [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) permiten que una función se ejecute en primer lugar, quizás para realizar la transformación en un tipo que admita la comparación.

[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2)agrega los elementos de una matriz y [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) llama a una función en cada elemento y agrega los resultados juntos.

Para ejecutar una función en cada elemento de una matriz sin almacenar los valores devueltos, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516) . Para una función que implique dos matrices de igual longitud, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc) . Si también necesita mantener una matriz de los resultados de la función, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) o [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c) , que opera en dos matrices a la vez.

Las variaciones [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) y [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) permiten que el índice del elemento esté implicado en el cálculo; lo mismo sucede con [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) y [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0) .

Las funciones,,,, [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09) [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c) [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d) [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9) [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0) y [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) ejecutan algoritmos que implican todos los elementos de una matriz. Del mismo modo, las variaciones [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) y [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) realizan cálculos en dos matrices.

Estas funciones para realizar cálculos se corresponden con las funciones del mismo nombre en el [módulo de lista](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788). Para obtener ejemplos de uso, vea [listas](lists.md).

### <a name="modify-arrays"></a>Modificar matrices

[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)establece un elemento en un valor especificado. [`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2)establece un intervalo de elementos de una matriz en un valor especificado. En el código siguiente se proporciona un ejemplo de `Array.fill` .

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

La salida es la siguiente.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Puede usar [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) para copiar una subsección de una matriz en otra matriz.

### <a name="convert-to-and-from-other-types"></a>Conversión a y desde otros tipos

[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b)crea una matriz a partir de una lista. [`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c)crea una matriz a partir de una secuencia. [`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786)y [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) se convierten en estos otros tipos de colección del tipo de matriz.

### <a name="sort-arrays"></a>Ordenar matrices

Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) para ordenar una matriz utilizando la función de comparación genérica. Utilice [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) para especificar una función que genera un valor, al que se hace referencia como *clave*, para ordenar mediante la función de comparación genérica de la clave. Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) si desea proporcionar una función de comparación personalizada. `Array.sort`, `Array.sortBy` y `Array.sortWith` devuelven la matriz ordenada como una nueva matriz. Las variaciones [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0) , [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f) y [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modifican la matriz existente en lugar de devolver una nueva.

### <a name="arrays-and-tuples"></a>Matrices y tuplas

Las funciones [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) y [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convierten matrices de pares de tupla en tuplas de matrices y viceversa. [`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d)y [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) son similares, salvo que funcionan con tuplas de tres elementos o tuplas de tres matrices.

## <a name="parallel-computations-on-arrays"></a>Cálculos paralelos en matrices

El módulo [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contiene funciones para realizar cálculos paralelos en matrices. Este módulo no está disponible en las aplicaciones que tienen como destino versiones de .NET Framework anteriores a la versión 4.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
