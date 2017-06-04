---
title: "C&#243;mo ejecutar una consulta de Entity SQL parametrizada con EntityCommand | Microsoft Docs"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo ejecutar una consulta de Entity SQL parametrizada con EntityCommand
En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que tiene parámetros utilizando un objeto <xref:System.Data.EntityClient.EntityCommand>.  
  
### Para ejecutar el código de este ejemplo  
  
1.  Agregue el [AdventureWorks Sales Model](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configúrelo para usar [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo construir una cadena de consulta con dos parámetros.  Después crea un <xref:System.Data.EntityClient.EntityCommand>, agrega dos parámetros a la colección <xref:System.Data.EntityClient.EntityParameter> de ese <xref:System.Data.EntityClient.EntityCommand>, y procesa una iteración en la colección de elementos `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## Vea también  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/es-es/42048f03-c65c-4d98-b50a-3e7d537a63e8)   
 [Lenguaje Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)