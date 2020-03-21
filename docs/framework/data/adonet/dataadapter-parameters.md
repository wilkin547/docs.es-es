---
title: Parámetros de DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 9954570dcf33c5eea4dcccf880de2c307de0aeca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151551"
---
# <a name="dataadapter-parameters"></a>Parámetros de DataAdapter
<xref:System.Data.Common.DbDataAdapter> tiene cuatro propiedades que se utilizan para recuperar y actualizar datos en el origen de datos: la propiedad <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> devuelve datos del origen de datos y las propiedades <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> y <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> se utilizan para administrar los cambios en el origen de datos. La propiedad `SelectCommand` debe establecerse antes de llamar al método `Fill` de `DataAdapter`. Las propiedades `InsertCommand`, `UpdateCommand` o `DeleteCommand` se deben establecer antes llamar al método `Update` de `DataAdapter`, en función de las modificaciones realizadas en los datos en <xref:System.Data.DataTable>. Por ejemplo, si se han agregado filas, se debe establecer `InsertCommand` antes de llamar a `Update`. Cuando `Update` procesa una fila insertada, actualizada o eliminada, `DataAdapter` utiliza la propiedad `Command` que corresponde a la acción en cuestión. La información actual relacionada con la fila modificada se pasa al objeto `Command` a través de la colección `Parameters`.  
  
 Cuando se actualiza una fila en el origen de datos, se llama a la instrucción UPDATE, que usa un identificador único para identificar la fila de la tabla que se va a actualizar. El identificador único suele ser el valor del campo de clave principal. La instrucción UPDATE utiliza parámetros que contienen el identificador único y las columnas y valores que se van a actualizar, como muestra la siguiente instrucción Transact-SQL.  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> La sintaxis de los marcadores de posición de parámetros depende del origen de datos. En este ejemplo se muestran marcadores de posición para un origen de datos de SQL Server. Utilice signos de interrogación de cierre (?) como marcadores de posición de para los parámetros <xref:System.Data.OleDb> y <xref:System.Data.Odbc>.  
  
 En este ejemplo de `CompanyName` Visual Basic, el `@CompanyName` campo se actualiza `CustomerID` con el valor `@CustomerID` del parámetro para la fila donde es igual al valor del parámetro. Los parámetros recuperan información <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> de la <xref:System.Data.SqlClient.SqlParameter> fila modificada mediante la propiedad del objeto. A continuación se muestran los parámetros del ejemplo anterior de la instrucción UPDATE. En el código se parte de que el `adapter` de la variable representa a un objeto <xref:System.Data.SqlClient.SqlDataAdapter> válido.  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 El método `Add` de la colección `Parameters` toma el nombre del parámetro, el tipo de datos, el tamaño (si corresponde al tipo) y el nombre de la propiedad <xref:System.Data.Common.DbParameter.SourceColumn%2A> de `DataTable`. Tenga en cuenta que <xref:System.Data.Common.DbParameter.SourceVersion%2A> del parámetro `@CustomerID` se establece en `Original`. De esta forma se garantiza que la fila existente en el origen de datos se actualice cuando el valor de la columna o columnas identificadas haya cambiado en la fila <xref:System.Data.DataRow> modificada. En ese caso, el valor de la fila `Original` coincidiría con el valor actual en el origen de datos y el valor de la fila `Current` contendría el valor actualizado. No se asigna ningún valor a `SourceVersion` para el parámetro `@CompanyName`, por lo que se utiliza el valor predeterminado, el de la fila `Current`.  
  
> [!NOTE]
> Para las `Fill` operaciones `DataAdapter` del `Get` `DataReader`, el tipo de .NET Framework se deduce del tipo devuelto por el proveedor de datos de .NET Framework. Los tipos de .NET Framework deducidos y los métodos de descriptor de acceso para los tipos de datos de Microsoft SQL Server, OLE DB y ODBC se describen en [Asignaciones](data-type-mappings-in-ado-net.md)de tipos de datos en ADO.NET .  
  
## <a name="parametersourcecolumn-parametersourceversion"></a>Parameter.SourceColumn, Parameter.SourceVersion  
 `SourceColumn` y `SourceVersion` se pueden pasar como argumentos al constructor `Parameter`, o también se pueden establecer como propiedades de un `Parameter` existente. `SourceColumn` es el nombre de <xref:System.Data.DataColumn> de <xref:System.Data.DataRow> en la que se recupera el valor de `Parameter`. `SourceVersion` especifica la versión de `DataRow` que utiliza `DataAdapter` para recuperar el valor.  
  
 En la tabla siguiente se muestran los valores de la enumeración <xref:System.Data.DataRowVersion> disponibles para su uso con `SourceVersion`.  
  
