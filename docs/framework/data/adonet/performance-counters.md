---
title: Contadores de rendimiento
description: Use los contadores de rendimiento de ADO.NET para supervisar el estado de la aplicación y sus recursos de conexión mediante el monitor de rendimiento de Windows o mediante programación.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: dca259ef6d8a2229349d88a9fcae3298cb8a829c
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739469"
---
# <a name="performance-counters-in-adonet"></a>Contadores de rendimiento de ADO.NET

ADO.NET 2.0 incorporó la compatibilidad expandida para los contadores de rendimiento que incluye la compatibilidad tanto con <xref:System.Data.SqlClient> como con <xref:System.Data.OracleClient>. Los contadores de rendimiento <xref:System.Data.SqlClient> que estaban disponibles en las versiones anteriores de ADO.NET están en desuso y se han sustituido por los nuevos contadores de rendimiento que se describen aquí. Puede utilizar los contadores de rendimiento de ADO.NET para supervisar el estado de su aplicación y los recursos de conexión que emplea. Los contadores de rendimiento se pueden controlar con el Monitor de rendimiento de Windows pero también se puede tener acceso a ellos mediante programación usando la clase <xref:System.Diagnostics.PerformanceCounter> del espacio de nombres <xref:System.Diagnostics>.

## <a name="available-performance-counters"></a>Contadores de rendimiento disponibles

 Actualmente hay disponibles 14 contadores de rendimiento para <xref:System.Data.SqlClient> y <xref:System.Data.OracleClient>, tal y como se describe en la siguiente tabla. Tenga en cuenta que los nombres de los contadores individuales no se localizan en las versiones regionales de Microsoft .NET Framework.

