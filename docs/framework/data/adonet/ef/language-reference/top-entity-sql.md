---
title: "TOP (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# TOP (Entity SQL)
La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL\/DISTINCT. La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.  
  
## Sintaxis  
  
```  
  
[ TOP (n) ]  
```  
  
## Argumentos  
 `n`  
 Expresión numérica válida que especifica el número de filas que se va a devolver.`n` puede ser un literal numérico único o un parámetro único.  
  
## Comentarios  
 La expresión TOP debe ser un literal numérico único o un parámetro único. Si se utiliza un literal constante, el tipo de literal debe poderse promocionar implícitamente a Edm.Int64 \(byte, int16, int32 o int64, o cualquier tipo de proveedor que se asigna a un tipo que se puede promocionar a Edm.Int64\) y su valor debe ser igual o mayor que cero. De lo contrario, se producirá una excepción. Si un parámetro se utiliza como una expresión, el tipo de parámetro también debe poderse promocionar implícitamente a Edm.Int64, pero no habrá ninguna validación del valor de parámetro real durante la compilación porque los valores de parámetro se enlazan en tiempo de ejecución.  
  
 El siguiente es un ejemplo de expresión TOP constante:  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 El siguiente es un ejemplo de expresión TOP constante con parámetros:  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 TOP es no determinista a menos que la consulta esté ordenada. Si necesita un resultado determinista, utilice las subcláusulas [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) en la cláusula [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md). TOP y SKIP\/LIMIT se excluyen mutuamente.  
  
## Ejemplo  
 La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa la cláusula TOP para especificar la fila superior que se va a devolver del resultado de la consulta. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## Vea también  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)   
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)   
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)   
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)   
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)