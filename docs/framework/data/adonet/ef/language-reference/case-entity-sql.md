---
title: "CASE (Entity SQL) | Microsoft Docs"
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
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# CASE (Entity SQL)
Evalúa un conjunto de expresiones `Boolean` para determinar el resultado.  
  
## Sintaxis  
  
```  
  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## Argumentos  
 `n`  
 Es un marcador de posición que indica que se pueden usar varias cláusulas WHEN `Boolean_expression` THEN `result_expression`.  
  
 THEN `result_expression`  
 Es la expresión devuelta cuando `Boolean_expression` se evalúa como `true`.`result expression` es cualquier expresión válida.  
  
 ELSE `else_result_expression`  
 Expresión que se devuelve si ninguna operación de comparación se evalúa como `true`. Si se omite este argumento y ninguna comparación se evalúa como `true`, CASE devuelve NULL.`else_result_expression` es cualquier expresión válida. Los tipos de datos de `else_result_expression` y cualquier `result_expression` deben ser iguales o deben ser una conversión implícita.  
  
 WHEN `Boolean_expression`  
 Es la expresión `Boolean` que se evalúa cuando se usa el formato CASE buscado.`Boolean_expression` es cualquier expresión `Boolean` válida.  
  
## Valor devuelto  
 Devuelve el tipo de prioridad más alto del conjunto de tipos de `result_expression` y de la expresión `else_result_expression` opcional.  
  
## Comentarios  
 La expresión case de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se parece a la de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Puede usar la expresión case para efectuar una serie de pruebas condicionales que permitan determinar qué expresión dará el resultado apropiado. Este formato de expresión case se aplica a una serie de una o varias expresiones `Boolean` para determinar la que produce el resultado correcto.  
  
 La función CASE evalúa la `Boolean_expression` de cada cláusula WHEN en el orden especificado, y devuelve la `result_expression` de la primera `Boolean_expression` que se evalúa como `true`. Las expresiones restantes no se evalúan. Si ninguna `Boolean_expression` se evalúa como `true`, el motor de base de datos devuelve la `else_result_expression` si se especifica una cláusula ELSE, o un valor Null en otro caso.  
  
 Una instrucción CASE no puede devolver un conjunto múltiple.  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` en orden con el fin de determinar el resultado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## Vea también  
 [THEN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)   
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)   
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)