---
title: Recuperar datos utilizando un objeto DataReader
ms.date: 10/259/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: d3c59b667c05be083e44de8cc3e7e44d50fefc71
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "43516796"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperar datos mediante DataReader
Para recuperar datos mediante un **DataReader**, cree una instancia de la **comando** objeto y, a continuación, cree un **DataReader** mediante una llamada a **Command.ExecuteReader**  para recuperar filas de un origen de datos. El **DataReader** proporciona una secuencia sin almacenamiento en búfer de datos que permite la lógica de procedimientos procesar secuencialmente de forma eficaz los resultados de un origen de datos. El **DataReader** es una buena elección cuando se está recuperando grandes cantidades de datos porque no se almacena en caché los datos en memoria.

El ejemplo siguiente se muestra cómo utilizar un **DataReader**, donde `reader` representa un DataReader válido y `command` representa un objeto Command válido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Use la **DataReader.Read** método para obtener una fila de resultados de la consulta. Puede tener acceso a cada columna de la fila devuelta, pasando el nombre o número ordinal de la columna a la **DataReader**. Sin embargo, para obtener el mejor rendimiento, la **DataReader** proporciona una serie de métodos que permiten tener acceso a los valores de columna en sus tipos de datos nativos (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, y así sucesivamente). Para obtener una lista de métodos de descriptor de acceso con tipo de datos específico del proveedor **DataReaders**, consulte <xref:System.Data.OleDb.OleDbDataReader> y <xref:System.Data.SqlClient.SqlDataReader>. Mediante los métodos de descriptor de acceso con tipo cuando se saben que los datos subyacentes tipo reduce la cantidad de conversión de tipo necesaria para recuperar el valor de columna.  
  
 En el ejemplo siguiente se recorre un **DataReader** de objetos y devuelve dos columnas de cada fila.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Cerrar el DataReader  
 Llame siempre a la **cerrar** método cuando haya terminado de utilizar el **DataReader** objeto.  
  
 Si su **comando** contiene la salida de parámetros o valores devueltos, dichos valores no están disponibles hasta que el **DataReader** está cerrado.  
  
 Mientras un **DataReader** está abierto, el **conexión** está en uso de forma exclusiva **DataReader**. No se puede ejecutar ningún comando para el **conexión**, incluida la creación de otro **DataReader**, hasta que el original **DataReader** está cerrado.  
  
> [!NOTE]
>  No llame a **cerrar** o **Dispose** en un **conexión**, un **DataReader**, o cualquier otro objeto administrado en el **Finalize**  método de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no dispone de los recursos no administrados, no incluya un **Finalize** método en la definición de clase. Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recuperando resultados múltiples establece con NextResult  
 Si el **DataReader** devuelve varios conjuntos de resultados, llamada la **NextResult** método para recorrer en iteración el resultado se establece secuencialmente. En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Obtención de información de esquema de DataReader  
 Mientras un **DataReader** está abierto, puede recuperar información del esquema acerca del actual conjunto de resultados mediante el **GetSchemaTable** método. **GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual. El **DataTable** contiene una fila por cada columna del conjunto de resultados. Cada columna de la tabla de esquema se asigna a una propiedad de las columnas devueltas en las filas del resultado conjunto, donde el **ColumnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad. El ejemplo siguiente escribe la información de esquema **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Trabajar con capítulos de OLE DB  
 Conjuntos jerárquicos de filas o capítulos (tipo de OLE DB **DBTYPE_HCHAPTER**, tipo de ADO **adChapter**), se puede recuperar mediante el <xref:System.Data.OleDb.OleDbDataReader>. Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, éste se devuelve como una columna en la que **DataReader** y se expone como un **DataReader** objeto.  
  
 ADO.NET **DataSet** también se puede usar para representar conjuntos jerárquicos de filas utilizando relaciones de elementos primarios y secundarios entre las tablas. Para obtener más información, consulte [DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 En el ejemplo de código siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Devolver resultados con cursores REF cursor de Oracle  
 El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta. Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Puede recuperar un <xref:System.Data.OracleClient.OracleDataReader> objeto que representa un REF CURSOR de Oracle mediante el uso de la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método. También puede especificar un <xref:System.Data.OracleClient.OracleCommand> que devuelve uno o varios cursores REF de Oracle como el **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un <xref:System.Data.DataSet>.  
  
 Para obtener acceso a un REF CURSOR devuelto desde un origen de datos de Oracle, cree un <xref:System.Data.OracleClient.OracleCommand> para la consulta y agregue un parámetro de salida que hace referencia el REF CURSOR y la <xref:System.Data.OracleClient.OracleCommand.Parameters> colección de su <xref:System.Data.OracleClient.OracleCommand>. El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta. Establezca el tipo del parámetro para <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. El <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método de su <xref:System.Data.OracleClient.OracleCommand> devuelve un <xref:System.Data.OracleClient.OracleDataReader> para el REF CURSOR.  
  
 Si su <xref:System.Data.OracleClient.OracleCommand> devuelve varios cursores REF CURSOR, agregue varios parámetros de salida. Puede tener acceso a los distintos cursores REF CURSOR llamando a la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método. La llamada a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> devuelve un <xref:System.Data.OracleClient.OracleDataReader> hacer referencia al primer REF CURSOR. A continuación, puede llamar a la <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> método para acceder a los cursores REF CURSOR posteriores. Aunque los parámetros en su <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> parámetros de salida de coincidencia de la colección el REF CURSOR por su nombre, el <xref:System.Data.OracleClient.OracleDataReader> tiene acceso a ellos en el orden en que se agregaron a la <xref:System.Data.OracleClient.OracleCommand.Parameters> colección.  
  
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
  
 El código siguiente crea un <xref:System.Data.OracleClient.OracleCommand> que devuelve los cursores REF cursor del paquete anterior de Oracle mediante la adición de dos parámetros de tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> a la <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> colección.  
  
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
  
 El código siguiente devuelve los resultados del comando anterior utilizando el <xref:System.Data.OracleClient.OracleDataReader.Read> y <xref:System.Data.OracleClient.OracleDataReader.NextResult> métodos de la <xref:System.Data.OracleClient.OracleDataReader>. Los parámetros REF CURSOR se devuelven en orden.  
  
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
  
 En el ejemplo siguiente se usa el comando anterior para rellenar un <xref:System.Data.DataSet> con los resultados del paquete de Oracle.  
  
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

> [!NOTE]
>  Para evitar un **OverflowException**, se recomienda que controle también cualquier conversión de tipo NUMBER de Oracle a un tipo válido de .NET Framework antes de almacenar el valor en un <xref:System.Data.DataRow>. Puede usar el <xref:System.Data.Common.DataAdapter.FillError> evento para determinar si un **OverflowException** se ha producido. Para obtener más información sobre la <xref:System.Data.Common.DataAdapter.FillError> eventos, consulte [controlar eventos de DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con DataReaders](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Recuperación de información del esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
