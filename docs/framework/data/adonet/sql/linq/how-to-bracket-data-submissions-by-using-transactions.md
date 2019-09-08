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
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones
Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos. Para obtener más información, consulte [compatibilidad con transacciones](transaction-support.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Realización y envío de cambios de datos](making-and-submitting-data-changes.md)
- [Compatibilidad con transacciones](transaction-support.md)
