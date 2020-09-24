---
title: Integración de System.Transactions con SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 5adf40f96854e08736cdef77300d69e452de5eea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191689"
---
# <a name="systemtransactions-integration-with-sql-server"></a>Integración de System.Transactions con SQL Server

La versión .NET Framework 2,0 presentó un marco de trabajo de transacciones al que se puede tener acceso a través del <xref:System.Transactions> espacio de nombres. Este marco de trabajo expone las transacciones de una manera totalmente integrada en el .NET Framework, incluido ADO.NET.  
  
 Además de las mejoras de programación, <xref:System.Transactions> y ADO.net pueden funcionar juntos para coordinar las optimizaciones al trabajar con transacciones. Una transacción promovible es una transacción ligera (local) que, en caso necesario, se puede promover automáticamente a una transacción completamente distribuida.  
  
 A partir de ADO.NET 2,0, <xref:System.Data.SqlClient> admite transacciones promocionadas al trabajar con SQL Server. Las transacciones promovibles no invocan la sobrecarga adicional de las transacciones distribuidas a menos que sea necesario. Las transacciones promocionadas son automáticas y no requieren la intervención del desarrollador.  
  
 Las transacciones promocionadas solo están disponibles cuando se usa el proveedor de datos de .NET Framework para SQL Server ( `SqlClient` ) con SQL Server.  
  
## <a name="creating-promotable-transactions"></a>Creación de transacciones promocionadas  

 El proveedor de .NET Framework para SQL Server proporciona compatibilidad con las transacciones promocionadas, que se administran a través de las clases en el <xref:System.Transactions> espacio de nombres .NET Framework. Las transacciones promocionadas optimizan las transacciones distribuidas ya que aplazan la creación de las mismas hasta que es necesario. Si solo se necesita un administrador de recursos, no tiene lugar ninguna transacción distribuida.  
  
> [!NOTE]
> En un caso que no es de plena confianza, se requiere <xref:System.Transactions.DistributedTransactionPermission> cuando la transacción se promueve al nivel de transacción distribuida.  
  
## <a name="promotable-transaction-scenarios"></a>Situaciones de uso de transacciones promocionadas  

 Normalmente, las transacciones distribuidas consumen muchos recursos del sistema, siendo el encargado de administrarlas Microsoft DTC (Coordinador de transacciones distribuidas), que integra todos los administradores de recursos a los que se tiene acceso en la transacción. Una transacción promocionada es una forma especial de una <xref:System.Transactions> transacción que delega eficazmente el trabajo a una transacción de SQL Server simple. <xref:System.Transactions>, <xref:System.Data.SqlClient> y SQL Server coordinar el trabajo implicado en el control de la transacción y promoverla a una transacción distribuida completa según sea necesario.  
  
 La ventaja de utilizar transacciones promocionadas es que cuando se abre una conexión utilizando una transacción <xref:System.Transactions.TransactionScope> activa, y no hay ninguna otra conexión abierta, la transacción se confirma como una transacción ligera, en lugar de incurrir en la sobrecarga adicional de una transacción completamente distribuida.  
  
### <a name="connection-string-keywords"></a>Palabras clave de cadena de conexión  

 La propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> admite una palabra clave, `Enlist`, que indica si <xref:System.Data.SqlClient> detectará contextos transaccionales e inscribirá automáticamente la conexión en una transacción distribuida. Si `Enlist=true`, la conexión se inscribe automáticamente en el contexto de transacción actual del subproceso de apertura. Si `Enlist=false`, la conexión `SqlClient` no interactúa con una transacción distribuida. El valor predeterminado de `Enlist` es true. Si no se especifica `Enlist` en la cadena de conexión, la conexión se da de alta automáticamente en una transacción distribuida si se detecta una al abrirse la conexión.  
  
 Las palabras clave `Transaction Binding` en una cadena de conexión <xref:System.Data.SqlClient.SqlConnection> controlan la asociación de la conexión con una transacción `System.Transactions` dada de alta. También está disponible mediante la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  
  
 La siguiente tabla describe los posibles valores.  
  
|Palabra clave|Descripción|  
|-------------|-----------------|  
|Desenlace implícito|El valor predeterminado. La conexión se separa de la transacción cuando termina, y vuelve a cambiar al modo de confirmación automática.|  
|Desenlace explícito|La conexión sigue adjuntada a la transacción hasta que ésta se cierra. La conexión producirá errores si no está activa o no coincide con <xref:System.Transactions.Transaction.Current%2A>.|  
  
