---
title: "Recuperar datos mediante DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Recuperar datos mediante DataReader
La recuperación de datos mediante **DataReader** implica crear una instancia del objeto **Command** y de un **DataReader** a continuación, para lo cual se llama a **Command.ExecuteReader** a fin de recuperar filas de un origen de datos.  En el ejemplo siguiente se muestra cómo se utiliza un **DataReader**, donde `reader` representa un DataReader válido y `command` representa un objeto Command válido.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Puede utilizar el método **Read** del objeto **DataReader** para obtener una fila a partir de los resultados de una consulta.  Para tener acceso a cada columna de la fila devuelta, puede pasar a **DataReader** el nombre o referencia numérica de la columna en cuestión.  Sin embargo, el mejor rendimiento se logra con los métodos que ofrece **DataReader** y que permiten tener acceso a los valores de las columnas en sus tipos de datos nativos \(**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, etc.\).  Para obtener una lista de métodos de descriptor de acceso con tipo para **DataReaders** de proveedores de datos específicos, vea las secciones <xref:System.Data.OleDb.OleDbDataReader> y <xref:System.Data.SqlClient.SqlDataReader>.  Si se utilizan los métodos de descriptor de acceso con tipo, dando por supuesto que se conoce el tipo de datos subyacentes, se reduce el número de conversiones de tipo necesarias para recuperar el valor de una columna.  
  
> [!NOTE]
>  En la versión de .NET Framework de Windows Server 2003 se incluye una propiedad adicional para el **DataReader**, **HasRows**, que permite determinar si el **DataReader** ha devuelto algún resultado antes de realizar una lectura del mismo.  
  
 En el ejemplo de código siguiente se repite por un objeto **DataReader** y se devuelven dos columnas de cada fila.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader** proporciona un flujo de datos sin búfer que permite a la lógica de los procedimientos procesar eficazmente y de forma secuencial los resultados procedentes de un origen de datos.  **DataReader** es la mejor opción cuando se trata de recuperar grandes cantidades de datos, ya que éstos no se almacenan en la memoria caché.  
  
## Cerrar el DataReader  
 Siempre debe llamar al método **Close** cuando haya terminado de utilizar el objeto **DataReader**.  
  
 Si **Command** contiene parámetros de salida o valores devueltos, éstos no estarán disponibles hasta que se cierre el **DataReader**.  
  
 Tenga en cuenta que mientras está abierto un **DataReader**, ese **DataReader** utiliza de forma exclusiva el objeto **Connection**.  No se podrá ejecutar ningún comando para el objeto **Connection** hasta que se cierre el **DataReader** original, incluida la creación de otro **DataReader**.  
  
> [!NOTE]
>  No llame a **Close** o **Dispose** para objetos **Connection** o **DataReader** ni para ningún otro objeto administrado en el método **Finalize** de su clase.  En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.  Si la clase no dispone de recursos no administrados, no incluya un método **Finalize** en la definición de clase.  Para obtener más información, consulta [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## Recuperar varios conjuntos de resultados con NextResult  
 En el caso en que se devuelvan varios resultados, el **DataReader** proporciona el método **NextResult** para recorrer los conjuntos de resultados en orden.  En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## Obtener información del esquema a partir del DataReader  
 Mientras hay abierto un **DataReader**, puede utilizar el método **GetSchemaTable** para recuperar información del esquema acerca del conjunto actual de resultados.  **GetSchemaTable** devuelve un objeto <xref:System.Data.DataTable> rellenado con filas y columnas que contienen la información del esquema del conjunto actual de resultados.  **DataTable** contiene una fila por cada una de las columnas del conjunto de resultados.  Cada columna de una fila de la tabla de esquema está asociada a una propiedad de la columna que se devuelve en el conjunto de resultados. **ColumnName** es el nombre de la propiedad y el valor de la columna es el de la propiedad.  En el ejemplo de código siguiente se muestra la información del esquema de **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## Trabajar con capítulos de OLE DB  
 Mediante <xref:System.Data.OleDb.OleDbDataReader> puede recuperar conjuntos jerárquicos de filas o capítulos \(tipo **DBTYPE\_HCHAPTER** de OLE DB y tipo **adChapter** de ADO\) .  Cuando se devuelve en forma de **DataReader** una consulta que incluye un capítulo, éste se devuelve como una columna del **DataReader** y se expone como un objeto **DataReader**.  
  
 También se puede utilizar **DataSet** de ADO.NET para representar conjuntos jerárquicos de filas utilizando relaciones entre tablas primarias y secundarias.  Para obtener más información, consulta [DataSets, DataTables y DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 En el ejemplo de código siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## Devolver resultados con cursores REF CURSOR de Oracle  
 El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta.  Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Puede recuperar un objeto **OracleDataReader**, que representa un REF CURSOR de Oracle, mediante el método <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>. También puede especificar un <xref:System.Data.OracleClient.OracleCommand> que devuelva uno o varios cursores REF CURSOR de Oracle como **SelectCommand** de un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un <xref:System.Data.DataSet>.  
  
 Para obtener acceso a un REF CURSOR devuelto desde un origen de datos de Oracle, cree un **OracleCommand** para la consulta y agregue un parámetro de salida que establezca una referencia entre el REF CURSOR y la colección **Parameters** de **OracleCommand**.  El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta.  Establezca el tipo del parámetro en **OracleType.Cursor**.  El método **ExecuteReader** del **OracleCommand** devolverá un **OracleDataReader** para el REF CURSOR.  
  
 Si **OracleCommand** devuelve varios cursores REF CURSOR, agregue varios parámetros de salida.  Puede tener acceso a los distintos cursores REF CURSOR llamando al método **OracleCommand.ExecuteReader**.  La llamada a **ExecuteReader** devuelve un objeto **OracleDataReader** que haga referencia al primer REF CURSOR.  A continuación, puede llamar al método **OracleDataReader.NextResult** para obtener acceso a los cursores REF CURSOR posteriores.  Aunque los parámetros de la colección **OracleCommand.Parameters** tengan el mismo nombre que los parámetros de salida de REF CURSOR, **OracleDataReader** obtendrá acceso a éstos en el mismo orden en el que se agregaron a la colección **Parameters**.  
  
 Por ejemplo, considere el siguiente paquete de Oracle y, concretamente, el cuerpo del paquete.  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 En el código siguiente se crea un **OracleCommand** que devuelve los cursores REF CURSOR del paquete anterior de Oracle mediante la adición de dos parámetros de tipo **OracleType.Cursor** a la colección **Parameters**.  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 El código siguiente devuelve los resultados del comando anterior utilizando los métodos **Read** y **NextResult** del **OracleDataReader**.  Los parámetros REF CURSOR se devuelven en orden.  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 En el siguiente ejemplo se utiliza el comando anterior para rellenar un **DataSet** con los resultados del paquete de Oracle.  
  
> [!NOTE]
>  Se recomienda que el usuario controle también cualquier conversión del tipo NUMBER de Oracle a un tipo válido de .NET Framework antes de almacenar el valor en **DataRow** para evitar que se produzca una excepción **OverflowException**.  Puede utilizar el evento **FillError** para determinar si se ha producido una excepción **OverflowException**.  Para obtener más información sobre el evento **FillError**, vea [Control de eventos DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## Vea también  
 [Working with DataReaders](http://msdn.microsoft.com/es-es/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [DataAdapters y DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Recuperar información de esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)