---
title: Procedimiento para mostrar un conjunto de cambios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 92acee0d36634ea09c245418fcc7a8b97d208aa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903115"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="6a5d5-102">Procedimiento para mostrar un conjunto de cambios</span><span class="sxs-lookup"><span data-stu-id="6a5d5-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="6a5d5-103">Puede ver los cambios de los que <xref:System.Data.Linq.DataContext> ha realizado un seguimiento mediante <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a5d5-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a5d5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a5d5-104">Example</span></span>  
 <span data-ttu-id="6a5d5-105">En el ejemplo siguiente se recuperan los clientes cuya ciudad es Londres, se cambia la ciudad a París y se envían los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d5-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="6a5d5-106">El resultado de este código es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a5d5-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="6a5d5-107">Observe que el resumen final indica que se realizaron ocho cambios.</span><span class="sxs-lookup"><span data-stu-id="6a5d5-107">Note that the summary at the end shows that eight changes were made.</span></span>  

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
  
## <a name="see-also"></a><span data-ttu-id="6a5d5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a5d5-108">See also</span></span>

- [<span data-ttu-id="6a5d5-109">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="6a5d5-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