|Enumeración DataRowVersion|Descripción|  
|--------------------------------|-----------------|  
|`Current`|El parámetro utiliza el valor actual de la columna. Este es el valor predeterminado.|  
|`Default`|El parámetro utiliza el `DefaultValue` de la columna.|  
|`Original`|El parámetro utiliza el valor original de la columna.|  
|`Proposed`|El parámetro utiliza un valor propuesto.|  
  
 En el ejemplo de código de `SqlClient` de la siguiente sección se define un parámetro para <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> donde la columna `CustomerID` se utiliza como `SourceColumn` para dos parámetros: `@CustomerID` (`SET CustomerID = @CustomerID`) y `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`). El `@CustomerID` parámetro se utiliza para actualizar la columna `DataRow` **CustomerID** al valor actual en el archivo . Como resultado, `CustomerID` `SourceColumn` se `SourceVersion` utiliza `Current` el con un. El `@OldCustomerID` parámetro se utiliza para identificar la fila actual en el origen de datos. Dado que el valor de la columna coincidente se encuentra en la versión `Original` de la fila, también se usa el mismo objeto `SourceColumn` (`CustomerID`) con `SourceVersion` de `Original`.  
  
## <a name="working-with-sqlclient-parameters"></a>Trabajar con parámetros SqlClient  
 En el ejemplo siguiente se muestra cómo crear <xref:System.Data.SqlClient.SqlDataAdapter> y establecer <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> en <xref:System.Data.MissingSchemaAction.AddWithKey> para recuperar información de esquema adicional de la base de datos. Las propiedades <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> y <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> establecen sus correspondientes objetos <xref:System.Data.SqlClient.SqlParameter> agregados a la colección <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>. El método devuelve un objeto `SqlDataAdapter`.  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a>Marcadores de posición de parámetros OleDb  
 En el caso de los objetos <xref:System.Data.OleDb.OleDbDataAdapter> y <xref:System.Data.Odbc.OdbcDataAdapter>, debe utilizar signos de interrogación de cierre (?) como marcadores de posición para identificar los parámetros.  
  
```vb  
Dim selectSQL As String = _  
  "SELECT CustomerID, CompanyName FROM Customers " & _  
  "WHERE CountryRegion = ? AND City = ?"  
Dim insertSQL AS String = _  
  "INSERT INTO Customers (CustomerID, CompanyName) VALUES (?, ?)"  
Dim updateSQL AS String = _  
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " & _  
  WHERE CustomerID = ?"  
Dim deleteSQL As String = "DELETE FROM Customers WHERE CustomerID = ?"  
```  
  
```csharp  
string selectSQL =
  "SELECT CustomerID, CompanyName FROM Customers " +  
  "WHERE CountryRegion = ? AND City = ?";  
string insertSQL =
  "INSERT INTO Customers (CustomerID, CompanyName) " +  
  "VALUES (?, ?)";  
string updateSQL =
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " +  
  "WHERE CustomerID = ? ";  
string deleteSQL = "DELETE FROM Customers WHERE CustomerID = ?";  
```  
  
 Las instrucciones de consulta con parámetros definen qué parámetros de entrada y de salida se deben crear. Para crear un parámetro, se utiliza el método `Parameters.Add` o el constructor `Parameter` con el fin de especificar el nombre de columna, tipo de datos y tamaño. En el caso de tipos de datos intrínsecos, como `Integer`, no es necesario incluir el tamaño, aunque se puede especificar el tamaño predeterminado.  
  
 En el ejemplo de código siguiente se crean los parámetros para una instrucción SQL y, a continuación, se llena un `DataSet`.  
  
## <a name="oledb-example"></a>Ejemplo de OleDb  
  
```vb  
' Assumes that connection is a valid OleDbConnection object.  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter
  
Dim selectCMD AS OleDbCommand = New OleDbCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add parameters and set values.  
selectCMD.Parameters.Add( _  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add( _  
  "@City", OleDbType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OleDbConnection object.  
OleDbDataAdapter adapter = new OleDbDataAdapter();  
  
OleDbCommand selectCMD = new OleDbCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
// Add parameters and set values.  
selectCMD.Parameters.Add(  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add(  
  "@City", OleDbType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
## <a name="odbc-parameters"></a>Parámetros Odbc  
  
```vb  
' Assumes that connection is a valid OdbcConnection object.  
Dim adapter As OdbcDataAdapter = New OdbcDataAdapter  
  
Dim selectCMD AS OdbcCommand = New OdbcCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OdbcConnection object.  
OdbcDataAdapter adapter = new OdbcDataAdapter();  
  
OdbcCommand selectCMD = new OdbcCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
//Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> Si no se proporciona un nombre de parámetro para un parámetro, el parámetro recibe un nombre predeterminado incremental de Parámetro*N* *,* empezando por "Parameter1". Se recomienda evitar la convención de nomenclatura Parámetro*N* al proporcionar un nombre de parámetro, ya que el nombre que proporcione podría entrar en conflicto con un nombre de parámetro predeterminado existente en el `ParameterCollection`archivo . Si el nombre proporcionado ya existe, se inicia una excepción.  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)
- [Modificación de datos con procedimientos almacenados](modifying-data-with-stored-procedures.md)
- [Asignaciones de tipos de datos en ADO.NET](data-type-mappings-in-ado-net.md)
- [Información general de ADO.NET](ado-net-overview.md)
