---
title: "Variables (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Variables (Entity SQL)
## Variable  
 Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual.  Una referencia a una variable debe ser un identificador de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] válido, según se define en [Identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 En el siguiente ejemplo se muestra el uso de una variable en la expresión.  La `c` de la cláusula FROM es la definición de la variable.  El uso de `c` en la cláusula SELECT representa la referencia a la variable.  
  
```  
select c   
from LOB.customers as c  
```  
  
## Vea también  
 [Identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)   
 [Parámetros](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)   
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)