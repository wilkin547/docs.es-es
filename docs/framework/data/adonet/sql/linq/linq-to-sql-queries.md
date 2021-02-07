---
description: 'Más información acerca de: LINQ to SQL de consultas'
title: Consultas de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 5b5df2095043b01eb426de86e4add91941bb74c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712485"
---
# <a name="linq-to-sql-queries"></a>Consultas de LINQ to SQL

Las consultas se definen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la misma sintaxis que en Linq. La única diferencia es que los objetos a los que se hace referencia en las consultas se asignan a elementos de una base de datos. Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento. Más específicamente, la aplicación utiliza la API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para solicitar la ejecución de la consulta. Después, el proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] transforma la consulta en texto SQL y delega la ejecución al proveedor ADO. El proveedor ADO devuelve los resultados de la consulta como `DataReader`. El [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proveedor convierte los resultados de ADO en una <xref:System.Linq.IQueryable> colección de objetos de usuario.  
  
> [!NOTE]
> La mayoría de los métodos y operadores de .NET Framework tipos integrados tienen traducciones directas a SQL. Los que LINQ no puede traducir generan excepciones en tiempo de ejecución. Para obtener más información, consulte [SQL-CLR Type mapping](sql-clr-type-mapping.md).  
  
 En la tabla siguiente se muestran las similitudes y diferencias entre LINQ y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los elementos de consulta.  
  
|Elemento|Consulta LINQ|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Query|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo de valor devuelto de la variable local que contiene la consulta (para las consultas que devuelven secuencias)|Generic <ph id="ph1">`IEnumerable`</ph>|Generic <ph id="ph1">`IQueryable`</ph>|  
|Especificar el origen de datos|Usa la `From` cláusula (Visual Basic) o `from` (C#)|Iguales|  
|Filtrado|Usa la `Where` / `where` cláusula|Iguales|  
|Agrupar|Usa la `Group…By` / `groupby` cláusula|Iguales|  
|Seleccionar (proyectar)|Usa la `Select` / `select` cláusula|Iguales|  
|Ejecución diferida frente a ejecución inmediata|Vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Iguales|  
|Implementar combinaciones|Usa la `Join` / `join` cláusula|Puede utilizar la `Join` / `join` cláusula, pero utiliza el atributo de forma más eficaz <xref:System.Data.Linq.Mapping.AssociationAttribute> . Para obtener más información, consulte [realizar consultas en varias relaciones](querying-across-relationships.md).|  
|Ejecución remota frente a ejecución local||Para obtener más información, consulte [ejecución remota frente a ejecución local](remote-vs-local-execution.md).|  
|Consultas con transmisión por frecuencias frente a consultas con almacenamiento en caché|No aplicable en un escenario de memoria local||  
  
## <a name="see-also"></a>Vea también

- [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operaciones básicas de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relaciones entre tipos en las operaciones de consulta LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Conceptos sobre consultas](query-concepts.md)
