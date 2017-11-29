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
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="3a8df-102">Cómo: Reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="3a8df-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="3a8df-103">Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] forma parte de la [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] familia de tecnologías y se basa en los servicios proporcionados por [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], puede reutilizar una conexión entre un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando y un <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="3a8df-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a8df-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a8df-104">Example</span></span>  
 <span data-ttu-id="3a8df-105">En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] y <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="3a8df-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3a8df-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a8df-106">See Also</span></span>  
 [<span data-ttu-id="3a8df-107">Información general</span><span class="sxs-lookup"><span data-stu-id="3a8df-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="3a8df-108">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3a8df-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [<span data-ttu-id="3a8df-109">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="3a8df-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
