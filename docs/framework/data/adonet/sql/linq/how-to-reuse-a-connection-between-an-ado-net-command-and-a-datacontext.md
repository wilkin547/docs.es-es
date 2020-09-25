---
title: Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 89c9a12399d3d76487d1fdc2bd82aa037c167710
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197357"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext

Dado [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que forma parte de la familia de tecnologías ADO.net y se basa en los servicios proporcionados por ADO.net, puede reutilizar una conexión entre un comando ADO.net y un <xref:System.Data.Linq.DataContext> .  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando ADO.NET y <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [Información general](background-information.md)
- [ADO.NET y LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Comunicarse con la base de datos](communicating-with-the-database.md)
