---
title: Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793292"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext
Dado [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que forma parte de la familia de tecnologías ADO.net y se basa en los servicios proporcionados por ADO.net, puede reutilizar una conexión entre un comando ADO.net <xref:System.Data.Linq.DataContext>y un.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo reutilizar la misma conexión entre un comando ADO.NET <xref:System.Data.Linq.DataContext>y.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
- [ADO.NET y LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Comunicación con la base de datos](communicating-with-the-database.md)
