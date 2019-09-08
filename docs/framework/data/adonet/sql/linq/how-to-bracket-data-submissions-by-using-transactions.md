---
title: Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793806"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="a89b3-102">Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="a89b3-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="a89b3-103">Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a89b3-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="a89b3-104">Para obtener más información, consulte [compatibilidad con transacciones](transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="a89b3-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89b3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a89b3-105">Example</span></span>  
 <span data-ttu-id="a89b3-106">El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="a89b3-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a89b3-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a89b3-107">See also</span></span>

- [<span data-ttu-id="a89b3-108">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a89b3-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="a89b3-109">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="a89b3-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="a89b3-110">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="a89b3-110">Transaction Support</span></span>](transaction-support.md)
