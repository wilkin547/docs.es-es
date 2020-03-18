---
title: Ordenar los resultados de una cláusula join (LINQ en C#)
description: Obtenga información sobre cómo ordenar los resultados de una cláusula join de LINQ en C#.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659870"
---
# <a name="order-the-results-of-a-join-clause"></a>Ordenar los resultados de una cláusula join

En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación. Observe que la ordenación se realiza después de la combinación. Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda. Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.

## <a name="example"></a>Ejemplo

Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito. Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)
- [orderby (cláusula)](../language-reference/keywords/orderby-clause.md)
- [join (cláusula)](../language-reference/keywords/join-clause.md)
