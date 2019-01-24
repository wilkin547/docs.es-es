---
title: Procedimiento Llamar a funciones de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 2b157f9ff1e87b54b965a3ed57865bf7963a7509
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742047"
---
# <a name="how-to-call-database-functions"></a>Procedimiento Llamar a funciones de base de datos
La clase <xref:System.Data.Objects.SqlClient.SqlFunctions> contiene métodos que exponen funciones de SQL Server para usarlas en consultas LINQ to Entities. Al usar los métodos <xref:System.Data.Objects.SqlClient.SqlFunctions> en consultas LINQ to Entities, las funciones de base de datos correspondientes se ejecutan en la base de datos.  
  
> [!NOTE]
>  Las funciones de base de datos que realizan un cálculo en un conjunto de valores y devuelven un valor único (también denominadas funciones de agregado de base de datos) se pueden invocar directamente. Otras funciones canónicas solo se pueden llamar como parte de una consulta LINQ to Entities. Para llamar directamente a una función de agregado, debe pasar un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función. Para obtener más información, vea el segundo ejemplo siguiente.  
  
> [!NOTE]
>  Los métodos de la clase <xref:System.Data.Objects.SqlClient.SqlFunctions> son específicos de las funciones de SQL Server. Es posible que otros proveedores dispongan de clases similares que exponen funciones de base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). En el ejemplo se ejecuta una consulta LINQ to Entities que usa el método <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> para devolver todos los contactos cuyos apellidos empiezan por "Si":  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). El ejemplo llama directamente al método de agregado <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>. Observe que se pasa un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función, lo que permite llamarla aunque no forme parte de una consulta LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Vea también
- [Llamada a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
