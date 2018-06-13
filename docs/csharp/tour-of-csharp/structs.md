---
title: 'Estructuras de C#: un paseo por el lenguaje C#'
description: 'Aprenda los conceptos básicos de los tipos de valores de C #, llamados structs.'
ms.date: 08/10/2016
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: dac0952e6a55a16ecefec79f9789f9e2d44aada1
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058970"
---
# <a name="structs"></a>Estructuras

Al igual que las clases, los ***structs*** son estructuras de datos que pueden contener miembros de datos y miembros de función, pero a diferencia de las clases, los structs son tipos de valor y no requieren asignación del montón. Una variable de un tipo de struct almacena directamente los datos del struct, mientras que una variable de un tipo de clase almacena una referencia a un objeto asignado dinámicamente. Los tipos struct no admiten la herencia especificada por el usuario y todos los tipos de struct se heredan implícitamente del tipo <xref:System.ValueType>, que a su vez se hereda implícitamente de `object`.

Los structs son particularmente útiles para estructuras de datos pequeñas que tengan semánticas de valor. Los números complejos, los puntos de un sistema de coordenadas o los pares clave-valor de un diccionario son buenos ejemplos de structs. El uso de un struct en lugar de una clase para estructuras de datos pequeñas puede suponer una diferencia sustancial en el número de asignaciones de memoria que realiza una aplicación. Por ejemplo, el siguiente programa crea e inicializa una matriz de 100 puntos. Si `Point` se implementa como una clase, se crean instancias de 101 objetos distintos: uno para la matriz y uno por cada uno de los 100 elementos.

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

Una alternativa es convertir Point en un struct.

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

Ahora, se crea la instancia de un solo objeto: la de la matriz, y las instancias de `Point` se asignan en línea dentro de la matriz.

Los structs se invocan con el operador `new`, pero eso no implica que se asigne memoria. En lugar de asignar dinámicamente un objeto y devolver una referencia a él, un constructor de structs simplemente devuelve el valor del struct propiamente dicho (normalmente en una ubicación temporal en la pila) y este valor se copia luego cuando es necesario.

Con las clases, es posible que dos variables hagan referencia al mismo objeto y, que por tanto, las operaciones en una variable afecten al objeto al que hace referencia la otra variable. Con los struct, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una afecten a la otra. Por ejemplo, la salida producida por el fragmento de código siguiente depende de si Point es una clase o un struct.

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

Si `Point` es una clase, la salida es 20 porque a y b hacen referencia al mismo objeto. Si Point es un struct, la salida es 10 porque la asignación de `a` a `b` crea una copia del valor, y esta copia no se ve afectada por la asignación posterior a `a.x`.

En el ejemplo anterior se resaltan dos de las limitaciones de los structs. En primer lugar, copiar un struct entero normalmente es menos eficaz que copiar una referencia a un objeto, por lo que el paso de parámetros de asignación y valor puede ser más costoso con structs que con tipos de referencia. En segundo lugar, a excepción de los parámetros `in`, `ref` y `out`, no es posible crear referencias a structs, que excluyen su uso en varias situaciones.

>[!div class="step-by-step"]
[Anterior](classes-and-objects.md)
[Siguiente](arrays.md)
