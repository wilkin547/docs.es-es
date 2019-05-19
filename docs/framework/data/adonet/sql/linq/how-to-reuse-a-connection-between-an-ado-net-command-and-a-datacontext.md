---
title: Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 92b0d8cf2c4904fabc17241ef2c31175f0c87baf
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878536"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="c3ada-102">Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="c3ada-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="c3ada-103">Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] es una parte de la familia ADO.NET de tecnologías y se basa en los servicios proporcionados por ADO.NET, puede reutilizar una conexión entre un comando de ADO.NET y un <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="c3ada-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3ada-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3ada-104">Example</span></span>  
 <span data-ttu-id="c3ada-105">El ejemplo siguiente muestra cómo reutilizar la misma conexión entre un comando de ADO.NET y la <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="c3ada-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c3ada-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3ada-106">See also</span></span>

- [<span data-ttu-id="c3ada-107">Información general</span><span class="sxs-lookup"><span data-stu-id="c3ada-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="c3ada-108">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c3ada-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="c3ada-109">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="c3ada-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
