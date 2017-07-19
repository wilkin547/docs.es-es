---
title: "Estad&#237;sticas de proveedor para SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Estad&#237;sticas de proveedor para SQL Server
Desde .NET Framework versión 2.0, el proveedor de datos .NET Framework para servidor SQL Server admite estadísticas en tiempo de ejecución.  Para habilitar las estadísticas, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> en `True` después de que haya creado un objeto de conexión válido.  Una vez habilitadas las estadísticas, puede revisarlas como una "instantánea en el tiempo" si recupera una referencia <xref:System.Collections.IDictionary> mediante el método <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.  La enumeración tiene lugar a través de la lista como un conjunto de entradas de diccionario de pares de nombre y valor.  Estos pares de nombre y valor están sin ordenar.  En cualquier momento, puede llamar al método <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para restablecer los contadores.  Si la recopilación de estadísticas no se ha habilitado, no se genera una excepción.  Además, si se llama a <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> sin haber llamado primero a <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>, los valores recuperados son los valores iniciales de cada entrada.  Si habilita las estadísticas, ejecuta la aplicación durante un rato y, a continuación, deshabilita las estadísticas, los valores recuperados reflejarán los valores recopilados hasta el momento en que se deshabilitaron las estadísticas.  Todos los valores estadísticos recuperados son por cada conexión.  
  
