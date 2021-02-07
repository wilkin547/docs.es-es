---
description: 'Más información sobre: devolver u omitir elementos de una secuencia'
title: Devolver u omitir elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 6eba93562d4c6a8ffa4150453deed88844d4e297
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695143"
---
# <a name="return-or-skip-elements-in-a-sequence"></a>Devolver u omitir elementos de una secuencia

Utilice el operador <xref:System.Linq.Queryable.Take%2A> para devolver un número determinado de elementos de una secuencia y omitir el resto.  
  
 Utilice el operador <xref:System.Linq.Queryable.Skip%2A> para omitir un número determinado de elementos de una secuencia y devolver el resto.  
  
> [!NOTE]
> <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000. Para obtener más información, vea la entrada sobre cómo omitir y tomar excepciones en SQL Server 2000 "en [solución de problemas](troubleshooting.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traduce mediante <xref:System.Linq.Queryable.Skip%2A> una subconsulta con la `NOT EXISTS` cláusula SQL. Esta conversión tiene las limitaciones siguientes:  
  
- El argumento debe ser un conjunto. No se admiten los conjuntos múltiples, aunque estén ordenados.  
  
- La consulta generada puede ser mucho más compleja que la consulta generada para la consulta base en la que se aplica <xref:System.Linq.Queryable.Skip%2A>. Esta complejidad puede mermar el rendimiento o incluso hacer que se agote el tiempo de espera.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza `Take` para seleccionar los cinco primeros `Employees` contratados. Observe que la colección primero se ordena por `HireDate`.  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.Skip%2A> para seleccionar todos los `Products` excepto los 10 más caros.  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se combinan los métodos <xref:System.Linq.Queryable.Skip%2A> y <xref:System.Linq.Queryable.Take%2A> para omitir los 50 primeros registros y después devolver los 10 siguientes.  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 Las operaciones <xref:System.Linq.Queryable.Take%2A> y <xref:System.Linq.Queryable.Skip%2A> solo están perfectamente definidas para los conjuntos ordenados. La semántica para los conjuntos no ordenados o conjuntos múltiples no está definida.  
  
 Debido a las limitaciones de la ordenación en SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta trasladar la ordenación del argumento del operador <xref:System.Linq.Queryable.Take%2A> o <xref:System.Linq.Queryable.Skip%2A> al resultado del operador.  
  
> [!NOTE]
> La traducción es diferente para SQL Server 2000 y SQL Server 2005. Si tiene previsto usar <xref:System.Linq.Queryable.Skip%2A> con una consulta de cualquier complejidad, use SQL Server 2005.  
  
 Considere la siguiente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consulta para SQL Server 2000:  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traslada la operación de ordenación al final en el código de SQL, como se observa a continuación:  
  
```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 Cuando se encadenan <xref:System.Linq.Queryable.Take%2A> y <xref:System.Linq.Queryable.Skip%2A>, todos los criterios de ordenación especificados deben ser coherentes. De lo contrario, los resultados no están definidos.  
  
 Para los argumentos integrales constantes no negativos basados en la especificación de SQL, tanto <xref:System.Linq.Queryable.Take%2A> como <xref:System.Linq.Queryable.Skip%2A> están perfectamente definidos.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
