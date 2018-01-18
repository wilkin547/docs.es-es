---
title: "Devolver la unión de conjuntos de dos secuencias"
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 24a3c7e7ee33d616afdbc9651850c10716a0547c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-set-union-of-two-sequences"></a>Devolver la unión de conjuntos de dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Union%2A> para devolver una secuencia de todos los países en los que hay `Customers` o `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> operador se define para conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (hecho, el resultado de la `UNION ALL` cláusula de SQL).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Traslación del operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
