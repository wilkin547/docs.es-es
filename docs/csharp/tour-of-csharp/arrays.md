---
title: 'Matrices de C#: un paseo por el lenguaje C#'
description: Las matrices son el tipo más básico de colección en el lenguaje C#.
ms.date: 02/27/2020
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: 3e045c0933a21beab6958c7851546ba6e0b55ef9
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159200"
---
# <a name="arrays"></a>Matrices

Una ***matriz*** es una estructura de datos que contiene un número de variables a las que se accede mediante índices calculados. Las variables contenidas en una matriz, denominadas también ***elementos*** de la matriz, son todas del mismo tipo y este tipo se conoce como ***tipo de elemento*** de la matriz.

Los tipos de matriz son tipos de referencia, y la declaración de una variable de matriz simplemente establece un espacio reservado para una referencia a una instancia de matriz. Las instancias de matriz reales se crean dinámicamente en tiempo de ejecución mediante el operador `new`. La nueva operación especifica la ***longitud*** de la nueva instancia de matriz, que luego se fija para la vigencia de la instancia. Los índices de los elementos de una matriz van de `0` a `Length - 1`. El operador `new` inicializa automáticamente los elementos de una matriz a su valor predeterminado, que, por ejemplo, es cero para todos los tipos numéricos y `null` para todos los tipos de referencias.

En el ejemplo siguiente se crea una matriz de elementos `int`, se inicializa la matriz y se imprime el contenido de la matriz.

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

Este ejemplo se crea y se pone en funcionamiento en una ***matriz unidimensional***. C# también admite ***matrices multidimensionales***. El número de dimensiones de un tipo de matriz, conocido también como ***rango*** del tipo de matriz, es una más el número de comas escritas entre los corchetes del tipo de matriz. En el ejemplo siguiente se asignan una matriz unidimensional, bidimensional y tridimensional, respectivamente.

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

La matriz `a1` contiene 10 elementos, la matriz `a2` 50 (10 × 5) elementos y la matriz `a3` 100 (10 × 5 × 2) elementos.
El tipo de elemento de una matriz puede ser cualquiera, incluido un tipo de matriz. Una matriz con elementos de un tipo de matriz a veces se conoce como ***matriz escalonada*** porque las longitudes de las matrices de elementos no tienen que ser iguales. En el ejemplo siguiente se asigna una matriz de matrices de `int`:

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

La primera línea crea una matriz con tres elementos, cada uno de tipo `int[]` y cada uno con un valor inicial de `null`. Las líneas posteriores inicializan entonces los tres elementos con referencias a instancias de matriz individuales de longitud variable.

El nuevo operador permite especificar los valores iniciales de los elementos de matriz mediante un ***inicializador de matriz***, que es una lista de las expresiones escritas entre los delimitadores `{` y `}`. En el ejemplo siguiente se asigna e inicializa un tipo `int[]` con tres elementos.

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

La longitud de la matriz se deduce del número de expresiones entre { y }. Las declaraciones de variable local y campo se pueden acortar más para que así no sea necesario reformular el tipo de matriz.

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

Los dos ejemplos anteriores son equivalentes al código siguiente:

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
>[Anterior](classes-and-objects.md)
>[Siguiente](interfaces.md)
