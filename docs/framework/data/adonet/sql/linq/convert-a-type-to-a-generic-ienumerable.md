---
title: Convertir un tipo en una interfaz IEnumerable genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d75c9b9123b52b3e241bea1bbd1d302c406715e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032713"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Convertir un tipo en una interfaz IEnumerable genérica
Utilice <xref:System.Linq.Enumerable.AsEnumerable%2A> para devolver el argumento cuyo tipo es una interfaz genérica `IEnumerable`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mediante la `Query` genérica predeterminada) intentaría convertir la consulta en SQL y ejecutarla en el servidor. Sin embargo, la cláusula `where` hace referencia a un método de cliente definido por el usuario (`isValidProduct`), que no se puede convertir a SQL.  
  
 La solución es especificar la implementación de interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> de `where` en el cliente para reemplazar la interfaz genérica <xref:System.Linq.IQueryable%601>. Para ello se invoca al operador <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
