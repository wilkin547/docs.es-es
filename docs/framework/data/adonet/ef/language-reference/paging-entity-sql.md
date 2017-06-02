---
title: "Paginaci&#243;n (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Paginaci&#243;n (Entity SQL)
La paginación física puede realizarse mediante las subcláusulas [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) de la cláusula [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  Para llevar a cabo la paginación física de forma determinista, debe usar SKIP y LIMIT.  Si solo se desea restringir el número de filas en el resultado de forma no determinista, se debe usar [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  TOP y SKIP\/LIMIT se excluyen mutuamente.  
  
## Introducción a TOP  
 La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL\/DISTINCT.  La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.  Para obtener más información, vea [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## Introducción a SKIP y LIMIT  
 SKIP y LIMIT son parte de la cláusula ORDER BY.  Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP.  Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.  Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.  Por ejemplo, LIMIT 5 restringirá el conjunto de resultados a cinco instancias o filas.  SKIP y LIMIT no tienen que usarse conjuntamente; se puede usar solo una de ellas con la cláusula ORDER BY.  Para obtener más información, vea los temas siguientes:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [How to: Page Through Query Results](http://msdn.microsoft.com/es-es/ffc0f920-e7de-42e0-9b12-ef356421d030)