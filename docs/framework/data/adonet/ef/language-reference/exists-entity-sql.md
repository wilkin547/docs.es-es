---
title: "EXISTS (Entity SQL) | Microsoft Docs"
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
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# EXISTS (Entity SQL)
Determina si una colección está vacía.  
  
## Sintaxis  
  
```  
  
[NOT] EXISTS (expression)  
```  
  
## Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
 NOT  
 Especifica que el resultado de EXISTS se niega.  
  
## Valor devuelto  
 `true` si la colección no está vacía; en caso contrario, `false`.  
  
## Comentarios  
 EXISTS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información de prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador EXISTS para determinar si la colección está vacía. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)