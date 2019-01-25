---
title: Procedimiento Envíos de datos mediante el uso de transacciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 2cbb50cc8762780849c337b597bbb36631c6ac1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584537"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedimiento Envíos de datos mediante el uso de transacciones
Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos. Para obtener más información, consulte [compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también
- [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [Compatibilidad con transacciones](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
