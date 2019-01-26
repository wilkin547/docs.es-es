---
title: Procedimiento Mostrar un conjunto de cambios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: e6030a48a773dcf985eee5c4c113b02386780707
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065822"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="884cc-102">Procedimiento Mostrar un conjunto de cambios</span><span class="sxs-lookup"><span data-stu-id="884cc-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="884cc-103">Puede ver los cambios de los que <xref:System.Data.Linq.DataContext> ha realizado un seguimiento mediante <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span><span class="sxs-lookup"><span data-stu-id="884cc-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="884cc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="884cc-104">Example</span></span>  
 <span data-ttu-id="884cc-105">En el ejemplo siguiente se recuperan los clientes cuya ciudad es Londres, se cambia la ciudad a París y se envían los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="884cc-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="884cc-106">El resultado de este código es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="884cc-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="884cc-107">Observe que el resumen final indica que se realizaron ocho cambios.</span><span class="sxs-lookup"><span data-stu-id="884cc-107">Note that the summary at the end shows that eight changes were made.</span></span>  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a><span data-ttu-id="884cc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="884cc-108">See also</span></span>
- [<span data-ttu-id="884cc-109">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="884cc-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
