---
title: Recuperar datos utilizando un objeto DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: f3add49d48a569664d4cbb6b5c26d5f3379b6f18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794414"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperación de datos mediante DataReader
Para recuperar datos mediante un **DataReader**, cree una instancia del objeto de **comando** y, a continuación, cree un **DataReader** mediante una llamada a **Command. ExecuteReader** para recuperar las filas de un origen de datos. **DataReader** proporciona un flujo de datos no almacenado en búfer que permite que la lógica de procedimientos procese eficazmente los resultados de un origen de datos de forma secuencial. **DataReader** es una buena elección cuando se recuperan grandes cantidades de datos porque los datos no se almacenan en la memoria caché.

En el ejemplo siguiente se muestra el uso de **DataReader**, donde `reader` representa un DataReader válido y `command` representa un objeto de comando válido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Use el método **DataReader. Read** para obtener una fila de los resultados de la consulta. Puede tener acceso a cada columna de la fila devuelta pasando el nombre o el número ordinal de la columna al **DataReader**. Sin embargo, para obtener el mejor rendimiento, **DataReader** proporciona una serie de métodos que le permiten tener acceso a los valores de columna en sus tipos de datos nativos (**GetDateTime**, **getDouble**, **GetGuid**, **GetInt32**, etc.). Para obtener una lista de métodos de descriptor de acceso con tipo para los **DataReader**específicos <xref:System.Data.OleDb.OleDbDataReader> del <xref:System.Data.SqlClient.SqlDataReader>proveedor de datos, vea y. El uso de los métodos de descriptor de acceso con tipo cuando se conoce el tipo de datos subyacente reduce la cantidad de conversión de tipos necesaria al recuperar el valor de la columna.  
  
 En el ejemplo siguiente se recorre en iteración un objeto **DataReader** y se devuelven dos columnas de cada fila.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Cerrar el DataReader  
 Llame siempre al método **Close** cuando haya terminado de usar el objeto **DataReader** .  
  
 Si el **comando** contiene parámetros de salida o valores devueltos, esos valores no estarán disponibles hasta que se cierre **DataReader** .  
  
 Mientras un **DataReader** está abierto, la **conexión** está en uso exclusivamente por parte de **DataReader**. No se puede ejecutar ningún comando para la **conexión**, incluida la creación de otro **DataReader**, hasta que se cierre el **DataReader** original.  
  
> [!NOTE]
> No llame a **Close** o **Dispose** en una **conexión**, **DataReader**o cualquier otro objeto administrado en el método **Finalize** de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no posee recursos no administrados, no incluya un método **Finalize** en la definición de clase. Para obtener más información, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recuperar varios conjuntos de resultados mediante NextResult  
 Si **DataReader** devuelve varios conjuntos de resultados, llame al método **NextResult** para recorrer en iteración los conjuntos de resultados secuencialmente. En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Obtención de información de esquema de DataReader  
 Mientras un **DataReader** está abierto, puede recuperar información de esquema sobre el conjunto de resultados actual mediante el método **GetSchemaTable** . **GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual. El **objeto DataTable** contiene una fila por cada columna del conjunto de resultados. Cada columna de la tabla de esquema se asigna a una propiedad de las columnas devueltas en las filas del conjunto de resultados, donde **columnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad. En el ejemplo siguiente se escribe la información de esquema de **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Trabajar con capítulos de OLE DB  
 Los conjuntos<xref:System.Data.OleDb.OleDbDataReader>de filas jerárquicos, o capítulos (OLE DB Type **DBTYPE_HCHAPTER**, adChapter Type de ADO), se pueden recuperar mediante. Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, el capítulo se devuelve como una columna en ese **DataReader** y se expone como un objeto **DataReader** .  
  
 El **conjunto** de ADO.net también se puede usar para representar conjuntos de filas jerárquicos mediante el uso de relaciones de elementos primarios y secundarios entre las tablas. Para obtener más información, vea conjuntos de datos [, tablas de datos y vistas](./dataset-datatable-dataview/index.md)de datos.  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Devolver resultados con CURSOres REF CURSOR de Oracle  
 El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta. Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Puede recuperar un <xref:System.Data.OracleClient.OracleDataReader> objeto que representa un cursor Ref cursor de Oracle mediante el <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método. También <xref:System.Data.OracleClient.OracleCommand> puede especificar un que devuelve uno o varios cursores REF cursor de Oracle como **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un. <xref:System.Data.DataSet>  
  
 Para tener acceso a un Ref cursor devuelto desde un origen de datos <xref:System.Data.OracleClient.OracleCommand> de Oracle, cree un para la consulta y agregue un parámetro de salida que <xref:System.Data.OracleClient.OracleCommand.Parameters> haga referencia al <xref:System.Data.OracleClient.OracleCommand>cursor Ref a la colección de. El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta. Establezca el tipo del parámetro en <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. El <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método <xref:System.Data.OracleClient.OracleDataReader> de devuelve un para el cursor Ref. <xref:System.Data.OracleClient.OracleCommand>  
  
 <xref:System.Data.OracleClient.OracleCommand> Si devuelve varios cursores REF cursor, agregue varios parámetros de salida. Puede tener acceso a los diferentes cursores REF cursor llamando <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> al método. La llamada a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> devuelve un <xref:System.Data.OracleClient.OracleDataReader> que hace referencia al primer cursor Ref. Después, puede llamar al <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> método para tener acceso a los siguientes cursores REF cursor. Aunque los parámetros de la <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> colección coinciden con los parámetros de salida Ref cursor por <xref:System.Data.OracleClient.OracleDataReader> nombre, el obtiene acceso a ellos en el orden en que se <xref:System.Data.OracleClient.OracleCommand.Parameters> agregaron a la colección.  
  
 Por ejemplo, considere el siguiente paquete de Oracle y, concretamente, el cuerpo del paquete.  
  
```sql
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
  
 En el código siguiente se <xref:System.Data.OracleClient.OracleCommand> crea un que devuelve los cursores REF cursor del paquete anterior de Oracle agregando dos <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> parámetros de <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> tipo a la colección.  
  
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
  
 El código siguiente devuelve los resultados del comando anterior mediante los <xref:System.Data.OracleClient.OracleDataReader.Read> métodos y <xref:System.Data.OracleClient.OracleDataReader.NextResult> de. <xref:System.Data.OracleClient.OracleDataReader> Los parámetros REF CURSOR se devuelven en orden.  
  
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
  
 En el ejemplo siguiente se usa el comando anterior para <xref:System.Data.DataSet> rellenar un con los resultados del paquete de Oracle.  
  
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
> Para evitar una **excepción OverflowException**, se recomienda que también se controle cualquier conversión del tipo Number de Oracle a un tipo de .NET Framework válido antes de almacenar <xref:System.Data.DataRow>el valor en. Puede utilizar el <xref:System.Data.Common.DataAdapter.FillError> evento para determinar si se ha producido una **excepción OverflowException** . Para obtener más información sobre <xref:System.Data.Common.DataAdapter.FillError> el evento, vea [controlar eventos DataAdapter](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vea también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Recuperación de información del esquema de la base de datos](retrieving-database-schema-information.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
