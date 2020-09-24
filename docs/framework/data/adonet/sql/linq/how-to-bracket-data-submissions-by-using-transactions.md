---
title: Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161365"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones

Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos. Para obtener más información, consulte [compatibilidad con transacciones](transaction-support.md).  
  
## <a name="example"></a>Ejemplo  

 El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Realizar y enviar cambios de datos](making-and-submitting-data-changes.md)
- [Compatibilidad con transacciones](transaction-support.md)
