---
title: Secuencias
description: 'Obtenga información sobre cómo usar secuencias de F #, si tiene una colección de datos ordenada de gran tamaño, pero no es necesario que use todos los elementos.'
ms.date: 11/04/2019
ms.openlocfilehash: fa5073f33b9dae52371c249bfb257a2446b4d26a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855327"
---
# <a name="sequences"></a>Secuencias

Una *secuencia* es una serie lógica de elementos de un tipo. Las secuencias son especialmente útiles cuando se tiene una colección grande ordenada de datos, pero no se espera necesariamente usar todos los elementos. Los elementos de secuencia individuales solo se calculan según sea necesario, por lo que una secuencia puede proporcionar un mejor rendimiento que una lista en situaciones en las que no se usan todos los elementos. Las secuencias se representan mediante el `seq<'T>` tipo, que es un alias para <xref:System.Collections.Generic.IEnumerable%601> . Por lo tanto, cualquier tipo .NET que implemente <xref:System.Collections.Generic.IEnumerable%601> una interfaz se puede usar como una secuencia. El [módulo SEQ](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) proporciona compatibilidad con las manipulaciones que implican secuencias.

> [!NOTE]
> La referencia de la API de docs.microsoft.com para F # no está completa. Si encuentra vínculos rotos, consulte la [documentación de la biblioteca básica de F #](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="sequence-expressions"></a>Expresiones de secuencia

Una *expresión de secuencia* es una expresión que se evalúa como una secuencia. Las expresiones de secuencia pueden tomar varias formas. La forma más sencilla especifica un intervalo. Por ejemplo, `seq { 1 .. 5 }` crea una secuencia que contiene cinco elementos, incluidos los puntos de conexión 1 y 5. También puede especificar un incremento (o decremento) entre dos períodos dobles. Por ejemplo, el código siguiente crea la secuencia de múltiplos de 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Las expresiones de secuencia se componen de expresiones de F # que generan valores de la secuencia. También puede generar valores mediante programación:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

En el ejemplo anterior se usa el `->` operador, que permite especificar una expresión cuyo valor se convertirá en parte de la secuencia. Solo se puede usar `->` si cada parte del código que aparece a continuación devuelve un valor.

También puede especificar la `do` palabra clave, con un opcional `yield` que sigue a:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

El código siguiente genera una lista de pares de coordenadas junto con un índice en una matriz que representa la cuadrícula. Tenga en cuenta que la primera `for` expresión requiere que `do` se especifique un.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Una `if` expresión utilizada en una secuencia es un filtro. Por ejemplo, para generar una secuencia de números primos, suponiendo que tiene una función `isprime` de tipo `int -> bool` , construya la secuencia como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Como se mencionó anteriormente, `do` es necesario aquí porque no hay ninguna rama que se refiere `else` a `if` . Si intenta usar, recibirá `->` un error que indica que no todas las ramas devuelven un valor.

## <a name="the-yield-keyword"></a>La palabra clave `yield!`.

A veces, puede que desee incluir una secuencia de elementos en otra secuencia. Para incluir una secuencia dentro de otra secuencia, debe usar la `yield!` palabra clave:

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

Otra forma de pensar `yield!` es que reduce una secuencia interna y, a continuación, la incluye en la secuencia contenedora.

Cuando `yield!` se usa en una expresión, todos los demás valores únicos deben usar la `yield` palabra clave:

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

Si se especifica solo `x` en el ejemplo anterior, la secuencia no genera valores.

## <a name="examples"></a>Ejemplos

En el primer ejemplo se usa una expresión de secuencia que contiene una iteración, un filtro y un rendimiento para generar una matriz. Este código imprime una secuencia de números primos entre 1 y 100 en la consola.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

En el ejemplo siguiente se crea una tabla de multiplicación que consta de tuplas de tres elementos, cada una de las cuales consta de dos factores y el producto:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

En el siguiente ejemplo se muestra el uso de `yield!` para combinar secuencias individuales en una sola secuencia final. En este caso, las secuencias de cada subárbol de un árbol binario se concatenan en una función recursiva para generar la secuencia final.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Utilizar secuencias

