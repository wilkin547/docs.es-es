---
title: Parámetros de DataAdapter
description: Obtenga información sobre las propiedades de DbDataAdapter que devuelven datos de un origen de datos y administran los cambios en el origen de datos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 1264d678b4823149498150f13d8783a82890f6a0
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91177720"
---
# <a name="dataadapter-parameters"></a><span data-ttu-id="12d5c-103">Parámetros de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="12d5c-103">DataAdapter Parameters</span></span>

<span data-ttu-id="12d5c-104"><xref:System.Data.Common.DbDataAdapter> tiene cuatro propiedades que se utilizan para recuperar y actualizar datos en el origen de datos: la propiedad <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> devuelve datos del origen de datos y las propiedades <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> y <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> se utilizan para administrar los cambios en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12d5c-104">The <xref:System.Data.Common.DbDataAdapter> has four properties that are used to retrieve data from and update data to the data source: the <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> property returns data from the data source; and the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, and <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> properties are used to manage changes at the data source.</span></span> <span data-ttu-id="12d5c-105">La propiedad `SelectCommand` debe establecerse antes de llamar al método `Fill` de `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-105">The `SelectCommand` property must be set before you call the `Fill` method of the `DataAdapter`.</span></span> <span data-ttu-id="12d5c-106">Las propiedades `InsertCommand`, `UpdateCommand` o `DeleteCommand` se deben establecer antes llamar al método `Update` de `DataAdapter`, en función de las modificaciones realizadas en los datos en <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="12d5c-106">The `InsertCommand`, `UpdateCommand`, or `DeleteCommand` properties must be set before the `Update` method of the `DataAdapter` is called, depending on what changes were made to the data in the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="12d5c-107">Por ejemplo, si se han agregado filas, se debe establecer `InsertCommand` antes de llamar a `Update`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-107">For example, if rows have been added, the `InsertCommand` must be set before you call `Update`.</span></span> <span data-ttu-id="12d5c-108">Cuando `Update` procesa una fila insertada, actualizada o eliminada, `DataAdapter` utiliza la propiedad `Command` que corresponde a la acción en cuestión.</span><span class="sxs-lookup"><span data-stu-id="12d5c-108">When `Update` is processing an inserted, updated, or deleted row, the `DataAdapter` uses the respective `Command` property to process the action.</span></span> <span data-ttu-id="12d5c-109">La información actual relacionada con la fila modificada se pasa al objeto `Command` a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-109">Current information about the modified row is passed to the `Command` object through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="12d5c-110">Al actualizar una fila en el origen de datos, se llama a la instrucción UPDATE, que utiliza un identificador único para identificar la fila de la tabla que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="12d5c-110">When you update a row at the data source, you call the UPDATE statement, which uses a unique identifier to identify the row in the table to be updated.</span></span> <span data-ttu-id="12d5c-111">El identificador único suele ser el valor del campo de clave principal.</span><span class="sxs-lookup"><span data-stu-id="12d5c-111">The unique identifier is typically the value of a primary key field.</span></span> <span data-ttu-id="12d5c-112">La instrucción UPDATE utiliza parámetros que contienen el identificador único y las columnas y valores que se van a actualizar, como muestra la siguiente instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="12d5c-112">The UPDATE statement uses parameters that contain both the unique identifier and the columns and values to be updated, as shown in the following Transact-SQL statement.</span></span>  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> <span data-ttu-id="12d5c-113">La sintaxis de los marcadores de posición de parámetros depende del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12d5c-113">The syntax for parameter placeholders depends on the data source.</span></span> <span data-ttu-id="12d5c-114">En este ejemplo se muestran marcadores de posición para un origen de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12d5c-114">This example shows placeholders for a SQL Server data source.</span></span> <span data-ttu-id="12d5c-115">Utilice signos de interrogación de cierre (?) como marcadores de posición de para los parámetros <xref:System.Data.OleDb> y <xref:System.Data.Odbc>.</span><span class="sxs-lookup"><span data-stu-id="12d5c-115">Use question mark (?) placeholders for <xref:System.Data.OleDb> and <xref:System.Data.Odbc> parameters.</span></span>  
  
 <span data-ttu-id="12d5c-116">En este Visual Basic ejemplo, el `CompanyName` campo se actualiza con el valor del `@CompanyName` parámetro de la fila donde `CustomerID` es igual al valor del `@CustomerID` parámetro.</span><span class="sxs-lookup"><span data-stu-id="12d5c-116">In this Visual Basic example, the `CompanyName` field is updated with the value of the `@CompanyName` parameter for the row where `CustomerID` equals the value of the `@CustomerID` parameter.</span></span> <span data-ttu-id="12d5c-117">Los parámetros recuperan información de la fila modificada mediante la <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> propiedad del <xref:System.Data.SqlClient.SqlParameter> objeto.</span><span class="sxs-lookup"><span data-stu-id="12d5c-117">The parameters retrieve information from the modified row using the <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> property of the <xref:System.Data.SqlClient.SqlParameter> object.</span></span> <span data-ttu-id="12d5c-118">A continuación se muestran los parámetros del ejemplo anterior de la instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="12d5c-118">The following are the parameters for the previous sample UPDATE statement.</span></span> <span data-ttu-id="12d5c-119">En el código se parte de que el `adapter` de la variable representa a un objeto <xref:System.Data.SqlClient.SqlDataAdapter> válido.</span><span class="sxs-lookup"><span data-stu-id="12d5c-119">The code assumes that the variable `adapter` represents a valid <xref:System.Data.SqlClient.SqlDataAdapter> object.</span></span>  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 <span data-ttu-id="12d5c-120">El método `Add` de la colección `Parameters` toma el nombre del parámetro, el tipo de datos, el tamaño (si corresponde al tipo) y el nombre de la propiedad <xref:System.Data.Common.DbParameter.SourceColumn%2A> de `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-120">The `Add` method of the `Parameters` collection takes the name of the parameter, the data type, the size (if applicable to the type), and the name of the <xref:System.Data.Common.DbParameter.SourceColumn%2A> from the `DataTable`.</span></span> <span data-ttu-id="12d5c-121">Tenga en cuenta que <xref:System.Data.Common.DbParameter.SourceVersion%2A> del parámetro `@CustomerID` se establece en `Original`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-121">Notice that the <xref:System.Data.Common.DbParameter.SourceVersion%2A> of the `@CustomerID` parameter is set to `Original`.</span></span> <span data-ttu-id="12d5c-122">De esta forma se garantiza que la fila existente en el origen de datos se actualice cuando el valor de la columna o columnas identificadas haya cambiado en la fila <xref:System.Data.DataRow> modificada.</span><span class="sxs-lookup"><span data-stu-id="12d5c-122">This guarantees that the existing row in the data source is updated if the value of the identifying column or columns has been changed in the modified <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="12d5c-123">En ese caso, el valor de la fila `Original` coincidiría con el valor actual en el origen de datos y el valor de la fila `Current` contendría el valor actualizado.</span><span class="sxs-lookup"><span data-stu-id="12d5c-123">In that case, the `Original` row value would match the current value at the data source, and the `Current` row value would contain the updated value.</span></span> <span data-ttu-id="12d5c-124">No se asigna ningún valor a `SourceVersion` para el parámetro `@CompanyName`, por lo que se utiliza el valor predeterminado, el de la fila `Current`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-124">The `SourceVersion` for the `@CompanyName` parameter is not set and uses the default, `Current` row value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12d5c-125">Para las `Fill` operaciones de `DataAdapter` y los `Get` métodos de `DataReader` , el tipo de .NET Framework se deduce del tipo devuelto por el proveedor de datos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12d5c-125">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the type returned from the .NET Framework data provider.</span></span> <span data-ttu-id="12d5c-126">Los tipos de .NET Framework inferidos y los métodos de descriptor de acceso para los tipos de datos Microsoft SQL Server, OLE DB y ODBC se describen en [asignaciones de tipos de datos en ADO.net](data-type-mappings-in-ado-net.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-126">The inferred .NET Framework types and accessor methods for Microsoft SQL Server, OLE DB, and ODBC data types are described in [Data Type Mappings in ADO.NET](data-type-mappings-in-ado-net.md).</span></span>  
  
## <a name="parametersourcecolumn-parametersourceversion"></a><span data-ttu-id="12d5c-127">Parameter.SourceColumn, Parameter.SourceVersion</span><span class="sxs-lookup"><span data-stu-id="12d5c-127">Parameter.SourceColumn, Parameter.SourceVersion</span></span>  

 <span data-ttu-id="12d5c-128">`SourceColumn` y `SourceVersion` se pueden pasar como argumentos al constructor `Parameter`, o también se pueden establecer como propiedades de un `Parameter` existente.</span><span class="sxs-lookup"><span data-stu-id="12d5c-128">The `SourceColumn` and `SourceVersion` may be passed as arguments to the `Parameter` constructor, or set as properties of an existing `Parameter`.</span></span> <span data-ttu-id="12d5c-129">`SourceColumn` es el nombre de <xref:System.Data.DataColumn> de <xref:System.Data.DataRow> en la que se recupera el valor de `Parameter`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-129">The `SourceColumn` is the name of the <xref:System.Data.DataColumn> from the <xref:System.Data.DataRow> where the value of the `Parameter` will be retrieved.</span></span> <span data-ttu-id="12d5c-130">`SourceVersion` especifica la versión de `DataRow` que utiliza `DataAdapter` para recuperar el valor.</span><span class="sxs-lookup"><span data-stu-id="12d5c-130">The `SourceVersion` specifies the `DataRow` version that the `DataAdapter` uses to retrieve the value.</span></span>  
  
 <span data-ttu-id="12d5c-131">En la tabla siguiente se muestran los valores de la enumeración <xref:System.Data.DataRowVersion> disponibles para su uso con `SourceVersion`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-131">The following table shows the <xref:System.Data.DataRowVersion> enumeration values available for use with `SourceVersion`.</span></span>  
  
|<span data-ttu-id="12d5c-132">Enumeración DataRowVersion</span><span class="sxs-lookup"><span data-stu-id="12d5c-132">DataRowVersion Enumeration</span></span>|<span data-ttu-id="12d5c-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d5c-133">Description</span></span>|  
|--------------------------------|-----------------|  
|`Current`|<span data-ttu-id="12d5c-134">El parámetro utiliza el valor actual de la columna.</span><span class="sxs-lookup"><span data-stu-id="12d5c-134">The parameter uses the current value of the column.</span></span> <span data-ttu-id="12d5c-135">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12d5c-135">This is the default.</span></span>|  
|`Default`|<span data-ttu-id="12d5c-136">El parámetro utiliza el `DefaultValue` de la columna.</span><span class="sxs-lookup"><span data-stu-id="12d5c-136">The parameter uses the `DefaultValue` of the column.</span></span>|  
|`Original`|<span data-ttu-id="12d5c-137">El parámetro utiliza el valor original de la columna.</span><span class="sxs-lookup"><span data-stu-id="12d5c-137">The parameter uses the original value of the column.</span></span>|  
|`Proposed`|<span data-ttu-id="12d5c-138">El parámetro utiliza un valor propuesto.</span><span class="sxs-lookup"><span data-stu-id="12d5c-138">The parameter uses a proposed value.</span></span>|  
  
 <span data-ttu-id="12d5c-139">En el ejemplo de código de `SqlClient` de la siguiente sección se define un parámetro para <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> donde la columna `CustomerID` se utiliza como `SourceColumn` para dos parámetros: `@CustomerID` (`SET CustomerID = @CustomerID`) y `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span><span class="sxs-lookup"><span data-stu-id="12d5c-139">The `SqlClient` code example in the next section defines a parameter for an <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in which the `CustomerID` column is used as a `SourceColumn` for two parameters: `@CustomerID` (`SET CustomerID = @CustomerID`), and `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span></span> <span data-ttu-id="12d5c-140">El `@CustomerID` parámetro se utiliza para actualizar la columna **CustomerID** al valor actual de `DataRow` .</span><span class="sxs-lookup"><span data-stu-id="12d5c-140">The `@CustomerID` parameter is used to update the **CustomerID** column to the current value in the `DataRow`.</span></span> <span data-ttu-id="12d5c-141">Como resultado, `CustomerID` `SourceColumn` se utiliza con un `SourceVersion` de `Current` .</span><span class="sxs-lookup"><span data-stu-id="12d5c-141">As a result, the `CustomerID` `SourceColumn` with a `SourceVersion` of `Current` is used.</span></span> <span data-ttu-id="12d5c-142">El `@OldCustomerID` parámetro se utiliza para identificar la fila actual en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12d5c-142">The `@OldCustomerID` parameter is used to identify the current row in the data source.</span></span> <span data-ttu-id="12d5c-143">Dado que el valor de la columna coincidente se encuentra en la versión `Original` de la fila, también se usa el mismo objeto `SourceColumn` (`CustomerID`) con `SourceVersion` de `Original`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-143">Because the matching column value is found in the `Original` version of the row, the same `SourceColumn` (`CustomerID`) with a `SourceVersion` of `Original` is used.</span></span>  
  
## <a name="working-with-sqlclient-parameters"></a><span data-ttu-id="12d5c-144">Trabajar con parámetros SqlClient</span><span class="sxs-lookup"><span data-stu-id="12d5c-144">Working with SqlClient Parameters</span></span>  

 <span data-ttu-id="12d5c-145">En el ejemplo siguiente se muestra cómo crear <xref:System.Data.SqlClient.SqlDataAdapter> y establecer <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> en <xref:System.Data.MissingSchemaAction.AddWithKey> para recuperar información de esquema adicional de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="12d5c-145">The following example demonstrates how to create a <xref:System.Data.SqlClient.SqlDataAdapter> and set the <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> to <xref:System.Data.MissingSchemaAction.AddWithKey> in order to retrieve additional schema information from the database.</span></span> <span data-ttu-id="12d5c-146">Las propiedades <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> y <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> establecen sus correspondientes objetos <xref:System.Data.SqlClient.SqlParameter> agregados a la colección <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>.</span><span class="sxs-lookup"><span data-stu-id="12d5c-146">The <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties set and their corresponding <xref:System.Data.SqlClient.SqlParameter> objects added to the <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection.</span></span> <span data-ttu-id="12d5c-147">El método devuelve un objeto `SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-147">The method returns a `SqlDataAdapter` object.</span></span>  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a><span data-ttu-id="12d5c-148">Marcadores de posición de parámetros OleDb</span><span class="sxs-lookup"><span data-stu-id="12d5c-148">OleDb Parameter Placeholders</span></span>  

 <span data-ttu-id="12d5c-149">En el caso de los objetos <xref:System.Data.OleDb.OleDbDataAdapter> y <xref:System.Data.Odbc.OdbcDataAdapter>, debe utilizar signos de interrogación de cierre (?) como marcadores de posición para identificar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="12d5c-149">For the <xref:System.Data.OleDb.OleDbDataAdapter> and <xref:System.Data.Odbc.OdbcDataAdapter> objects, you must use question mark (?) placeholders to identify the parameters.</span></span>  
  
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
  
 <span data-ttu-id="12d5c-150">Las instrucciones de consulta con parámetros definen qué parámetros de entrada y de salida se deben crear.</span><span class="sxs-lookup"><span data-stu-id="12d5c-150">The parameterized query statements define which input and output parameters must be created.</span></span> <span data-ttu-id="12d5c-151">Para crear un parámetro, se utiliza el método `Parameters.Add` o el constructor `Parameter` con el fin de especificar el nombre de columna, tipo de datos y tamaño.</span><span class="sxs-lookup"><span data-stu-id="12d5c-151">To create a parameter, use the `Parameters.Add` method or the `Parameter` constructor to specify the column name, data type, and size.</span></span> <span data-ttu-id="12d5c-152">En el caso de tipos de datos intrínsecos, como `Integer`, no es necesario incluir el tamaño, aunque se puede especificar el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12d5c-152">For intrinsic data types, such as `Integer`, you do not have to include the size, or you can specify the default size.</span></span>  
  
 <span data-ttu-id="12d5c-153">En el ejemplo de código siguiente se crean los parámetros para una instrucción SQL y, a continuación, se llena un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-153">The following code example creates the parameters for a SQL statement and then fills a `DataSet`.</span></span>  
  
