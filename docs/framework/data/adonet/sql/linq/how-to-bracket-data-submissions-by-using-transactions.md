---
description: 'Más información acerca de: Cómo: corchete los envíos de datos mediante transacciones'
title: Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: a1bbebfcdb4b65e83c4ac6dc9b87b06f33f2cb41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739032"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="916e7-103">Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="916e7-103">How to: Bracket Data Submissions by Using Transactions</span></span>

<span data-ttu-id="916e7-104">Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="916e7-104">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="916e7-105">Para obtener más información, consulte [compatibilidad con transacciones](transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="916e7-105">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="916e7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="916e7-106">Example</span></span>  

 <span data-ttu-id="916e7-107">El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="916e7-107">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="916e7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="916e7-108">See also</span></span>

- [<span data-ttu-id="916e7-109">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="916e7-109">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="916e7-110">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="916e7-110">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="916e7-111">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="916e7-111">Transaction Support</span></span>](transaction-support.md)
