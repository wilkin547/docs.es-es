---
title: "REF (Entity SQL) | Microsoft Docs"
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
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# REF (Entity SQL)
Devuelve una referencia a una instancia de entidad.  
  
## Sintaxis  
  
```  
  
REF( expression )   
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión válida que produzca una instancia de un tipo de entidad.  
  
## Valor devuelto  
 Referencia a la instancia de la entidad especificada.  
  
## Comentarios  
 La referencia a una entidad está compuesta de la clave de entidad y de un nombre de conjunto de entidades. Dado que diferentes conjuntos de entidades pueden basarse en el mismo tipo de entidad, una clave de entidad en particular podría aparecer en varios conjuntos de entidades. Sin embargo, una referencia a entidad siempre es única. Si la expresión de entrada representa una entidad conservada, se devolverá una referencia a esta entidad. Si la expresión de entrada no es una entidad conservada, se devolverá una referencia nula.  
  
 Si el operador de extracción de propiedad \(.\) se usa para acceder a una propiedad de una entidad, la referencia se desreferencia automáticamente.  
  
## Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador REF para devolver la referencia para un argumento de entidad de entrada. La misma consulta desreferencia la referencia porque se usa un operador de extracción de propiedad \(.\) para acceder a una propiedad de la entidad Product. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## Vea también  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Definiciones de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)