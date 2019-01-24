---
title: Procedimiento Visualización de LINQ to SQL comandos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: a70f1e0dd471e86afe2e744c157d4aed2a217deb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630832"
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="c4fbf-102">Procedimiento Visualización de LINQ to SQL comandos</span><span class="sxs-lookup"><span data-stu-id="c4fbf-102">How to: Display LINQ to SQL Commands</span></span>
<span data-ttu-id="c4fbf-103">Utilice <xref:System.Data.Linq.DataContext.GetCommand%2A> para mostrar comandos SQL y otra información.</span><span class="sxs-lookup"><span data-stu-id="c4fbf-103">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4fbf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4fbf-104">Example</span></span>  
 <span data-ttu-id="c4fbf-105">En el ejemplo siguiente, la ventana de la consola muestra el resultado de la consulta, seguido de los comandos SQL que se generan, el tipo de los comandos y el tipo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="c4fbf-105">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="c4fbf-106">El resultado se muestra de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4fbf-106">Output appears as follows:</span></span>  
  
```  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4fbf-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4fbf-107">See also</span></span>
- [<span data-ttu-id="c4fbf-108">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="c4fbf-108">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
