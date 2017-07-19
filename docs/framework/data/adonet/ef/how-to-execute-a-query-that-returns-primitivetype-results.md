---
title: "Ejecutar una consulta que devuelve resultados PrimitiveType | Microsoft Docs"
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
  - "jsharp"
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Ejecutar una consulta que devuelve resultados PrimitiveType
En este tema se muestra cómo ejecutar un comando en un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.PrimitiveType> usando un objeto <xref:System.Data.EntityClient.EntityDataReader>.  
  
### Para ejecutar el código de este ejemplo  
  
1.  Agregue el [AdventureWorks Sales Model](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configúrelo para usar [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Ejemplo  
 En este ejemplo se ejecuta una consulta que devuelve un resultado <xref:System.Data.Metadata.Edm.PrimitiveType>.  Si pasa la siguiente consulta como un argumento a la función `ExecutePrimitiveTypeQuery`, la función muestra el precio de venta medio de todos los `Products`:  
  
 [!code-csharp[DP EntityServices Concepts#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
 [!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]  
  
 Si pasa una consulta parametrizada, como la siguiente, agregue los objetos <xref:System.Data.EntityClient.EntityParameter> a la propiedad <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> en el objeto <xref:System.Data.EntityClient.EntityCommand>.  
  
 [!code-csharp[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#case_when_then_else)]
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)