---
title: Consultas de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 478138d26d6cdf656b2487c637a5eb13784126e9
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634385"
---
# <a name="linq-to-sql-queries"></a>Consultas de LINQ to SQL
Las consultas de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se definen con la misma sintaxis que en LINQ. La única diferencia es que los objetos a los que se hace referencia en las consultas se asignan a elementos de una base de datos. Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento. Más específicamente, la aplicación utiliza la API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para solicitar la ejecución de la consulta. Después, el proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] transforma la consulta en texto SQL y delega la ejecución al proveedor ADO. El proveedor ADO devuelve los resultados de la consulta como `DataReader`. El proveedor de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traduce los resultados de ADO en una colección <xref:System.Linq.IQueryable> de objetos user.  
  
> [!NOTE]
> La mayoría de los métodos y operadores de .NET Framework tipos integrados tienen traducciones directas a SQL. Los que LINQ no puede traducir generan excepciones en tiempo de ejecución. Para obtener más información, consulte [SQL-CLR Type mapping](sql-clr-type-mapping.md).  
  
 En la tabla siguiente se muestran las similitudes y diferencias entre LINQ y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] elementos de consulta.  
  
|Elemento|Consulta LINQ|Consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo de valor devuelto de la variable local que contiene la consulta (para las consultas que devuelven secuencias)|`IEnumerable` genérico|`IQueryable` genérico|  
|Especificar el origen de datos|Usa la cláusula `From` (Visual Basic) o `from`C#()|Igual|  
|Filtrado|Usa la cláusula `Where`/`where`|Igual|  
|Agrupar|Usa la cláusula `Group…By`/`groupby`|Igual|  
|Seleccionar (proyectar)|Usa la cláusula `Select`/`select`|Igual|  
|Ejecución diferida frente a ejecución inmediata|Vea [Introducción a las consultas LINQC#()](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Igual|  
|Implementar combinaciones|Usa la cláusula `Join`/`join`|Puede usar la cláusula `Join`/`join`, pero utiliza de forma más eficaz el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute>. Para obtener más información, consulte [realizar consultas en varias relaciones](querying-across-relationships.md).|  
|Ejecución remota frente a ejecución local||Para obtener más información, vea [Remote vs. ](remote-vs-local-execution.md)de ejecución local.|  
|Consultas con transmisión por frecuencias frente a consultas con almacenamiento en caché|No aplicable en un escenario de memoria local||  
  
## <a name="see-also"></a>Vea también

- [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operaciones básicas de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relaciones entre tipos en las operaciones de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Conceptos sobre consultas](query-concepts.md)
