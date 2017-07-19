---
title: "= (Igual que) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# = (Igual que) (Entity SQL)
Compara la igualdad de dos expresiones.  
  
## Sintaxis  
  
```  
  
          expression  
          =  
          expression  
or   
expression==expression  
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos convertibles implícitamente.  
  
## Tipos de resultado  
 `true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.  
  
## Comentarios  
 El operador \=\= es equivalente a \=.  
  
## Ejemplo  
 La siguiente consulta de Entity SQL utiliza el operador de comparación \= para comparar la igualdad de dos expresiones. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)