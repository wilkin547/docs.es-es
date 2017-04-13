---
title: "C&#243;mo ejecutar un procedimiento almacenado parametrizado usando EntityCommand | Microsoft Docs"
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
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo ejecutar un procedimiento almacenado parametrizado usando EntityCommand
En este tema se muestra cómo ejecutar un procedimiento almacenado parametrizado usando la clase <xref:System.Data.EntityClient.EntityCommand>.  
  
### Para ejecutar el código de este ejemplo  
  
1.  Agregue el [School Model](http://msdn.microsoft.com/es-es/859a9587-81ea-4a45-9bc0-f8d330e1adac) al proyecto y configúrelo para usar [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Importe el procedimiento almacenado `GetStudentGrades` y especifique entidades `CourseGrade` como tipo de valor devuelto.  Para obtener información sobre cómo importar un procedimiento almacenado, vea [How to: Import a Stored Procedure](http://msdn.microsoft.com/es-es/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).  
  
## Ejemplo  
 El código siguiente ejecuta el procedimiento almacenado `GetStudentGrades` donde `StudentId` es un parámetro necesario.  Los resultados los lee después una clase <xref:System.Data.EntityClient.EntityDataReader>.  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## Vea también  
 [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)