---
description: 'Más información acerca de: estadísticas de proveedor para SQL Server'
title: Estadísticas de proveedor de SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: ece5a6214d438ecac64e8738755d5fb5d0ed7245
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767601"
---
# <a name="provider-statistics-for-sql-server"></a>Estadísticas de proveedor de SQL Server

Desde .NET Framework versión 2.0, el proveedor de datos .NET Framework para servidor SQL Server admite estadísticas en tiempo de ejecución. Debe habilitar las estadísticas estableciendo la propiedad <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> en `True` después de haber creado un objeto de conexión válido. Una vez habilitadas las estadísticas, puede revisarlas como una "instantánea en el tiempo" recuperando una referencia <xref:System.Collections.IDictionary> a través del método <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>. Se enumeran a través de la lista como un conjunto de entradas de diccionario de pares nombre-valor. Estos pares nombre-valor están desordenados. En cualquier momento, puede llamar al método <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para restablecer los contadores. Si no se ha habilitado la recopilación de estadísticas, no se genera una excepción. Además, si se llama a <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> sin haber llamado a <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> primero, los valores recuperados son los valores iniciales de cada entrada. Si habilita las estadísticas, ejecuta la aplicación durante un tiempo y, a continuación, deshabilita las estadísticas, los valores recuperados reflejarán los valores recopilados hasta el momento en que se deshabilitaron las estadísticas. Todos los valores estadísticos se recopilan por conexión.  
  
