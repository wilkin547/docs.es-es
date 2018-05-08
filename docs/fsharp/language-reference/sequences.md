---
title: Secuencias (F#)
description: 'Obtenga información acerca de cómo usar las secuencias de F # cuando disponga de una gran colección ordenada de datos pero no necesariamente espera utilizar todos los elementos.'
ms.date: 05/16/2016
ms.openlocfilehash: ebebec3a69fd0f4fb8e3ad8d554541fa1cc8945e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="sequences"></a>Secuencias

> [!NOTE]
Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

A *secuencia* es una serie lógica de elementos del mismo tipo. Las secuencias son especialmente útiles cuando disponga de una gran colección ordenada de datos pero no pretenda usar todos los elementos. Secuencia individual elementos se calculan únicamente como necesario, por lo que una secuencia puede proporcionar un rendimiento mejor que una lista en situaciones en que no se usan todos los elementos. Las secuencias se representan mediante la `seq<'T>` tipo, que es un alias para `System.Collections.Generic.IEnumerable`. Por lo tanto, cualquier tipo de .NET Framework que implemente `System.IEnumerable` puede utilizarse como una secuencia. El [Seq (módulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) proporciona compatibilidad para las manipulaciones que implican las secuencias.

## <a name="sequence-expressions"></a>Expresiones de secuencia
A *expresión de secuencia* es una expresión que se evalúa como una secuencia. Expresiones de secuencia pueden tener varios formatos. La forma más sencilla, especifica un intervalo. Por ejemplo, `seq { 1 .. 5 }` crea una secuencia que contiene cinco elementos, incluidos los extremos 1 y 5. También puede especificar un incremento (o decremento) entre dos puntos dobles. Por ejemplo, el código siguiente crea la secuencia de múltiplos de 10.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Expresiones de secuencia se componen de expresiones de F # que generan valores de la secuencia. Puede usar el `yield` palabra clave para generar valores que pasan a formar parte de la secuencia.

Aquí te mostramos un ejemplo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Puede usar el `->` en lugar del operador `yield`, en cuyo caso se puede omitir el `do` palabra clave, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

El código siguiente genera una lista de pares de coordenadas junto con un índice en una matriz que representa la cuadrícula.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Un `if` expresión utilizada en una secuencia es un filtro. Por ejemplo, para generar una secuencia de solo números primos, suponiendo que tenga una función `isprime` de tipo `int -> bool`, construya la secuencia como sigue.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Cuando usas `yield` o `->` en una iteración, cada iteración se espera para generar un único elemento de la secuencia. Si cada iteración genera una secuencia de elementos, utilice `yield!`. En ese caso, los elementos generados en cada iteración se concatenan para generar la secuencia final.

Puede combinar varias expresiones en una expresión de secuencia. Los elementos generados por cada expresión se concatenan juntos. Para obtener un ejemplo, vea la sección "Ejemplos" de este tema.

## <a name="examples"></a>Ejemplos
El primer ejemplo utiliza una expresión de secuencia que contiene una iteración, un filtro y un rendimiento para generar una matriz. Este código imprime una secuencia de números primos entre 1 y 100 en la consola.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

El siguiente código utiliza `yield` para crear una tabla de multiplicación que consta de tuplas de tres elementos, cada uno de los que consta de dos factores y el producto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

En el ejemplo siguiente se muestra el uso de `yield!` para combinar las secuencias individuales en una única secuencia final. En este caso, las secuencias de cada subárbol de un árbol binario se concatenan en una función recursiva para generar la secuencia final.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a>Uso de secuencias
Las secuencias admiten muchas de las mismas funciones que [muestra](lists.md). Las secuencias también admiten operaciones como la agrupación y el recuento mediante funciones de generación de claves. Las secuencias también admiten funciones más diversas para extraer subsecuencias.

Muchos tipos de datos, como listas, matrices, conjuntos y asignaciones son implícitamente secuencias porque son colecciones enumerables. Una función que toma una secuencia como un argumento funciona con cualquiera de los comunes F # tipos de datos, además de a cualquier tipo de datos de .NET Framework que implementa `System.Collections.Generic.IEnumerable<'T>`. Esto contrasta con una función que toma una lista como argumento, que solo puede tomar listas. El tipo `seq<'T>` es una abreviatura de tipo para `IEnumerable<'T>`. Esto significa que cualquier tipo que implemente la interfaz genérica `System.Collections.Generic.IEnumerable<'T>`, que incluye matrices, listas, Establece y asignaciones en F # y también tipos de la mayoría de .NET Framework colección, es compatible con la `seq` escriba y se pueden utilizar donde se espera una secuencia.


## <a name="module-functions"></a>Funciones del módulo
El [Seq (módulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) en el [Microsoft.FSharp.Collections espacio de nombres](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contiene funciones para trabajar con secuencias. Estas funciones trabajar con listas, matrices, asignaciones y conjuntos, porque todos esos tipos son enumerables y por lo tanto, se pueden tratar como secuencias.


## <a name="creating-sequences"></a>Creación de secuencias
Puede crear secuencias mediante expresiones de secuencia, como se describió anteriormente, o mediante el uso de determinadas funciones.

Puede crear una secuencia vacía mediante [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), o puede crear una secuencia de un solo elemento especificado mediante [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

Puede usar [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) para crear una secuencia para el que los elementos se crean mediante una función proporcionada por usted. También se proporciona el tamaño de la secuencia. Esta función es exactamente igual que [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), salvo que los elementos no se crean hasta que se recorra en iteración la secuencia. En el código siguiente, se muestra el uso de `Seq.init`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

El resultado es

```
0 10 20 30 40
```

Mediante el uso de [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) y [Seq.ofList&#60;' t&#62; función](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), puede crear secuencias de matrices y listas. Sin embargo, también puede convertir matrices y listas en secuencias mediante el uso de un operador de conversión. En el código siguiente se muestran dos técnicas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

Mediante el uso de [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), puede crear una secuencia de una colección con tipos débiles, como las definidas en `System.Collections`. Las colecciones débilmente tipadas tienen el tipo de elemento `System.Object` y se enumeran mediante el uso de no genérica `System.Collections.Generic.IEnumerable&#96;1` tipo. El código siguiente muestra el uso de `Seq.cast` para convertir un `System.Collections.ArrayList` en una secuencia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

Puede definir las secuencias infinitas mediante la [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) función. Para este tipo de secuencia, se proporciona una función que genera cada elemento del índice del elemento. Las secuencias infinitas son posibles debido a la evaluación diferida; los elementos se crean según sea necesario mediante una llamada a la función que especifique. En el ejemplo de código siguiente se genera una secuencia infinita de números decimales, en este caso la serie alternas de recíprocos de cuadrados de enteros sucesivas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) genera una secuencia de una función de cálculo que toma un estado y lo transforma para generar cada elemento subsiguiente en la secuencia. El estado es simplemente un valor que se utiliza para calcular cada elemento y puede cambiar conforme se calcula a cada elemento. El segundo argumento `Seq.unfold` es el valor inicial que se usa para iniciar la secuencia. `Seq.unfold` usa un tipo de opción para el estado, lo que permite terminar la secuencia devolviendo el `None` valor. El código siguiente muestra dos ejemplos de secuencias, `seq1` y `fib`, que se generan mediante una `unfold` operación. La primera, `seq1`, es simplemente una secuencia sencilla con números de hasta 100. El segundo, `fib`, usa `unfold` para calcular la secuencia de Fibonacci. Dado que cada elemento de la secuencia de Fibonacci es la suma de los dos números de Fibonacci anteriores, el valor de estado es una tupla que consta de los dos números anteriores en la secuencia. El valor inicial es `(1,1)`, los primeros dos números en la secuencia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

La salida es la siguiente:

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

El código siguiente es un ejemplo que usa muchas de las funciones del módulo de secuencia que se describe a continuación para generar y calcular los valores de las secuencias infinitas. El código puede tardar unos minutos en ejecutarse.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a>Buscar y encontrar elementos
Las secuencias admiten la funcionalidad disponible con listas: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), y [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Las versiones de estas funciones que están disponibles para las secuencias de evaluarán la secuencia solo hasta el elemento que se va a buscar. Para obtener ejemplos, vea [muestra](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).


## <a name="obtaining-subsequences"></a>Obtener subsecuencias
[Seq.Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) y [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) son similares a las funciones correspondientes que están disponibles para las listas, excepto en que el filtrado y la elección no se produce hasta que se evalúan los elementos de la secuencia.

[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) crea una secuencia a partir de otra secuencia, pero limitará la secuencia a un número especificado de elementos. [Seq.Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) crea una nueva secuencia que contiene solo un número especificado de elementos desde el principio de una secuencia. Si hay menos elementos en la secuencia que el especificado para aprovechar, `Seq.take` produce una `System.InvalidOperationException`. La diferencia entre `Seq.take` y `Seq.truncate` es que `Seq.truncate` no produce un error si el número de elementos es menor que el número especifique.

El código siguiente se muestra el comportamiento de y las diferencias entre `Seq.truncate` y `Seq.take`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

El resultado, antes de que se produce el error, es como sigue.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

Mediante el uso de [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), puede especificar una función de predicado (una función booleana) y crear una secuencia a partir de otra secuencia que consta de los elementos de la secuencia original para que el predicado es `true`, pero se detiene antes del primer elemento para el que el predicado devuelve `false`. [Seq.Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) devuelve una secuencia que omite un número especificado de los primeros elementos de otra secuencia y devuelve los elementos restantes. [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) devuelve una secuencia que omite los primeros elementos de otra secuencia siempre y cuando el predicado devuelve `true`y, a continuación, devuelve los elementos restantes, empezando por el primer elemento para el cual el predicado devuelve `false`.

En el ejemplo de código siguiente se muestra el comportamiento de y las diferencias entre `Seq.takeWhile`, `Seq.skip`, y `Seq.skipWhile`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

La salida es la siguiente.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Transformar secuencias
[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) crea una nueva secuencia en la que se agrupan los elementos sucesivos de la secuencia de entrada en tuplas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) es similar a `Seq.pairwise`, excepto que en lugar de generar una secuencia de tuplas, genera una secuencia de matrices que contienen copias de los elementos adyacentes (un *ventana*) de la secuencia. Especifique el número de elementos adyacentes que desee en cada matriz.

En el siguiente ejemplo de código se muestra el uso de `Seq.windowed`. En este caso, el número de elementos en la ventana es 3. El ejemplo se utiliza `printSeq`, que se define en el ejemplo de código anterior.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

La salida es la siguiente.

Secuencia inicial:

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operaciones con varias secuencias
[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) y [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) tomar dos o tres secuencias y producen una secuencia de tuplas. Estas funciones son similares a las funciones correspondientes disponibles para [muestra](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). No hay ninguna funcionalidad correspondiente para separar una secuencia en dos o más secuencias. Si necesita esta funcionalidad para una secuencia, convierta la secuencia en una lista y utilice [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).


## <a name="sorting-comparing-and-grouping"></a>Ordenar, comparar y agrupar
Las funciones de ordenación admitidas para las listas también funcionan con las secuencias. Esto incluye [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) y [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Estas funciones recorrer en iteración toda la secuencia.

Comparar dos secuencias mediante la [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) función. La función compara los elementos sucesivos a su vez y se detiene cuando encuentra el primer par desigual. Cualquier elemento adicional no contribuye a la comparación.

En el código siguiente se muestra el uso de `Seq.compareWith`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

En el código anterior, se calcula y examinar únicamente el primer elemento, y el resultado es -1.

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) toma una función que genera un valor denominado un *clave* para cada elemento. Se genera una clave para cada elemento mediante una llamada a esta función en cada elemento. `Seq.countBy` a continuación, devuelve una secuencia que contiene los valores de clave y un recuento del número de elementos que generaron cada valor de la clave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

La salida es la siguiente.

```
(1, 34) (2, 33) (0, 33)
```

La salida anterior muestra que había 34 elementos de la secuencia original que produjo la clave 1, 33 valores generaron la clave 2 y 33 valores que generó la tecla 0.

Puede agrupar los elementos de una secuencia mediante una llamada a [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy` toma una secuencia y una función que genera una clave de un elemento. La función se ejecuta en cada elemento de la secuencia. `Seq.groupBy` Devuelve una secuencia de tuplas, donde el primer elemento de cada tupla es la clave y el segundo es una secuencia de elementos que generan esa clave.

En el ejemplo de código siguiente se muestra el uso de `Seq.groupBy` para la partición de la secuencia de números de 1 a 100 en tres grupos que tienen los distintos valores de clave 0, 1 y 2.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

La salida es la siguiente.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Puede crear una secuencia que elimina los elementos duplicados mediante una llamada a [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). O bien puede usar [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), que toma una función de generación de clave que se llame en cada elemento. La secuencia resultante contiene elementos de la secuencia original que tienen claves únicas; se descartan los elementos posteriores que generan una clave duplicada en un elemento anterior.

En el siguiente ejemplo de código, se muestra el uso de `Seq.distinct`. `Seq.distinct` se muestran en generar secuencias que representan números binarios y, a continuación, que muestra que los únicos elementos distintos son 0 y 1.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

El código siguiente muestra `Seq.distinctBy` a partir de una secuencia que contiene números negativos y positivos y utilizando la función de valor absoluto como la función de generación de claves. La secuencia resultante no tiene todos los números positivos que corresponden a los números negativos en la secuencia, porque los números negativos aparecen antes en la secuencia y, por tanto, se seleccionan en lugar de los números positivos que tienen el mismo absoluto valor o clave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a>ReadOnly y secuencias en caché
[Seq.ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) crea una copia de solo lectura de una secuencia. `Seq.readonly` es útil cuando tiene una colección de lectura y escritura, como una matriz, y no desea modificar la colección original. Esta función puede utilizarse para conservar la encapsulación de datos. En el ejemplo de código siguiente, se crea un tipo que contiene una matriz. Una propiedad expone la matriz, pero en lugar de devolver una matriz, devuelve una secuencia que se crea a partir de la matriz mediante el uso de `Seq.readonly`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.Cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) crea una versión almacenada de una secuencia. Usar `Seq.cache` para evitar la reevaluación de una secuencia, o si tienes varios subprocesos que utilizan una secuencia, pero debe asegurarse de que cada elemento es actuar solo una vez. Si tiene una secuencia que está siendo utilizada por varios subprocesos, puede tener un subproceso que enumera y calcula los valores de la secuencia original y subprocesos restantes pueden usar la secuencia almacenada en caché.


## <a name="performing-computations-on-sequences"></a>Realizar cálculos en secuencias
Operaciones aritméticas sencillas son similares a las listas, como [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1), y así sucesivamente.

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), y [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) son similares a las funciones correspondientes que están disponibles para las listas. Las secuencias admiten un subconjunto de todas las variantes de estas funciones admitidas por las listas. Para obtener más información y ejemplos, vea [muestra](lists.md).

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Tipos en F#](fsharp-types.md)
