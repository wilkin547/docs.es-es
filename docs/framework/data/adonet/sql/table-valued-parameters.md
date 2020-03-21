---
title: Parámetros con valores de tabla
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: 2917a8d9b42d831566855271a2f2110637db586f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174477"
---
# <a name="table-valued-parameters"></a>Parámetros con valores de tabla
Los parámetros con valores de tabla proporcionan una manera sencilla de serializar varias filas de datos de una aplicación cliente en SQL Server sin necesidad de ir y volver repetidas veces ni de ninguna lógica especial de servidor para procesar los datos. Puede usar parámetros con valores de tabla para encapsular filas de datos en una aplicación cliente y enviar los datos al servidor en un único comando con parámetros. Las filas de datos entrantes se almacenan en una variable de tabla en la que, a continuación, se puede operar mediante el uso de Transact-SQL.  
  
 El acceso a los valores de columna de los parámetros con valores de tabla se realiza con instrucciones estándar SELECT de Transact-SQL. Los parámetros con valores de tabla están fuertemente tipados y su estructura se valida automáticamente. El tamaño de los parámetros con valores de tabla solo está limitado por la memoria del servidor.  
  
> [!NOTE]
> No se pueden devolver datos en un parámetro con valores de tabla. Los parámetros con valores de tabla son de solo entrada; no se admite la palabra clave OUTPUT.  
  
 Para obtener más información sobre los parámetros con valores de tabla, vea los siguientes recursos.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Usar parámetros con valores de tabla (motor de base de datos)](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|Describe cómo crear y usar parámetros con valores de tabla.|  
|[Tipos de tablas definidas por el usuario](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))|Describe los tipos de tabla definidos por el usuario que se usan para declarar parámetros con valores de tabla.|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>Pasar varias filas de versiones previas de SQL Server  
 Antes de la incorporación de los parámetros con valores de tabla a SQL Server 2008, las opciones para pasar varias filas de datos a un procedimiento almacenado o a un comando SQL con parámetros eran limitadas. Un desarrollador podría elegir entre las siguientes opciones para pasar varias filas al servidor:  
  
- Usar una serie de parámetros individuales para representar los valores de varias columnas y filas de datos. La cantidad de datos que se pueden pasar mediante este método está limitada por el número de parámetros permitidos. Los procedimientos de SQL Server pueden tener 2100 parámetros como máximo. La lógica del lado servidor es necesaria para ensamblar estos valores individuales en una variable de tabla o una tabla temporal para su procesamiento.  
  
- Agrupar varios valores de datos en cadenas delimitadas o documentos XML y, a continuación, pasar esos valores de texto a un procedimiento o instrucción. Esto requiere que el procedimiento o la instrucción incluyan la lógica necesaria para validar las estructuras de datos y desagrupar los valores.  
  
- Crear una serie de instrucciones SQL individuales para las modificaciones de datos que afecten a varias filas, como los que se crean con una llamada al método `Update` de <xref:System.Data.SqlClient.SqlDataAdapter>. Los cambios se pueden enviar al servidor individualmente o por lotes en grupos. Sin embargo, incluso cuando se envían en lotes que contienen varias instrucciones, cada instrucción se ejecuta por separado en el servidor.  
  
- Use el programa de la utilidad `bcp` o el objeto <xref:System.Data.SqlClient.SqlBulkCopy> para cargar muchas filas de datos en una tabla. Aunque esta técnica es muy eficaz, no admite el procesamiento del lado servidor a menos que los datos se carguen en una tabla temporal o una variable de tabla.  
  
## <a name="creating-table-valued-parameter-types"></a>Crear tipos de parámetros con valores de tabla  
 Los parámetros con valores de tabla se basan en estructuras de tabla fuertemente tipadas definidas mediante instrucciones CREATE TYPE de Transact-SQL. Debe crear un tipo de tabla y definir la estructura en SQL Server para poder usar los parámetros con valores de tabla en las aplicaciones de cliente. Para obtener más información sobre la creación de tipos de tabla, vea [Tipos de tabla definidos por](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))el usuario .  
  
 La instrucción siguiente crea un tipo de tabla denominado CategoryTableType que consta de las columnas CategoryID y CategoryName:  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 Después de crear un tipo de tabla, puede declarar parámetros con valores de tabla basados en ese tipo. El siguiente fragmento de Transact-SQL muestra cómo declarar un parámetro con valores de tabla en una definición de procedimiento almacenado. Tenga en cuenta que la palabra clave READONLY es necesaria para declarar un parámetro con valores de tabla.  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>Modificar datos con parámetros con valores de tabla (Transact-SQL)  
 Los parámetros con valores de tabla se pueden utilizar en las modificaciones de datos basadas en conjuntos que afectan a varias filas mediante la ejecución de una única instrucción. Por ejemplo, puede seleccionar todas las filas de un parámetro con valores de tabla e insertarlas en una tabla de base de datos, o puede crear una instrucción UPDATE combinando un parámetro con valores de tabla en la tabla que desea actualizar.  
  
 La siguiente instrucción UPDATE de Transact-SQL muestra cómo usar un parámetro con valores de tabla al unirlo a la tabla Categories. Cuando se usa un parámetro con valores de tabla con JOIN en una cláusula FROM, también se debe crear el alias, como se muestra aquí, donde el parámetro con valores de tabla tiene el alias "EC":  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 Este ejemplo de Transact-SQL muestra cómo seleccionar filas de un parámetro con valores de tabla para ejecutar INSERT en una sola operación basada en conjuntos.  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a>Limitaciones de los parámetros con valores de tabla  
 Existen varias limitaciones para los parámetros con valores de tabla:  
  
