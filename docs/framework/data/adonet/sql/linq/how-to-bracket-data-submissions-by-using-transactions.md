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
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones

Puede utilizar <xref:System.Transactions.TransactionScope> para catalogar sus envíos a la base de datos. Para obtener más información, consulte [compatibilidad con transacciones](transaction-support.md).  
  
## <a name="example"></a>Ejemplo  

 El código siguiente incluye el envío de base de datos en <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Realizar y enviar cambios de datos](making-and-submitting-data-changes.md)
- [Compatibilidad con transacciones](transaction-support.md)
