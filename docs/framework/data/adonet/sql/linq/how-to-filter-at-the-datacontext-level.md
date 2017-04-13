---
title: "C&#243;mo: Filtrar en el nivel de contexto de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Filtrar en el nivel de contexto de datos
Puede filtrar `EntitySets` en el nivel de `DataContext`.  Tales filtros se aplican a todas las consultas realizadas con esa instancia de <xref:System.Data.Linq.DataContext>.  
  
## Ejemplo  
 En el ejemplo siguiente, se usa <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=fullName> para filtrar los pedidos de clientes previamente cargados por `ShippedDate`.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## Vea también  
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)