---
title: Tipos de colección F#
description: Obtenga información sobre F# tipos de colección y cómo se diferencian de los tipos de colección en .NET Framework.
ms.date: 05/16/2016
ms.openlocfilehash: b370d850deaacc961dff9515ffa8c20634af4ed6
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041723"
---
# <a name="f-collection-types"></a>Tipos de colección F#

Al revisar este tema, puede determinar qué F# tipo de colección que mejor se adapte a una necesidad concreta. Estos tipos de colección difieren de los tipos de colección en .NET Framework, como los de la `System.Collections.Generic` espacio de nombres, en el que el F# tipos de colección están diseñados desde una perspectiva de la programación funcional en lugar de orientado a objetos perspectiva. Más concretamente, solo la colección de matriz tiene elementos mutables. Por lo tanto, cuando se modifica una colección, cree una instancia de la colección modificada en lugar de modificar la colección original.

Tipos de colección también difieren en el tipo de estructura de datos en el que se almacenan los objetos. Estructuras de datos como tablas hash, listas vinculadas y las matrices tienen distintas características de rendimiento y un conjunto diferente de las operaciones disponibles.

## <a name="f-collection-types"></a>Tipos de colección F#

La tabla siguiente muestra F# tipos de colección.

|Tipo|Descripción|Vínculos relacionados|
|----|-----------|-------------|
|[List](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Una serie ordenada e inmutable de elementos del mismo tipo. Se implementa como una lista vinculada.|[Listas](lists.md)<br /><br />[List (módulo)](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[matriz](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Una colección de tamaño fijo, basado en cero, mutable de elementos de datos consecutivos que son todas del mismo tipo.|[Matrices](arrays.md)<br /><br />[Array (módulo)](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Array2D módulo](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Array3D módulo](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Una serie lógica de elementos que son del mismo tipo. Las secuencias son especialmente útiles cuando disponga de una gran colección ordenada de datos pero no espere usar todos los elementos. Secuencia individual se calculan los elementos sólo como necesario, por lo que una secuencia puede funcionar mejor que una lista si no se usan todos los elementos. Las secuencias se representan mediante el `seq<'T>` tipo, que es un alias para `IEnumerable<T>`. Por lo tanto, cualquier tipo de .NET Framework que implementa `System.Collections.Generic.IEnumerable<'T>` puede usarse como una secuencia.|[Secuencias](sequences.md)<br /><br />[Seq (módulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Mapa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Diccionario inmutable de elementos. Se tiene acceso a los elementos por clave.|[Map (módulo)](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Un conjunto inmutable que se basa en árboles binarios, donde la comparación es el F# función de comparación estructural, que potencialmente usa implementaciones de la `System.IComparable` interfaz en los valores de clave.|[Establecer módulo](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabla de funciones

Esta sección comparan las funciones que están disponibles en F# tipos de colección. La complejidad del cálculo de la función se especifica, donde N es el tamaño de la primera colección, y M es el tamaño de la segunda colección, si existe. Un guión (-) indica que esta función no está disponible en la colección. Dado que las secuencias se evalúan de forma diferida, una función como Seq.distinct puede ser o (1) porque devuelve inmediatamente, aunque todavía afecta al rendimiento de la secuencia cuando se enumera.

|Función|Matriz|Lista|Secuencia|Asignación|Set|Descripción|
|--------|-----|----|--------|---|---|-----------|
|append|APROXIMADO|O(N)|O(N)|-|-|Devuelve una nueva colección que contiene los elementos de la primera colección seguidos por elementos de la segunda colección.|
|agregar|-|-|-|O (log N)|O (log N)|Devuelve una nueva colección con el elemento agregado.|
|Promedio|O(N)|O(N)|O(N)|-|-|Devuelve el promedio de los elementos de la colección.|
|averageBy|O(N)|O(N)|O(N)|-|-|Devuelve el promedio de los resultados de la función proporcionada que se aplica a cada elemento.|
|blit|O(N)|-|-|-|-|Copia una sección de una matriz.|
|caché|-|-|O(N)|-|-|Calcula y almacena los elementos de una secuencia.|
|conversión|-|-|O(N)|-|-|Convierte los elementos en el tipo especificado.|
|Elija|O(N)|O(N)|O(N)|-|-|Aplica la función especificada `f` a cada elemento `x` de la lista. Devuelve la lista que contiene los resultados para cada elemento de la cual la función devuelve `Some(f(x))`.|
|recopilar|O(N)|O(N)|O(N)|-|-|Aplica la función especificada a cada elemento de la colección, concatena todos los resultados y devuelve la lista combinada.|
|compareWith|-|-|O(N)|-|-|Compara dos secuencias mediante la función de comparación especificada, elemento por elemento.|
|concat|O(N)|O(N)|O(N)|-|-|Combina el determinado enumeración de enumeraciones como una sola enumeración concatenada.|
|contains|-|-|-|-|O (log N)|Devuelve true si el conjunto contiene el elemento especificado.|
|containsKey|-|-|-|O (log N)|-|Comprueba si un elemento está en el dominio de un mapa.|
|count|-|-|-|-|O(N)|Devuelve el número de elementos del conjunto.|
|countBy|-|-|O(N)|-|-|Aplica una función de generación de claves a cada elemento de una secuencia y devuelve una secuencia que genera claves únicas y su número de apariciones de la secuencia original.|
|copy|O(N)|-|O(N)|-|-|Copia la colección.|
|create|O(N)|-|-|-|-|Crea una matriz de elementos enteros que son todos inicialmente el valor especificado.|
|Retraso|-|-|O(1)|-|-|Devuelve una secuencia que se basa en la especificación retrasada dada de una secuencia.|
|diferencia|-|-|-|-|O (M &#42; log N)|Devuelve un nuevo conjunto con los elementos del segundo conjunto quitados del primer conjunto.|
|DISTINCT|||O(1)&#42;|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones de hash e igualdad genéricas en las entradas. Si un elemento aparece varias veces en la secuencia, se descartan las apariciones posteriores.|
|distinctBy|||O(1)&#42;|||Devuelve una secuencia que no contiene ninguna entrada duplicada según las comparaciones genéricas hash e igualdad de las claves que devuelve la función de generación de claves especificada. Si un elemento aparece varias veces en la secuencia, se descartan las apariciones posteriores.|
|vacío|O(1)|O(1)|O(1)|O(1)|O(1)|Crea una colección vacía.|
|exists|O(N)|O(N)|O(N)|O (log N)|O (log N)|Comprueba si algún elemento de la secuencia cumple el predicado especificado.|
|exists2|O(min(N,M))|-|O(min(N,M))|||Comprueba si algún par de elementos correspondientes de las secuencias de entrada cumple el predicado especificado.|
|fill|O(N)|||||Establece un intervalo de elementos de la matriz en el valor especificado.|
|filtro|O(N)|O(N)|O(N)|O(N)|O(N)|Devuelve una nueva colección que contiene solo los elementos de la colección para los cuales el predicado especificado devuelve `true`.|
|find|O(N)|O(N)|O(N)|O (log N)|-|Devuelve el primer elemento para el cual la función especificada devuelve `true`. Devuelve `System.Collections.Generic.KeyNotFoundException` si no existe ese elemento.|
|findIndex|O(N)|O(N)|O(N)|-|-|Devuelve el índice del primer elemento de la matriz que cumple el predicado especificado. Genera `System.Collections.Generic.KeyNotFoundException` si ningún elemento satisface el predicado.|
|findKey|-|-|-|O (log N)|-|Evalúa la función en cada asignación de la colección y devuelve la clave de la primera asignación donde la función devuelve `true`. Si no existe ese elemento, esta función genera `System.Collections.Generic.KeyNotFoundException`.|
|plegamiento|O(N)|O(N)|O(N)|O(N)|O(N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador durante el cálculo. Si la función de entrada es f y los elementos son i0... iN, esta función calcula f (...) (f s i0)...) En.|
|fold2|O(N)|O(N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador durante el cálculo. Las colecciones deben tener el mismo tamaño. Si la función de entrada es f y los elementos son i0... iN y j0... jN, esta función calcula f (...) (f s i0 j0)...) En jN.|
|foldBack|O(N)|O(N)|-|O(N)|O(N)|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador durante el cálculo. Si la función de entrada es f y los elementos son i0... iN, esta función calcula f i0 (...) (f en s)).|
|foldBack2|O(N)|O(N)|-|-|-|Aplica una función a los elementos correspondientes de dos colecciones y subprocesa un argumento acumulador durante el cálculo. Las colecciones deben tener el mismo tamaño. Si la función de entrada es f y los elementos son i0... iN y j0... jN, esta función calcula f i0 j0 (...) (f en jN s)).|
|ForAll|O(N)|O(N)|O(N)|O(N)|O(N)|Comprueba si todos los elementos de la colección satisfacen el predicado especificado.|
|forall2|O(N)|O(N)|O(N)|-|-|Comprueba si todos los elementos correspondientes de la colección satisfacen el predicado especificado en pares.|
|obtener / n|O(1)|O(N)|O(N)|-|-|Devuelve un elemento de la colección según su índice.|
|head|-|O(1)|O(1)|-|-|Devuelve el primer elemento de la colección.|
|init|O(N)|O(N)|O(1)|-|-|Crea una colección que especifican la dimensión y una función de generador para calcular los elementos.|
|initInfinite|-|-|O(1)|-|-|Genera una secuencia que, cuando se itera, devuelve los elementos sucesivos mediante una llamada a la función especificada.|
|intersect|-|-|-|-|O (log N &#42; registro M)|Calcula la intersección de dos conjuntos.|
|intersectMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcula la intersección de una secuencia de conjuntos. La secuencia no debe estar vacía.|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|Devuelve `true` si la colección está vacía.|
|isProperSubset|-|-|-|-|O (M &#42; log N)|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto, y al menos un elemento del segundo conjunto no se encuentra en el primer conjunto.|
|isProperSuperset|-|-|-|-|O (M &#42; log N)|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto y, al menos un elemento del primer conjunto no se encuentra en el segundo conjunto.|
|isSubset|-|-|-|-|O (M &#42; log N)|Devuelve `true` si todos los elementos del primer conjunto se encuentran en el segundo conjunto.|
|isSuperset|-|-|-|-|O (M &#42; log N)|Devuelve `true` si todos los elementos del segundo conjunto se encuentran en el primer conjunto.|
|ITER|O(N)|O(N)|O(N)|O(N)|O(N)|Aplica la función especificada a cada elemento de la colección.|
|iteri|O(N)|O(N)|O(N)|-|-|Aplica la función especificada a cada elemento de la colección. El entero que se pasa a la función indica el índice del elemento.|
|iteri2|O(N)|O(N)|-|-|-|Aplica la función especificada a un par de elementos que se extraen de los índices correspondientes de dos matrices. El entero que se pasa a la función indica el índice de los elementos. Las dos matrices deben tener la misma longitud.|
|iter2|O(N)|O(N)|O(N)|-|-|Aplica la función especificada a un par de elementos que se extraen de los índices correspondientes de dos matrices. Las dos matrices deben tener la misma longitud.|
|last|O(1)|O(N)|O(N)|-|-|Devuelve el último elemento de la colección aplicable.|
|longitud|O(1)|O(N)|O(N)|-|-|Devuelve el número de elementos de la colección.|
|map|O(N)|O(N)|O(1)|-|-|Compila una colección cuyos elementos son el resultado de aplicar la función especificada a cada elemento de la matriz.|
|map2|O(N)|O(N)|O(1)|-|-|Compila una colección cuyos elementos son el resultado de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares. Las dos matrices de entrada deben tener la misma longitud.|
|map3|-|O(N)|-|-|-|Compila una colección cuyos elementos son el resultado de aplicar la función especificada a los elementos correspondientes de las tres colecciones simultáneamente.|
|mapi|O(N)|O(N)|O(N)|-|-|Compila una matriz cuyos elementos son el resultado de aplicar la función especificada a cada elemento de la matriz. El índice de entero que se pasa a la función indica el índice del elemento que se transforman.|
|mapi2|O(N)|O(N)|-|-|-|Compila una colección cuyos elementos son el resultado de aplicar la función especificada a los elementos correspondientes de las dos colecciones en pares y también pasa el índice de los elementos. Las dos matrices de entrada deben tener la misma longitud.|
|max|O(N)|O(N)|O(N)|-|-|Devuelve el elemento mayor en la colección, se comparan utilizando el [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) operador.|
|maxBy|O(N)|O(N)|O(N)|-|-|Devuelve el elemento mayor en la colección, se comparan mediante [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) en el resultado de la función.|
|maxElement|-|-|-|-|O (log N)|Devuelve el mayor elemento del conjunto según la ordenación que se usa para el conjunto.|
|min|O(N)|O(N)|O(N)|-|-|Devuelve el elemento mínimo de la colección, se comparan utilizando el [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operador.|
|minBy|O(N)|O(N)|O(N)|-|-|Devuelve el elemento mínimo de la colección, se comparan utilizando el [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operador en el resultado de la función.|
|minElement|-|-|-|-|O (log N)|Devuelve el menor elemento del conjunto según el orden que se usa para el conjunto.|
|ofArray|-|O(N)|O(1)|O(N)|O(N)|Crea una colección que contiene los mismos elementos que la matriz especificada.|
|ofList|O(N)|-|O(1)|O(N)|O(N)|Crea una colección que contiene los mismos elementos que la lista especificada.|
|ofSeq|O(N)|O(N)|-|O(N)|O(N)|Crea una colección que contiene los mismos elementos que la secuencia especificada.|
|en pares|-|-|O(N)|-|-|Devuelve una secuencia de cada elemento en la secuencia de entrada y su predecesor, excepto el primer elemento, que se devuelve únicamente como predecesor del segundo elemento.|
|partition|O(N)|O(N)|-|O(N)|O(N)|Divide la colección en dos colecciones. La primera colección contiene los elementos para los cuales el predicado especificado devuelve `true`, y la segunda colección contiene los elementos para los cuales el predicado especificado devuelve `false`.|
|permute|O(N)|O(N)|-|-|-|Devuelve una matriz con todos los elementos permutados según la permutación especificada.|
|selección|O(N)|O(N)|O(N)|O (log N)|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado donde la función devuelve Some. Si la función nunca devuelve Some, `System.Collections.Generic.KeyNotFoundException` se genera.|
|readonly|-|-|O(N)|-|-|Crea un objeto de secuencia que delega en el objeto de secuencia especificado. Esta operación garantiza que una conversión de tipo no se puede volver a detectar y modifique la secuencia original. Por ejemplo, si especifica una matriz, la secuencia devuelta devolverá los elementos de la matriz, pero no se puede convertir el objeto de secuencia devuelto en una matriz.|
|reduce|O(N)|O(N)|O(N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador durante el cálculo. Esta función inicia aplicando la función a los dos primeros elementos, pasa este resultado en la función junto con el tercer elemento y así sucesivamente. La función devuelve el resultado final.|
|reduceBack|O(N)|O(N)|-|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador durante el cálculo. Si la función de entrada es f y los elementos son i0... iN, esta función calcula f i0 (...) (f en-1 en)).|
|remove|-|-|-|O (log N)|O (log N)|Quita un elemento desde el dominio de la asignación. No se produce ninguna excepción si el elemento no está presente.|
|replicar|-|O(N)|-|-|-|Crea una lista de una longitud especificada con cada elemento en el valor dado.|
|rev|O(N)|O(N)|-|-|-|Devuelve una nueva lista con los elementos en orden inverso.|
|examen|O(N)|O(N)|O(N)|-|-|Aplica una función a cada elemento de la colección y subprocesa un argumento acumulador durante el cálculo. Esta operación aplica la función para el segundo argumento y el primer elemento de la lista. La operación, a continuación, pasa este resultado en la función junto con el segundo elemento y así sucesivamente. Por último, la operación devuelve la lista de resultados intermedios y el resultado final.|
|scanBack|O(N)|O(N)|-|-|-|Es similar a la operación foldBack pero devuelve los resultados intermedios y finales.|
|singleton|-|-|O(1)|-|O(1)|Devuelve una secuencia que genera un único elemento.|
|establecer|O(1)|-|-|-|-|Establece un elemento de una matriz en el valor especificado.|
|skip|-|-|O(N)|-|-|Devuelve una secuencia que omite N elementos de la secuencia subyacente y, a continuación, produce los elementos restantes de la secuencia.|
|skipWhile|-|-|O(N)|-|-|Devuelve una secuencia que, cuando se itera, omite los elementos de la secuencia subyacente mientras el predicado especificado devuelva `true` y, a continuación, produce los elementos restantes de la secuencia.|
|sort|Promedio de O (N log N)<br /><br />O(N^2) peor caso|O (N log N)|O (N log N)|-|-|Ordena la colección por el valor del elemento. Los elementos se comparan mediante [comparar](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|Promedio de O (N log N)<br /><br />O(N^2) peor caso|O (N log N)|O (N log N)|-|-|Ordena la lista especificada mediante el uso de claves que proporciona la proyección especificada. Las claves se comparan mediante [comparar](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace|Promedio de O (N log N)<br /><br />O(N^2) peor caso|-|-|-|-|Ordena los elementos de una matriz mediante una mutación de él en su lugar y con la función de comparación especificada. Los elementos se comparan utilizando [comparar](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|Promedio de O (N log N)<br /><br />O(N^2) peor caso|-|-|-|-|Ordena los elementos de una matriz mediante una mutación de él en su lugar y con la proyección especificada para las claves. Los elementos se comparan utilizando [comparar](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|Promedio de O (N log N)<br /><br />O(N^2) peor caso|-|-|-|-|Ordena los elementos de una matriz mediante una mutación de él en su lugar y con la función de comparación especificada como criterio de ordenación.|
|sortWith|Promedio de O (N log N)<br /><br />O(N^2) peor caso|O (N log N)|-|-|-|Ordena los elementos de una colección, utilizando la función de comparación especificada como criterio de ordenación y devuelve una colección nueva.|
|sub|O(N)|-|-|-|-|Compila una matriz que contiene el subintervalo especificado por índice de inicio y longitud.|
|suma|O(N)|O(N)|O(N)|-|-|Devuelve la suma de los elementos de la colección.|
|sumBy|O(N)|O(N)|O(N)|-|-|Devuelve la suma de los resultados que se generan aplicando la función a cada elemento de la colección.|
|Tail|-|O(1)|-|-|-|Devuelve la lista sin su primer elemento.|
|Take|-|-|O(N)|-|-|Devuelve los elementos de la secuencia hasta un número especificado.|
|takeWhile|-|-|O(1)|-|-|Devuelve una secuencia que, cuando se itera, proporciona elementos de la secuencia subyacente mientras el predicado especificado devuelva `true` y, a continuación, se devuelve ningún elemento más.|
|ToArray|-|O(N)|O(N)|O(N)|O(N)|Crea una matriz a partir de la colección especificada.|
|ToList|O(N)|-|O(N)|O(N)|O(N)|Crea una lista de la colección dada.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Crea una secuencia de la colección dada.|
|truncar|-|-|O(1)|-|-|Devuelve una secuencia que, cuando se enumera, devuelve no más de N elementos.|
|tryFind|O(N)|O(N)|O(N)|O (log N)|-|Busca un elemento que cumple un predicado especificado.|
|tryFindIndex|O(N)|O(N)|O(N)|-|-|Busca el primer elemento que cumple un predicado especificado y devuelve el índice del elemento coincidente, o `None` si no existe ese elemento.|
|tryFindKey|-|-|-|O (log N)|-|Devuelve la clave de la primera asignación de la colección que cumple el predicado especificado, o bien devuelve `None` si no existe ese elemento.|
|tryPick|O(N)|O(N)|O(N)|O (log N)|-|Aplica la función especificada a elementos sucesivos y devuelve el primer resultado que devuelve la función `Some` de algún valor. Si no existe ese elemento, la operación devuelve `None`.|
|Expandir|-|-|O(N)|-|-|Devuelve una secuencia que contiene los elementos que genera el cálculo especificado.|
|union|-|-|-|-|O (M &#42; log N)|Calcula la unión de los dos conjuntos.|
|unionMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcula la unión de una secuencia de conjuntos.|
|unzip|O(N)|O(N)|O(N)|-|-|Divide una lista de pares en dos listas.|
|unzip3|O(N)|O(N)|O(N)|-|-|Divide una lista de triples en tres listas.|
|división de particiones|-|-|O(N)|-|-|Devuelve una secuencia que genera ventanas deslizantes de que contiene los elementos que se extraen de la secuencia de entrada. Cada ventana se devuelve como una matriz nueva.|
|zip|O(N)|O(N)|O(N)|-|-|Combina las dos colecciones en una lista de pares. Las dos listas deben tener la misma longitud.|
|zip3|O(N)|O(N)|O(N)|-|-|Combina las tres colecciones en una lista de triples. Las listas deben tener la misma longitud.|

## <a name="see-also"></a>Vea también

- [Tipos en F#](fsharp-types.md)
- [Referencia del lenguaje F#](index.md)
