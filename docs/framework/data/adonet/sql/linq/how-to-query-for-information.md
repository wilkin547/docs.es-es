---
title: "C&#243;mo: Consultar informaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Consultar informaci&#243;n
Las consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan la misma sintaxis que las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  La única diferencia es que los objetos a los que se hace referencia en las consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se asignan a elementos de una base de datos.  Para obtener más información, consulta [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.  
  
 Algunas características de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] podrían requerir una atención especial en las aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Para obtener más información, consulta [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## Ejemplo  
 La consulta siguiente solicita una lista de clientes de Londres.  En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## Vea también  
 [Crear el modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)   
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Consultar la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)