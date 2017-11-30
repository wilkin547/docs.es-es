---
title: "Realizar una unión usando claves compuestas"
description: "Cómo realizar una unión usando claves compuestas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: c285e768d64d1da7e428e29fc67838e87575500c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="join-by-using-composite-keys"></a>Realizar una unión usando claves compuestas

En este ejemplo se muestra cómo realizar operaciones de combinación en las que se quiere usar más de una clave para definir a una coincidencia. Esto se logra mediante una clave compuesta. Una clave compuesta se crea como un tipo anónimo o un nombre con tipo con los valores que se quieren comparar. Si la variable de consulta se pasará a través de límites de método, use un tipo con nombre que invalida <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> para la clave. Los nombres de las propiedades y el orden en que aparecen deben ser idénticos en cada clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar una clave compuesta para combinar datos de tres tablas:  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 La inferencia de tipos en las claves compuestas depende de los nombres de las propiedades de las claves y el orden en que aparecen. Si las propiedades de las secuencias de origen no tienen los mismos nombres, deberá asignar nuevos nombres en las claves. Por ejemplo, si la tabla `Orders` y la tabla `OrderDetails` usan nombres diferentes para las columnas, se podrían crear claves compuestas asignando nombres idénticos a los tipos anónimos:  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 Las claves compuestas también se pueden usar en una cláusula `group`.  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)  
 [join (cláusula)](../language-reference/keywords/join-clause.md)  
 [group (cláusula)](../language-reference/keywords/group-clause.md)