Las secuencias admiten muchas de las mismas funciones que las [listas](lists.md). Las secuencias también admiten operaciones como la agrupación y el recuento mediante el uso de funciones de generación de claves. Las secuencias también admiten funciones más diversas para extraer subsecuencias.

Muchos tipos de datos, como listas, matrices, conjuntos y asignaciones, son secuencias implícitamente porque son colecciones enumerables. Una función que toma una secuencia como argumento funciona con cualquiera de los tipos de datos comunes de F #, además de cualquier tipo de datos de .NET que implemente `System.Collections.Generic.IEnumerable<'T>` . Compare esto con una función que toma una lista como argumento, que solo puede tomar listas. El tipo `seq<'T>` es una abreviatura de tipo para `IEnumerable<'T>` . Esto significa que cualquier tipo que implemente el genérico `System.Collections.Generic.IEnumerable<'T>` , que incluye matrices, listas, conjuntos y asignaciones en F #, y también la mayoría de los tipos de colección de .net, es compatible con el `seq` tipo y se puede usar siempre que se espere una secuencia.

## <a name="module-functions"></a>Funciones del módulo

El [módulo SEQ](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) del [espacio de nombres Microsoft. FSharp. Collections](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contiene funciones para trabajar con secuencias. Estas funciones también funcionan con listas, matrices, asignaciones y conjuntos, ya que todos estos tipos son enumerables y, por tanto, se pueden tratar como secuencias.

## <a name="creating-sequences"></a>Crear secuencias

Puede crear secuencias mediante el uso de expresiones de secuencia, como se ha descrito anteriormente, o mediante el uso de determinadas funciones.

Puede crear una secuencia vacía mediante [Seq. Empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), o bien, puede crear una secuencia de solo un elemento especificado mediante [Seq. singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

Puede usar [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) para crear una secuencia para la que se crean los elementos mediante el uso de una función proporcionada por el usuario. También proporciona un tamaño para la secuencia. Esta función es como [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), salvo que los elementos no se crean hasta que se recorre en iteración la secuencia. En el código siguiente, se muestra el uso de `Seq.init`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

El resultado es

```console
0 10 20 30 40
```

Al usar [Seq. myArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) y [Seq. allist&#60; la función&#62;](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), puede crear secuencias a partir de matrices y listas. Sin embargo, también puede convertir matrices y listas en secuencias mediante el uso de un operador de conversión. Ambas técnicas se muestran en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

Con [Seq. Cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), puede crear una secuencia a partir de una colección débilmente tipada, como las que se definen en `System.Collections` . Estas colecciones débilmente tipadas tienen el tipo de elemento `System.Object` y se enumeran con el tipo no genérico `System.Collections.Generic.IEnumerable&#96;1` . En el código siguiente se muestra el uso de `Seq.cast` para convertir un `System.Collections.ArrayList` en una secuencia.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

Puede definir secuencias infinitas mediante el [Seq.inifunción tInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) . Para este tipo de secuencia, se proporciona una función que genera cada elemento a partir del índice del elemento. Las secuencias infinitas son posibles debido a una evaluación diferida; los elementos se crean según sea necesario mediante una llamada a la función que especifique. En el ejemplo de código siguiente se genera una secuencia infinita de números de punto flotante, en este caso, la serie alterna de recíprocos de cuadrados de enteros sucesivos.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq. unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) genera una secuencia a partir de una función de cálculo que toma un estado y la transforma para generar cada elemento subsiguiente de la secuencia. El estado es simplemente un valor que se usa para calcular cada elemento y puede cambiar a medida que se calcula cada elemento. El segundo argumento `Seq.unfold` es el valor inicial que se utiliza para iniciar la secuencia. `Seq.unfold`utiliza un tipo de opción para el estado, lo que permite finalizar la secuencia devolviendo el `None` valor. En el código siguiente se muestran dos ejemplos de secuencias, `seq1` y `fib` , que genera una `unfold` operación. La primera, `seq1` , es simplemente una secuencia simple con números de hasta 20. El segundo, `fib` , utiliza `unfold` para calcular la secuencia de Fibonacci. Dado que cada elemento de la secuencia de Fibonacci es la suma de los dos números de Fibonacci anteriores, el valor de estado es una tupla que consta de los dos números anteriores de la secuencia. El valor inicial es `(1,1)` , los dos primeros números de la secuencia.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

La salida es como sigue:

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

El código siguiente es un ejemplo que usa muchas de las funciones de módulo de secuencia que se describen aquí para generar y calcular los valores de las secuencias infinitas. El código puede tardar unos minutos en ejecutarse.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Buscar y buscar elementos

Las secuencias admiten la funcionalidad disponible con listas: [Seq. exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq. exists2 (](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq. Find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq. FindIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq. Pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq. tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)y [Seq. tryfindindex (](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Las versiones de estas funciones que están disponibles para las secuencias evalúan la secuencia solo hasta el elemento que se está buscando. Para obtener ejemplos, vea [listas](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).

## <a name="obtaining-subsequences"></a>Obtener subsecuencias

[Seq. Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) y [Seq. Choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) son como las funciones correspondientes que están disponibles para las listas, con la excepción de que el filtrado y la elección no se producen hasta que se evalúan los elementos de la secuencia.

[Seq. TRUNCATE](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) crea una secuencia a partir de otra secuencia, pero limita la secuencia a un número especificado de elementos. [Seq. Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) crea una nueva secuencia que solo contiene un número especificado de elementos desde el inicio de una secuencia. Si hay menos elementos en la secuencia de los que se van a tomar, se `Seq.take` produce una excepción `System.InvalidOperationException` . La diferencia entre `Seq.take` y `Seq.truncate` es que `Seq.truncate` no genera un error si el número de elementos es menor que el número especificado.

En el código siguiente se muestra el comportamiento de y las diferencias entre `Seq.truncate` y `Seq.take` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

La salida, antes de que se produzca el error, es como se indica a continuación.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

Mediante [Seq. takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), puede especificar una función de predicado (una función booleana) y crear una secuencia a partir de otra secuencia que se compone de los elementos de la secuencia original para la que el predicado es `true` , pero se detiene antes del primer elemento para el que el predicado devuelve `false` . [Seq. SKIP](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) devuelve una secuencia que omite un número especificado de los primeros elementos de otra secuencia y devuelve los elementos restantes. [Seq. skipwhile (](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) devuelve una secuencia que omite los primeros elementos de otra secuencia siempre que el predicado devuelva `true` y, a continuación, devuelve los elementos restantes, empezando por el primer elemento para el que el predicado devuelve `false` .

En el ejemplo de código siguiente se muestra el comportamiento de y las diferencias entre `Seq.takeWhile` , `Seq.skip` y `Seq.skipWhile` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

La salida es la siguiente.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Transformar secuencias

[Seq. en pares](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) crea una nueva secuencia en la que los elementos sucesivos de la secuencia de entrada se agrupan en tuplas.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) es como `Seq.pairwise` , salvo que, en lugar de generar una secuencia de tuplas, genera una secuencia de matrices que contienen copias de elementos adyacentes (una *ventana*) de la secuencia. Especifique el número de elementos adyacentes que desee en cada matriz.

En el siguiente ejemplo de código se muestra el uso de `Seq.windowed`. En este caso, el número de elementos de la ventana es 3. En el ejemplo `printSeq` se usa, que se define en el ejemplo de código anterior.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

La salida es la siguiente.

Secuencia inicial:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operaciones con varias secuencias

[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) y [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) toman dos o tres secuencias y generan una secuencia de tuplas. Estas funciones son similares a las funciones correspondientes disponibles para [las listas](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). No hay ninguna funcionalidad correspondiente para separar una secuencia en dos o más secuencias. Si necesita esta funcionalidad para una secuencia, convierta la secuencia en una lista y use [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

## <a name="sorting-comparing-and-grouping"></a>Ordenar, comparar y agrupar

Las funciones de ordenación compatibles con las listas también funcionan con secuencias. Esto incluye [Seq. Sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) y [Seq. sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Estas funciones recorren en iteración toda la secuencia.

Se comparan dos secuencias mediante la función [Seq. compareWith (](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) . La función compara los elementos sucesivos a su vez y se detiene cuando encuentra el primer par diferente. Cualquier elemento adicional no contribuye a la comparación.

En el código siguiente se muestra el uso de `Seq.compareWith`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

En el código anterior, solo se calcula y examina el primer elemento y el resultado es-1.

[Seq. countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) toma una función que genera un valor denominado *clave* para cada elemento. Se genera una clave para cada elemento mediante una llamada a esta función en cada elemento. `Seq.countBy`a continuación, devuelve una secuencia que contiene los valores de clave y un recuento del número de elementos que genera cada valor de la clave.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

La salida es la siguiente.

```console
(1, 34) (2, 33) (0, 33)
```

La salida anterior muestra que había 34 elementos de la secuencia original que generaban los valores de la clave 1, 33 que generaban los valores de la clave 2 y 33 que generaban la clave 0.

Puede agrupar los elementos de una secuencia mediante una llamada a [Seq. groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy`toma una secuencia y una función que genera una clave a partir de un elemento. La función se ejecuta en cada elemento de la secuencia. `Seq.groupBy`Devuelve una secuencia de tuplas, donde el primer elemento de cada tupla es la clave y el segundo es una secuencia de elementos que generan esa clave.

En el ejemplo de código siguiente se muestra el uso de `Seq.groupBy` para particionar la secuencia de números de 1 a 100 en tres grupos que tienen los valores de clave distintos 0, 1 y 2.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

La salida es la siguiente.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Puede crear una secuencia que elimine elementos duplicados mediante una llamada a [Seq. DISTINCT](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). O bien, puede usar [Seq. distinctby (](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), que toma una función de generación de claves a la que se va a llamar en cada elemento. La secuencia resultante contiene elementos de la secuencia original que tienen claves únicas. los elementos posteriores que producen una clave duplicada en un elemento anterior se descartan.

En el siguiente ejemplo de código, se muestra el uso de `Seq.distinct`. `Seq.distinct`se muestra generando secuencias que representan números binarios y, a continuación, mostrando que los únicos elementos distintos son 0 y 1.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

En el código siguiente se muestra el `Seq.distinctBy` Inicio con una secuencia que contiene números positivos y negativos y el uso de la función de valor absoluto como la función de generación de claves. En la secuencia resultante faltan todos los números positivos que corresponden a los números negativos de la secuencia, ya que los números negativos aparecen antes en la secuencia y, por lo tanto, se seleccionan en lugar de los números positivos que tienen el mismo valor absoluto o clave.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Secuencias de solo lectura y en caché

[Seq. ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) crea una copia de solo lectura de una secuencia. `Seq.readonly`resulta útil cuando se tiene una colección de lectura y escritura, como una matriz, y no se desea modificar la colección original. Esta función se puede utilizar para conservar la encapsulación de datos. En el ejemplo de código siguiente, se crea un tipo que contiene una matriz. Una propiedad expone la matriz, pero en lugar de devolver una matriz, devuelve una secuencia que se crea a partir de la matriz mediante el uso de `Seq.readonly` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) crea una versión almacenada de una secuencia. Use `Seq.cache` para evitar la reevaluación de una secuencia o si tiene varios subprocesos que usan una secuencia, pero debe asegurarse de que cada elemento se actúa solo una vez. Si tiene una secuencia que usan varios subprocesos, puede tener un subproceso que Enumere y calcule los valores de la secuencia original, y los subprocesos restantes puedan utilizar la secuencia almacenada en caché.

## <a name="performing-computations-on-sequences"></a>Realizar cálculos en secuencias

Las operaciones aritméticas simples son similares a las de las listas, como [Seq. Average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq. SUM](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq. averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq. sumBy (](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1), etc.

[Seq. Fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq. reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)y [Seq. Scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) son como las funciones correspondientes que están disponibles para las listas. Las secuencias admiten un subconjunto de las variaciones completas de estas funciones que enumeran la compatibilidad. Para obtener más información y ejemplos, vea [listas](lists.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
