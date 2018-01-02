---
title: "Cómo: Reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8cf28a7535cb09946654d4fb43b2f5567fff40c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Cómo: Reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] forma parte de la [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] familia de tecnologías y se basa en los servicios proporcionados por [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], puede reutilizar una conexión entre un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando y un <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] y <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET y LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [Comunicación con la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
