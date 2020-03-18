---
title: Realizar operaciones de combinación personalizadas (LINQ en C#)
description: Obtenga información sobre cómo realizar operaciones de combinación de LINQ personalizadas en C#.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659857"
---
# <a name="perform-custom-join-operations"></a>Realizar operaciones de combinación personalizadas

En este ejemplo se muestra cómo realizar operaciones de combinación que no son posibles con la cláusula `join`. En una expresión de consulta, la cláusula `join` se limita a combinaciones de igualdad (y se optimiza para estas), que son con diferencia el tipo más común de operación de combinación. Al realizar una combinación de igualdad, probablemente obtendrá siempre el mejor rendimiento con la cláusula `join`.

En cambio, la cláusula `join` no se puede usar en los siguientes casos:

- Cuando la combinación se basa en una expresión de desigualdad (una combinación que no es de igualdad).

- Cuando la combinación se basa en más de una expresión de igualdad o desigualdad.

- Cuando tenga que introducir una variable de rango temporal para la secuencia de la derecha (interior) antes de la operación de combinación.

 Para realizar combinaciones que no son de igualdad, puede usar varias cláusulas `from` para presentar cada origen de datos de forma independiente. Después, aplique una expresión de predicado de una cláusula `where` a la variable de rango para cada origen. La expresión también puede adoptar la forma de una llamada de método.

> [!NOTE]
> No confunda este tipo de operación de combinación personalizada con el uso de varias cláusulas `from` para acceder a colecciones internas. Para obtener más información, vea [join (Cláusula, Referencia de C#)](../language-reference/keywords/join-clause.md).

## <a name="example"></a>Ejemplo

En el primer método del siguiente ejemplo se muestra una combinación cruzada sencilla. Las combinaciones cruzadas se deben usar con precaución porque pueden generar conjuntos de resultados muy grandes. En cambio, pueden resultar útiles en algunos escenarios para crear secuencias de origen en las que se ejecutan consultas adicionales.

El segundo método genera una secuencia de todos los productos cuyo identificador de categoría aparece en la lista de categorías en el lado izquierdo. Observe el uso de la cláusula `let` y el método `Contains` para crear una matriz temporal. También se puede crear la matriz antes de la consulta y eliminar la primera cláusula `from`.

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la consulta debe combinar dos secuencias basándose en las claves coincidentes que, en el caso de la secuencia interna (lado derecho), no se pueden obtener antes de la propia cláusula de combinación. Si esta combinación se realizara con una cláusula `join`, se tendría que llamar al método `Split` para cada elemento. El uso de varias cláusulas `from` permite a la consulta evitar la sobrecarga que supone la llamada al método repetida. En cambio, puesto que `join` está optimizada, en este caso particular puede que siga resultando más rápido que usar varias cláusulas `from`. Los resultados variarán dependiendo principalmente de cuántos recursos requiera la llamada de método.

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)
- [join (cláusula)](../language-reference/keywords/join-clause.md)
- [Ordenar los resultados de una cláusula join](order-the-results-of-a-join-clause.md)
