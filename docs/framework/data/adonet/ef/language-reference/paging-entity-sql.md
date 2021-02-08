---
description: 'Más información acerca de: paginación (Entity SQL)'
title: Paginación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: c32474b772be359dbf2ffd46e5489cc0b4b2abb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791860"
---
# <a name="paging-entity-sql"></a>Paginación (Entity SQL)

La paginación física se puede realizar mediante las subcláusulas [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) . Para llevar a cabo la paginación física de forma determinista, debe usar SKIP y LIMIT. Si solo desea restringir el número de filas del resultado de forma no determinista, debe utilizar [Top](top-entity-sql.md). TOP y SKIP/LIMIT se excluyen mutuamente.  
  
## <a name="top-overview"></a>Introducción a TOP  

 La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT. La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta. Para obtener más información, vea [Top](top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Introducción a SKIP y LIMIT  

 SKIP y LIMIT son parte de la cláusula ORDER BY. Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP. Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta. Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT. Por ejemplo, LIMIT 5 restringirá el conjunto de resultados a cinco instancias o filas. SKIP y LIMIT no tienen que usarse conjuntamente; se puede usar solo una de ellas con la cláusula ORDER BY. Para obtener más información, vea los temas siguientes:  
  
- [IRÁ](skip-entity-sql.md)  
  
- [ILIMITADO](limit-entity-sql.md)  
  
- [ORDER BY](order-by-entity-sql.md)  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
