---
title: "Determinar si alguno o todos los elementos de una secuencia satisfacen una condición"
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
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b9b79915e94ed1015c7869692647c10da58f60
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Determinar si alguno o todos los elementos de una secuencia satisfacen una condición
El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.  
  
 El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido. El `Where` / `where` cláusula se evalúa como `true` si el determinado `Customer` tiene `Order`.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Ejemplo  
 El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C". En el resultado devuelto se incluyen también los clientes que no tienen pedidos. (Por diseño, el operador <xref:System.Linq.Queryable.All%2A> devuelve `true` para una secuencia vacía.) Los clientes sin pedidos se eliminan en los resultados de la consola mediante el operador `Count`.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
