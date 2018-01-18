---
title: Devolver el primer elemento de una secuencia
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
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bbdfe78f15490ce2c6722c83a4615ca29cbc5863
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-first-element-in-a-sequence"></a>Devolver el primer elemento de una secuencia
Utilice el operador <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una secuencia. Las consultas que usan <xref:System.Linq.Enumerable.First%2A> se ejecutan inmediatamente.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite el operador <xref:System.Linq.Enumerable.Last%2A>.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente busca el primer `Shipper` de una tabla:  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son  
  
 `ID = 1, Company = Speedy Express`.  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente busca el `Customer` único cuyo `CustomerID` es BONAP.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son `ID = BONAP, Contact = Laurence Lebihan`.  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
