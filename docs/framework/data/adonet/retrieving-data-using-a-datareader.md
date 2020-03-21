---
title: Recuperar datos utilizando un objeto DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149029"
---
# <a name="retrieve-data-using-a-datareader"></a>Recuperar datos mediante un DataReader
Para recuperar datos mediante un **DataReader**, cree una instancia de la **Command** objeto y, a continuación, cree un **DataReader** mediante una llamada a **Command.ExecuteReader** para recuperar filas de un origen de datos. **DataReader** proporciona un flujo de datos sin búfer que permite que la lógica de procedimientos procese eficazmente los resultados de un origen de datos secuencialmente. **DataReader** es una buena opción cuando se recuperan grandes cantidades de datos porque los datos no se almacenan en caché en la memoria.

En el ejemplo siguiente se muestra `reader` el uso de `command` un **DataReader**, donde representa un DataReader válido y representa un objeto Command válido.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Utilice el método **DataReader.Read** para obtener una fila de los resultados de la consulta. Puede tener acceso a cada columna de la fila devuelta pasando el nombre o el número ordinal de la columna al **DataReader**. Sin embargo, para obtener el mejor rendimiento, **DataReader** proporciona una serie de métodos que permiten tener acceso a los valores de columna en sus tipos de datos nativos (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, etc.). Para obtener una lista de métodos de descriptor <xref:System.Data.OleDb.OleDbDataReader> de <xref:System.Data.SqlClient.SqlDataReader>acceso con tipo para **DataReaders**específicos del proveedor de datos , vea y . El uso de los métodos de descriptor de acceso con tipo cuando conoce el tipo de datos subyacente reduce la cantidad de conversión de tipos necesaria al recuperar el valor de columna.  
  
 En el ejemplo siguiente se recorre en iteración un **DataReader** objeto y devuelve dos columnas de cada fila.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Cerrar el DataReader  
 Llame siempre a la **Close** método cuando haya terminado de usar el **DataReader** objeto.  
  
 Si **el comando** contiene parámetros de salida o valores devueltos, esos valores no están disponibles hasta que se cierra **DataReader.**  
  
 Mientras un **DataReader** está abierto, la **conexión** está en uso exclusivamente por ese **DataReader**. No puede ejecutar ningún comando para **Connection**, incluida la creación de otro **DataReader**, hasta que se cierre el **DataReader** original.  
  
> [!NOTE]
> No llame a **Close** o **Dispose** en una **conexión**, un **DataReader**o cualquier otro objeto administrado en el **Finalize** método de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no posee ningún recurso no administrado, no incluya un método **Finalize** en la definición de clase. Para obtener más información, consulte [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Recuperación de varios conjuntos de resultados mediante NextResult  
 Si el **DataReader** devuelve varios conjuntos de resultados, llame a la **NextResult** método para recorrer en iteración los conjuntos de resultados secuencialmente. En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Obtener información de esquema del DataReader  
 Mientras un **DataReader** está abierto, puede recuperar información de esquema sobre el conjunto de resultados actual mediante el **GetSchemaTable** método. **GetSchemaTable** devuelve <xref:System.Data.DataTable> un objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual. **DataTable** contiene una fila para cada columna del conjunto de resultados. Cada columna de la tabla de esquema se asigna a una propiedad de las columnas devueltas en las filas del conjunto de resultados, donde **ColumnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad. En el ejemplo siguiente se escribe la información de esquema para **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Trabajar con capítulos OLE DB  
 Los conjuntos de filas jerárquicos o los capítulos (tipo <xref:System.Data.OleDb.OleDbDataReader>OLE DB **DBTYPE_HCHAPTER**, tipo **aDO adChapter**), se pueden recuperar mediante el archivo . Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, el capítulo se devuelve como una columna en ese **DataReader** y se expone como un **DataReader** objeto.  
  
 El ADO.NET **DataSet** también se puede utilizar para representar conjuntos de filas jerárquicos mediante el uso de relaciones primario-secundario entre tablas. Para obtener más información, vea [DataSets, DataTables y DataViews](./dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Devolución de resultados con Oracle REF CURSOR  
 El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta. Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Puede recuperar <xref:System.Data.OracleClient.OracleDataReader> un objeto que representa un REF <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> CURSOR de Oracle mediante el método. También puede especificar <xref:System.Data.OracleClient.OracleCommand> un que devuelve uno o varios CURSORes <xref:System.Data.OracleClient.OracleDataAdapter> ref de <xref:System.Data.DataSet>Oracle como **SelectCommand** para un archivo .  
  
 Para tener acceso a un REF CURSOR <xref:System.Data.OracleClient.OracleCommand> devuelto desde un origen de datos de Oracle, cree un para la consulta y agregue un parámetro de salida que haga referencia a REF CURSOR a la <xref:System.Data.OracleClient.OracleCommand.Parameters> colección de su <xref:System.Data.OracleClient.OracleCommand>archivo . El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta. Establezca el tipo del <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>parámetro en . El <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método <xref:System.Data.OracleClient.OracleCommand> de <xref:System.Data.OracleClient.OracleDataReader> sus devuelve un para el REF CURSOR.  
  
 Si <xref:System.Data.OracleClient.OracleCommand> devuelve varios REF CURSORS, agregue varios parámetros de salida. Puede acceder a los diferentes REF <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> CURSOR llamando al método. La llamada <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> a <xref:System.Data.OracleClient.OracleDataReader> devuelve una referencia al primer REF CURSOR. A continuación, <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> puede llamar al método para acceder a ref CURSOR posteriores. Aunque los parámetros de la colección <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> coinciden <xref:System.Data.OracleClient.OracleDataReader> con los parámetros de salida REF <xref:System.Data.OracleClient.OracleCommand.Parameters> CURSOR por nombre, el acceso a ellos en el orden en que se agregaron a la colección.  
  
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
  
 El código siguiente <xref:System.Data.OracleClient.OracleCommand> crea un que devuelve los REF CURSOR del paquete <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> de <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> Oracle anterior agregando dos parámetros de tipo a la colección.  
  
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
  
 El código siguiente devuelve los resultados <xref:System.Data.OracleClient.OracleDataReader.Read> del <xref:System.Data.OracleClient.OracleDataReader.NextResult> comando <xref:System.Data.OracleClient.OracleDataReader>anterior mediante los métodos y del archivo . Los parámetros REF CURSOR se devuelven en orden.  
  
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
  
 En el ejemplo siguiente se <xref:System.Data.DataSet> utiliza el comando anterior para rellenar a con los resultados del paquete de Oracle.  
  
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
> Para evitar una **OverflowException**, se recomienda controlar también cualquier conversión del tipo Oracle NUMBER a <xref:System.Data.DataRow>un tipo válido de .NET Framework antes de almacenar el valor en un archivo . Puede usar <xref:System.Data.Common.DataAdapter.FillError> el evento para determinar si se ha producido una **excepción OverflowException.** Para obtener más <xref:System.Data.Common.DataAdapter.FillError> información sobre el evento, vea [Controlar eventos DataAdapter](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Recuperación de información del esquema de la base de datos](retrieving-database-schema-information.md)
- [Información general de ADO.NET](ado-net-overview.md)
