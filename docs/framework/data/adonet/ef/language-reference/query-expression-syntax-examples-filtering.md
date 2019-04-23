---
title: 'Ejemplos de sintaxis de expresiones de consulta: Filtrado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
ms.openlocfilehash: eb1680ba8ca2fab5511dc20c94ad997ef04974fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134555"
---
# <a name="query-expression-syntax-examples-filtering"></a>Ejemplos de sintaxis de expresiones de consulta: Filtrado
Los ejemplos de este tema muestran cómo usar el `Where` y `Where…Contains` métodos para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) con la sintaxis de expresión de consulta. Note, Where…`Contains` no se puede usar como parte de un [consulta compilada](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).  
  
 El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a>Where  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se devuelven todos los pedidos en línea.  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se devuelven los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se devuelven todos los productos de color rojo.  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a>Where…Contains  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa una matriz como parte de una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` que coincide con un valor de la matriz.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  Como parte del predicado de una cláusula `Where…Contains`, puede utilizar <xref:System.Array>, <xref:System.Collections.Generic.List%601> o una colección de cualquier tipo que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601>. También puede declarar e inicializar una colección en una consulta LINQ to Entities. Para obtener más información, vea el ejemplo siguiente.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente declara e inicializa las matrices en una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` o `Size` que coinciden con los valores de las matrices.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
