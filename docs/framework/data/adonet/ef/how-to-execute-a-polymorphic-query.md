---
title: "C&#243;mo ejecutar una consulta polim&#243;rfica | Microsoft Docs"
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
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo ejecutar una consulta polim&#243;rfica
En este tema se muestra cómo ejecutar una consulta de [!INCLUDE[esql](../../../../../includes/esql-md.md)] polimórfica usando el operador [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md).  
  
### Para ejecutar el código de este ejemplo  
  
1.  Agregue el [School Model](http://msdn.microsoft.com/es-es/859a9587-81ea-4a45-9bc0-f8d330e1adac) al proyecto y configúrelo para usar Entity Framework.  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Modifique el modelo conceptual para que tenga una herencia de tabla por jerarquía siguiendo los pasos descritos en [Walkthrough: Mapping Inheritance \- Table\-per\-Hierarchy](http://msdn.microsoft.com/es-es/49b685cf-9db8-4d6d-b885-8837ed238f55).  
  
## Ejemplo  
 En el ejemplo siguiente se usa un operador OFTYPE para obtener y mostrar una colección únicamente de `OnsiteCourses` a partir de una colección de `Courses`.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## Vea también  
 [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)   
 [Lenguaje Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)