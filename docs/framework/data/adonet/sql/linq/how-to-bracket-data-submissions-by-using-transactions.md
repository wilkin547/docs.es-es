---
title: Filtrar para poner entre corchetes envíos de datos mediante el uso de transacciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 3e58c6f2849ed9714b3356662dae313ab9d11696
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134009"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="30c77-102">Filtrar para poner entre corchetes envíos de datos mediante el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="30c77-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="30c77-103">Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="30c77-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="30c77-104">Para obtener más información, consulte [compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="30c77-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c77-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30c77-105">Example</span></span>  
 <span data-ttu-id="30c77-106">El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="30c77-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="30c77-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c77-107">See also</span></span>

- [<span data-ttu-id="30c77-108">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="30c77-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="30c77-109">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="30c77-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="30c77-110">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="30c77-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
