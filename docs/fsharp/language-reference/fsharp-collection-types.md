---
title: Tipos de colección
description: 'Obtenga información sobre los tipos de colección de F # y cómo se diferencian de los tipos de colección .NET.'
ms.date: 08/14/2020
ms.openlocfilehash: 394f6bbaf58e7e8607abc3a0c20bbc2b1c9c3c8d
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656910"
---
# <a name="f-collection-types"></a>Tipos de colección F#

Al revisar este tema, puede determinar qué tipo de colección de F # se adapta mejor a una necesidad concreta. Estos tipos de colección se diferencian de los tipos de colección en .NET, como los del `System.Collections.Generic` espacio de nombres, en que los tipos de colección de F # están diseñados desde una perspectiva de programación funcional en lugar de una perspectiva orientada a objetos. Más concretamente, solo la colección de matrices tiene elementos mutables. Por lo tanto, cuando se modifica una colección, se crea una instancia de la colección modificada en lugar de modificar la colección original.

Los tipos de colección también difieren en el tipo de estructura de datos en el que se almacenan los objetos. Las estructuras de datos como las tablas hash, las listas vinculadas y las matrices tienen diferentes características de rendimiento y un conjunto diferente de operaciones disponibles.

## <a name="f-collection-types"></a>Tipos de colección F#

En la tabla siguiente se muestran los tipos de colección de F #.

