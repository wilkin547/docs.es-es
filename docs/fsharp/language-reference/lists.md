---
title: Listas
description: 'Obtenga información sobre las listas de F #, una serie ordenada e inmutable de elementos del mismo tipo.'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720353"
---
# <a name="lists"></a>Listas

En F#, una lista es una serie ordenada e inmutable de elementos del mismo tipo. Para realizar operaciones básicas en listas, use las funciones del [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

## <a name="creating-and-initializing-lists"></a>Crear e inicializar listas

Para definir una lista, puede enumerar explícitamente los elementos, separados por punto y coma y escritos entre corchetes, tal y como se muestra en la línea de código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

También puede insertar saltos de línea entre los elementos, en cuyo caso el signo de punto y coma es opcional. La última sintaxis produce un código más legible cuando las expresiones de inicialización de elementos son más largas o si quiere incluir un comentario para cada elemento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

Normalmente, todos los elementos de lista deben ser del mismo tipo. Una excepción es que una lista en la cual los elementos se han especificado para que sean de un tipo base puede tener elementos que sean de tipos derivados. Por lo tanto, lo siguiente es aceptable, porque tanto `Button` como `CheckBox` derivan de `Control`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

También puede definir elementos de lista usando un intervalo indicado por enteros separados por el operador de intervalo (`..`), tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

Una lista vacía se especifica por un par de corchetes con nada entre ellos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

