---
title: "BETWEEN (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# BETWEEN (Entity SQL)
Determina si el resultado de una expresión es un valor incluido en un intervalo especificado. La expresión BETWEEN de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tiene la misma funcionalidad que la expresión BETWEEN de Transact\-SQL.  
  
## Sintaxis  
  
```  
  
expression [ NOT ] BETWEEN begin_expression AND end_expression  
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`.`expression` debe ser del mismo tipo que `begin_expression` y `end_expression`.  
  
 `begin_expression`  
 Cualquier expresión válida.`begin_expression` debe ser del mismo tipo que `expression` y `end_expression`.`begin_expression` debe ser menor que `end_expression`; de lo contrario, el valor devuelto se negará.  
  
 `end_expression`  
 Cualquier expresión válida.`end_expression` debe ser del mismo tipo que `expression` y `begin_expression`.  
  
 NOT  
 Especifica que el resultado de BETWEEN se niega.  
  
 AND  
 Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.  
  
## Valor devuelto  
 `true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`. Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.  
  
## Comentarios  
 Para especificar un intervalo exclusivo, utilice los operadores mayor que \(\>\) y menor que \(\<\) en lugar de BETWEEN.  
  
## Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)