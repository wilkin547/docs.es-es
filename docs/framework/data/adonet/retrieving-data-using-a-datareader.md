---
title: Recuperar datos utilizando un objeto DataReader
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
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fd44502b5aa07e1421b6b226188155cac56d3473
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-data-using-a-datareader"></a>Recuperar datos utilizando un objeto DataReader
Recuperar datos mediante un **DataReader** implica la creación de una instancia de la **comando** objeto y, a continuación, crear un **DataReader** mediante una llamada a  **Command.ExecuteReader** para recuperar filas de un origen de datos. En el ejemplo siguiente se muestra cómo utilizar un **DataReader** donde `reader` representa un DataReader válido y `command` representa un objeto Command válido.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Usa el **lectura** método de la **DataReader** objeto para obtener una fila de los resultados de la consulta. Puede tener acceso a cada columna de la fila devuelta, pasando el nombre o la referencia ordinal de la columna a la **DataReader**. Sin embargo, para un rendimiento óptimo, el **DataReader** proporciona una serie de métodos que permiten tener acceso a los valores de las columnas en sus tipos de datos nativos (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, y así sucesivamente). Para obtener una lista de métodos de descriptor de acceso con tipo de datos específico del proveedor **DataReaders**, consulte <xref:System.Data.OleDb.OleDbDataReader> y <xref:System.Data.SqlClient.SqlDataReader>. Si se utilizan los métodos de descriptor de acceso con tipo, dando por supuesto que se conoce el tipo de datos subyacentes, se reduce el número de conversiones de tipo necesarias para recuperar el valor de una columna.  
  
> [!NOTE]
>  La versión de Windows Server 2003 de .NET Framework incluye una propiedad adicional para la **DataReader**, **HasRows**, lo que permite determinar si el **DataReader**ha devuelto algún resultado antes de leer de él.  
  
 En el ejemplo de código siguiente se recorre en iteración un **DataReader** objeto y devuelven dos columnas de cada fila.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 El **DataReader** proporciona un flujo de datos que permite la lógica de procedimientos procesar los resultados de un origen de datos de forma secuencial eficazmente no almacenado en búfer. El **DataReader** es una buena opción para recuperar grandes cantidades de datos porque no se almacena en caché los datos en memoria.  
  
## <a name="closing-the-datareader"></a>Cerrar el DataReader  
 Siempre debe llamar a la **cerrar** método cuando haya terminado de utilizar el **DataReader** objeto.  
  
 Si su **comando** contiene salida parámetros o valores devueltos, no estarán disponibles hasta que el **DataReader** está cerrado.  
  
 Tenga en cuenta que mientras un **DataReader** está abierto, el **conexión** está en uso exclusivo por que **DataReader**. No se puede ejecutar ningún comando para el **conexión**, incluida la creación de otro **DataReader**, hasta que el original **DataReader** está cerrado.  
  
> [!NOTE]
>  No llame a **cerrar** o **Dispose** en un **conexión**, **DataReader**, o cualquier otro objeto administrado en el **Finalize**  método de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no dispone de los recursos no administrados, no incluya un **Finalize** método en la definición de clase. Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recuperar varios conjuntos de resultados con NextResult  
 Si se devuelven varios conjuntos de resultados, el **DataReader** proporciona el **NextResult** método para recorrer en iteración el resultado se establece en orden. En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Obtener información del esquema a partir del DataReader  
 Mientras un **DataReader** está abierto, puede recuperar información de esquema sobre el actual conjunto de resultados mediante el **GetSchemaTable** método. **GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual. El **DataTable** contiene una fila por cada columna del conjunto de resultados. Cada columna de la fila de la tabla de esquema que se asigna a una propiedad de la columna devuelta en el conjunto de resultados, donde el **ColumnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad. En el ejemplo de código siguiente se muestra la información de esquema para **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Trabajar con capítulos de OLE DB  
 Conjuntos jerárquicos de filas, o capítulos (tipo de OLE DB **DBTYPE_HCHAPTER**, tipo de ADO **Dbtype_hchapter**) se puede recuperar mediante el <xref:System.Data.OleDb.OleDbDataReader>. Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, éste se devuelve como una columna en la que **DataReader** y se expone como un **DataReader** objeto.  
  
 ADO.NET **conjunto de datos** también puede usarse para representar conjuntos jerárquicos de filas utilizando relaciones de elementos primarios y secundarios entre tablas. Para obtener más información, consulte [conjuntos de datos, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Devolver resultados con cursores REF CURSOR de Oracle  
 El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta. Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Puede recuperar un **OracleDataReader** objeto, que representa un REF CURSOR de Oracle utilizando el <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método y, también puede especificar un <xref:System.Data.OracleClient.OracleCommand> que devuelve uno o varios cursores REF de Oracle como la  **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un <xref:System.Data.DataSet>.  
  
 Para obtener acceso a un REF CURSOR devuelto desde un origen de datos de Oracle, cree un **OracleCommand** para la consulta y agregue un parámetro de salida que hace referencia el REF CURSOR y la **parámetros** colección de su  **OracleCommand**. El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta. Establezca el tipo del parámetro para **OracleType.Cursor**. El **ExecuteReader** método de su **OracleCommand** devolverá un **OracleDataReader** para el REF CURSOR.  
  
 Si su **OracleCommand** devuelve varios cursores REF CURSOR, agregue varios parámetros de salida. Puede tener acceso a los distintos cursores REF CURSOR llamando el **OracleCommand.ExecuteReader** método. La llamada a **ExecuteReader** devuelve un **OracleDataReader** hacer referencia al primer REF CURSOR. A continuación, puede llamar a la **OracleDataReader.NextResult** método para tener acceso a los cursores REF CURSOR posteriores. Aunque los parámetros en su **OracleCommand.Parameters** colección REF CURSOR parámetros de salida por su nombre, el **OracleDataReader** obtendrá acceso a éstos en el orden en que se agregaron a la  **Parámetros de** colección.  
  
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
  
 El siguiente código crea un **OracleCommand** que devuelve los cursores REF cursor del paquete anterior de Oracle mediante la adición de dos parámetros de tipo **OracleType.Cursor** a la **parámetros** colección.  
  
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
  
 El código siguiente devuelve los resultados del comando anterior utilizando el **lectura** y **NextResult** métodos de la **OracleDataReader**. Los parámetros REF CURSOR se devuelven en orden.  
  
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
  
 En el ejemplo siguiente se utiliza el comando anterior para rellenar un **conjunto de datos** con los resultados del paquete de Oracle.  
  
> [!NOTE]
>  Para evitar un **OverflowException**, se recomienda que se controle también cualquier conversión del tipo NUMBER de Oracle a un tipo válido de .NET Framework antes de almacenar el valor de un **DataRow**. Puede usar el **FillError** evento para determinar si un **OverflowException** se ha producido. Para obtener más información sobre la **FillError** eventos, vea [control de eventos de DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
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
  
## <a name="see-also"></a>Vea también  
 [Trabajar con DataReaders](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Recuperación de información del esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
