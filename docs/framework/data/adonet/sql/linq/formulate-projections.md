---
title: Formular proyecciones
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8afd48c6ce7c6313e82a7b74c2271f52833d1f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-projections"></a>Formular proyecciones
En los ejemplos siguientes se muestra cómo la instrucción `select` en C# y la instrucción `Select` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] se puede combinar con otras características para formar proyecciones de consulta.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) para devolver una secuencia de nombres de contacto para `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono de `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados. El `FirstName` y `LastName` campos se combinan en un único campo (`Name`) y el `HomePhone` campo cambia a `Phone` en la secuencia resultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de todos los `ProductID`s y un valor calculado denominado `HalfPrice`. Este valor se establece en `UnitPrice` dividido entre 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y un *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad de los productos.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` cláusula (`select` cláusula en C#) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza `Select` y `Where` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` y `where` en C#) para devolver un *secuencia filtrada* de nombres de contacto para los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:  
  
-   Una secuencia de todos los pedidos y sus `OrderID` correspondientes.  
  
-   Una subsecuencia de los elementos del pedido que tienen descuento.  
  
-   La cantidad de dinero que se ahorra si no se incluye el envío en el precio.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