|Tipo|Descripción|Vínculos relacionados|
|----|-----------|-------------|
|[Lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharplist-1.html)|Una serie ordenada e inmutable de elementos del mismo tipo. Se implementa como una lista vinculada.|[Listas](lists.md)<br /><br />[List (Módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)|
|[Array](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-array-1.html)|Colección mutable de tamaño fijo y de base cero de elementos de datos consecutivos que son del mismo tipo.|[Matrices](arrays.md)<br /><br />[Array (Módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html)<br /><br />[Array2D (Módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html)<br /><br />[Array3D (Módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array3dmodule.html)|
|[Próx](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seq-1.html)|Serie lógica de elementos que son todos de un tipo. Las secuencias son especialmente útiles cuando se tiene una colección grande ordenada de datos, pero no es necesario utilizar todos los elementos. Los elementos de secuencia individuales solo se calculan según sea necesario, por lo que una secuencia puede funcionar mejor que una lista si no se utilizan todos los elementos. Las secuencias se representan mediante el `seq<'T>` tipo, que es un alias para `IEnumerable<T>` . Por lo tanto, cualquier tipo de .NET Framework que implementa `System.Collections.Generic.IEnumerable<'T>` puede usarse como una secuencia.|[Secuencias](sequences.md)<br /><br />[Seq (módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html)|
|[Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpmap-2.html)|Diccionario inmutable de elementos. Se obtiene acceso a los elementos por clave.|[Módulo de asignación](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-mapmodule.html)|
|[Establecimiento](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpset-1.html)|Conjunto inmutable que se basa en árboles binarios, donde la comparación es la función de comparación estructural de F #, que puede usar implementaciones de la `System.IComparable` interfaz en valores de clave.|[Establecer módulo](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-setmodule.html)|

### <a name="table-of-functions"></a>Tabla de funciones

En esta sección se comparan las funciones que están disponibles en los tipos de colección de F #. Se proporciona la complejidad computacional de la función, donde N es el tamaño de la primera colección y M es el tamaño de la segunda colección, si existe. Un guión (-) indica que esta función no está disponible en la colección. Dado que las secuencias se evalúan de forma diferida, una función como seq. DISTINCT puede ser O (1) porque vuelve inmediatamente, aunque todavía afecta al rendimiento de la secuencia cuando se enumera.

|Función|Array|List|Secuencia|Map|Set|Descripción|
|--------|-----|----|--------|---|---|-----------|
|append|O (N)|O (N)|O (N)|-|-|Devuelve una nueva colección que contiene los elementos de la primera colección seguidos de los elementos de la segunda colección.|
|add|-|-|-|O (log (N))|O (log (N))|Devuelve una nueva colección con el elemento agregado.|
|average|O (N)|O (N)|O (N)|-|-|Devuelve el promedio de los elementos de la colección.|
|averageBy|O (N)|O (N)|O (N)|-|-|Devuelve el promedio de los resultados de la función proporcionada que se aplica a cada elemento.|
|fundir|O (N)|-|-|-|-|Copia una sección de una matriz.|
|caché|-|-|O (N)|-|-|Calcula y almacena elementos de una secuencia.|
|conversión|-|-|O (N)|-|-|Convierte los elementos en el tipo especificado.|
|choose|O (N)|O (N)|O (N)|-|-|Aplica la función especificada `f` a cada elemento `x` de la lista. Devuelve la lista que contiene los resultados de cada elemento en el que la función devuelve `Some(f(x))` .|
|collect|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a cada elemento de la colección, concatena todos los resultados y devuelve la lista combinada.|
|compareWith (|-|-|O (N)|-|-|Compara dos secuencias mediante la función de comparación especificada, elemento a elemento.|
|concat|O (N)|O (N)|O (N)|-|-|Combina la enumeración de enumeraciones dada como una sola enumeración concatenada.|
|contains|-|-|-|-|O (log (N))|Devuelve true si el conjunto contiene el elemento especificado.|
|ContainsKey (|-|-|-|O (log (N))|-|Comprueba si un elemento está en el dominio de un mapa.|
|count|-|-|-|-|O (N)|Devuelve el número de elementos del conjunto.|
|CountBy (|-|-|O (N)|-|-|Aplica una función de generación de claves a cada elemento de una secuencia y devuelve una secuencia que produce claves únicas y su número de apariciones en la secuencia original.|
|copy|O (N)|-|O (N)|-|-|Copia la colección.|
|create|O (N)|-|-|-|-|Crea una matriz de elementos completos que son todos inicialmente el valor especificado.|
|delay|-|-|O(1)|-|-|Devuelve una secuencia que se genera a partir de la especificación retrasada especificada de una secuencia.|
|diferencia|-|-|-|-|O ( \* registro M (N))|Devuelve un nuevo conjunto con los elementos del segundo conjunto que se han quitado del primer conjunto.|
|distinct|||O(1)\*|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones de igualdad y hash genéricas en las entradas. Si un elemento aparece varias veces en la secuencia, se descartan las repeticiones posteriores.|
|Distinctby (|||O(1)\*|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones de igualdad y hash genéricas de las claves que devuelve la función de generación de claves determinada. Si un elemento aparece varias veces en la secuencia, se descartan las repeticiones posteriores.|
|empty|O(1)|O(1)|O(1)|O(1)|O(1)|Crea una colección vacía.|
|exists|O (N)|O (N)|O (N)|O (log (N))|O (log (N))|Comprueba si algún elemento de la secuencia satisface el predicado especificado.|
|exists2 (|O (min (N, M))|-|O (min (N, M))|||Comprueba si algún par de elementos correspondientes de las secuencias de entrada satisface el predicado especificado.|
|fill|O (N)|||||Establece un intervalo de elementos de la matriz en el valor especificado.|
|filter|O (N)|O (N)|O (N)|O (N)|O (N)|Devuelve una nueva colección que contiene solo los elementos de la colección para los que el predicado especificado devuelve `true` .|
|find|O (N)|O (N)|O (N)|O (log (N))|-|Devuelve el primer elemento para el que devuelve la función especificada `true` . Devuelve `System.Collections.Generic.KeyNotFoundException` si no existe ningún elemento de este tipo.|
|FindIndex (|O (N)|O (N)|O (N)|-|-|Devuelve el índice del primer elemento de la matriz que cumple el predicado especificado. Se produce `System.Collections.Generic.KeyNotFoundException` si ningún elemento cumple el predicado.|
|findKey|-|-|-|O (log (N))|-|Evalúa la función en cada asignación de la colección y devuelve la clave de la primera asignación en la que se devuelve la función `true` . Si no existe ningún elemento de este tipo, esta función genera `System.Collections.Generic.KeyNotFoundException` .|
|doblar|O (N)|O (N)|O (N)|O (N)|O (N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f (... (f s I0)...) de.|
|fold2 (|O (N)|O (N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador a través del cálculo. Las colecciones deben tener tamaños idénticos. Si la función de entrada es f y los elementos son I0... En y J0... jN, esta función calcula f (... (f s I0 J0)...) En jN.|
|Foldback (|O (N)|O (N)|-|O (N)|O (N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f I0 (... (f en s)).|
|Foldback2 (|O (N)|O (N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador a través del cálculo. Las colecciones deben tener tamaños idénticos. Si la función de entrada es f y los elementos son I0... En y J0... jN, esta función calcula J0 de f I0 (... (f en jN s)).|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|Comprueba si todos los elementos de la colección satisfacen el predicado especificado.|
|forall2 (|O (N)|O (N)|O (N)|-|-|Comprueba si todos los elementos correspondientes de la colección satisfacen el predicado especificado en pares.|
|obtener/n|O(1)|O (N)|O (N)|-|-|Devuelve un elemento de la colección a partir de su índice.|
|head|-|O(1)|O(1)|-|-|Devuelve el primer elemento de la colección.|
|init|O (N)|O (N)|O(1)|-|-|Crea una colección a partir de la dimensión y una función de generador para calcular los elementos.|
|initInfinite (|-|-|O(1)|-|-|Genera una secuencia que, cuando se itera, devuelve elementos sucesivos mediante una llamada a la función especificada.|
|intersect|-|-|-|-|O (log (N) \* log (M))|Calcula la intersección de dos conjuntos.|
|Intersectmany (|-|-|-|-|O (N1 \* N2...)|Calcula la intersección de una secuencia de conjuntos. La secuencia no debe estar vacía.|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|Devuelve `true` si la colección está vacía.|
|Ispropersubset (|-|-|-|-|O ( \* registro M (N))|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto y al menos un elemento del segundo conjunto no está en el primer conjunto.|
|Ispropersuperset (|-|-|-|-|O ( \* registro M (N))|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto y al menos un elemento del primer conjunto no está en el segundo conjunto.|
|isSubset (|-|-|-|-|O ( \* registro M (N))|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto.|
|Issuperset (|-|-|-|-|O ( \* registro M (N))|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto.|
|ITER|O (N)|O (N)|O (N)|O (N)|O (N)|Aplica la función especificada a cada elemento de la colección.|
|ITERI (|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a cada elemento de la colección. El entero que se pasa a la función indica el índice del elemento.|
|iteri2 (|O (N)|O (N)|-|-|-|Aplica la función especificada a un par de elementos que se dibujan desde índices coincidentes en dos matrices. El entero que se pasa a la función indica el índice de los elementos. Las dos matrices deben tener la misma longitud.|
|iter2 (|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a un par de elementos que se dibujan desde índices coincidentes en dos matrices. Las dos matrices deben tener la misma longitud.|
|last|O(1)|O (N)|O (N)|-|-|Devuelve el último elemento de la colección correspondiente.|
|length|O(1)|O (N)|O (N)|-|-|Devuelve el número de elementos de la colección.|
|map|O (N)|O (N)|O(1)|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a cada elemento de la matriz.|
|MAP2 (|O (N)|O (N)|O(1)|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares. Las dos matrices de entrada deben tener la misma longitud.|
|map3 (|-|O (N)|-|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las tres colecciones simultáneamente.|
|interfaz|O (N)|O (N)|O (N)|-|-|Crea una matriz cuyos elementos son los resultados de aplicar la función especificada a cada elemento de la matriz. El índice de entero que se pasa a la función indica el índice del elemento que se va a transformar.|
|mapi2 (|O (N)|O (N)|-|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares, pasando también el índice de los elementos. Las dos matrices de entrada deben tener la misma longitud.|
|max|O (N)|O (N)|O (N)|-|-|Devuelve el mayor elemento de la colección, comparado mediante el operador [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) .|
|Maxby (|O (N)|O (N)|O (N)|-|-|Devuelve el mayor elemento de la colección, en comparación con el uso de [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) en el resultado de la función.|
|maxElement (|-|-|-|-|O (log (N))|Devuelve el mayor elemento del conjunto según la ordenación usada para el conjunto.|
|Min|O (N)|O (N)|O (N)|-|-|Devuelve el elemento mínimo de la colección, comparado mediante el operador [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) .|
|minBy (|O (N)|O (N)|O (N)|-|-|Devuelve el elemento mínimo de la colección, comparado mediante el operador [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) en el resultado de la función.|
|Minelement (|-|-|-|-|O (log (N))|Devuelve el elemento más bajo del conjunto según la ordenación que se usa para el conjunto.|
|Ofarray (|-|O (N)|O(1)|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la matriz especificada.|
|Oflist (|O (N)|-|O(1)|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la lista especificada.|
|ofSeq|O (N)|O (N)|-|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la secuencia especificada.|
|quería|-|-|O (N)|-|-|Devuelve una secuencia de cada elemento en la secuencia de entrada y su antecesor, excepto para el primer elemento, que solo se devuelve como predecesor del segundo elemento.|
|partición|O (N)|O (N)|-|O (N)|O (N)|Divide la colección en dos colecciones. La primera colección contiene los elementos para los que el predicado especificado devuelve `true` y la segunda colección contiene los elementos para los que el predicado especificado devuelve `false` .|
|permute|O (N)|O (N)|-|-|-|Devuelve una matriz con todos los elementos permutados según la permutación especificada.|
|elegir|O (N)|O (N)|O (N)|O (log (N))|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado en el que la función devuelve some. Si la función nunca devuelve some, `System.Collections.Generic.KeyNotFoundException` se genera.|
|readonly|-|-|O (N)|-|-|Crea un objeto de secuencia que delega en el objeto de secuencia especificado. Esta operación garantiza que una conversión de tipos no puede volver a detectar y mutar la secuencia original. Por ejemplo, si se proporciona una matriz, la secuencia devuelta devolverá los elementos de la matriz, pero no se puede convertir el objeto de secuencia devuelto en una matriz.|
|reduce|O (N)|O (N)|O (N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Esta función comienza aplicando la función a los dos primeros elementos, pasa este resultado a la función junto con el tercer elemento, y así sucesivamente. La función devuelve el resultado final.|
|Reduceback (|O (N)|O (N)|-|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f I0 (... (f en-1 iN)).|
|remove|-|-|-|O (log (N))|O (log (N))|Quita un elemento del dominio de la asignación. No se produce ninguna excepción si el elemento no está presente.|
|réplica|-|O (N)|-|-|-|Crea una lista de una longitud especificada con cada elemento establecido en el valor especificado.|
|Rev|O (N)|O (N)|-|-|-|Devuelve una nueva lista con los elementos en orden inverso.|
|revisar|O (N)|O (N)|O (N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Esta operación aplica la función al segundo argumento y al primer elemento de la lista. A continuación, la operación pasa este resultado a la función junto con el segundo elemento, etc. Por último, la operación devuelve la lista de resultados intermedios y el resultado final.|
|ScanBack (|O (N)|O (N)|-|-|-|Se parece a la operación foldBack pero devuelve los resultados intermedios y finales.|
|singleton|-|-|O(1)|-|O(1)|Devuelve una secuencia que produce un solo elemento.|
|set|O(1)|-|-|-|-|Establece un elemento de una matriz en el valor especificado.|
|skip|-|-|O (N)|-|-|Devuelve una secuencia que omite N elementos de la secuencia subyacente y, a continuación, produce los elementos restantes de la secuencia.|
|Skipwhile (|-|-|O (N)|-|-|Devuelve una secuencia que, cuando se itera, omite los elementos de la secuencia subyacente mientras el predicado especificado devuelve `true` y, a continuación, produce los elementos restantes de la secuencia.|
|sort|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|O (N \* registro (n))|O (N \* registro (n))|-|-|Ordena la colección por valor de elemento. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|O (N \* registro (n))|O (N \* registro (n))|-|-|Ordena la lista especificada mediante el uso de claves que proporciona la proyección especificada. Las claves se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|Sortinplace (|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la función de comparación especificada. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|Sortinplaceby (|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la proyección especificada para las claves. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith (|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la función de comparación especificada como el orden.|
|sortWith (|O (N \* log (n)) promedio<br /><br />O (N ^ 2) peor de los casos|O (N \* registro (n))|-|-|-|Ordena los elementos de una colección, usando la función de comparación especificada como el orden y devuelve una nueva colección.|
|sub|O (N)|-|-|-|-|Crea una matriz que contiene el subintervalo dado especificado por el índice de inicio y la longitud.|
|Sum|O (N)|O (N)|O (N)|-|-|Devuelve la suma de los elementos de la colección.|
|sumBy (|O (N)|O (N)|O (N)|-|-|Devuelve la suma de los resultados que se generan aplicando la función a cada elemento de la colección.|
|cola|-|O(1)|-|-|-|Devuelve la lista sin su primer elemento.|
|take|-|-|O (N)|-|-|Devuelve los elementos de la secuencia hasta un recuento especificado.|
|takeWhile|-|-|O(1)|-|-|Devuelve una secuencia que, cuando se itera, proporciona elementos de la secuencia subyacente mientras el predicado especificado devuelve `true` y, a continuación, no devuelve ningún elemento más.|
|toArray (|-|O (N)|O (N)|O (N)|O (N)|Crea una matriz a partir de la colección especificada.|
|toList|O (N)|-|O (N)|O (N)|O (N)|Crea una lista a partir de la colección especificada.|
|Toseq (|O(1)|O(1)|-|O(1)|O(1)|Crea una secuencia a partir de la colección especificada.|
|truncate|-|-|O(1)|-|-|Devuelve una secuencia que, cuando se enumera, no devuelve más de N elementos.|
|tryFind|O (N)|O (N)|O (N)|O (log (N))|-|Busca un elemento que satisface un predicado determinado.|
|Tryfindindex (|O (N)|O (N)|O (N)|-|-|Busca el primer elemento que cumple un predicado especificado y devuelve el índice del elemento coincidente, o `None` si no existe ese elemento.|
|Tryfindkey (|-|-|-|O (log (N))|-|Devuelve la clave de la primera asignación de la colección que satisface el predicado especificado, o devuelve `None` si no existe ese elemento.|
|tryPick (|O (N)|O (N)|O (N)|O (log (N))|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado en el que la función devuelve `Some` un valor. Si no existe ningún elemento de este tipo, la operación devuelve `None` .|
|Fold|-|-|O (N)|-|-|Devuelve una secuencia que contiene los elementos generados por el cálculo especificado.|
|union|-|-|-|-|O ( \* registro M (N))|Calcula la Unión de los dos conjuntos.|
|unionMany (|-|-|-|-|O (N1 \* N2...)|Calcula la Unión de una secuencia de conjuntos.|
|unzip|O (N)|O (N)|O (N)|-|-|Divide una lista de pares en dos listas.|
|unzip3 (|O (N)|O (N)|O (N)|-|-|Divide una lista de triples en tres listas.|
|ventanas|-|-|O (N)|-|-|Devuelve una secuencia que produce ventanas deslizantes de elementos contenedores que se extraen de la secuencia de entrada. Cada ventana se devuelve como una nueva matriz.|
|zip|O (N)|O (N)|O (N)|-|-|Combina las dos colecciones en una lista de pares. Las dos listas deben tener la misma longitud.|
|zip3 (|O (N)|O (N)|O (N)|-|-|Combina las tres colecciones en una lista de triples. Las listas deben tener la misma longitud.|

## <a name="see-also"></a>Consulte también

- [Tipos en F#](fsharp-types.md)
- [Referencia del lenguaje F#](index.md)
