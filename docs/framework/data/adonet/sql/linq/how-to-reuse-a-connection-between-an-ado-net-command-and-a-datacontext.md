---
description: 'Más información sobre: Cómo: reutilizar una conexión entre un comando ADO.NET y un DataContext'
title: Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: d5bf45dfd705ed6e9b9d4ed9659e01bfcb539df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785957"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="0b602-103">Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="0b602-103">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>

<span data-ttu-id="0b602-104">Dado [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que forma parte de la familia de tecnologías ADO.net y se basa en los servicios proporcionados por ADO.net, puede reutilizar una conexión entre un comando ADO.net y un <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="0b602-104">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b602-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b602-105">Example</span></span>  

 <span data-ttu-id="0b602-106">En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando ADO.NET y <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="0b602-106">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0b602-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b602-107">See also</span></span>

- [<span data-ttu-id="0b602-108">Información general</span><span class="sxs-lookup"><span data-stu-id="0b602-108">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="0b602-109">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0b602-109">ADO.NET and LINQ to SQL</span></span>](ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="0b602-110">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="0b602-110">Communicating with the Database</span></span>](communicating-with-the-database.md)
