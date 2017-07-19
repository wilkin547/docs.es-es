---
title: "USING (Entity SQL) | Microsoft Docs"
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
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# USING (Entity SQL)
Especifica espacios de nombres que se usan en una expresión de consulta.  
  
## Sintaxis  
  
```  
USING [ alias = ] namespace  
```  
  
## Argumentos  
 `alias`  
 Especifica un alias más breve con el que calificar un espacio de nombres.  
  
 `namespace`  
 Cualquier espacio de nombres válido.  
  
## Ejemplo  
 En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.  Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery`:  
  
```  
using SqlServer; RAND()  
```  
  
## Vea también  
 [Espacios de nombres](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)   
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)