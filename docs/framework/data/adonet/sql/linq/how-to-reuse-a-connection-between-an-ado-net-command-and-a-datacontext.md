---
title: 'Cómo: Reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 9618ffd3f6b1a050a4c47d1912b4612ce4031cd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352953"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="27239-102">Cómo: Reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="27239-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="27239-103">Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] forma parte de la [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] familia de tecnologías y se basa en los servicios proporcionados por [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], puede reutilizar una conexión entre un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando y un <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="27239-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27239-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27239-104">Example</span></span>  
 <span data-ttu-id="27239-105">En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] y <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="27239-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="27239-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="27239-106">See Also</span></span>  
 [<span data-ttu-id="27239-107">Información general</span><span class="sxs-lookup"><span data-stu-id="27239-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="27239-108">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="27239-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [<span data-ttu-id="27239-109">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="27239-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
