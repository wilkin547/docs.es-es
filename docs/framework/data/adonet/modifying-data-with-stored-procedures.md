---
title: Modificar datos con procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150757"
---
# <a name="modifying-data-with-stored-procedures"></a>Modificar datos con procedimientos almacenados

Los procedimientos almacenados pueden aceptar datos como parámetros de entrada y pueden devolver datos como parámetros de salida, conjuntos de resultados o valores de retorno. En el ejemplo siguiente se muestra cómo ADO.NET envía y recibe parámetros de entrada, parámetros de salida y valores de retorno. El ejemplo inserta un nuevo registro en una tabla cuya columna de clave principal es una columna de identidad en una base de datos de SQL Server.  
  
> [!NOTE]
> Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con <xref:System.Data.SqlClient.SqlDataAdapter>, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado. Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad. En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo se usa el siguiente procedimiento almacenado para insertar una nueva categoría en la tabla **Categories** de **Northwind** . El procedimiento almacenado toma el valor de la columna **CategoryName** como parámetro de entrada y usa la función SCOPE_IDENTITY () para recuperar el nuevo valor del campo de identidad, **CategoryID**, y devolverlo en un parámetro de salida. La instrucción return utiliza la @ROWCOUNT función @ para devolver el número de filas insertadas.  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 En el siguiente ejemplo de código se utiliza el anterior procedimiento almacenado `InsertCategory` como origen de la propiedad <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> de <xref:System.Data.SqlClient.SqlDataAdapter>. El parámetro de salida `@Identity` se reflejará en <xref:System.Data.DataSet> una vez que se haya insertado el registro en la base de dados al llamar al método `Update` del <xref:System.Data.SqlClient.SqlDataAdapter>. El código también recupera el valor devuelto.  
  
> [!NOTE]
> Al utilizar <xref:System.Data.OleDb.OleDbDataAdapter> , debe especificar los parámetros con un <xref:System.Data.ParameterDirection> de **ReturnValue** antes que los demás parámetros.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Ejecutar un comando](executing-a-command.md)
- [Información general de ADO.NET](ado-net-overview.md)
