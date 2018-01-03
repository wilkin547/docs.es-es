---
title: "Cómo: Poner entre corchetes envíos de datos utilizando transacciones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3481bcae3c67d08dc372195b6dba65c6b506b7f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="a86f1-102">Cómo: Poner entre corchetes envíos de datos utilizando transacciones</span><span class="sxs-lookup"><span data-stu-id="a86f1-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="a86f1-103">Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a86f1-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="a86f1-104">Para obtener más información, consulte [compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="a86f1-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a86f1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a86f1-105">Example</span></span>  
 <span data-ttu-id="a86f1-106">El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="a86f1-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a86f1-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a86f1-107">See Also</span></span>  
 [<span data-ttu-id="a86f1-108">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a86f1-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="a86f1-109">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="a86f1-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="a86f1-110">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="a86f1-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
