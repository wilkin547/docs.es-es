---
title: "C&#243;mo: Catalogar env&#237;os de datos mediante transacciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Catalogar env&#237;os de datos mediante transacciones
Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos.  Para obtener más información, consulta [Compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## Ejemplo  
 El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## Vea también  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Crear y enviar cambios en los datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)