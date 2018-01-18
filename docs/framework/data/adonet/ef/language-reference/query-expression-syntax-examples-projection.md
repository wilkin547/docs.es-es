---
title: "Ejemplos de sintaxis de expresiones de consulta: proyección"
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
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a8339b02beb340709f4000a2373a4ce935fb6119
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="query-expression-syntax-examples-projection"></a>Ejemplos de sintaxis de expresiones de consulta: proyección
Los ejemplos de este tema muestran cómo usar el `Select` método y `From … From …` palabras clave para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) utilizando la sintaxis de expresiones de consulta. `From … From …` es el equivalente basado en las consultas del método `SelectMany`. El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a>Seleccionar  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el método <xref:System.Linq.Enumerable.Select%2A> para devolver todas las filas de la tabla `Product` y mostrar los nombres de producto.  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza <xref:System.Linq.Enumerable.Select%2A> para devolver una secuencia de nombres de producto solamente.  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el método <xref:System.Linq.Queryable.Select%2A> para proyectar las propiedades `Product.Name` y `Product.ProductID` en una secuencia de tipos anónimos.  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a>De... De... (SelectMany)  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa `From … From …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que `TotalDue` es inferior a 500,00.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza `From … From …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos efectuados a partir del 1 de octubre de 2002.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza `From … From …` (el equivalente al método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que el total del pedido es superior a 10000,00 y se utiliza la asignación `From` para evitar que se solicite dos veces el total.  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a>Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
