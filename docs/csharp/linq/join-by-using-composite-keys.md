---
title: Realizar una combinación mediante claves compuestas (LINQ en C#)
description: Obtenga información sobre como cómo realizar una combinación mediante claves compuestas en LINQ.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: ae37d03f996f0b0cc184a86663f16d62e6c29c69
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43452872"
---
# <a name="join-by-using-composite-keys"></a>Realizar una unión usando claves compuestas

En este ejemplo se muestra cómo realizar operaciones de combinación en las que se quiere usar más de una clave para definir a una coincidencia. Esto se logra mediante una clave compuesta. Una clave compuesta se crea como un tipo anónimo o un nombre con tipo con los valores que se quieren comparar. Si la variable de consulta se pasará a través de límites de método, use un tipo con nombre que invalida <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> para la clave. Los nombres de las propiedades y el orden en que aparecen deben ser idénticos en cada clave.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar una clave compuesta para combinar datos de tres tablas:

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

La inferencia de tipos en las claves compuestas depende de los nombres de las propiedades de las claves y el orden en que aparecen. Si las propiedades de las secuencias de origen no tienen los mismos nombres, deberá asignar nombres nuevos en las claves. Por ejemplo, si la tabla `Orders` y la tabla `OrderDetails` usan nombres diferentes para las columnas, se podrían crear claves compuestas asignando nombres idénticos a los tipos anónimos:

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

Las claves compuestas también se pueden usar en una cláusula `group`.

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)  
- [join (cláusula)](../language-reference/keywords/join-clause.md)  
- [group (cláusula)](../language-reference/keywords/group-clause.md)  