---
title: Tipos de colección
description: Obtenga información F# sobre los tipos de colección y cómo se diferencian de los tipos de colección en el .NET Framework.
ms.date: 05/16/2016
ms.openlocfilehash: e5735efbffb1010f3886f3b32800a61e2d3b0d36
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344570"
---
# <a name="f-collection-types"></a>Tipos de colección F#

Al revisar este tema, puede determinar qué F# tipo de colección se adapta mejor a una necesidad concreta. Estos tipos de colección se diferencian de los tipos de colección en el .NET Framework, como los del espacio de nombres `System.Collections.Generic` F# , en que los tipos de colección están diseñados desde una perspectiva de programación funcional en lugar de una perspectiva orientada a objetos. Más concretamente, solo la colección de matrices tiene elementos mutables. Por lo tanto, cuando se modifica una colección, se crea una instancia de la colección modificada en lugar de modificar la colección original.

Los tipos de colección también difieren en el tipo de estructura de datos en el que se almacenan los objetos. Las estructuras de datos como las tablas hash, las listas vinculadas y las matrices tienen diferentes características de rendimiento y un conjunto diferente de operaciones disponibles.

## <a name="f-collection-types"></a>Tipos de colección F#

En la tabla siguiente F# se muestran los tipos de colección.

|Tipo de|Descripción|Vínculos relacionados|
|----|-----------|-------------|
|[List](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Una serie ordenada e inmutable de elementos del mismo tipo. Se implementa como una lista vinculada.|[Listas](lists.md)<br /><br />[Módulo de lista](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Matriz](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Colección mutable de tamaño fijo y de base cero de elementos de datos consecutivos que son del mismo tipo.|[Matrices](arrays.md)<br /><br />[Módulo de matriz](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Módulo Array2D](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Módulo Array3D](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Serie lógica de elementos que son todos de un tipo. Las secuencias son especialmente útiles cuando se tiene una colección grande ordenada de datos, pero no es necesario utilizar todos los elementos. Los elementos de secuencia individuales solo se calculan según sea necesario, por lo que una secuencia puede funcionar mejor que una lista si no se utilizan todos los elementos. Las secuencias se representan mediante el tipo de `seq<'T>`, que es un alias de `IEnumerable<T>`. Por lo tanto, cualquier tipo de .NET Framework que implementa `System.Collections.Generic.IEnumerable<'T>` puede usarse como una secuencia.|[Secuencias](sequences.md)<br /><br />[Seq (módulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Mapa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Diccionario inmutable de elementos. Se obtiene acceso a los elementos por clave.|[Módulo de asignación](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Conjunto inmutable que se basa en árboles binarios, donde la comparación F# es la función de comparación estructural, que potencialmente utiliza implementaciones de la interfaz `System.IComparable` en valores de clave.|[Establecer módulo](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabla de funciones

En esta sección se comparan las funciones que F# están disponibles en los tipos de colección. Se proporciona la complejidad computacional de la función, donde N es el tamaño de la primera colección y M es el tamaño de la segunda colección, si existe. Un guión (-) indica que esta función no está disponible en la colección. Dado que las secuencias se evalúan de forma diferida, una función como seq. DISTINCT puede ser O (1) porque vuelve inmediatamente, aunque todavía afecta al rendimiento de la secuencia cuando se enumera.

|Función|Matriz|Lista|Secuencia|Asignación|Set|Descripción|
|--------|-----|----|--------|---|---|-----------|
|append|O(M)|O (N)|O (N)|-|-|Devuelve una nueva colección que contiene los elementos de la primera colección seguidos de los elementos de la segunda colección.|
|agregar|-|-|-|O (log N)|O (log N)|Devuelve una nueva colección con el elemento agregado.|
|Media|O (N)|O (N)|O (N)|-|-|Devuelve el promedio de los elementos de la colección.|
|averageBy|O (N)|O (N)|O (N)|-|-|Devuelve el promedio de los resultados de la función proporcionada que se aplica a cada elemento.|
|fundir|O (N)|-|-|-|-|Copia una sección de una matriz.|
|caché|-|-|O (N)|-|-|Calcula y almacena elementos de una secuencia.|
|conversión|-|-|O (N)|-|-|Convierte los elementos en el tipo especificado.|
|elige|O (N)|O (N)|O (N)|-|-|Aplica la función especificada `f` a cada elemento `x` de la lista. Devuelve la lista que contiene los resultados de cada elemento en el que la función devuelve `Some(f(x))`.|
|recopilar|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a cada elemento de la colección, concatena todos los resultados y devuelve la lista combinada.|
|compareWith (|-|-|O (N)|-|-|Compara dos secuencias mediante la función de comparación especificada, elemento a elemento.|
|concat|O (N)|O (N)|O (N)|-|-|Combina la enumeración de enumeraciones dada como una sola enumeración concatenada.|
|contains|-|-|-|-|O (log N)|Devuelve true si el conjunto contiene el elemento especificado.|
|containsKey|-|-|-|O (log N)|-|Comprueba si un elemento está en el dominio de un mapa.|
|count|-|-|-|-|O (N)|Devuelve el número de elementos del conjunto.|
|countBy|-|-|O (N)|-|-|Aplica una función de generación de claves a cada elemento de una secuencia y devuelve una secuencia que produce claves únicas y su número de apariciones en la secuencia original.|
|copy|O (N)|-|O (N)|-|-|Copia la colección.|
|create|O (N)|-|-|-|-|Crea una matriz de elementos completos que son todos inicialmente el valor especificado.|
|delay|-|-|O (1)|-|-|Devuelve una secuencia que se genera a partir de la especificación retrasada especificada de una secuencia.|
|diferencia|-|-|-|-|O (Registro &#42; M N)|Devuelve un nuevo conjunto con los elementos del segundo conjunto que se han quitado del primer conjunto.|
|distinct|||O(1)&#42;|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones de igualdad y hash genéricas en las entradas. Si un elemento aparece varias veces en la secuencia, se descartan las repeticiones posteriores.|
|Distinctby (|||O(1)&#42;|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones de igualdad y hash genéricas de las claves que devuelve la función de generación de claves determinada. Si un elemento aparece varias veces en la secuencia, se descartan las repeticiones posteriores.|
|vacío|O (1)|O (1)|O (1)|O (1)|O (1)|Crea una colección vacía.|
|existe|O (N)|O (N)|O (N)|O (log N)|O (log N)|Comprueba si algún elemento de la secuencia satisface el predicado especificado.|
|exists2 (|O (min (N, M))|-|O (min (N, M))|||Comprueba si algún par de elementos correspondientes de las secuencias de entrada satisface el predicado especificado.|
|fill|O (N)|||||Establece un intervalo de elementos de la matriz en el valor especificado.|
|filtro|O (N)|O (N)|O (N)|O (N)|O (N)|Devuelve una nueva colección que contiene solo los elementos de la colección para los que el predicado especificado devuelve `true`.|
|find|O (N)|O (N)|O (N)|O (log N)|-|Devuelve el primer elemento para el que la función especificada devuelve `true`. Devuelve `System.Collections.Generic.KeyNotFoundException` si no existe ningún elemento de este tipo.|
|findIndex|O (N)|O (N)|O (N)|-|-|Devuelve el índice del primer elemento de la matriz que cumple el predicado especificado. Genera `System.Collections.Generic.KeyNotFoundException` si ningún elemento satisface el predicado.|
|findKey|-|-|-|O (log N)|-|Evalúa la función en cada asignación de la colección y devuelve la clave de la primera asignación en la que la función devuelve `true`. Si no existe ningún elemento de este tipo, esta función genera `System.Collections.Generic.KeyNotFoundException`.|
|plegar|O (N)|O (N)|O (N)|O (N)|O (N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f (... (f s I0)...) de.|
|fold2 (|O (N)|O (N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador a través del cálculo. Las colecciones deben tener tamaños idénticos. Si la función de entrada es f y los elementos son I0... En y J0... jN, esta función calcula f (... (f s I0 J0)...) En jN.|
|Foldback (|O (N)|O (N)|-|O (N)|O (N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f I0 (... (f en s)).|
|Foldback2 (|O (N)|O (N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador a través del cálculo. Las colecciones deben tener tamaños idénticos. Si la función de entrada es f y los elementos son I0... En y J0... jN, esta función calcula J0 de f I0 (... (f en jN s)).|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|Comprueba si todos los elementos de la colección satisfacen el predicado especificado.|
|forall2 (|O (N)|O (N)|O (N)|-|-|Comprueba si todos los elementos correspondientes de la colección satisfacen el predicado especificado en pares.|
|obtener/n|O (1)|O (N)|O (N)|-|-|Devuelve un elemento de la colección a partir de su índice.|
|head|-|O (1)|O (1)|-|-|Devuelve el primer elemento de la colección.|
|init|O (N)|O (N)|O (1)|-|-|Crea una colección a partir de la dimensión y una función de generador para calcular los elementos.|
|initInfinite|-|-|O (1)|-|-|Genera una secuencia que, cuando se itera, devuelve elementos sucesivos mediante una llamada a la función especificada.|
|Intersect|-|-|-|-|O (log N &#42; log M)|Calcula la intersección de dos conjuntos.|
|intersectMany|-|-|-|-|O (N1 &#42; N2...)|Calcula la intersección de una secuencia de conjuntos. La secuencia no debe estar vacía.|
|Vacío|O (1)|O (1)|O (1)|O (1)|-|Devuelve `true` si la colección está vacía.|
|isProperSubset|-|-|-|-|O (Registro &#42; M N)|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto y al menos un elemento del segundo conjunto no está en el primer conjunto.|
|isProperSuperset|-|-|-|-|O (Registro &#42; M N)|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto y al menos un elemento del primer conjunto no está en el segundo conjunto.|
|isSubset|-|-|-|-|O (Registro &#42; M N)|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto.|
|isSuperset|-|-|-|-|O (Registro &#42; M N)|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto.|
|ITER|O (N)|O (N)|O (N)|O (N)|O (N)|Aplica la función especificada a cada elemento de la colección.|
|ITERI (|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a cada elemento de la colección. El entero que se pasa a la función indica el índice del elemento.|
|iteri2|O (N)|O (N)|-|-|-|Aplica la función especificada a un par de elementos que se dibujan desde índices coincidentes en dos matrices. El entero que se pasa a la función indica el índice de los elementos. Las dos matrices deben tener la misma longitud.|
|iter2 (|O (N)|O (N)|O (N)|-|-|Aplica la función especificada a un par de elementos que se dibujan desde índices coincidentes en dos matrices. Las dos matrices deben tener la misma longitud.|
|last|O (1)|O (N)|O (N)|-|-|Devuelve el último elemento de la colección correspondiente.|
|longitud|O (1)|O (N)|O (N)|-|-|Devuelve el número de elementos de la colección.|
|map|O (N)|O (N)|O (1)|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a cada elemento de la matriz.|
|MAP2 (|O (N)|O (N)|O (1)|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares. Las dos matrices de entrada deben tener la misma longitud.|
|map3 (|-|O (N)|-|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las tres colecciones simultáneamente.|
|interfaz|O (N)|O (N)|O (N)|-|-|Crea una matriz cuyos elementos son los resultados de aplicar la función especificada a cada elemento de la matriz. El índice de entero que se pasa a la función indica el índice del elemento que se va a transformar.|
|mapi2|O (N)|O (N)|-|-|-|Compila una colección cuyos elementos son los resultados de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares, pasando también el índice de los elementos. Las dos matrices de entrada deben tener la misma longitud.|
|max|O (N)|O (N)|O (N)|-|-|Devuelve el mayor elemento de la colección, comparado mediante el operador [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) .|
|Maxby (|O (N)|O (N)|O (N)|-|-|Devuelve el mayor elemento de la colección, en comparación con el uso de [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) en el resultado de la función.|
|maxElement (|-|-|-|-|O (log N)|Devuelve el mayor elemento del conjunto según la ordenación usada para el conjunto.|
|min|O (N)|O (N)|O (N)|-|-|Devuelve el elemento mínimo de la colección, comparado mediante el operador [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) .|
|minBy (|O (N)|O (N)|O (N)|-|-|Devuelve el elemento mínimo de la colección, comparado mediante el operador [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) en el resultado de la función.|
|Minelement (|-|-|-|-|O (log N)|Devuelve el elemento más bajo del conjunto según la ordenación que se usa para el conjunto.|
|Ofarray (|-|O (N)|O (1)|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la matriz especificada.|
|Oflist (|O (N)|-|O (1)|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la lista especificada.|
|ofSeq|O (N)|O (N)|-|O (N)|O (N)|Crea una colección que contiene los mismos elementos que la secuencia especificada.|
|quería|-|-|O (N)|-|-|Devuelve una secuencia de cada elemento en la secuencia de entrada y su antecesor, excepto para el primer elemento, que solo se devuelve como predecesor del segundo elemento.|
|partition|O (N)|O (N)|-|O (N)|O (N)|Divide la colección en dos colecciones. La primera colección contiene los elementos para los que el predicado especificado devuelve `true`, y la segunda colección contiene los elementos para los que el predicado especificado devuelve `false`.|
|permute|O (N)|O (N)|-|-|-|Devuelve una matriz con todos los elementos permutados según la permutación especificada.|
|elegir|O (N)|O (N)|O (N)|O (log N)|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado en el que la función devuelve some. Si la función nunca devuelve some, se genera `System.Collections.Generic.KeyNotFoundException`.|
|readonly|-|-|O (N)|-|-|Crea un objeto de secuencia que delega en el objeto de secuencia especificado. Esta operación garantiza que una conversión de tipos no puede volver a detectar y mutar la secuencia original. Por ejemplo, si se proporciona una matriz, la secuencia devuelta devolverá los elementos de la matriz, pero no se puede convertir el objeto de secuencia devuelto en una matriz.|
|reduce|O (N)|O (N)|O (N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Esta función comienza aplicando la función a los dos primeros elementos, pasa este resultado a la función junto con el tercer elemento, y así sucesivamente. La función devuelve el resultado final.|
|Reduceback (|O (N)|O (N)|-|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Si la función de entrada es f y los elementos son I0... En, esta función calcula f I0 (... (f en-1 iN)).|
|remove|-|-|-|O (log N)|O (log N)|Quita un elemento del dominio de la asignación. No se produce ninguna excepción si el elemento no está presente.|
|réplica|-|O (N)|-|-|-|Crea una lista de una longitud especificada con cada elemento establecido en el valor especificado.|
|Rev|O (N)|O (N)|-|-|-|Devuelve una nueva lista con los elementos en orden inverso.|
|revisar|O (N)|O (N)|O (N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador a través del cálculo. Esta operación aplica la función al segundo argumento y al primer elemento de la lista. A continuación, la operación pasa este resultado a la función junto con el segundo elemento, etc. Por último, la operación devuelve la lista de resultados intermedios y el resultado final.|
|ScanBack (|O (N)|O (N)|-|-|-|Se parece a la operación foldBack pero devuelve los resultados intermedios y finales.|
|singleton|-|-|O (1)|-|O (1)|Devuelve una secuencia que produce un solo elemento.|
|establecer|O (1)|-|-|-|-|Establece un elemento de una matriz en el valor especificado.|
|skip|-|-|O (N)|-|-|Devuelve una secuencia que omite N elementos de la secuencia subyacente y, a continuación, produce los elementos restantes de la secuencia.|
|Skipwhile (|-|-|O (N)|-|-|Devuelve una secuencia que, cuando se itera, omite los elementos de la secuencia subyacente mientras el predicado especificado devuelve `true` y, a continuación, produce los elementos restantes de la secuencia.|
|sort|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|O (N log N)|O (N log N)|-|-|Ordena la colección por valor de elemento. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy (|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|O (N log N)|O (N log N)|-|-|Ordena la lista especificada mediante el uso de claves que proporciona la proyección especificada. Las claves se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|Sortinplace (|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la función de comparación especificada. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la proyección especificada para las claves. Los elementos se comparan mediante [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|-|-|-|-|Ordena los elementos de una matriz mediante la mutación y el uso de la función de comparación especificada como el orden.|
|sortWith (|Promedio de O (N log N)<br /><br />O (N ^ 2) peor de los casos|O (N log N)|-|-|-|Ordena los elementos de una colección, usando la función de comparación especificada como el orden y devuelve una nueva colección.|
|sub|O (N)|-|-|-|-|Crea una matriz que contiene el subintervalo dado especificado por el índice de inicio y la longitud.|
|sum|O (N)|O (N)|O (N)|-|-|Devuelve la suma de los elementos de la colección.|
|sumBy|O (N)|O (N)|O (N)|-|-|Devuelve la suma de los resultados que se generan aplicando la función a cada elemento de la colección.|
|cola|-|O (1)|-|-|-|Devuelve la lista sin su primer elemento.|
|take|-|-|O (N)|-|-|Devuelve los elementos de la secuencia hasta un recuento especificado.|
|takeWhile|-|-|O (1)|-|-|Devuelve una secuencia que, cuando se itera, proporciona elementos de la secuencia subyacente mientras el predicado especificado devuelve `true` y, a continuación, no devuelve ningún elemento más.|
|toArray (|-|O (N)|O (N)|O (N)|O (N)|Crea una matriz a partir de la colección especificada.|
|toList|O (N)|-|O (N)|O (N)|O (N)|Crea una lista a partir de la colección especificada.|
|toSeq|O (1)|O (1)|-|O (1)|O (1)|Crea una secuencia a partir de la colección especificada.|
|truncate|-|-|O (1)|-|-|Devuelve una secuencia que, cuando se enumera, no devuelve más de N elementos.|
|tryFind|O (N)|O (N)|O (N)|O (log N)|-|Busca un elemento que satisface un predicado determinado.|
|tryFindIndex|O (N)|O (N)|O (N)|-|-|Busca el primer elemento que cumple un predicado especificado y devuelve el índice del elemento coincidente, o bien `None` si no existe ese elemento.|
|tryFindKey|-|-|-|O (log N)|-|Devuelve la clave de la primera asignación de la colección que satisface el predicado especificado o devuelve `None` si no existe ese elemento.|
|tryPick (|O (N)|O (N)|O (N)|O (log N)|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado en el que la función devuelve `Some` para algún valor. Si no existe ningún elemento de este tipo, la operación devuelve `None`.|
|Fold|-|-|O (N)|-|-|Devuelve una secuencia que contiene los elementos generados por el cálculo especificado.|
|unión|-|-|-|-|O (Registro &#42; M N)|Calcula la Unión de los dos conjuntos.|
|unionMany (|-|-|-|-|O (N1 &#42; N2...)|Calcula la Unión de una secuencia de conjuntos.|
|unzip|O (N)|O (N)|O (N)|-|-|Divide una lista de pares en dos listas.|
|unzip3 (|O (N)|O (N)|O (N)|-|-|Divide una lista de triples en tres listas.|
|ventanas|-|-|O (N)|-|-|Devuelve una secuencia que produce ventanas deslizantes de elementos contenedores que se extraen de la secuencia de entrada. Cada ventana se devuelve como una nueva matriz.|
|zip|O (N)|O (N)|O (N)|-|-|Combina las dos colecciones en una lista de pares. Las dos listas deben tener la misma longitud.|
|zip3 (|O (N)|O (N)|O (N)|-|-|Combina las tres colecciones en una lista de triples. Las listas deben tener la misma longitud.|

## <a name="see-also"></a>Vea también

- [Tipos en F#](fsharp-types.md)
- [Referencia del lenguaje F#](index.md)
