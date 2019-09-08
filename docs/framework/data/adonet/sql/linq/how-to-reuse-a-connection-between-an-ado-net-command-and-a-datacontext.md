---
title: Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793292"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="6bd25-102">Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="6bd25-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="6bd25-103">Dado [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que forma parte de la familia de tecnologías ADO.net y se basa en los servicios proporcionados por ADO.net, puede reutilizar una conexión entre un comando ADO.net <xref:System.Data.Linq.DataContext>y un.</span><span class="sxs-lookup"><span data-stu-id="6bd25-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bd25-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6bd25-104">Example</span></span>  
 <span data-ttu-id="6bd25-105">En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando ADO.NET <xref:System.Data.Linq.DataContext>y.</span><span class="sxs-lookup"><span data-stu-id="6bd25-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6bd25-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bd25-106">See also</span></span>

- [<span data-ttu-id="6bd25-107">Información general</span><span class="sxs-lookup"><span data-stu-id="6bd25-107">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="6bd25-108">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6bd25-108">ADO.NET and LINQ to SQL</span></span>](ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="6bd25-109">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="6bd25-109">Communicating with the Database</span></span>](communicating-with-the-database.md)
