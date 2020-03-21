---
title: Secuencias de Oracle
ms.date: 03/30/2017
ms.assetid: 27cd371d-8252-414d-b5b2-5d31fa44b585
ms.openlocfilehash: d6e6bb51b8bd317c7161500b89993be689659fad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149419"
---
# <a name="oracle-sequences"></a>Secuencias de Oracle
El proveedor de datos .NET Framework para Oracle proporciona compatibilidad para recuperar los valores clave de secuencia de Oracle que genera el servidor después de realizar inserciones con <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
 SQL Server y Oracle admiten la creación de columnas de incremento automático que pueden designarse como claves principales. Estos valores los genera el servidor cuando se agregan filas a una tabla. En SQL Server se establece la propiedad Identity de una columna; en Oracle se crea una secuencia. La diferencia entre las columnas de incremento automático de SQL Server y las secuencias de Oracle es la siguiente:  
  
- En SQL Server, marca una columna como columna de incremento automático y SQL Server genera de forma automática nuevos valores para la columna cuando se inserta una nueva fila.  
  
- En Oracle, para generar nuevos valores en una columna de la tabla crea una secuencia, pero no existe vínculo directo entre la secuencia y la tabla o la columna. Las secuencias de Oracle son objetos, de la misma forma que las tablas o los procedimientos almacenados.  
  
 Cuando crea una secuencia en una base de datos de Oracle, puede definir su valor inicial y el incremento entre los valores. También puede consultar si existen nuevos valores en la secuencia antes de enviar nuevas filas. Esto implica que el código puede reconocer los valores clave de las nuevas filas antes de insertarlas en la base de datos.  
  
 Para obtener más información sobre la creación de columnas de incremento automático mediante SQL Server y ADO.NET, vea Recuperar valores de [identidad o numeración](retrieving-identity-or-autonumber-values.md) automática y Crear columnas de [incremento automático](./dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de C# se muestra cómo puede recuperar nuevos valores de secuencia de una base de datos de Oracle. El ejemplo hace referencia a la secuencia de la consulta INSERT INTO utilizada para enviar nuevas filas y, a continuación, devuelve el valor de secuencia que se genera mediante la cláusula RETURNING introducida en Oracle10g. El ejemplo agrega una serie de filas nuevas pendientes en un objeto <xref:System.Data.DataTable> mediante el uso de la funcionalidad de incremento automático de ADO.NET para generar "marcadores de posición" de valores clave principales. Tenga en cuenta que el valor de incremento que genera ADO.NET para la nueva fila es sólo un "marcador de posición". Esto significa que la base de datos puede generar valores distintos de los que genera ADO.NET.  
  
 Antes de enviar las inserciones pendientes a la base de datos, el ejemplo muestra el contenido de las filas. A continuación, el código crea un nuevo objeto <xref:System.Data.OracleClient.OracleDataAdapter> y establece sus propiedades <xref:System.Data.OracleClient.OracleDataAdapter.InsertCommand%2A> y <xref:System.Data.OracleClient.OracleDataAdapter.UpdateBatchSize%2A>. El ejemplo también proporciona la lógica para devolver los valores que genera el servidor mediante parámetros de salida. A continuación, ejecuta la actualización para enviar las filas pendientes y muestra el contenido del objeto <xref:System.Data.DataTable>.  
  
```csharp  
public void OracleSequence(String connectionString)  
{  
   String insertString =
      "INSERT INTO SequenceTest_Table (ID, OtherColumn)" +  
      "VALUES (SequenceTest_Sequence.NEXTVAL, :OtherColumn)" +  
      "RETURNING ID INTO :ID";  
  
   using (OracleConnection conn = new OracleConnection(connectionString))  
   {  
      //Open a connection.  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
  
      // Prepare the database.  
      cmd.CommandText = "DROP SEQUENCE SequenceTest_Sequence";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "DROP TABLE SequenceTest_Table";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "CREATE TABLE SequenceTest_Table " +  
                     "(ID int PRIMARY KEY, OtherColumn varchar(255))";  
      cmd.ExecuteNonQuery();  
  
      cmd.CommandText = "CREATE SEQUENCE SequenceTest_Sequence " +  
                        "START WITH 100 INCREMENT BY 5";  
      cmd.ExecuteNonQuery();  
  
      DataTable testTable = new DataTable();  
      DataColumn column = testTable.Columns.Add("ID", typeof(int));  
      column.AutoIncrement = true;  
      column.AutoIncrementSeed = -1;  
      column.AutoIncrementStep = -1;  
      testTable.PrimaryKey = new DataColumn[] { column };  
      testTable.Columns.Add("OtherColumn", typeof(string));  
      for (int rowCounter = 1; rowCounter <= 15; rowCounter++)  
      {  
         testTable.Rows.Add(null, "Row #" + rowCounter.ToString());  
      }  
  
      Console.WriteLine("Before Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      Console.WriteLine();  
  
      cmd.CommandText =
        "SELECT ID, OtherColumn FROM SequenceTest_Table";  
      OracleDataAdapter da = new OracleDataAdapter(cmd);  
      da.InsertCommand = new OracleCommand(insertString, conn);  
      da.InsertCommand.Parameters.Add(":ID", OracleType.Int32, 0, "ID");  
      da.InsertCommand.Parameters[0].Direction = ParameterDirection.Output;  
      da.InsertCommand.Parameters.Add(":OtherColumn", OracleType.VarChar, 255, "OtherColumn");  
      da.InsertCommand.UpdatedRowSource = UpdateRowSource.OutputParameters;  
      da.UpdateBatchSize = 10;  
  
      da.Update(testTable);  
  
      Console.WriteLine("After Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      // Close the connection.  
      conn.Close();  
   }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general de ADO.NET](ado-net-overview.md)