- No puede pasar parámetros con valores de tabla a [funciones definidas por el usuario CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).  
  
- Los parámetros con valores de tabla solo se pueden indizar para admitir restricciones UNIQUE o PRIMARY KEY. SQL Server no mantiene estadísticas en los parámetros con valores de tabla.  
  
- Los parámetros con valores de tabla son de solo lectura en el código de Transact-SQL. No se pueden actualizar los valores de columna de las filas de un parámetro con valores de tabla y no se pueden insertar ni eliminar filas. Para modificar los datos que se pasan a un procedimiento almacenado o a una instrucción con parámetros en el parámetro con valores de tabla, debe insertar los datos en una tabla temporal o en una variable de tabla.  
  
- No se pueden usar instrucciones ALTER TABLE para modificar el diseño de parámetros con valores de tabla.  
  
## <a name="configuring-a-sqlparameter-example"></a>Configurar un ejemplo de SqlParameter  
 <xref:System.Data.SqlClient> permite rellenar parámetros con valores de tabla a partir de objetos <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> o <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>. Debe especificar un nombre de tipo para el parámetro con valores de tabla mediante la propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de <xref:System.Data.SqlClient.SqlParameter>. El valor `TypeName` debe coincidir con el nombre de un tipo compatible creado previamente en el servidor. El fragmento de código siguiente muestra cómo se configura <xref:System.Data.SqlClient.SqlParameter> para insertar datos.  

En el siguiente ejemplo, la variable `addedCategories` contiene <xref:System.Data.DataTable>. Para ver cómo se rellena la variable, vea los ejemplos de la sección siguiente [Paso de un parámetro con valores de tabla a un procedimiento almacenado](#passing).

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 También puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos a un parámetro con valores de tabla, como se muestra en este fragmento:  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a>Pasar un parámetro con valores de tabla a un procedimiento almacenado  
 En este ejemplo se muestra cómo pasar datos de parámetros con valores de tabla a un procedimiento almacenado. El código extrae las filas agregadas a un nuevo objeto <xref:System.Data.DataTable> mediante el método <xref:System.Data.DataTable.GetChanges%2A>. A continuación, el código define <xref:System.Data.SqlClient.SqlCommand>, estableciendo la propiedad <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> en <xref:System.Data.CommandType.StoredProcedure>. El valor <xref:System.Data.SqlClient.SqlParameter> se rellena con el método <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> y el valor <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> se establece en `Structured`. A continuación, se ejecuta <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> utilizando el método <xref:System.Data.SqlClient.SqlCommand>.  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a>Pasar un parámetro con valores de tabla a una instrucción SQL con parámetros  
 En el ejemplo siguiente se muestra cómo insertar datos en la tabla dbo.Categories mediante una instrucción INSERT con una subconsulta SELECT que tiene un parámetro con valores de tabla como origen de datos. Al pasar un parámetro con valores de tabla a una instrucción SQL con parámetros, debe especificar un nombre de tipo para el parámetro con valores de tabla utilizando la nueva propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de un parámetro <xref:System.Data.SqlClient.SqlParameter>. El parámetro `TypeName` debe coincidir con el nombre de un tipo compatible creado previamente en el servidor. El código de este ejemplo usa la propiedad `TypeName` para hacer referencia a la estructura de tipo definida en dbo.CategoryTableType.  
  
> [!NOTE]
> Si proporciona un valor para una columna de identidad en un parámetro con valores de tabla, debe emitir la instrucción SET IDENTITY_INSERT para la sesión.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a>Transmitir filas por secuencias con un DataReader  
 También puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos a un parámetro con valores de tabla. En el fragmento de código siguiente se muestra cómo recuperar datos de una base de datos de Oracle mediante <xref:System.Data.OracleClient.OracleCommand> y <xref:System.Data.OracleClient.OracleDataReader>. A continuación, el código configura un valor <xref:System.Data.SqlClient.SqlCommand> para invocar un procedimiento almacenado con un único parámetro de entrada. La propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> de <xref:System.Data.SqlClient.SqlParameter> está establecida en `Structured`. El valor <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> pasa el conjunto de resultados `OracleDataReader` al procedimiento almacenado como un parámetro con valores de tabla.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a>Consulte también

- [Configuración de parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Comandos y parámetros](../commands-and-parameters.md)
- [Parámetros de DataAdapter](../dataadapter-parameters.md)
- [Operaciones de datos de SQL Server en ADO.NET](sql-server-data-operations.md)
- [Información general de ADO.NET](../ado-net-overview.md)
