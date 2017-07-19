---
title: "+ (Sumar) | Microsoft Docs"
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
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# + (Sumar)
Suma dos números.  
  
## Sintaxis  
  
```  
  
expression  
+  
expression  
  
```  
  
## Argumentos  
 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## Tipos de resultado  
 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información acerca de la promoción de tipos implícita, vea [Sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## Comentarios  
 Para los tipos EDM.String, la suma es una concatenación.  
  
## Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético \+  para sumar dos números. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Tipos de modelos conceptuales \(CSDL\)](http://msdn.microsoft.com/es-es/987b995f-e429-4569-9559-b4146744def4)