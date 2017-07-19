---
title: "COLLECTION (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# COLLECTION (Entity SQL)
La palabra clave COLLECTION solo se usa en la definición de una función inline. Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.  
  
## Sintaxis  
  
```  
  
COLLECTION(type_definition)   
```  
  
## Argumentos  
 `type_definition`  
 Una expresión que devuelve una colección de tipos, filas o referencias compatibles.  
  
## Comentarios  
 Para obtener más información sobre la palabra clave COLLECTION, vea [Definiciones de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)