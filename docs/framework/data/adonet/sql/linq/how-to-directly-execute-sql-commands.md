---
title: Filtrar para ejecutar directamente comandos SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: eeac6272f176ac8e780b72b0076d032ad9e8f108
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078907"
---
# <a name="how-to-directly-execute-sql-commands"></a>Filtrar para ejecutar directamente comandos SQL
En el supuesto de que tuviese una conexión <xref:System.Data.Linq.DataContext>, podría utilizar <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para ejecutar comandos SQL que no devuelven objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente hace que SQL Server aumente el precio unitario (UnitPrice) en 1,00.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Filtrar para ejecutar directamente consultas SQL](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [Comunicarse con la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
