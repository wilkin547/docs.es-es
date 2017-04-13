---
title: "Devolver la intersecci&#243;n de conjuntos de dos secuencias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Devolver la intersecci&#243;n de conjuntos de dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Intersect%2A> para devolver la intersección de conjuntos de dos secuencias.  
  
## Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Intersect%2A> para devolver una secuencia de todos los países en los que viven `Customers` y `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Intersect%2A> se define correctamente sólo en conjuntos.  La semántica de conjuntos múltiples no está definida.  
  
## Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [Conversión de operadores de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)