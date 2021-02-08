---
description: 'Más información acerca de cómo: ejecutar directamente comandos SQL'
title: Procedimiento para ejecutar directamente comandos SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 9dd53b3582b6099bae51dc008debd8cb3142e386
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786035"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="0e37a-103">Procedimiento para ejecutar directamente comandos SQL</span><span class="sxs-lookup"><span data-stu-id="0e37a-103">How to: Directly Execute SQL Commands</span></span>

<span data-ttu-id="0e37a-104">En el supuesto de que tuviese una conexión <xref:System.Data.Linq.DataContext>, podría utilizar <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para ejecutar comandos SQL que no devuelven objetos.</span><span class="sxs-lookup"><span data-stu-id="0e37a-104">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e37a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e37a-105">Example</span></span>  

 <span data-ttu-id="0e37a-106">El ejemplo siguiente hace que SQL Server aumente el precio unitario (UnitPrice) en 1,00.</span><span class="sxs-lookup"><span data-stu-id="0e37a-106">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0e37a-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e37a-107">See also</span></span>

- [<span data-ttu-id="0e37a-108">Procedimiento para ejecutar directamente consultas SQL</span><span class="sxs-lookup"><span data-stu-id="0e37a-108">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="0e37a-109">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="0e37a-109">Communicating with the Database</span></span>](communicating-with-the-database.md)
