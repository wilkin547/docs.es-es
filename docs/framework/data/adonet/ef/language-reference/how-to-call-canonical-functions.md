---
title: 'Cómo: Llamar a funciones canónicas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
ms.openlocfilehash: 7ad7f79cb41b5d4821a910ede7f955b4f0fe6fab
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-call-canonical-functions"></a>Cómo: Llamar a funciones canónicas
La clase <xref:System.Data.Objects.EntityFunctions> contiene métodos que exponen funciones canónicas para usarlas en consultas LINQ to Entities. Para obtener información sobre las funciones canónicas, vea [Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
> [!NOTE]
>  Los métodos <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> y <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> de la clase <xref:System.Data.Objects.EntityFunctions> no tienen equivalentes de función canónica.  
  
 Las funciones canónicas que realizan un cálculo en un conjunto de valores y devuelven un valor único (también denominadas funciones canónicas de agregado) se pueden invocar directamente. Otras funciones canónicas solo se pueden llamar como parte de una consulta LINQ to Entities. Para llamar directamente a una función de agregado, debe pasar un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función. Para obtener más información, vea el segundo ejemplo siguiente.  
  
 Puede llamar a algunas funciones canónicas utilizando los métodos de Common Language Runtime (CLR) en consultas LINQ to Entities. Para obtener una lista de métodos CLR que se asignan a funciones canónicas, vea [método CLR a la asignación de función canónica](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). En el ejemplo se ejecuta una consulta LINQ to Entities que utiliza el método <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> para devolver todos los productos para los que la diferencia entre `SellEndDate` y `SellStartDate` es menor a 365 días:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). El ejemplo llama directamente al método de agregado <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> para devolver la desviación estándar de subtotales `SalesOrderHeader`. Observe que se pasa un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función, lo que permite llamarla aunque no forme parte de una consulta LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Llamada a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
