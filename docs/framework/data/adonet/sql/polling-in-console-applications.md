---
title: Sondear aplicaciones de consola
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4ff084d5-5956-4db1-8e18-c5a66b000882
ms.openlocfilehash: 35275206e0486c35f262116fa1deb06b9f285723
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183135"
---
# <a name="polling-in-console-applications"></a><span data-ttu-id="3c700-102">Sondear aplicaciones de consola</span><span class="sxs-lookup"><span data-stu-id="3c700-102">Polling in Console Applications</span></span>

<span data-ttu-id="3c700-103">Las operaciones asincrónicas en ADO.NET permiten iniciar operaciones de base de datos que consumen mucho tiempo en un subproceso mientras se realizan otras tareas en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="3c700-103">Asynchronous operations in ADO.NET allow you to initiate time-consuming database operations on one thread while performing other tasks on another thread.</span></span> <span data-ttu-id="3c700-104">Sin embargo, en la mayoría de los escenarios llegará a un punto en el que la aplicación no debería continuar hasta que se complete la operación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c700-104">In most scenarios, however, you will eventually reach a point where your application should not continue until the database operation is complete.</span></span> <span data-ttu-id="3c700-105">En estos casos, resulta útil sondear la operación asincrónica para determinar si la operación se ha completado o no.</span><span class="sxs-lookup"><span data-stu-id="3c700-105">For such cases, it is useful to poll the asynchronous operation to determine whether the operation has completed or not.</span></span>  
  
 <span data-ttu-id="3c700-106">Puede usar la propiedad <xref:System.IAsyncResult.IsCompleted%2A> para averiguar si se ha completado o no la operación.</span><span class="sxs-lookup"><span data-stu-id="3c700-106">You can use the <xref:System.IAsyncResult.IsCompleted%2A> property to find out whether or not the operation has completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c700-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c700-107">Example</span></span>  

 <span data-ttu-id="3c700-108">La siguiente aplicación de consola actualiza los datos de la base de datos de ejemplo **AdventureWorks** y lo hace de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="3c700-108">The following console application updates data within the **AdventureWorks** sample database, doing its work asynchronously.</span></span> <span data-ttu-id="3c700-109">Para emular un proceso de ejecución prolongada, en este ejemplo se inserta una instrucción WAITFOR en el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="3c700-109">In order to emulate a long-running process, this example inserts a WAITFOR statement in the command text.</span></span> <span data-ttu-id="3c700-110">Normalmente, no intentaría que los comandos se ejecutaran más lentamente, pero en este caso facilita la demostración del comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3c700-110">Normally, you would not try to make your commands run slower, but doing so in this case makes it easier to demonstrate asynchronous behavior.</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
  
Module Module1  
  
    Sub Main()  
        ' The WAITFOR statement simply adds enough time to prove the
        ' asynchronous nature of the command.  
        Dim commandText As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:3';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        RunCommandAsynchronously(commandText, GetConnectionString())  
  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub RunCommandAsynchronously( _  
     ByVal commandText As String, ByVal connectionString As String)  
  
        ' Given command text and connection string, asynchronously
        ' execute the specified command against the connection. For
        ' this example, the code displays an indicator as it's working,
        ' verifying the asynchronous behavior.
        Using connection As New SqlConnection(connectionString)  
            Try  
                Dim count As Integer = 0  
                Dim command As New SqlCommand(commandText, connection)  
                connection.Open()  
                Dim result As IAsyncResult = _  
                 command.BeginExecuteNonQuery()  
                While Not result.IsCompleted  
                    Console.WriteLine("Waiting ({0})", count)  
                    ' Wait for 1/10 second, so the counter  
                    ' doesn't consume all available resources
                    ' on the main thread.  
                    Threading.Thread.Sleep(100)  
                    count += 1  
                End While  
                Console.WriteLine( _  
                 "Command complete. Affected {0} rows.", _  
                 command.EndExecuteNonQuery(result))  
            Catch ex As SqlException  
                Console.WriteLine("Error ({0}): {1}", _  
                 ex.Number, ex.Message)  
            Catch ex As InvalidOperationException  
                Console.WriteLine("Error: {0}", ex.Message)  
            Catch ex As Exception  
                ' You might want to pass these errors  
                ' back out to the caller.  
                Console.WriteLine("Error: {0}", ex.Message)  
            End Try  
        End Using  
    End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
  
        ' If you have not included "Asynchronous Processing=true"
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks; " & _  
          "Asynchronous Processing=true"  
    End Function  
End Module
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
{  
    [STAThread]  
    static void Main()  
    {  
        // The WAITFOR statement simply adds enough time to
        // prove the asynchronous nature of the command.  
  
        string commandText =  
          "UPDATE Production.Product SET ReorderPoint = " +  
          "ReorderPoint + 1 " +  
          "WHERE ReorderPoint Is Not Null;" +  
          "WAITFOR DELAY '0:0:3';" +  
          "UPDATE Production.Product SET ReorderPoint = " +  
          "ReorderPoint - 1 " +  
          "WHERE ReorderPoint Is Not Null";  
  
        RunCommandAsynchronously(  
            commandText, GetConnectionString());  
  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  
    private static void RunCommandAsynchronously(  
      string commandText, string connectionString)  
    {  
        // Given command text and connection string, asynchronously  
        // execute the specified command against the connection.
        // For this example, the code displays an indicator as it's
        // working, verifying the asynchronous behavior.
        using (SqlConnection connection =  
          new SqlConnection(connectionString))  
        {  
            try  
            {  
                int count = 0;  
                SqlCommand command =
                    new SqlCommand(commandText, connection);  
                connection.Open();  
  
                IAsyncResult result =
                    command.BeginExecuteNonQuery();  
                while (!result.IsCompleted)  
                {  
                    Console.WriteLine(  
                                    "Waiting ({0})", count++);  
                    // Wait for 1/10 second, so the counter  
                    // doesn't consume all available
                    // resources on the main thread.  
                    System.Threading.Thread.Sleep(100);  
                }  
                Console.WriteLine(  
                    "Command complete. Affected {0} rows.",  
                command.EndExecuteNonQuery(result));  
            }  
            catch (SqlException ex)  
            {  
                Console.WriteLine("Error ({0}): {1}",
                    ex.Number, ex.Message);  
            }  
            catch (InvalidOperationException ex)  
            {  
                Console.WriteLine("Error: {0}", ex.Message);  
            }  
            catch (Exception ex)  
            {  
                // You might want to pass these errors  
                // back out to the caller.  
                Console.WriteLine("Error: {0}", ex.Message);  
            }  
        }  
    }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
  
        // If you have not included "Asynchronous Processing=true"  
        // in the connection string, the command will not be able  
        // to execute asynchronously.  
        return "Data Source=(local);Integrated Security=SSPI;" +  
        "Initial Catalog=AdventureWorks; " +
        "Asynchronous Processing=true";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c700-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c700-111">See also</span></span>

- [<span data-ttu-id="3c700-112">Operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="3c700-112">Asynchronous Operations</span></span>](asynchronous-operations.md)
- [<span data-ttu-id="3c700-113">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3c700-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
