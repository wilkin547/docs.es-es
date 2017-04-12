---
title: "Ordenar los resultados de una cláusula join"
description: "Cómo ordenar los resultados de una cláusula join."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0252dd62e5638ffd1ab4eeebcfc2382a65997e30
ms.lasthandoff: 03/13/2017

---
# <a name="order-the-results-of-a-join-clause"></a>Ordenar los resultados de una cláusula join
En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación. Observe que la ordenación se realiza después de la combinación. Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda. Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.  
  
## <a name="example"></a>Ejemplo  
 Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito. Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.  
  
 [!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)   
 [orderby (Cláusula)](../language-reference/keywords/orderby-clause.md)   
 [join (cláusula)](../language-reference/keywords/join-clause.md) 
