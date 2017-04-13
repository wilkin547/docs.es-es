---
title: "C&#243;mo: Recuperar informaci&#243;n sobre conflictos de simultaneidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Recuperar informaci&#243;n sobre conflictos de simultaneidad
Puede utilizar objetos de la clase <xref:System.Data.Linq.ObjectChangeConflict> para proporcionar información sobre los conflictos que revelan las excepciones <xref:System.Data.Linq.ChangeConflictException>.  Para obtener más información, consulta [Simultaneidad optimista: Información general](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## Ejemplo  
 En el ejemplo siguiente se recorre en iteración una lista de conflictos acumulados.  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## Vea también  
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)