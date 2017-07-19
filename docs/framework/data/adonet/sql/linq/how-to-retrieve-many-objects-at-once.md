---
title: "C&#243;mo: Recuperar muchos objetos de una vez | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Recuperar muchos objetos de una vez
Puede recuperar muchos objetos en una consulta mediante <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## Ejemplo  
 El código siguiente utiliza el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para recuperar los objetos `Customer` y `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## Vea también  
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)