---
title: Actualizar datos de un origen de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: d7b57a9572a285dfdc13afb0a520de67e231a1c0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463915"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="0f21e-102">Actualizar datos de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="0f21e-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="0f21e-103">Las instrucciones SQL que modifican datos (por ejemplo INSERT, UPDATE o DELETE) no devuelven ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="0f21e-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="0f21e-104">De la misma forma, muchos procedimientos almacenados realizan alguna acción pero no devuelven filas.</span><span class="sxs-lookup"><span data-stu-id="0f21e-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="0f21e-105">Para ejecutar comandos que no devuelven filas, crear un **comando** objeto con el comando SQL adecuado y un **conexión**, las que se requiere incluidas **parámetros**.</span><span class="sxs-lookup"><span data-stu-id="0f21e-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="0f21e-106">Ejecute el comando con el **ExecuteNonQuery** método de la **comando** objeto.</span><span class="sxs-lookup"><span data-stu-id="0f21e-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="0f21e-107">El **ExecuteNonQuery** método devuelve un entero que representa el número de filas afectadas por la instrucción o procedimiento almacenado que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="0f21e-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="0f21e-108">Si se ejecutan varias instrucciones, el valor devuelto es la suma de los registros afectados por todas las instrucciones ejecutadas.</span><span class="sxs-lookup"><span data-stu-id="0f21e-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f21e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f21e-109">Example</span></span>  
 <span data-ttu-id="0f21e-110">En el ejemplo de código siguiente se ejecuta una instrucción INSERT para insertar un registro en una base de datos mediante **ExecuteNonQuery**.</span><span class="sxs-lookup"><span data-stu-id="0f21e-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
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
  
 <span data-ttu-id="0f21e-111">En el ejemplo de código siguiente se ejecuta el procedimiento almacenado creado por el código de ejemplo en [realizar operaciones de catálogo](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0f21e-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span></span> <span data-ttu-id="0f21e-112">No se devuelven filas por el procedimiento almacenado, por lo que la **ExecuteNonQuery** se utiliza el método, pero el procedimiento almacenado reciba un parámetro de entrada y devuelve un parámetro de salida y un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0f21e-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="0f21e-113">Para el <xref:System.Data.OleDb.OleDbCommand> objeto, el **ReturnValue** parámetro debe agregarse a la **parámetros** colección primero.</span><span class="sxs-lookup"><span data-stu-id="0f21e-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f21e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f21e-114">See Also</span></span>  
 [<span data-ttu-id="0f21e-115">Uso de comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="0f21e-115">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [<span data-ttu-id="0f21e-116">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="0f21e-116">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="0f21e-117">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="0f21e-117">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="0f21e-118">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0f21e-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
