---
title: "Cómo: Formular combinaciones y consultas entre productos"
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 703823368f451839304ce02ff8b5f7259a44b935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a>Cómo: Formular combinaciones y consultas entre productos
En los ejemplos siguientes se muestra cómo combinar los resultados procedentes de varias tablas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la `From` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` cláusula en C#) para seleccionar todos los pedidos de los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la `Where` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` cláusula en C#) para filtrar las existencias `Products` cuyo `Supplier` se encuentra en Estados Unidos.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la cláusula `From` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (cláusula `from` en C#) para aplicar un filtro y obtener los empleados de Seattle y una lista de sus áreas.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) para filtrar los pares de empleados que informa de un empleado a otro y que ambos empleados pertenecen a la misma `City`.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] ejemplo busca todos los clientes y pedidos, se asegura de que los pedidos se hacen coincidir con los clientes y que garantice que para cada cliente de esa lista, se proporciona un nombre de contacto.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se combinan explícitamente dos tablas y se proyectan los resultados de ambas.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se combinan explícitamente tres tablas y se proyectan los resultados de cada una de ellas.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo lograr una `LEFT OUTER JOIN` mediante `DefaultIfEmpty()`. El método `DefaultIfEmpty()` devuelve null cuando no hay ningún `Order` para `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se proyecta una expresión `let` que es el resultado de una combinación.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una `join` con una clave compuesta.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo construir una `join` de tal forma que una parte acepte valores NULL y la otra no.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