## Valores estadísticos disponibles  
 Actualmente, hay 18 elementos diferentes disponibles con el proveedor de Microsoft SQL Server.  Se puede tener acceso al número de elementos disponibles mediante la propiedad **Count** de la referencia a la interfaz <xref:System.Collections.IDictionary> devuelta por <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.  Todos los contadores de las estadísticas de proveedor utilizan el tipo <xref:System.Int64> de Common Language Runtime \(**long** en C\# y Visual Basic\), que tiene una amplitud de 64 bits.  El valor máximo del tipo de datos **int64**, tal como se define en el campo **int64.MaxValue**, es \(\(2^63\)\-1\)\).  Cuando los valores de los contadores alcanzan este valor máximo, ya no se deben considerar precisos.  Esto significa que **int64.MaxValue**\-1 \(\(2^63\)\-2\) es realmente el valor válido más alto para cualquier estadística.  
  
> [!NOTE]
>  Para devolver estadísticas de proveedor se emplea un diccionario, dado que el número, los nombres y el orden de las estadísticas devueltas podrían cambiar en el futuro.  Las aplicaciones no deben depender de que se encuentre un valor específico en el diccionario, sino que, por el contrario, deben comprobar si el valor está ahí y bifurcarse en consecuencia.  
  
 En la siguiente tabla se describen los valores estadísticos actuales disponibles.  Tenga en cuenta que los nombres de claves de los valores individuales no se localizan en las versiones regionales de Microsoft .NET Framework.  
  
|Nombre de clave|Descripción|  
|---------------------|-----------------|  
|`BuffersReceived`|Devuelve el número de paquetes de flujo de datos en tabla \(TDS\) recibidos por el proveedor de SQL Server una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`BuffersSent`|Devuelve el número de paquetes TDS enviados a SQL Server por el proveedor una vez que se han habilitado las estadísticas.  Los comandos grandes pueden necesitar varios búferes.  Por ejemplo, si se envía un comando largo al servidor y necesita seis paquetes, `ServerRoundtrips` aumenta en uno y `BuffersSent` aumenta en seis.|  
|`BytesReceived`|Devuelve el número de bytes de datos de los paquetes TDS recibidos por el proveedor de SQL Server una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`BytesSent`|Devuelve el número de bytes de datos enviados a SQL Server en paquetes TDS una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`ConnectionTime`|El periodo de tiempo \(en milisegundos\) durante el cual la conexión ha estado abierta tras haber habilitado las estadísticas \(el tiempo total de conexión si las estadísticas se han habilitado antes de abrir la conexión\).|  
|`CursorOpens`|Devuelve el número de veces que se ha abierto un cursor a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.<br /><br /> Tenga en cuenta que los resultados de solo lectura y solo avance que devuelven las instrucciones SELECT no se consideran cursores y, por tanto, no afectan a este contador.|  
|`ExecutionTime`|Devuelve el periodo de tiempo acumulado \(en milisegundos\) que ha invertido el proveedor en el procesamiento una vez que se han habilitado las estadísticas, lo que incluye el tiempo dedicado a esperar una respuesta del servidor, así como el tiempo dedicado a ejecutar código en el propio servidor.<br /><br /> Las clases que incluyen código de tiempo son:<br /><br /> SqlConnection<br /><br /> SqlCommand<br /><br /> SqlDataReader<br /><br /> SqlDataAdapter<br /><br /> SqlTransaction<br /><br /> SqlCommandBuilder<br /><br /> Para mantener los miembros críticos para el rendimiento lo más pequeños posible, no se calcula el tiempo de los siguientes miembros:<br /><br /> SqlDataReader<br /><br /> este\[\] operador \(todas las sobrecargas\)<br /><br /> GetBoolean<br /><br /> GetChar<br /><br /> GetDateTime<br /><br /> GetDecimal<br /><br /> GetDouble<br /><br /> GetFloat<br /><br /> GetGuid<br /><br /> GetInt16<br /><br /> GetInt32<br /><br /> GetInt64<br /><br /> GetName<br /><br /> GetOrdinal<br /><br /> GetSqlBinary<br /><br /> GetSqlBoolean<br /><br /> GetSqlByte<br /><br /> GetSqlDateTime<br /><br /> GetSqlDecimal<br /><br /> GetSqlDouble<br /><br /> GetSqlGuid<br /><br /> GetSqlInt16<br /><br /> GetSqlInt32<br /><br /> GetSqlInt64<br /><br /> GetSqlMoney<br /><br /> GetSqlSingle<br /><br /> GetSqlString<br /><br /> GetString<br /><br /> IsDBNull|  
|`IduCount`|Devuelve el número total de instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`IduRows`|Devuelve el número total de filas afectadas por las instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`NetworkServerTime`|Devuelve el periodo de tiempo acumulado \(en milisegundos\) que el proveedor ha dedicado a esperar una respuesta del servidor una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`PreparedExecs`|Devuelve el número de comandos preparados ejecutados a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`Prepares`|Devuelve el número de instrucciones preparadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`SelectCount`|Devuelve el número de instrucciones SELECT ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.  Esto incluye las instrucciones FETCH, para recuperar filas a partir de cursores, y el número de instrucciones SELECT que se actualizan cuando se llega al final de un <xref:System.Data.SqlClient.SqlDataReader>.|  
|`SelectRows`|Devuelve el número de filas seleccionadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.  Este contador refleja todas las filas que generan las instrucciones SQL, incluso las que no ha consumido realmente la persona que llama.  Por ejemplo, cerrar un lector de datos antes de leer todo el conjunto de resultados no afectará al recuento.  Aquí se incluyen las filas recuperadas con cursores a través de instrucciones FETCH.|  
|`ServerRoundtrips`|Devuelve el número de veces que la conexión ha enviado comandos al servidor y ha obtenido una respuesta una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
|`SumResultSets`|Devuelve el número de conjuntos de resultados que se han utilizado una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.  Por ejemplo, esto incluiría cualquier conjunto de resultados devuelto al cliente.  En el caso de cursores, cada operación FETCH y BLOCK\-FETCH se considera un conjunto de resultados independiente.|  
|`Transactions`|Devuelve el número de transacciones de usuario iniciadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas. Esto incluye las transacciones deshechas.  Si una conexión se ejecuta con la confirmación automática activada, cada comando se considera una transacción.<br /><br /> Este contador aumenta el recuento de transacciones tan pronto se ejecuta una transacción BEGIN TRAN, con independencia de si la transacción se confirma o revierte en un momento posterior.|  
|`UnpreparedExecs`|Devuelve el número de instrucciones no preparadas ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.|  
  
### Recuperación de un valor  
 La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar cuatro valores estadísticos individuales y escribirlos en la ventana de la consola.  
  
> [!NOTE]
>  En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  La cadena de conexión proporcionada en el código de ejemplo asume que la base de datos está instalada y disponible en el equipo local.  Modifique la cadena de conexión según sea necesario para su entorno.  
  
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
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
 \[C\#\]  
  
```  
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
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### Recuperación de todos los valores  
 La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar todos los valores estadísticos disponibles y escribirlos en la ventana de la consola.  
  
> [!NOTE]
>  En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  La cadena de conexión proporcionada en el código de ejemplo asume que la base de datos está instalada y disponible en el equipo local.  Modifique la cadena de conexión según sea necesario para su entorno.  
  
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
    ' you can retrive it from a configuration file.  
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
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)