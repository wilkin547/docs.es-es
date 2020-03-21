---
title: Actualizar datos de un origen de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 18bb03e17b19243ee1bc6e3f7ebd70afb4d4c60b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174451"
---
# <a name="updating-data-in-a-data-source"></a>Actualizar datos de un origen de datos
Las instrucciones SQL que modifican datos (por ejemplo INSERT, UPDATE o DELETE) no devuelven ninguna fila. De la misma forma, muchos procedimientos almacenados realizan alguna acción pero no devuelven filas. Para ejecutar comandos que no devuelven filas, cree un objeto **Command** con el comando SQL adecuado y una **conexión**, incluidos los **parámetros necesarios.** Ejecute el comando con el método **ExecuteNonQuery** del objeto **Command.**  
  
 El **Método ExecuteNonQuery** devuelve un entero que representa el número de filas afectadas por la instrucción o el procedimiento almacenado que se ejecutó. Si se ejecutan varias instrucciones, el valor devuelto es la suma de los registros afectados por todas las instrucciones ejecutadas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se ejecuta una instrucción INSERT para insertar un registro en una base de datos mediante **ExecuteNonQuery**.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 En el ejemplo de código siguiente se ejecuta el procedimiento almacenado creado por el código de ejemplo en [Realizar operaciones](performing-catalog-operations.md)de catálogo . El procedimiento almacenado no devuelve ninguna fila, por lo que se usa el método **ExecuteNonQuery,** pero el procedimiento almacenado recibe un parámetro de entrada y devuelve un parámetro de salida y un valor devuelto.  
  
 Para <xref:System.Data.OleDb.OleDbCommand> el objeto, el **parámetro ReturnValue** debe agregarse primero a la colección **Parameters.**  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a>Consulte también

- [Uso de comandos para modificar datos](using-commands-to-modify-data.md)
- [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Información general de ADO.NET](ado-net-overview.md)
