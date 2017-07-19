---
title: "- (Restar) (Entity SQL) | Microsoft Docs"
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
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# - (Restar) (Entity SQL)
Resta dos números.  
  
## Sintaxis  
  
```  
  
expression  
-  
expression  
  
```  
  
## Argumentos  
 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## Tipos de resultado  
 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información acerca de la promoción de tipos implícita, vea [Sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético \- para restar dos números. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)