También puede usar una expresión de secuencia para crear una lista. Vea [expresiones de secuencia](sequences.md#sequence-expressions) para obtener más información. Por ejemplo, el código siguiente crea una lista de cuadrados de enteros, de 1 a 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>Operadores para trabajar con listas

Puede asociar elementos a una lista usando el operador `::` (cons). Si `list1` es `[2; 3; 4]`, el código siguiente crea `list2` como `[100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

Para concatenar listas que tengan tipos compatibles, puede usar el operador `@`, como en el código siguiente. Si `list1` es `[2; 3; 4]` y `list2` es `[100; 2; 3; 4]`, este código crea `list3` como `[2; 3; 4; 100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

Las funciones para realizar operaciones en listas están disponibles en el [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

Como en F# las listas son inmutables, las operaciones de modificación generan nuevas listas en lugar de modificar las existentes.

Las listas de F # se implementan como listas vinculadas individualmente, lo que significa que las operaciones que tienen acceso solo al encabezado de la lista son O (1) y el acceso a los elementos es O (*n*).

## <a name="properties"></a>Propiedades

El tipo de lista admite las siguientes propiedades:

|Propiedad|Tipo|Descripción|
|--------|----|-----------|
|[Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|El primer elemento.|
|[Vacía](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|Propiedad estática que devuelve una lista vacía del tipo apropiado.|
|[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|`true` si la lista no tiene ningún elemento.|
|[Elemento](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|Elemento en el índice especificado (base cero).|
|[Longitud](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|Número de elementos.|
|[Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|La lista sin el primer elemento.|

Los siguientes son algunos ejemplos de cómo usar estas propiedades.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>Usar listas

Programar con listas permite realizar operaciones complejas con una pequeña cantidad de código. En esta sección se describen las operaciones comunes en las listas que son importantes para la programación funcional.

### <a name="recursion-with-lists"></a>Recursión con listas

Las listas están especialmente indicadas para las técnicas de programación recursiva. Tomemos una operación que deba realizarse en todos los elementos de una lista. Puede hacerlo recursivamente ejecutando una operación en el encabezado de la lista y, después, devolviendo la cola de la lista (que es una lista más pequeña formada por la lista original sin el primer elemento) de nuevo al siguiente nivel de recursión.

Para escribir una función recursiva de este estilo, se usa el operador cons (`::`) en coincidencia de patrones, lo que permite separar el encabezado de una lista de la cola.

En el ejemplo de código siguiente se muestra cómo usar la coincidencia de patrones para implementar una función recursiva que realice operaciones en una lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

El código anterior funciona bien para listas pequeñas, pero en listas mayores podría desbordar la pila. El código siguiente mejora este código usando un argumento acumulador, una técnica estándar para trabajar con funciones recursivas. El uso del argumento acumulador hace que la función sea recursiva en la cola, lo que ahorra espacio en la pila.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

La función `RemoveAllMultiples` es una función recursiva que toma dos listas. La primera lista contiene los números cuyos múltiplos se van a quitar, y la segunda es la lista de la que se van a quitar los números. El código del ejemplo siguiente usa esta función recursiva para eliminar de una lista todos los números que no sean primos, dejando como resultado una lista de números primos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

La salida es como sigue:

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>Funciones del módulo

El [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) proporciona funciones que tienen acceso a los elementos de una lista. El elemento de encabezado es la manera más rápida y sencilla de acceder. Use el [encabezado](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) de propiedad o la función de módulo [List. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head). Puede tener acceso al final de una lista mediante la propiedad [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) o la función [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) . Para buscar un elemento por índice, use la función [List. nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) . `List.nth` atraviesa la lista. Por lo tanto, es O (*n*). Si su código usa `List.nth` con frecuencia, quizás quiera considerar la posibilidad de usar una matriz en lugar de una lista. El acceso a elementos en las matrices es O(1).

### <a name="boolean-operations-on-lists"></a>Operaciones booleanas en listas

La función [List. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) determina si una lista tiene elementos.

La función [List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) aplica una prueba booleana a los elementos de una lista y devuelve `true` si algún elemento cumple la prueba. [List. exists2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) es similar pero funciona en pares sucesivos de elementos de dos listas.

En el código siguiente se muestra cómo usar `List.exists`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

La salida es como sigue:

```console
For list [0; 1; 2; 3], contains zero is true
```

El siguiente ejemplo muestra el uso de `List.exists2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

La salida es como sigue:

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

Puede usar [List. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) si desea comprobar si todos los elementos de una lista cumplen una condición.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

La salida es como sigue:

```console
true
false
```

De forma similar, [List. forall2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determina si todos los elementos de las posiciones correspondientes de dos listas satisfacen una expresión booleana que implica cada par de elementos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

La salida es como sigue:

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Operaciones de ordenación en listas

Las funciones [List. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List. sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)y [List. sortWith (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) ordenan las listas. La función de ordenación determina cuál de estas tres funciones se usará. `List.sort` usa una comparación genérica predeterminada. La comparación genérica usa operadores globales basados en la función de comparación genérica para comparar valores. Funciona de forma eficaz con una amplia variedad de tipos de elemento, como tipos numéricos simples, tuplas, registros, uniones discriminadas, listas, matrices y cualquier tipo que implemente `System.IComparable`. Para los tipos que implementan `System.IComparable`, la comparación genérica usa la función `System.IComparable.CompareTo()`. La comparación genérica también trabaja con cadenas, pero usa una ordenación independiente de la referencia cultural. La comparación genérica no se debe usar en tipos no admitidos, como los tipos de función. Además, el rendimiento de la comparación genérica predeterminada es mejor para tipos estructurados pequeños; para los tipos estructurados mayores que deben compararse y ordenarse con frecuencia, considere la posibilidad de implementar `System.IComparable` y de proporcionar una implementación eficaz del método `System.IComparable.CompareTo()`.

`List.sortBy` toma una función que devuelve un valor que se usa como criterio de ordenación, y `List.sortWith` toma una función de comparación como argumento. Estas dos últimas funciones son útiles cuando se trabaja con tipos que no permiten la comparación, o cuando la comparación requiere semánticas de comparación más complejas, como es el caso de las cadenas que tienen en cuenta la referencia cultural.

El siguiente ejemplo muestra el uso de `List.sort`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

La salida es como sigue:

```console
[-2; 1; 4; 5; 8]
```

El siguiente ejemplo muestra el uso de `List.sortBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

La salida es como sigue:

```console
[1; -2; 4; 5; 8]
```

El siguiente ejemplo muestra el uso de `List.sortWith`. En este ejemplo, la función de comparación personalizada `compareWidgets` se usa para comparar primero un campo de un tipo personalizado, y después otro cuando los valores del primer campo son iguales.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

La salida es como sigue:

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>Operaciones de búsqueda en listas

Se admiten numerosas operaciones de búsqueda en las listas. La más sencilla, [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), permite buscar el primer elemento que coincide con una condición determinada.

El ejemplo de código siguiente muestra el uso de `List.find` para buscar el primer número que es divisible por 5 en una lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

El resultado es 5.

Si los elementos se deben transformar primero, llame a [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), que toma una función que devuelve una opción y busca el primer valor de opción que sea `Some(x)` . En lugar de devolver el elemento, `List.pick` devuelve el resultado `x`. Si no se encuentra ningún elemento coincidente, `List.pick` activa `System.Collections.Generic.KeyNotFoundException`. En el código siguiente se muestra el uso de `List.pick`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

La salida es como sigue:

```console
"b"
```

Otro grupo de operaciones de búsqueda, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) y funciones relacionadas, devuelven un valor de opción. La función `List.tryFind` devuelve el primer elemento de una lista que cumple una condición si ese elemento existe, pero el valor de opción `None` si no. La variación [List. tryfindindex (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) devuelve el índice del elemento, si se encuentra uno, en lugar del propio elemento. Estas funciones quedan reflejadas en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

La salida es como sigue:

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Operaciones aritméticas en listas

Las operaciones aritméticas comunes, como SUM y Average, se integran en el [módulo List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Para trabajar con [List. SUM](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), el tipo de elemento de lista debe admitir el `+` operador y tener un valor de cero. Todos los tipos aritmético integrados cumplen estas condiciones. Para trabajar con [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), el tipo de elemento debe admitir la división sin resto, lo que excluye los tipos enteros, pero permite tipos de punto flotante. Las funciones [List. sumBy (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) y [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) toman una función como parámetro, y los resultados de esta función se usan para calcular los valores de la suma o el promedio.

En el código siguiente se muestra cómo usar `List.sum`, `List.sumBy` y `List.average`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

La salida es `1.000000`.

En el código siguiente se muestra el uso de `List.averageBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

La salida es `5.5`.

### <a name="lists-and-tuples"></a>Listas y tuplas

Las listas que contienen tuplas se pueden manipular con las funciones zip y unzip. Estas funciones combinan dos listas de valores únicos en una lista de tuplas o separan una lista de tuplas en dos listas de valores únicos. La función [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) más sencilla toma dos listas de elementos únicos y genera una sola lista de pares de tupla. Otra versión, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), toma tres listas de elementos únicos y genera una sola lista de tuplas que tienen tres elementos. En el siguiente ejemplo de código se muestra el uso de `List.zip`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

La salida es como sigue:

```console
[(1, -1); (2, -2); (3; -3)]
```

En el siguiente ejemplo de código se muestra el uso de `List.zip3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

La salida es como sigue:

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

Las versiones de unzip correspondientes, [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) y [List. unzip3 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), toman listas de tuplas y devuelven listas en una tupla, donde la primera lista contiene todos los elementos que estaban en primer lugar en cada tupla, y la segunda lista contiene el segundo elemento de cada tupla, y así sucesivamente.

En el ejemplo de código siguiente se muestra el uso de [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

La salida es como sigue:

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

En el ejemplo de código siguiente se muestra el uso de [List. unzip3 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

La salida es como sigue:

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Operar en elementos de lista

F# admite diferentes operaciones en los elementos de lista. La más sencilla es [List. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), que le permite llamar a una función en cada elemento de una lista. Las variaciones incluyen [List. iter2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), que permite realizar una operación en elementos de dos listas, [List. ITERI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), que es como, a `List.iter` excepción de que el índice de cada elemento se pasa como argumento a la función a la que se llama para cada elemento y [List. iteri2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), que es una combinación de la funcionalidad de `List.iter2` y `List.iteri` . En el siguiente ejemplo de código se muestran estas funciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

La salida es como sigue:

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

Otra función que se usa con frecuencia que transforma elementos de lista es [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), que permite aplicar una función a cada elemento de una lista y colocar todos los resultados en una nueva lista. [List. MAP2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) y [List. map3 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) son variaciones que toman varias listas. También puede usar [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) y [List. mapi2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)si, además del elemento, la función debe pasar el índice de cada elemento. La única diferencia entre `List.mapi2` y `List.mapi` es que `List.mapi2` trabaja con dos listas. En el ejemplo siguiente se muestra [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

La salida es como sigue:

```console
[2; 3; 4]
```

En el siguiente ejemplo se muestra el uso de `List.map2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

La salida es como sigue:

```console
[5; 7; 9]
```

En el siguiente ejemplo se muestra el uso de `List.map3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

La salida es como sigue:

```console
[7; 10; 13]
```

En el siguiente ejemplo se muestra el uso de `List.mapi`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

La salida es como sigue:

```console
[1; 3; 5]
```

En el siguiente ejemplo se muestra el uso de `List.mapi2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

La salida es como sigue:

```console
[0; 7; 18]
```

[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) es como `List.map` , salvo que cada elemento genera una lista y todas estas listas se concatenan en una lista final. En el código siguiente, cada elemento de la lista genera tres números. Todos ellos se recopilan en una lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

La salida es como sigue:

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

También puede usar [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), que toma una condición booleana y genera una nueva lista que solo consta de los elementos que satisfacen la condición especificada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

La lista resultante es `[2; 4; 6]`.

Una combinación de asignación y filtro, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) permite transformar y seleccionar elementos al mismo tiempo. `List.choose` aplica una función que devuelve una opción a cada elemento de una lista, y devuelve una nueva lista de resultados de elementos cuando la función devuelve el valor de opción `Some`.

El código siguiente muestra cómo usar `List.choose` para seleccionar las palabras en mayúsculas de una lista de palabras.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

La salida es como sigue:

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Operar en varias listas

Las listas se pueden unir entre sí. Para combinar dos listas en una, use [List. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append). Para combinar más de dos listas, use [List. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Operaciones de plegamiento y exploración

Algunas operaciones de lista implican interdependencias entre todos los elementos de lista. Las operaciones de plegamiento y de recorrido son como `List.iter` y `List.map` , en el caso de que se invoque una función en cada elemento, pero estas operaciones proporcionan un parámetro adicional denominado el *acumulador* que lleva información a través del cálculo.

Use `List.fold` para realizar un cálculo en una lista.

En el ejemplo de código siguiente se muestra el uso de [List. Fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) para realizar varias operaciones.

La lista se atraviesa; el acumulador `acc` es un valor que va pasando mientras se realiza el cálculo. El primer argumento toma el acumulador y el elemento de lista y devuelve el resultado provisional del cálculo para ese elemento de lista. El segundo argumento es el valor inicial del acumulador.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Las versiones de estas funciones que tienen un dígito en el nombre de la función operan en más de una lista. Por ejemplo, [List. fold2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) realiza cálculos en dos listas.

El siguiente ejemplo muestra el uso de `List.fold2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold` y [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) difiere en que `List.fold` devuelve el valor final del parámetro adicional, pero `List.scan` devuelve la lista de los valores intermedios (junto con el valor final) del parámetro adicional.

Cada una de estas funciones incluye una variación inversa, por ejemplo, [List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), que difiere en el orden en el que se recorre la lista y el orden de los argumentos. Además, `List.fold` y `List.foldBack` tienen variaciones, [List. fold2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) y [List. foldBack2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), que toman dos listas de la misma longitud. La función que se ejecuta en cada elemento puede usar los elementos correspondientes de ambas listas para realizar alguna acción. Los tipos de elemento de las dos listas pueden ser diferentes, como en el ejemplo siguiente, en el que una lista contiene los importes de las transacciones de una cuenta bancaria y la otra lista contiene el tipo de transacción: ingreso o retirada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

Para un cálculo como la suma, `List.fold` y `List.foldBack` tiene el mismo efecto porque el resultado no depende del orden del recorrido. En el ejemplo siguientes, se usa `List.foldBack` para sumar los elementos de una lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

El ejemplo siguiente vuelve al ejemplo de la cuenta bancaria. Esta vez se agrega un nuevo tipo de transacción: un cálculo de interés. El saldo final depende ahora del orden de las transacciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

La lista de funciones [. reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) es similar a `List.fold` y `List.scan` , salvo que, en lugar de pasar un acumulador independiente, `List.reduce` toma una función que toma dos argumentos del tipo de elemento en lugar de uno solo, y uno de esos argumentos actúa como el acumulador, lo que significa que almacena el resultado intermedio del cálculo. `List.reduce` comienza por operar en los dos primeros elementos y, después, usa el resultado de la operación con el siguiente elemento. Como no hay un acumulador diferente que tenga su propio tipo, se puede usar `List.reduce` en lugar de `List.fold` solo cuando el acumulador y el elemento sean del mismo tipo. En el código siguiente se muestra cómo usar `List.reduce`. `List.reduce` activa una excepción si la lista proporciona no tiene elementos.

En el código siguiente, en la primera llamada a la expresión lambda se proporcionan los argumentos 2 y 4, y devuelve 6; en la siguiente llamada se proporcionan los argumentos 6 y 10, por lo que el resultado es 16.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Convertir entre listas y otros tipos de colecciones

El módulo `List` proporciona funciones para convertir desde y hacia secuencias y matrices. Para convertir a o desde una secuencia, use [List. toseq (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) o [List. ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq). Para realizar la conversión a o desde una matriz, use [List. toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) o [List. myArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).

### <a name="additional-operations"></a>Otras operaciones

Para obtener información sobre otras operaciones en listas, vea el módulo de [lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)de temas de referencia de la biblioteca.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
- [Secuencias](sequences.md)
- [Matrices](arrays.md)
- [Opciones](options.md)