## <a name="statistical-values-available"></a>Valores estadísticos disponibles  

 Actualmente hay 18 elementos diferentes disponibles en el proveedor de Microsoft SQL Server. Se puede acceder al número de elementos disponibles mediante la propiedad **Count** de la referencia de la interfaz <xref:System.Collections.IDictionary> devuelta por <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>. Todos los contadores de las estadísticas de proveedor usan el tipo <xref:System.Int64> de Common Language Runtime (**long** en C# y Visual Basic), que tiene un ancho de 64 bits. El valor máximo del tipo de datos **int64**, como se define en el campo **int64.MaxValue**, es ((2^63)-1)). Cuando los valores de los contadores alcanzan este valor máximo, ya no se deben considerar precisos. Esto significa que **int64.MaxValue**-1((2^63)-2) es realmente el valor válido más alto de cualquier estadística.  
  
> [!NOTE]
> Se usa un diccionario para devolver las estadísticas del proveedor porque el número, los nombres y el orden de las estadísticas devueltas pueden cambiar en el futuro. Las aplicaciones no deben depender de que haya un valor específico en el diccionario, sino que, en su lugar, deben comprobar si el valor está ahí y, en ese caso, crear una rama.  
  
 En la tabla siguiente se describen los valores estadísticos actuales disponibles. Tenga en cuenta que los nombres de claves de los valores individuales no se localizan en las versiones regionales de Microsoft .NET Framework.  
  
|Nombre de clave|Descripción|  
|--------------|-----------------|  
|`BuffersReceived`|Devuelve el número de paquetes de flujo TDS recibidos por el proveedor de SQL Server después de que la aplicación se haya iniciado con el proveedor y haya habilitado las estadísticas.|  
|`BuffersSent`|Devuelve el número de paquetes TDS enviados a SQL Server por el proveedor una vez que se han habilitado las estadísticas. Los comandos grandes pueden requerir varios búferes. Por ejemplo, si se envía un comando grande al servidor y se requieren seis paquetes, `ServerRoundtrips` se incrementa en uno y `BuffersSent` se incrementa en seis.|  
|`BytesReceived`|Devuelve el número de bytes de datos de los paquetes TDS recibidos por el proveedor de SQL Server una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.|  
|`BytesSent`|Devuelve el número de bytes de datos enviados a SQL Server en paquetes TDS después de que la aplicación se haya iniciado con el proveedor y haya habilitado las estadísticas.|  
|`ConnectionTime`|Cantidad de tiempo (en milisegundos) que se ha abierto la conexión después de habilitarse las estadísticas (el tiempo total de conexión si las estadísticas se han habilitado antes de abrir la conexión).|  
|`CursorOpens`|Devuelve el número de veces que se abrió un cursor a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.<br /><br /> Tenga en cuenta que los resultados de solo lectura y solo avance devueltos por las instrucciones SELECT no se consideran cursores y, por tanto, no afectan a este contador.|  
|`ExecutionTime`|Devuelve la cantidad acumulada de tiempo (en milisegundos) que ha invertido el proveedor en el procesamiento una vez que se han habilitado las estadísticas, lo que incluye el tiempo dedicado a esperar una respuesta del servidor, así como el tiempo dedicado a ejecutar código en el propio proveedor.<br /><br /> Las clases que incluyen código de tiempo son:<br /><br /> SqlConnection<br /><br /> SqlCommand<br /><br /> SqlDataReader<br /><br /> SqlDataAdapter<br /><br /> SqlTransaction<br /><br /> SqlCommandBuilder<br /><br /> Para que el tamaño de los miembros esenciales para el rendimiento sea lo más reducido posible, no se cronometran los siguientes miembros:<br /><br /> SqlDataReader<br /><br /> Este operador [] (todas las sobrecargas)<br /><br /> GetBoolean<br /><br /> GetChar<br /><br /> GetDateTime<br /><br /> GetDecimal<br /><br /> GetDouble<br /><br /> GetFloat<br /><br /> GetGuid<br /><br /> GetInt16<br /><br /> GetInt32<br /><br /> GetInt64<br /><br /> GetName<br /><br /> GetOrdinal<br /><br /> GetSqlBinary<br /><br /> GetSqlBoolean<br /><br /> GetSqlByte<br /><br /> GetSqlDateTime<br /><br /> GetSqlDecimal<br /><br /> GetSqlDouble<br /><br /> GetSqlGuid<br /><br /> GetSqlInt16<br /><br /> GetSqlInt32<br /><br /> GetSqlInt64<br /><br /> GetSqlMoney<br /><br /> GetSqlSingle<br /><br /> GetSqlString<br /><br /> GetString<br /><br /> IsDBNull|  
|`IduCount`|Devuelve el número total de instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`IduRows`|Devuelve el número total de filas afectadas por las instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`NetworkServerTime`|Devuelve la cantidad acumulada de tiempo (en milisegundos) que el proveedor ha dedicado a esperar una respuesta del servidor una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`PreparedExecs`|Devuelve el número de comandos preparados que se ejecutan a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`Prepares`|Devuelve el número de instrucciones preparadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`SelectCount`|Devuelve el número de instrucciones SELECT ejecutadas a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas. Esto incluye las instrucciones FETCH para recuperar las filas de los cursores, y el recuento de las instrucciones SELECT se actualiza cuando se alcanza el final de un objeto <xref:System.Data.SqlClient.SqlDataReader>.|  
|`SelectRows`|Devuelve el número de filas seleccionadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas. Este contador refleja todas las filas generadas por las instrucciones SQL, incluso las que el autor de la llamada no usó realmente. Por ejemplo, cerrar un lector de datos antes de leer todo el conjunto de resultados no afectaría al recuento. Esto incluye las filas recuperadas de los cursores a través de las instrucciones FETCH.|  
|`ServerRoundtrips`|Devuelve el número de veces que la conexión envió comandos al servidor y recibió una respuesta una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas.|  
|`SumResultSets`|Devuelve el número de conjuntos de resultados que se han utilizado una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas. Por ejemplo, esto incluiría cualquier conjunto de resultados devuelto al cliente. En el caso de los cursores, cada operación de captura o bloqueo se considera un conjunto de resultados independiente.|  
|`Transactions`|Devuelve el número de transacciones de usuario que se inician una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas, incluidas las reversiones. Si una conexión se ejecuta con la confirmación automática activada, cada comando se considera una transacción.<br /><br /> Este contador incrementa el recuento de transacciones en cuanto se ejecuta una instrucción BEGIN TRAN, independientemente de si la transacción se confirma o se revierte más tarde.|  
|`UnpreparedExecs`|Devuelve el número de instrucciones no preparadas que se ejecutan a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.|  
  
### <a name="retrieving-a-value"></a>Recuperación de un valor  

 La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar cuatro valores de estadística individuales y escribirlos en la ventana de la consola.  
  
> [!NOTE]
> En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server. La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local. Modifique la cadena de conexión según sea necesario para el entorno.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a>Recuperación de todos los valores  

 La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar todos los valores de estadística disponibles mediante el enumerador y escribirlos en la ventana de la consola.  
  
> [!NOTE]
> En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server. La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local. Modifique la cadena de conexión según sea necesario para el entorno.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [SQL Server y ADO.NET](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
