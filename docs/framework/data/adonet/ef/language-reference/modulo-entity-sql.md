---
title: "(M&#243;dulo) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# (M&#243;dulo) (Entity SQL)
Devuelve el resto de una expresión dividida entre otra.  
  
## Sintaxis  
  
```  
  
dividend  
%  
divisor  
  
```  
  
## Argumentos  
 `dividend`  
 Expresión numérica que se va a dividir.`dividend` es una expresión válida de cualquier tipo de datos numérico.  
  
 `divisor`  
 Expresión numérica entre la que se divide el dividendo.`divisor` es una expresión válida de cualquier tipo de datos numérico.  
  
## Tipos de resultado  
 Edm.Int32  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético % para devolver el resto de una expresión dividida entre otra. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)