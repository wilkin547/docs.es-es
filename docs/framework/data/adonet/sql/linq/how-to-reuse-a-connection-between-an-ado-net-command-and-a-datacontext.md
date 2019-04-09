---
title: Filtrar para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 47e1e45cfe693e3569c343f1058ce2d610af96dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163155"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="38402-102">Filtrar para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="38402-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="38402-103">Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] es una parte de la [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] familia de tecnologías y se basa en los servicios proporcionados por [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], puede reutilizar una conexión entre un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comandos y un <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="38402-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38402-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38402-104">Example</span></span>  
 <span data-ttu-id="38402-105">En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] y <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="38402-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="38402-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="38402-106">See also</span></span>

- [<span data-ttu-id="38402-107">Información general</span><span class="sxs-lookup"><span data-stu-id="38402-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="38402-108">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="38402-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="38402-109">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="38402-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
