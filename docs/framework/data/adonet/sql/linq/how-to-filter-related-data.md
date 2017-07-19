---
title: "C&#243;mo: Filtrar datos relacionados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Filtrar datos relacionados
Utilice el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> para especificar subconsultas para limitar la cantidad de los datos recuperados.  
  
## Ejemplo  
 En el ejemplo siguiente, el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita los `Orders` recuperados a los que no se han enviado hoy.  Sin este enfoque, se habrían recuperado todos los `Orders` aunque sólo se requiere un subconjunto.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## Vea también  
 [Consultar la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)