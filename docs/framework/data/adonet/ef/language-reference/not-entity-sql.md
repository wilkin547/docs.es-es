---
title: "! (NOT) (Entity SQL) | Microsoft Docs"
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
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ! (NOT) (Entity SQL)
Niega una expresión `Boolean`.  
  
## Sintaxis  
  
```  
  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## Argumentos  
 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor booleano.  
  
## Comentarios  
 El signo de admiración \(\!\) tiene la misma funcionalidad que el operador NOT.  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador NOT para negar una expresión `Boolean`. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)