## <a name="using-transactionscope"></a>Uso de TransactionScope  

 La clase <xref:System.Transactions.TransactionScope> crea un bloque de código transaccional dando de alta implícitamente las conexiones en una transacción distribuida. Debe llamar al método <xref:System.Transactions.TransactionScope.Complete%2A> al final del bloque <xref:System.Transactions.TransactionScope> antes de abandonarlo. Al salir del bloque se invoca el método <xref:System.Transactions.TransactionScope.Dispose%2A> . Si se ha producido una excepción que ocasiona que el código salga del ámbito, la transacción se considera anulada.  
  
 Se recomienda el uso de un bloque `using` para asegurarse de que se llama a <xref:System.Transactions.TransactionScope.Dispose%2A> en el objeto <xref:System.Transactions.TransactionScope> cuando se sale de dicho bloque. Si no se confirman ni revierten las transacciones pendientes, el rendimiento puede verse seriamente afectado ya que el tiempo de espera predeterminado de <xref:System.Transactions.TransactionScope> es un minuto. Si no utiliza una instrucción `using`, debe realizar todo el trabajo de un bloque `Try` y llamar explícitamente al método <xref:System.Transactions.TransactionScope.Dispose%2A> del bloque `Finally`.  
  
 Si se produce una excepción en <xref:System.Transactions.TransactionScope>, la transacción se marca como incoherente y se abandona. Se revertirá cuando se elimine el <xref:System.Transactions.TransactionScope> . Si no se produce ninguna excepción, las transacciones participantes se confirman.  
  
> [!NOTE]
> La clase `TransactionScope` crea una transacción con <xref:System.Transactions.Transaction.IsolationLevel%2A> de `Serializable` de forma predeterminada. Dependiendo de la aplicación, puede considerar la opción de reducir el nivel de aislamiento para evitar conflictos en ella.  
  
> [!NOTE]
> Se recomienda que solo realice actualizaciones, inserciones y eliminaciones en transacciones distribuidas, ya que consumen una cantidad considerable de recursos de base de datos. Las instrucciones SELECT pueden bloquear los recursos de base de datos de forma innecesaria y, en algunas situaciones, es posible que tengan que utilizarse transacciones para las selecciones. Todo el trabajo que no sea de base de datos debe realizarse fuera del ámbito de la transacción, a menos que estén implicados otros administradores de recursos de transacción. Aunque una excepción en el ámbito de la transacción impide que se confirme la misma, la clase <xref:System.Transactions.TransactionScope> no deja revertir los cambios que haya realizado el código fuera del ámbito de la propia transacción. Si es necesario realizar alguna acción cuando se revierta la transacción, deberá escribir su propia implementación de la interfaz <xref:System.Transactions.IEnlistmentNotification> y darla de alta explícitamente en la transacción.  
  
## <a name="example"></a>Ejemplo  

 Trabajar con <xref:System.Transactions> requiere disponer de una referencia a System.Transactions.dll.  
  
 La siguiente función muestra cómo crear una transacción promocionada en dos instancias de SQL Server diferentes, representadas por dos objetos <xref:System.Data.SqlClient.SqlConnection> diferentes, que se incluyen en un bloque <xref:System.Transactions.TransactionScope> . El código crea el bloque <xref:System.Transactions.TransactionScope> con una instrucción `using` y abre la primera conexión, que automáticamente se da de alta en <xref:System.Transactions.TransactionScope>. La transacción se da de alta inicialmente como una transacción ligera, no como una transacción distribuida completa. La segunda conexión se inscribe en <xref:System.Transactions.TransactionScope> únicamente si el comando de la primera conexión no produce una excepción. Cuando se abre la segunda conexión, la transacción se promociona automáticamente a una transacción completamente distribuida. Se invoca el método <xref:System.Transactions.TransactionScope.Complete%2A> , que confirma la transacción únicamente si no se han producido excepciones. Si en algún punto del bloque <xref:System.Transactions.TransactionScope> se ha producido una excepción, no se llamará a `Complete` y, cuando se elimine <xref:System.Transactions.TransactionScope> al final de su bloque `using` , se revertirá la transacción distribuida.  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a>Consulte también

- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Información general de ADO.NET](ado-net-overview.md)
