---
description: 'Más información acerca de: determinar si alguno o todos los elementos de una secuencia satisfacen una condición'
title: Determinar si alguno o todos los elementos de una secuencia satisfacen una condición
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: a46cf7e4e213eba830dc203f9266a408103cee80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786113"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Determinar si alguno o todos los elementos de una secuencia satisfacen una condición

El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.  
  
 El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido. La `Where` / `where` cláusula se evalúa como `true` si el especificado `Customer` tiene any `Order` .  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Ejemplo  

 El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C". En el resultado devuelto se incluyen también los clientes que no tienen pedidos. (Por diseño, el <xref:System.Linq.Queryable.All%2A> operador devuelve `true` para una secuencia vacía). Los clientes sin pedidos se eliminan en la salida de la consola mediante el `Count` operador.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
