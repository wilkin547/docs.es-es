---
title: "Contar el número de elementos de una secuencia"
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
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f6d1403384b8725720abbe9a81f98cbbfdb9c6e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Contar el número de elementos de una secuencia
Utilice al operador <xref:System.Linq.Enumerable.Count%2A> para contar el número de elementos de una secuencia.  
  
 Al ejecutar esta consulta en la base de datos de ejemplo Northwind, se genera un resultado de `91`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se cuenta el número de `Customers` en la base de datos.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se cuenta el número de productos de la base de datos que no han dejado de fabricarse.  
  
 Al ejecutar este ejemplo en la base de datos de ejemplo Northwind, se genera un resultado de `69`.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Consultas de agregado](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
