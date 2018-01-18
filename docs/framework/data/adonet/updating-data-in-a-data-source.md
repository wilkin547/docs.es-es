---
title: Actualizar datos de un origen de datos
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
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3c611e2d7c4c1de17588ba5220124db55bca2764
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="updating-data-in-a-data-source"></a>Actualizar datos de un origen de datos
Las instrucciones SQL que modifican datos (por ejemplo INSERT, UPDATE o DELETE) no devuelven ninguna fila. De la misma forma, muchos procedimientos almacenados realizan alguna acción pero no devuelven filas. Para ejecutar comandos que no devuelven filas, debe crear un **comando** objeto con el comando SQL adecuado y un **conexión**, los necesarios incluidos **parámetros**. Ejecute el comando con el **ExecuteNonQuery** método de la **comando** objeto.  
  
 El **ExecuteNonQuery** método devuelve un entero que representa el número de filas afectadas por la instrucción o procedimiento almacenado que se ejecutó. Si se ejecutan varias instrucciones, el valor devuelto es la suma de los registros afectados por todas las instrucciones ejecutadas.  
  
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
  
 En el ejemplo de código siguiente se ejecuta el procedimiento almacenado creado por el código de ejemplo en [realizar operaciones de catálogo](../../../../docs/framework/data/adonet/performing-catalog-operations.md). No se devuelven filas por el procedimiento almacenado, por lo que la **ExecuteNonQuery** se utiliza el método, pero el procedimiento almacenado reciba un parámetro de entrada y devuelve un parámetro de salida y un valor devuelto.  
  
 Para el <xref:System.Data.OleDb.OleDbCommand> objeto, el **ReturnValue** parámetro debe agregarse a la **parámetros** colección primero.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Uso de comandos para modificar datos](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [Actualizar orígenes de datos con objetos DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
