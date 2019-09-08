---
title: Consultas de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: a170beae3a9f0c923502028f5579de1f3916c07d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793002"
---
# <a name="linq-to-sql-queries"></a>Consultas de LINQ to SQL
Las consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se definen utilizando la misma sintaxis que utilizaría en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. La única diferencia es que los objetos a los que se hace referencia en las consultas se asignan a elementos de una base de datos. Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento. Más específicamente, la aplicación utiliza la API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para solicitar la ejecución de la consulta. Después, el proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] transforma la consulta en texto SQL y delega la ejecución al proveedor ADO. El proveedor ADO devuelve los resultados de la consulta como `DataReader`. El [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proveedor convierte los resultados de ADO en una <xref:System.Linq.IQueryable> colección de objetos de usuario.  
  
> [!NOTE]
> La mayoría de los métodos y operadores de .NET Framework tipos integrados tienen traducciones directas a SQL. Los que [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] no puede convertir generan excepciones en tiempo de ejecución. Para obtener más información, consulte [SQL-CLR Type mapping](sql-clr-type-mapping.md).  
  
 La tabla siguiente muestra las similitudes y diferencias entre los elementos de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Elemento|Consulta LINQ|Consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo de valor devuelto de la variable local que contiene la consulta (para las consultas que devuelven secuencias)|`IEnumerable` genérico|`IQueryable` genérico|  
|Especificar el origen de datos|Usa la `From` cláusula (Visual Basic) `from` oC#()|Igual|  
|Filtrado|Usa la `Where`cláusula / `where`|Igual|  
|Agrupar|Usa la `Group…By`cláusula / `groupby`|Igual|  
|Seleccionar (proyectar)|Usa la `Select`cláusula / `select`|Igual|  
|Ejecución diferida frente a ejecución inmediata|Vea [Introducción a las consultas LINQC#()](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Igual|  
|Implementar combinaciones|Usa la `Join`cláusula / `join`|Puede utilizar la `Join` / <xref:System.Data.Linq.Mapping.AssociationAttribute> cláusula, pero utiliza el atributo de forma más eficaz. `join` Para obtener más información, consulte [realizar consultas en varias relaciones](querying-across-relationships.md).|  
|Ejecución remota frente a ejecución local||Para obtener más información, [vea Remote vs. Ejecución](remote-vs-local-execution.md)local.|  
|Consultas con transmisión por frecuencias frente a consultas con almacenamiento en caché|No aplicable en un escenario de memoria local||  
  
## <a name="see-also"></a>Vea también

- [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operaciones básicas de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relaciones entre tipos en las operaciones de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Conceptos sobre consultas](query-concepts.md)
