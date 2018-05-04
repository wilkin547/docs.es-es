---
title: 'Ejemplos de sintaxis de consultas basadas en métodos: conversión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: 6ca770f067a3086f021cd87e226f66716b39e595
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-conversion"></a>Ejemplos de sintaxis de consultas basadas en métodos: conversión
Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> y <xref:System.Linq.Enumerable.ToList%2A> métodos para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizando sintaxis de consulta basada en métodos. El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a>ToArray  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a>ToDictionary  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToDictionary%2A> para evaluar de forma inmediata una secuencia y una expresión de clave relacionada en un diccionario.  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a>ToList  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToList%2A> para evaluar inmediatamente una secuencia en <xref:System.Collections.Generic.List%601>, donde `T` es de tipo <xref:System.Data.DataRow>.  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a>Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