## <a name="oledb-example"></a><span data-ttu-id="12d5c-154">Ejemplo de OleDb</span><span class="sxs-lookup"><span data-stu-id="12d5c-154">OleDb Example</span></span>  
  
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
  
## <a name="odbc-parameters"></a><span data-ttu-id="12d5c-155">Parámetros Odbc</span><span class="sxs-lookup"><span data-stu-id="12d5c-155">Odbc Parameters</span></span>  
  
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
> <span data-ttu-id="12d5c-156">Si no se proporciona un nombre de parámetro para un parámetro, el parámetro recibe un nombre predeterminado incremental del parámetro *N* *,* comenzando por "parámetro1".</span><span class="sxs-lookup"><span data-stu-id="12d5c-156">If a parameter name is not supplied for a parameter, the parameter is given an incremental default name of Parameter *N* *,* starting with "Parameter1".</span></span> <span data-ttu-id="12d5c-157">Se recomienda evitar la Convención de nomenclatura del parámetro *N* cuando se proporciona un nombre de parámetro, porque el nombre proporcionado puede entrar en conflicto con un nombre de parámetro predeterminado existente en `ParameterCollection` .</span><span class="sxs-lookup"><span data-stu-id="12d5c-157">We recommend that you avoid the Parameter *N* naming convention when you supply a parameter name, because the name that you supply might conflict with an existing default parameter name in the `ParameterCollection`.</span></span> <span data-ttu-id="12d5c-158">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="12d5c-158">If the supplied name already exists, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d5c-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12d5c-159">See also</span></span>

- [<span data-ttu-id="12d5c-160">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="12d5c-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="12d5c-161">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="12d5c-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="12d5c-162">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="12d5c-162">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="12d5c-163">Modificar datos con procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="12d5c-163">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="12d5c-164">Asignaciones de tipos de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12d5c-164">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="12d5c-165">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12d5c-165">ADO.NET Overview</span></span>](ado-net-overview.md)
