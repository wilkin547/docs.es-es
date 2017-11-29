---
title: Concatenar dos secuencias
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a>Concatenar dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Concat%2A> para concatenar dos secuencias.  
  
 El operador <xref:System.Linq.Queryable.Concat%2A> se define para conjuntos múltiples ordenados en los que el orden del receptor y del argumento son el mismo.  
  
 En SQL, la ordenación es el último paso antes de que se generen los resultados. Por esta razón, el operador <xref:System.Linq.Queryable.Concat%2A> se implementa utilizando `UNION ALL` y no conserva el orden de sus argumentos. Para garantizar que el orden de los resultados es correcto, no olvide ordenar los resultados explícitamente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todos los números de teléfono y fax de `Customer` y `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todas las asignaciones de números de teléfono y nombres de `Customer` y `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Conversión de operadores de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
