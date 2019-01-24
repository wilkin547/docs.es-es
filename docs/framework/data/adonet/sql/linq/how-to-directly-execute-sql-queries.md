---
title: Procedimiento Ejecutar directamente consultas SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 1caf81df5998e5aaef4ad011a399d70aff43ca9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634463"
---
# <a name="how-to-directly-execute-sql-queries"></a>Procedimiento Ejecutar directamente consultas SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL parametrizadas (en formato de texto) y las envía al servidor SQL Server para su procesamiento.  
  
 SQL no puede ejecutar todos los métodos que podrían estar localmente disponibles para una aplicación. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta convertir estos métodos locales en operaciones y funciones equivalentes que estén disponibles en el entorno de SQL. La mayoría de los métodos y operadores de los tipos integrados de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] tienen comandos SQL que son equivalentes directos. Algunos se pueden generar a partir de las funciones que están disponibles. Aquellos que no se pueden generar, inician excepciones en tiempo de ejecución. Para obtener más información, consulte [asignación de tipos de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Cuando una consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no es suficiente para una tarea especializada, puede utilizar el método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> para ejecutar una consulta SQL y después convertir el resultado de la consulta directamente en objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, supongamos que los datos de la clase `Customer` ocupan dos tablas (customer1 y customer2). La consulta devuelve una secuencia de objetos `Customer`.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 Siempre que los nombres de columna en los resultados tabulares coincidan con las propiedades de columna de la clase de entidad, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea objetos a partir de cualquier consulta SQL.  
  
## <a name="example"></a>Ejemplo  
 El método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> también permite el uso de parámetros. Utilice código como el siguiente para ejecutar una consulta parametrizada.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Los parámetros se expresan en el texto de la consulta con la misma notación con llaves que `Console.WriteLine()` y `String.Format()`. De hecho, `String.Format()` realmente se llama en la cadena de consulta proporcionada, sustituyendo los parámetros entre llaves con genera los nombres de parámetro como @p0, @p1 ..., @p(n).  
  
## <a name="see-also"></a>Vea también
- [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Consulta de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
