---
title: "Buscar el valor máximo de una secuencia numérica"
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
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 028a8e4a7fa215b0bdbce1de92c20dc51a15faa6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a>Buscar el valor máximo de una secuencia numérica
Utilice el operador <xref:System.Linq.Enumerable.Max%2A> para buscar el valor máximo de una secuencia de valores numéricos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se busca la fecha de la última contratación de cualquier empleado.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `11/15/1994 12:00:00 AM`.  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se busca el número máximo de unidades en existencias para cualquier producto.  
  
 Si ejecuta este ejemplo en la base de datos de ejemplo Northwind, el resultado es: `125`.  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza Max para encontrar los `Products` que tienen el precio unitario más alto en cada categoría. En este caso, los resultados se muestran por categoría.  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a>Vea también  
 [Consultas de agregado](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
