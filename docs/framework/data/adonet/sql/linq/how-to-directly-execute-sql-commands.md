---
title: 'Cómo: Ejecutar directamente comandos SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 90fb0d7027946ce4f38c2ba4930ac3510e2a42b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351877"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="5c87b-102">Cómo: Ejecutar directamente comandos SQL</span><span class="sxs-lookup"><span data-stu-id="5c87b-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="5c87b-103">En el supuesto de que tuviese una conexión <xref:System.Data.Linq.DataContext>, podría utilizar <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para ejecutar comandos SQL que no devuelven objetos.</span><span class="sxs-lookup"><span data-stu-id="5c87b-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c87b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c87b-104">Example</span></span>  
 <span data-ttu-id="5c87b-105">El ejemplo siguiente hace que SQL Server aumente el precio unitario (UnitPrice) en 1,00.</span><span class="sxs-lookup"><span data-stu-id="5c87b-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5c87b-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c87b-106">See Also</span></span>  
 [<span data-ttu-id="5c87b-107">Ejecución directa de consultas SQL</span><span class="sxs-lookup"><span data-stu-id="5c87b-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="5c87b-108">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="5c87b-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
