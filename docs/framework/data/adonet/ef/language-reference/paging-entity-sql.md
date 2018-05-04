---
title: Paginación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 946e7da12481eb7dac880d6ce8a56b546bdcd822
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="paging-entity-sql"></a>Paginación (Entity SQL)
La paginación física puede realizarse mediante la [omitir](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [límite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) subcláusulas en el [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) cláusula. Para llevar a cabo la paginación física de forma determinista, debe usar SKIP y LIMIT. Si solo desea restringir el número de filas en el resultado de una manera no determinista, debe usar [arriba](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). TOP y SKIP/LIMIT se excluyen mutuamente.  
  
## <a name="top-overview"></a>Introducción a TOP  
 La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT. La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta. Para obtener más información, consulte [arriba](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Introducción a SKIP y LIMIT  
 SKIP y LIMIT son parte de la cláusula ORDER BY. Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP. Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta. Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT. Por ejemplo, LIMIT 5 restringirá el conjunto de resultados a cinco instancias o filas. SKIP y LIMIT no tienen que usarse conjuntamente; se puede usar solo una de ellas con la cláusula ORDER BY. Para obtener más información, vea los temas siguientes:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Cómo: resultados de la página a través de consulta](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
