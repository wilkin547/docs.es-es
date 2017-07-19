---
title: "SET (Entity SQL) | Microsoft Docs"
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
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# SET (Entity SQL)
La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.  
  
## Sintaxis  
  
```  
  
SET (expression)  
```  
  
## Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## Comentarios  
 La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) para obtener información de prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)