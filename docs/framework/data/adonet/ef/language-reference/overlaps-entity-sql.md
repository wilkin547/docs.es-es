---
title: "OVERLAPS (Entity SQL) | Microsoft Docs"
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
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# OVERLAPS (Entity SQL)
Determina si dos colecciones tienen elementos comunes.  
  
## Sintaxis  
  
```  
  
expression OVERLAPS expression  
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta. Todas las expresiones deben ser del mismo tipo que `expression` o de un tipo base común o derivado.  
  
## Valor devuelto  
 `true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.  
  
## Comentarios  
 OVERLAPS es funcionalmente equivalente a la siguiente``expresión:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información de prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)