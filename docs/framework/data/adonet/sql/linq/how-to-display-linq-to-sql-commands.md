---
title: Procedimiento para mostrar comandos de LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: e703ea9be3ead50afae9b8f42aaa4f54a292c23c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169445"
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="7dd55-102">Procedimiento para mostrar comandos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7dd55-102">How to: Display LINQ to SQL Commands</span></span>

<span data-ttu-id="7dd55-103">Utilice <xref:System.Data.Linq.DataContext.GetCommand%2A> para mostrar comandos SQL y otra información.</span><span class="sxs-lookup"><span data-stu-id="7dd55-103">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd55-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dd55-104">Example</span></span>  

 <span data-ttu-id="7dd55-105">En el ejemplo siguiente, la ventana de la consola muestra el resultado de la consulta, seguido de los comandos SQL que se generan, el tipo de los comandos y el tipo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="7dd55-105">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="7dd55-106">El resultado se muestra de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="7dd55-106">Output appears as follows:</span></span>  
  
```console  
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
  
```console  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dd55-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7dd55-107">See also</span></span>

- [<span data-ttu-id="7dd55-108">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="7dd55-108">Debugging Support</span></span>](debugging-support.md)