|Contador de rendimiento|Descripción|
|-------------------------|-----------------|
|`HardConnectsPerSecond`|El número de conexiones por segundo que se establecen con un servidor de bases de datos.|
|`HardDisconnectsPerSecond`|El número de desconexiones por segundo que se producen con un servidor de bases de datos.|
|`NumberOfActiveConnectionPoolGroups`|El número de conjuntos de grupos de conexiones únicas que están activos. Este contador depende del número de cadenas de conexión única que haya en el AppDomain.|
|`NumberOfActiveConnectionPools`|El número total de grupos de conexiones.|
|`NumberOfActiveConnections`|El número de conexiones activas que se están utilizando actualmente. **Nota:**  Este contador de rendimiento no está habilitado de forma predeterminada. Para habilitar este contador de rendimiento, consulte [activación de contadores desactivados de forma predeterminada](#ActivatingOffByDefault).|
|`NumberOfFreeConnections`|El número de conexiones que se pueden utilizar en los grupos de conexiones. **Nota:**  Este contador de rendimiento no está habilitado de forma predeterminada. Para habilitar este contador de rendimiento, consulte [activación de contadores desactivados de forma predeterminada](#ActivatingOffByDefault).|
|`NumberOfInactiveConnectionPoolGroups`|El número de conjuntos de grupos de conexiones únicas que están marcados para ser eliminados. Este contador depende del número de cadenas de conexión única que haya en el AppDomain.|
|`NumberOfInactiveConnectionPools`|El número de grupos de conexiones inactivas que no han tenido ninguna actividad recientemente y que están a la espera de ser eliminadas.|
|`NumberOfNonPooledConnections`|El número de conexiones activas que no están agrupadas.|
|`NumberOfPooledConnections`|El número de conexiones activas que administra la infraestructura de agrupación de conexiones.|
|`NumberOfReclaimedConnections`|El número de conexiones que se han reclamado a través de la recolección de elementos no utilizados si la aplicación no llamó a `Close` o `Dispose`. Si no se cierran o eliminan explícitamente las conexiones, el rendimiento se verá perjudicado.|
|`NumberOfStasisConnections`|El número de conexiones que están actualmente en espera de que se finalice una acción y que por lo tanto no pueden ser utilizadas por la aplicación.|
|`SoftConnectsPerSecond`|El número de conexiones activas que se están extrayendo del grupo de conexiones. **Nota:**  Este contador de rendimiento no está habilitado de forma predeterminada. Para habilitar este contador de rendimiento, consulte [activación de contadores desactivados de forma predeterminada](#ActivatingOffByDefault).|
|`SoftDisconnectsPerSecond`|El número de conexiones activas que se devuelven al grupo de conexiones. **Nota:**  Este contador de rendimiento no está habilitado de forma predeterminada. Para habilitar este contador de rendimiento, consulte [activación de contadores desactivados de forma predeterminada](#ActivatingOffByDefault).|

### <a name="connection-pool-groups-and-connection-pools"></a>Conjuntos de grupos de conexiones y grupos de conexiones

 Si utiliza la autenticación de Windows (seguridad integrada) debe supervisar los contadores de rendimiento `NumberOfActiveConnectionPoolGroups` y `NumberOfActiveConnectionPools`. El motivo es que los conjuntos de grupos de conexiones se corresponden con cadenas de conexión única. Si se usa seguridad integrada, los grupos de conexiones se asignan a cadenas de conexión y además crean grupos diferentes para cada identidad de Windows. Por ejemplo, si Alfredo y Julia, los dos dentro del mismo AppDomain, utilizan la cadena de conexión `"Data Source=MySqlServer;Integrated Security=true"`, se crea un conjunto de grupos de conexiones para la cadena de conexión y dos grupos adicionales, uno para Alfredo y otro para Julia. Si John y Marta usan una cadena de conexión con un inicio de sesión de SQL Server idéntico, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=[PLACEHOLDER]"` , solo se creará un único grupo para la identidad **lowPrivUser** .

<a name="ActivatingOffByDefault"></a>

### <a name="activating-off-by-default-counters"></a>Activar contadores desactivados de forma predeterminada

 Los contadores de rendimiento `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` y `SoftConnectsPerSecond` están desactivados de forma predeterminada. Agregue la siguiente información al archivo de configuración de la aplicación para habilitarlos:

```xml
<system.diagnostics>
  <switches>
    <add name="ConnectionPoolPerformanceCounterDetail"
         value="4"/>
  </switches>
</system.diagnostics>
```

## <a name="retrieving-performance-counter-values"></a>Recuperar los valores de los contadores de rendimiento

 La siguiente aplicación de consola muestra cómo recuperar valores de los contadores de rendimiento en su aplicación. Las conexiones deben estar abiertas y activas para que se devuelva información de todos los contadores de rendimiento de ADO.NET.

> [!NOTE]
> En este ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server. Las cadenas de conexión que se incluyen en el código de ejemplo presuponen que la base de datos está instalada y disponible en el equipo local con el nombre de instancia SqlExpress y que se han creado inicios de sesión de SQL Server que coinciden con los proporcionados en las cadenas de conexión. Quizá deba habilitar inicios de sesión de SQL Server si su servidor se ha configurado usando la configuración de seguridad predeterminada, que solo admite la autenticación de Windows. Modifique las cadenas de conexión según sea necesario para su entorno.

### <a name="example"></a>Ejemplo

```vb
Option Explicit On
Option Strict On

Imports System.Data.SqlClient
Imports System.Diagnostics
Imports System.Runtime.InteropServices

Class Program

    Private PerfCounters(9) As PerformanceCounter
    Private connection As SqlConnection = New SqlConnection

    Public Shared Sub Main()
        Dim prog As Program = New Program
        ' Open a connection and create the performance counters.
        prog.connection.ConnectionString = _
           GetIntegratedSecurityConnectionString()
        prog.SetUpPerformanceCounters()
        Console.WriteLine("Available Performance Counters:")

        ' Create the connections and display the results.
        prog.CreateConnections()
        Console.WriteLine("Press Enter to finish.")
        Console.ReadLine()
    End Sub

    Private Sub CreateConnections()
        ' List the Performance counters.
        WritePerformanceCounters()

        ' Create 4 connections and display counter information.
        Dim connection1 As SqlConnection = New SqlConnection( _
           GetIntegratedSecurityConnectionString)
        connection1.Open()
        Console.WriteLine("Opened the 1st Connection:")
        WritePerformanceCounters()

        Dim connection2 As SqlConnection = New SqlConnection( _
           GetSqlConnectionStringDifferent)
        connection2.Open()
        Console.WriteLine("Opened the 2nd Connection:")
        WritePerformanceCounters()

        Console.WriteLine("Opened the 3rd Connection:")
        Dim connection3 As SqlConnection = New SqlConnection( _
           GetSqlConnectionString)
        connection3.Open()
        WritePerformanceCounters()

        Dim connection4 As SqlConnection = New SqlConnection( _
           GetSqlConnectionString)
        connection4.Open()
        Console.WriteLine("Opened the 4th Connection:")
        WritePerformanceCounters()

        connection1.Close()
        Console.WriteLine("Closed the 1st Connection:")
        WritePerformanceCounters()

        connection2.Close()
        Console.WriteLine("Closed the 2nd Connection:")
        WritePerformanceCounters()

        connection3.Close()
        Console.WriteLine("Closed the 3rd Connection:")
        WritePerformanceCounters()

        connection4.Close()
        Console.WriteLine("Closed the 4th Connection:")
        WritePerformanceCounters()
    End Sub

    Private Enum ADO_Net_Performance_Counters
        NumberOfActiveConnectionPools
        NumberOfReclaimedConnections
        HardConnectsPerSecond
        HardDisconnectsPerSecond
        NumberOfActiveConnectionPoolGroups
        NumberOfInactiveConnectionPoolGroups
        NumberOfInactiveConnectionPools
        NumberOfNonPooledConnections
        NumberOfPooledConnections
        NumberOfStasisConnections
        ' The following performance counters are more expensive to track.
        ' Enable ConnectionPoolPerformanceCounterDetail in your config file.
        '     SoftConnectsPerSecond
        '     SoftDisconnectsPerSecond
        '     NumberOfActiveConnections
        '     NumberOfFreeConnections
    End Enum

    Private Sub SetUpPerformanceCounters()
        connection.Close()
        Me.PerfCounters(9) = New PerformanceCounter()

        Dim instanceName As String = GetInstanceName()
        Dim apc As Type = GetType(ADO_Net_Performance_Counters)
        Dim i As Integer = 0
        Dim s As String = ""
        For Each s In [Enum].GetNames(apc)
            Me.PerfCounters(i) = New PerformanceCounter()
            Me.PerfCounters(i).CategoryName = ".NET Data Provider for SqlServer"
            Me.PerfCounters(i).CounterName = s
            Me.PerfCounters(i).InstanceName = instanceName
            i = (i + 1)
        Next
    End Sub

    Private Declare Function GetCurrentProcessId Lib "kernel32.dll" () As Integer

    Private Function GetInstanceName() As String
        'This works for Winforms apps.
        Dim instanceName As String = _
           System.Reflection.Assembly.GetEntryAssembly.GetName.Name

        ' Must replace special characters like (, ), #, /, \\
        Dim instanceName2 As String = _
           AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _
           .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")

        'For ASP.NET applications your instanceName will be your CurrentDomain's
        'FriendlyName. Replace the line above that sets the instanceName with this:
        'instanceName = AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _
        '    .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")

        Dim pid As String = GetCurrentProcessId.ToString
        instanceName = (instanceName + ("[" & (pid & "]")))
        Console.WriteLine("Instance Name: {0}", instanceName)
        Console.WriteLine("---------------------------")
        Return instanceName
    End Function

    Private Sub WritePerformanceCounters()
        Console.WriteLine("---------------------------")
        For Each p As PerformanceCounter In Me.PerfCounters
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue)
        Next
        Console.WriteLine("---------------------------")
    End Sub

    Private Shared Function GetIntegratedSecurityConnectionString() As String
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Data Source=.\SqlExpress;Integrated Security=True;" &
          "Initial Catalog=AdventureWorks")
    End Function

    Private Shared Function GetSqlConnectionString() As String
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=[PLACEHOLDER];" &
          "Initial Catalog=AdventureWorks")
    End Function

    Private Shared Function GetSqlConnectionStringDifferent() As String
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _
          "User Id=LowPriv;Password=[PLACEHOLDER];")
    End Function
End Class
```

```csharp
using System;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Runtime.InteropServices;

class Program
{
    PerformanceCounter[] PerfCounters = new PerformanceCounter[10];
    SqlConnection connection = new SqlConnection();

    static void Main()
    {
        Program prog = new Program();
        // Open a connection and create the performance counters.
        prog.connection.ConnectionString =
           GetIntegratedSecurityConnectionString();
        prog.SetUpPerformanceCounters();
        Console.WriteLine("Available Performance Counters:");

        // Create the connections and display the results.
        prog.CreateConnections();
        Console.WriteLine("Press Enter to finish.");
        Console.ReadLine();
    }

    private void CreateConnections()
    {
        // List the Performance counters.
        WritePerformanceCounters();

        // Create 4 connections and display counter information.
        SqlConnection connection1 = new SqlConnection(
              GetIntegratedSecurityConnectionString());
        connection1.Open();
        Console.WriteLine("Opened the 1st Connection:");
        WritePerformanceCounters();

        SqlConnection connection2 = new SqlConnection(
              GetSqlConnectionStringDifferent());
        connection2.Open();
        Console.WriteLine("Opened the 2nd Connection:");
        WritePerformanceCounters();

        SqlConnection connection3 = new SqlConnection(
              GetSqlConnectionString());
        connection3.Open();
        Console.WriteLine("Opened the 3rd Connection:");
        WritePerformanceCounters();

        SqlConnection connection4 = new SqlConnection(
              GetSqlConnectionString());
        connection4.Open();
        Console.WriteLine("Opened the 4th Connection:");
        WritePerformanceCounters();

        connection1.Close();
        Console.WriteLine("Closed the 1st Connection:");
        WritePerformanceCounters();

        connection2.Close();
        Console.WriteLine("Closed the 2nd Connection:");
        WritePerformanceCounters();

        connection3.Close();
        Console.WriteLine("Closed the 3rd Connection:");
        WritePerformanceCounters();

        connection4.Close();
        Console.WriteLine("Closed the 4th Connection:");
        WritePerformanceCounters();
    }

    private enum ADO_Net_Performance_Counters
    {
        NumberOfActiveConnectionPools,
        NumberOfReclaimedConnections,
        HardConnectsPerSecond,
        HardDisconnectsPerSecond,
        NumberOfActiveConnectionPoolGroups,
        NumberOfInactiveConnectionPoolGroups,
        NumberOfInactiveConnectionPools,
        NumberOfNonPooledConnections,
        NumberOfPooledConnections,
        NumberOfStasisConnections
        // The following performance counters are more expensive to track.
        // Enable ConnectionPoolPerformanceCounterDetail in your config file.
        //     SoftConnectsPerSecond
        //     SoftDisconnectsPerSecond
        //     NumberOfActiveConnections
        //     NumberOfFreeConnections
    }

    private void SetUpPerformanceCounters()
    {
        connection.Close();
        this.PerfCounters = new PerformanceCounter[10];
        string instanceName = GetInstanceName();
        Type apc = typeof(ADO_Net_Performance_Counters);
        int i = 0;
        foreach (string s in Enum.GetNames(apc))
        {
            this.PerfCounters[i] = new PerformanceCounter();
            this.PerfCounters[i].CategoryName = ".NET Data Provider for SqlServer";
            this.PerfCounters[i].CounterName = s;
            this.PerfCounters[i].InstanceName = instanceName;
            i++;
        }
    }

    [DllImport("kernel32.dll", SetLastError = true)]
    static extern int GetCurrentProcessId();

    private string GetInstanceName()
    {
        //This works for Winforms apps.
        string instanceName =
            System.Reflection.Assembly.GetEntryAssembly().GetName().Name;

        // Must replace special characters like (, ), #, /, \\
        string instanceName2 =
            AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(', '[')
            .Replace(')', ']').Replace('#', '_').Replace('/', '_').Replace('\\', '_');

        // For ASP.NET applications your instanceName will be your CurrentDomain's
        // FriendlyName. Replace the line above that sets the instanceName with this:
        // instanceName = AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(','[')
        // .Replace(')',']').Replace('#','_').Replace('/','_').Replace('\\','_');

        string pid = GetCurrentProcessId().ToString();
        instanceName = instanceName + "[" + pid + "]";
        Console.WriteLine("Instance Name: {0}", instanceName);
        Console.WriteLine("---------------------------");
        return instanceName;
    }

    private void WritePerformanceCounters()
    {
        Console.WriteLine("---------------------------");
        foreach (PerformanceCounter p in this.PerfCounters)
        {
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue());
        }
        Console.WriteLine("---------------------------");
    }

    private static string GetIntegratedSecurityConnectionString()
    {
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return @"Data Source=.\SqlExpress;Integrated Security=True;" +
          "Initial Catalog=AdventureWorks";
    }
    private static string GetSqlConnectionString()
    {
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=[PLACEHOLDER];" +
          "Initial Catalog=AdventureWorks";
    }

    private static string GetSqlConnectionStringDifferent()
    {
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +
          "User Id=LowPriv;Password=[PLACEHOLDER];";
    }
}
```

## <a name="see-also"></a>Vea también

- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Agrupación de conexiones de OLE DB, ODBC y Oracle](ole-db-odbc-and-oracle-connection-pooling.md)
- [Contadores de rendimiento para ASP.NET](/previous-versions/aspnet/fxk122b4(v=vs.100))
- [Generar perfiles en tiempo de ejecución](../../debug-trace-profile/runtime-profiling.md)
- [Introducción a los umbrales de rendimiento de supervisión](/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))
- [Información general de ADO.NET](ado-net-overview.md)
