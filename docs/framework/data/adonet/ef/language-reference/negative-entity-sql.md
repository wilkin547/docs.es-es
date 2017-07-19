---
title: "- (Negativo) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# - (Negativo) (Entity SQL)
Devuelve el valor negativo de una expresión numérica.  
  
## Sintaxis  
  
```  
  
-  
expression  
  
```  
  
## Argumentos  
 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## Tipos de resultado  
 Tipo de datos de `expression`.  
  
## Comentarios  
 Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`. Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético \- para devolver el valor negativo de una expresión numérica. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)