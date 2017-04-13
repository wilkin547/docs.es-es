---
title: "Determinar si alguno de los elementos de una secuencia satisface una condici&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Determinar si alguno de los elementos de una secuencia satisface una condici&#243;n
El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.  
  
 El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.  
  
## Ejemplo  
 En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido.  La cláusula `Where`\/`where` se evalúa como `true` si el `Customer` dado tiene cualquier `Order`.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## Ejemplo  
 El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## Ejemplo  
 En el ejemplo de C\# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C".  En el resultado devuelto se incluyen también los clientes que no tienen pedidos.  \(Por diseño, el operador <xref:System.Linq.Queryable.All%2A> devuelve `true` para una secuencia vacía.\) Los clientes sin pedidos se eliminan en los resultados de la consola mediante el operador `Count`.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)