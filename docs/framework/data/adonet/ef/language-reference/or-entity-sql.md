---
title: "|| (OR) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# || (OR) (Entity SQL)
Combina dos expresiones `Boolean`.  
  
## Sintaxis  
  
```  
  
          boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## Argumentos  
 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor `Boolean`.  
  
## Valor devuelto  
 `true` cuando alguna de las condiciones es `true`; de lo contrario, `false`.  
  
## Comentarios  
 OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Se usa para combinar dos condiciones. Cuando se utiliza más de un operador lógico en una instrucción, los operadores OR se evalúan después de los operadores AND. Sin embargo, se puede cambiar el orden de evaluación mediante paréntesis.  
  
 Las dobles barras verticales \(&#124;&#124;\) tienen la misma funcionalidad que el operador OR.  
  
 En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean`. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)