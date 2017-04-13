---
title: "EXCEPT (Entity SQL) | Microsoft Docs"
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
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# EXCEPT (Entity SQL)
Devuelve una colección de los valores distintos de la expresión de consulta situada a la izquierda del operando EXCEPT, que tampoco se devuelven en la expresión de consulta situada a la derecha del operando EXCEPT. Todas las expresiones deben ser del mismo tipo que `expression` o de un tipo base común o derivado.  
  
## Sintaxis  
  
```  
  
expression EXCEPT expression  
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.  
  
## Valor devuelto  
 Colección del mismo tipo que `expression` o de un tipo base común o derivado.  
  
## Comentarios  
 EXCEPT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. En la tabla siguiente se muestra la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Precedencia|Operadores|  
|-----------------|----------------|  
|Máxima|INTERSECT|  
||UNION<br /><br /> UNION ALL|  
||EXCEPT|  
|Mínima|EXISTS<br /><br /> OVERLAPS<br /><br /> FLATTEN<br /><br /> SET|  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador EXCEPT para devolver una colección de valores distintos de dos expresiones de consulta. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)