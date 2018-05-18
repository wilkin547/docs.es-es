---
title: Ordenar los resultados de una cláusula join
description: Cómo ordenar los resultados de una cláusula join.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f426152e614ed9a9c4aa41d7ba7cb8ddf1cd3063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="order-the-results-of-a-join-clause"></a>Ordenar los resultados de una cláusula join
En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación. Observe que la ordenación se realiza después de la combinación. Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda. Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.  
  
## <a name="example"></a>Ejemplo  
 Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito. Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)  
 [orderby (cláusula)](../language-reference/keywords/orderby-clause.md)  
 [join (cláusula)](../language-reference/keywords/join-clause.md) 
