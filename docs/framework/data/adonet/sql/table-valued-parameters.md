---
title: "Parámetros con valores de tabla"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 47956848079e6094dc000d95ec4066f814a70e35
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="table-valued-parameters"></a>Parámetros con valores de tabla
Los parámetros con valores de tabla proporcionan un método sencillo para calcular las referencias de varias filas de datos procedentes de una aplicación cliente en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] sin necesidad de efectuar varios viajes de ida y vuelta (round trip) ni de crear lógica especial de servidor para procesar los datos. Puede usar los parámetros con valores de tabla para encapsular las filas de datos de una aplicación cliente y enviar los datos al servidor en un único comando con parámetros. Las filas de datos de entrada se almacenan en una variable de tabla en la que se puede operar usando [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].  
  
 El acceso a los valores de columna de los parámetros con valores de tabla se realiza mediante instrucciones estándar SELECT de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]. Los parámetros con valores de tabla están fuertemente tipados y su estructura se valida automáticamente. El tamaño de los parámetros con valores de tabla está únicamente limitado por la memoria del servidor.  
  
> [!NOTE]
>  No puede devolver datos de un parámetro con valor de tabla. Los parámetros con valores de tabla son sólo de entrada; no se admite la palabra clave OUTPUT.  
  
 Para obtener más información sobre parámetros con valores de tabla, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Parámetros con valores de tabla (motor de base de datos)](http://go.microsoft.com/fwlink/?LinkId=98363) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla|Describe cómo se crean y se usan los parámetros con valores de tabla.|  
|[Tipos de tabla definidos por el usuario](http://go.microsoft.com/fwlink/?LinkId=98364) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla|Describe los tipos de tabla definidos por el usuario que se usan para declarar parámetros con valores de tabla.|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>Pasar varias filas de versiones previas de SQL Server  
 Antes de la incorporación de los parámetros con valores de tabla a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2008, las opciones para pasar varias filas de datos a un procedimiento almacenado o a un comando SQL con parámetros eran limitadas. Un programador podía elegir entre las siguientes opciones para pasar varias filas al servidor:  
  
-   Usar una serie de parámetros individuales para representar los valores en varias columnas y filas de datos. La cantidad de datos que se pueden pasar mediante este método está limitada por el número de parámetros permitidos. Los procedimientos de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] pueden tener 2100 parámetros como máximo. La lógica de servidor es necesaria para ensamblar estos valores individuales en una variable de tabla o en una tabla temporal para su procesamiento.  
  
-   Empaquetar varios valores de datos en cadenas delimitadas o documentos XML y, a continuación, pasar esos valores de texto a un procedimiento o instrucción. Por ello, el procedimiento o la instrucción deben incluir la lógica necesaria para validar las estructuras de datos y desempaquetar los valores.  
  
-   Crear una serie de instrucciones SQL individuales para las notificaciones de datos que afecten varias filas, como las creadas mediante la llamada al método `Update` de <xref:System.Data.SqlClient.SqlDataAdapter>. Los cambios se pueden enviar individualmente o por lotes en grupos al servidor. Sin embargo, aunque se envíen por lotes que contengan varias instrucciones, cada instrucción se ejecuta por separado en el servidor.  
  
-   Usar la utilidad `bcp` o el objeto <xref:System.Data.SqlClient.SqlBulkCopy> para cargar muchas filas de datos en una tabla. Aunque esta técnica sea muy eficaz, no es compatible con el procesamiento de servidor a menos que los datos se carguen en una tabla temporal o en una variable de tabla.  
  
## <a name="creating-table-valued-parameter-types"></a>Crear tipos de parámetros con valores de tabla  
 Los parámetros con valores de tabla se basan en estructuras de tabla fuertemente tipadas definidas mediante instrucciones CREATE TYPE de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]. Debe crear un tipo de tabla y definir la estructura en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] antes de poder usar los parámetros con valores de tabla en las aplicaciones cliente. Para obtener más información acerca de cómo crear tipos de tabla, vea [tipos de tabla definidos por el usuario](http://go.microsoft.com/fwlink/?LinkID=98364) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla.  
  
 La siguiente instrucción crea un tipo de tabla denominado CategoryTableType formada por las columnas CategoryID y CategoryName:  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 Después de crear un tipo de tabla, puede declarar los parámetros con valores de tabla basados en ese tipo. El siguiente fragmento de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo declarar un parámetro con valores de tabla en una definición de procedimiento almacenado. Observe que se requiere la palabra clave READONLY para declarar un parámetro con valores de tabla.  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>Modificar datos con parámetros con valores de tabla (Transact-SQL)  
 Los parámetros con valores de tabla se pueden usar en modificaciones de datos basados en conjuntos que afectan varias filas mediante la ejecución de una sola instrucción. Por ejemplo, puede seleccionar todas las filas de un parámetro con valores de tabla e insertarlas en una tabla de base de datos o crear una instrucción de actualización mediante la combinación de un parámetro con valores de tabla y la tabla que desee actualizar.  
  
 La siguiente instrucción UPDATE de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo usar un parámetro con valores de tabla mediante su unión con la tabla Categories. Cuando use un parámetro con valores de tabla con JOIN en una cláusula FROM, también debe asignarle un alias, como se muestra aquí, donde el parámetro con valores de tabla tiene el alias "ec":  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 Este ejemplo de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo seleccionar en un parámetro con valores de tabla para ejecutar INSERT en una sola operación basada en conjuntos.  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a>Limitaciones de los parámetros con valores de tabla  
 Existen varias limitaciones en los parámetros con valores de tabla:  
  
-   No se puede pasar parámetros con valores de tabla para [funciones CLR definidas por el usuario](http://msdn.microsoft.com/library/ms131077.aspx).  
  
-   Los parámetros con valores de tabla solo se pueden indizar para admitir restricciones UNIQUE o PRIMARY KEY. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] no mantiene estadísticas de parámetros con valores de tabla.  
  
-   Los parámetros con valores de tabla son de solo lectura en el código [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]. No puede actualizar los valores de columna de las filas de un parámetro con valores de tabla ni insertar ni eliminar filas. Para modificar los datos que se pasan a un procedimiento almacenado o a una instrucción con parámetros de un parámetro con valores de tabla, debe insertar los datos en una tabla temporal o en una variable de tabla.  
  
-   No puede usar instrucciones ALTER TABLE para modificar el diseño de los parámetros con valores de tabla.  
  
## <a name="configuring-a-sqlparameter-example"></a>Configurar un ejemplo de SqlParameter  
 <xref:System.Data.SqlClient>admite rellenar parámetros con valores de tabla desde <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> o <xref:System.Collections.Generic.IEnumerable%601>  \  <xref:Microsoft.SqlServer.Server.SqlDataRecord> objetos. Debe especificar un nombre de tipo para el parámetro con valores de tabla mediante la propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de una clase <xref:System.Data.SqlClient.SqlParameter>. El valor de `TypeName` debe coincidir con el nombre de un tipo compatible previamente creado en el servidor. El fragmento de código siguiente muestra cómo se configura <xref:System.Data.SqlClient.SqlParameter> para insertar datos.  
  
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
  
 Además puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos por secuencias a un parámetro con valores de tabla, como se muestra en este fragmento:  
  
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
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a>Pasar un parámetro con valores de tabla a un procedimiento almacenado  
 Este ejemplo muestra cómo pasar datos de parámetros con valores de tabla a un procedimiento almacenado. El código extrae las filas agregadas en un nuevo elemento <xref:System.Data.DataTable> mediante el uso del método <xref:System.Data.DataTable.GetChanges%2A>. Después, el código define <xref:System.Data.SqlClient.SqlCommand>, estableciendo el valor de la propiedad <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> en <xref:System.Data.CommandType.StoredProcedure>. <xref:System.Data.SqlClient.SqlParameter> se rellena mediante el método <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> y la propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> se establece en `Structured`. <xref:System.Data.SqlClient.SqlCommand> se ejecuta luego mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.  
  
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
 El siguiente ejemplo muestra cómo insertar datos en la tabla dbo.Categories mediante una instrucción INSERT con una subconsulta SELECT que tiene un parámetro con valores de tabla como el origen de los datos. Cuando se pasa un parámetro con valores de tabla a una instrucción SQL con parámetros, debe especificar un nombre de tipo para dicho parámetro mediante el uso de la nueva propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de <xref:System.Data.SqlClient.SqlParameter>. Este valor de `TypeName` debe coincidir con el nombre de un tipo compatible previamente creado en el servidor. El código de este ejemplo usa la propiedad `TypeName` para hacer referencia a la estructura de tipos definida en dbo.CategoryTableType.  
  
> [!NOTE]
>  Si proporciona un valor para una columna de identidad de un parámetro con valores de tabla, debe emitir la instrucción SET IDENTITY_INSERT de la sesión.  
  
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
 Asimismo puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos por secuencias a un parámetro con valores de tabla. El siguiente fragmento de código muestra la recuperación de datos de una base de datos de Oracle mediante el uso de <xref:System.Data.OracleClient.OracleCommand> y <xref:System.Data.OracleClient.OracleDataReader>. Después el código configura un elemento <xref:System.Data.SqlClient.SqlCommand> para invocar un procedimiento almacenado con un solo parámetro de entrada. La propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> de <xref:System.Data.SqlClient.SqlParameter> se establece en `Structured`. <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> pasa el conjunto de resultados de `OracleDataReader` al procedimiento almacenado como parámetro con valores de tabla.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Configurar parámetros y tipos de datos de parámetro](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Comandos y parámetros](../../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Parámetros de DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [Operaciones de datos de SQL Server en ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
