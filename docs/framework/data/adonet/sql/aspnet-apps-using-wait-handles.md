---
title: Aplicaciones ASP.NET que usan identificadores de espera
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f588597a-49de-4206-8463-4ef377e112ff
ms.openlocfilehash: b590b504d1d497e35612b9d7ea047fe12c43c386
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197604"
---
# <a name="aspnet-applications-using-wait-handles"></a><span data-ttu-id="54cee-102">Aplicaciones ASP.NET que usan identificadores de espera</span><span class="sxs-lookup"><span data-stu-id="54cee-102">ASP.NET Applications Using Wait Handles</span></span>

<span data-ttu-id="54cee-103">Los modelos de devolución de llamada y sondeo para controlar las operaciones asincrónicas son útiles cuando la aplicación está procesando una sola operación asincrónica a la vez.</span><span class="sxs-lookup"><span data-stu-id="54cee-103">The callback and polling models for handling asynchronous operations are useful when your application is processing only one asynchronous operation at a time.</span></span> <span data-ttu-id="54cee-104">Los modelos Wait proporcionan una manera más flexible de procesar varias operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="54cee-104">The Wait models provide a more flexible way of processing multiple asynchronous operations.</span></span> <span data-ttu-id="54cee-105">Existen dos modelos Wait, cuyo nombre se debe a los métodos <xref:System.Threading.WaitHandle> usados para implementarlos: Wait (Any) y Wait (All).</span><span class="sxs-lookup"><span data-stu-id="54cee-105">There are two Wait models, named for the <xref:System.Threading.WaitHandle> methods used to implement them: the Wait (Any) model and the Wait (All) model.</span></span>  
  
 <span data-ttu-id="54cee-106">Para usar cualquier modelo Wait, debe usar la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> del objeto <xref:System.IAsyncResult> devuelto por los métodos <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> o <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="54cee-106">To use either Wait model, you need to use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> object returned by the <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, or <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> methods.</span></span> <span data-ttu-id="54cee-107">Los métodos <xref:System.Threading.WaitHandle.WaitAny%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> requieren que se envíen los objetos <xref:System.Threading.WaitHandle> como argumento, agrupados en una matriz.</span><span class="sxs-lookup"><span data-stu-id="54cee-107">The <xref:System.Threading.WaitHandle.WaitAny%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> methods both require you to send the <xref:System.Threading.WaitHandle> objects as an argument, grouped together in an array.</span></span>  
  
 <span data-ttu-id="54cee-108">Ambos métodos Wait supervisan las operaciones asincrónicas, a la espera de su finalización.</span><span class="sxs-lookup"><span data-stu-id="54cee-108">Both Wait methods monitor the asynchronous operations, waiting for completion.</span></span> <span data-ttu-id="54cee-109">El <xref:System.Threading.WaitHandle.WaitAny%2A> método espera a que se complete o se agote el tiempo de espera de cualquiera de las operaciones. Una vez que sepa que se ha completado una operación determinada, puede procesar sus resultados y, después, esperar a que la siguiente operación se complete o se agote el tiempo de espera. El <xref:System.Threading.WaitHandle.WaitAll%2A> método espera a que se completen todos los procesos de la matriz de <xref:System.Threading.WaitHandle> instancias o se agote el tiempo de espera antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="54cee-109">The <xref:System.Threading.WaitHandle.WaitAny%2A> method waits for any of the operations to complete or time out. Once you know a particular operation is complete, you can process its results and then continue waiting for the next operation to complete or time out. The <xref:System.Threading.WaitHandle.WaitAll%2A> method waits for all of the processes in the array of <xref:System.Threading.WaitHandle> instances to complete or time out before continuing.</span></span>  
  
 <span data-ttu-id="54cee-110">La ventaja de los modelos Wait es más impactante cuando se necesita ejecutar varias operaciones de cierta longitud en servidores diferentes, o bien cuando el servidor es lo suficientemente eficaz como para procesar todas las consultas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="54cee-110">The Wait models' benefit is most striking when you need to run multiple operations of some length on different servers, or when your server is powerful enough to process all the queries at the same time.</span></span> <span data-ttu-id="54cee-111">En los ejemplos de este artículo, tres consultas emulan procesos largos agregando comandos WAITFOR de diferentes longitudes a consultas SELECT sin relevancia.</span><span class="sxs-lookup"><span data-stu-id="54cee-111">In the examples presented here, three queries emulate long processes by adding WAITFOR commands of varying lengths to inconsequential SELECT queries.</span></span>  
  
## <a name="example-wait-any-model"></a><span data-ttu-id="54cee-112">Ejemplo: Modelo Wait (Any)</span><span class="sxs-lookup"><span data-stu-id="54cee-112">Example: Wait (Any) Model</span></span>  

 <span data-ttu-id="54cee-113">En el ejemplo siguiente se ilustra el modelo Wait (Any).</span><span class="sxs-lookup"><span data-stu-id="54cee-113">The following example illustrates the Wait (Any) model.</span></span> <span data-ttu-id="54cee-114">Una vez iniciados tres procesos asincrónicos, se llama al método <xref:System.Threading.WaitHandle.WaitAny%2A> para esperar a que se complete cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="54cee-114">Once three asynchronous processes are started, the <xref:System.Threading.WaitHandle.WaitAny%2A> method is called to wait for the completion of any one of them.</span></span> <span data-ttu-id="54cee-115">Cuando se completa cada proceso, se llama al método <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> y se lee el objeto <xref:System.Data.SqlClient.SqlDataReader> devuelto.</span><span class="sxs-lookup"><span data-stu-id="54cee-115">As each process completes, the <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> method is called and the resulting <xref:System.Data.SqlClient.SqlDataReader> object is read.</span></span> <span data-ttu-id="54cee-116">En este punto, una aplicación real probablemente usaría <xref:System.Data.SqlClient.SqlDataReader> para rellenar una parte de la página.</span><span class="sxs-lookup"><span data-stu-id="54cee-116">At this point, a real-world application would likely use the <xref:System.Data.SqlClient.SqlDataReader> to populate a portion of the page.</span></span> <span data-ttu-id="54cee-117">En este sencillo ejemplo, se agrega la hora a la que se completa el proceso a un cuadro de texto correspondiente al proceso.</span><span class="sxs-lookup"><span data-stu-id="54cee-117">In this simple example, the time the process completed is added to a text box corresponding to the process.</span></span> <span data-ttu-id="54cee-118">Tomadas juntas, las horas de los cuadros de texto ilustran el punto: el código se ejecuta cada vez que se completa un proceso.</span><span class="sxs-lookup"><span data-stu-id="54cee-118">Taken together, the times in the text boxes illustrate the point: Code is executed each time a process completes.</span></span>  
  
 <span data-ttu-id="54cee-119">Para configurar este ejemplo, cree un proyecto de sitio web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="54cee-119">To set up this example, create a new ASP.NET Web Site project.</span></span> <span data-ttu-id="54cee-120">Coloque un control <xref:System.Web.UI.WebControls.Button> y cuatro controles <xref:System.Web.UI.WebControls.TextBox> en la página (aceptando el nombre predeterminado de cada control).</span><span class="sxs-lookup"><span data-stu-id="54cee-120">Place a <xref:System.Web.UI.WebControls.Button> control and four <xref:System.Web.UI.WebControls.TextBox> controls on the page (accepting the default name for each control).</span></span>  
  
 <span data-ttu-id="54cee-121">Agregue el código siguiente a la clase del formulario y modifique la cadena de conexión según sea necesario para su entorno.</span><span class="sxs-lookup"><span data-stu-id="54cee-121">Add the following code to the form's class, modifying the connection string as necessary for your environment.</span></span>  
  
```vb  
' Add these to the top of the class  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Threading  
  
' Add this code to the page's class:  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
  
        ' If you have not included "Asynchronous Processing=true"
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks;" & _  
          "Asynchronous Processing=true"  
    End Function
  
    Sub Button1_Click( _  
     ByVal sender As Object, ByVal e As System.EventArgs)  
  
        ' In a real-world application, you might be connecting to
        '  three different servers or databases. For the example,  
        '  we connect to only one.  
        Dim connection1 As New SqlConnection(GetConnectionString())  
        Dim connection2 As New SqlConnection(GetConnectionString())  
        Dim connection3 As New SqlConnection(GetConnectionString())  
  
        ' To keep the example simple, all three asynchronous
        ' processes select a row from the same table. WAITFOR  
        ' commands are used to emulate long-running processes  
        ' that complete after different periods of time.  
        Dim commandText1 As String = _  
            "WAITFOR DELAY '0:0:01';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim commandText2 As String = _  
            "WAITFOR DELAY '0:0:05';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim commandText3 As String = _  
            "WAITFOR DELAY '0:0:10';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim waitHandles(2) As WaitHandle  
        Try  
            ' For each process, open a connection and begin execution.  
            ' Use the IAsyncResult object returned by
            ' BeginExecuteReader to add a WaitHandle for the process  
            ' to the array.  
            connection1.Open()  
            Dim command1 As New SqlCommand(commandText1, connection1)  
            Dim result1 As IAsyncResult = _  
             command1.BeginExecuteReader()  
            waitHandles(0) = result1.AsyncWaitHandle  
  
            connection2.Open()  
            Dim command2 As New SqlCommand(commandText2, connection2)  
            Dim result2 As IAsyncResult = _  
             command2.BeginExecuteReader()  
            waitHandles(1) = result2.AsyncWaitHandle  
  
            connection3.Open()  
            Dim command3 As New SqlCommand(commandText3, connection3)  
            Dim result3 As IAsyncResult = _  
             command3.BeginExecuteReader()  
            waitHandles(2) = result3.AsyncWaitHandle  
  
            Dim index As Integer  
            For countWaits As Integer = 1 To 3  
                ' WaitAny waits for any of the processes to complete.  
                ' The return value is either the index of the  
                ' array element whose process just completed, or  
                ' the WaitTimeout value.  
                index = WaitHandle.WaitAny(waitHandles, 60000, False)  
                ' This example doesn't actually do anything with the
                ' data returned by the processes, but the code opens
                ' readers for each just to demonstrate the concept.  
                ' Instead of using the returned data to fill the
                ' controls on the page, the example adds the time  
                ' the process was completed to the corresponding  
                ' text box.  
                Select Case index  
                    Case 0  
                        Dim reader1 As SqlDataReader  
                        reader1 = command1.EndExecuteReader(result1)  
                        If reader1.Read Then  
                            TextBox1.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader1.Close()  
  
                    Case 1  
                        Dim reader2 As SqlDataReader  
                        reader2 = command2.EndExecuteReader(result2)  
                        If reader2.Read Then  
                            TextBox2.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader2.Close()  
                    Case 2  
                        Dim reader3 As SqlDataReader  
                        reader3 = command3.EndExecuteReader(result3)  
                        If reader3.Read Then  
                            TextBox3.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader3.Close()  
                    Case WaitHandle.WaitTimeout  
                        Throw New Exception("Timeout")  
                End Select  
  
            Next  
        Catch ex As Exception  
            TextBox4.Text = ex.ToString  
        End Try  
        connection1.Close()  
        connection2.Close()  
        connection3.Close()  
  
    End Sub  
```  
  
```csharp  
// Add the following using statements, if they are not already there.  
using System;  
using System.Data;  
using System.Configuration;  
using System.Web;  
using System.Web.Security;  
using System.Web.UI;  
using System.Web.UI.WebControls;  
using System.Web.UI.WebControls.WebParts;  
using System.Web.UI.HtmlControls;  
using System.Threading;  
using System.Data.SqlClient;  
  
// Add this code to the page's class  
string GetConnectionString()  
     //  To avoid storing the connection string in your code,
     //  you can retrieve it from a configuration file.
     //  If you have not included "Asynchronous Processing=true"
     //  in the connection string, the command will not be able  
     //  to execute asynchronously.  
{  
     return "Data Source=(local);Integrated Security=SSPI;" +  
          "Initial Catalog=AdventureWorks;" +  
          "Asynchronous Processing=true";  
}  
void Button1_Click(object sender, System.EventArgs e)  
{  
     //  In a real-world application, you might be connecting to
     //   three different servers or databases. For the example,  
     //   we connect to only one.  
  
     SqlConnection connection1 =
          new SqlConnection(GetConnectionString());  
     SqlConnection connection2 =
          new SqlConnection(GetConnectionString());  
     SqlConnection connection3 =
          new SqlConnection(GetConnectionString());  
     //  To keep the example simple, all three asynchronous
     //  processes select a row from the same table. WAITFOR  
     //  commands are used to emulate long-running processes  
     //  that complete after different periods of time.  
  
     string commandText1 = "WAITFOR DELAY '0:0:01';" +
          "SELECT * FROM Production.Product " +
          "WHERE ProductNumber = 'BL-2036'";  
     string commandText2 = "WAITFOR DELAY '0:0:05';" +
          "SELECT * FROM Production.Product " +
          "WHERE ProductNumber = 'BL-2036'";  
     string commandText3 = "WAITFOR DELAY '0:0:10';" +
          "SELECT * FROM Production.Product " +
          "WHERE ProductNumber = 'BL-2036'";  
     try  
          //  For each process, open a connection and begin
          //  execution. Use the IAsyncResult object returned by
          //  BeginExecuteReader to add a WaitHandle for the
          //  process to the array.  
     {  
          connection1.Open();  
          SqlCommand command1 =  
               new SqlCommand(commandText1, connection1);  
          IAsyncResult result1 = command1.BeginExecuteReader();  
          WaitHandle waitHandle1 = result1.AsyncWaitHandle;  
  
          connection2.Open();  
          SqlCommand command2 =  
               new SqlCommand(commandText2, connection2);  
          IAsyncResult result2 = command2.BeginExecuteReader();  
          WaitHandle waitHandle2 = result2.AsyncWaitHandle;  
  
          connection3.Open();  
          SqlCommand command3 =  
               new SqlCommand(commandText3, connection3);  
          IAsyncResult result3 = command3.BeginExecuteReader();  
          WaitHandle waitHandle3 = result3.AsyncWaitHandle;  
  
          WaitHandle[] waitHandles = {  
               waitHandle1, waitHandle2, waitHandle3  
          };  
  
          int index;  
          for (int countWaits = 0; countWaits <= 2; countWaits++)  
          {  
               //  WaitAny waits for any of the processes to
               //  complete. The return value is either the index
               //  of the array element whose process just
               //  completed, or the WaitTimeout value.  
  
               index = WaitHandle.WaitAny(waitHandles,
                    60000, false);  
               //  This example doesn't actually do anything with
               //  the data returned by the processes, but the
               //  code opens readers for each just to demonstrate
               //  the concept.  
               //  Instead of using the returned data to fill the
               //  controls on the page, the example adds the time  
               //  the process was completed to the corresponding  
               //  text box.  
  
               switch (index)  
               {  
                    case 0:  
                         SqlDataReader reader1;  
                         reader1 =
                              command1.EndExecuteReader(result1);  
                         if (reader1.Read())  
                         {  
                           TextBox1.Text =
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader1.Close();  
                         break;  
                    case 1:  
                         SqlDataReader reader2;  
                         reader2 =
                              command2.EndExecuteReader(result2);  
                         if (reader2.Read())  
                         {  
                           TextBox2.Text =
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader2.Close();  
                         break;  
                    case 2:  
                         SqlDataReader reader3;  
                         reader3 =
                              command3.EndExecuteReader(result3);  
                         if (reader3.Read())  
                         {  
                           TextBox3.Text =
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader3.Close();  
                         break;  
                    case WaitHandle.WaitTimeout:  
                         throw new Exception("Timeout");  
                         break;  
               }  
          }  
     }  
     catch (Exception ex)  
     {  
          TextBox4.Text = ex.ToString();  
     }  
     connection1.Close();  
     connection2.Close();  
     connection3.Close();  
}  
```  
  
## <a name="example-wait-all-model"></a><span data-ttu-id="54cee-122">Ejemplo: Modelo Wait (All)</span><span class="sxs-lookup"><span data-stu-id="54cee-122">Example: Wait (All) Model</span></span>  

 <span data-ttu-id="54cee-123">En el ejemplo siguiente se ilustra el modelo Wait (All).</span><span class="sxs-lookup"><span data-stu-id="54cee-123">The following example illustrates the Wait (All) model.</span></span> <span data-ttu-id="54cee-124">Una vez iniciados tres procesos asincrónicos, se llama al método <xref:System.Threading.WaitHandle.WaitAll%2A> para esperar a que los procesos se completen o agoten el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="54cee-124">Once three asynchronous processes are started, the <xref:System.Threading.WaitHandle.WaitAll%2A> method is called to wait for the processes to complete or time out.</span></span>  
  
 <span data-ttu-id="54cee-125">Al igual que en el ejemplo del modelo Wait (Any), la hora en que se completa el proceso se agrega al cuadro de texto correspondiente al proceso.</span><span class="sxs-lookup"><span data-stu-id="54cee-125">Like the example of the Wait (Any) model, the time the process completed is added to a text box corresponding to the process.</span></span> <span data-ttu-id="54cee-126">De nuevo, las horas de los cuadros de texto ilustran el punto: el código que sigue al método <xref:System.Threading.WaitHandle.WaitAny%2A> solo se ejecuta una vez completados todos los procesos.</span><span class="sxs-lookup"><span data-stu-id="54cee-126">Again, the times in the text boxes illustrate the point: Code following the <xref:System.Threading.WaitHandle.WaitAny%2A> method is executed only after all processes are complete.</span></span>  
  
 <span data-ttu-id="54cee-127">Para configurar este ejemplo, cree un proyecto de sitio web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="54cee-127">To set up this example, create a new ASP.NET Web Site project.</span></span> <span data-ttu-id="54cee-128">Coloque un control <xref:System.Web.UI.WebControls.Button> y cuatro controles <xref:System.Web.UI.WebControls.TextBox> en la página (aceptando el nombre predeterminado de cada control).</span><span class="sxs-lookup"><span data-stu-id="54cee-128">Place a <xref:System.Web.UI.WebControls.Button> control and four <xref:System.Web.UI.WebControls.TextBox> controls on the page (accepting the default name for each control).</span></span>  
  
 <span data-ttu-id="54cee-129">Agregue el código siguiente a la clase del formulario y modifique la cadena de conexión según sea necesario para su entorno.</span><span class="sxs-lookup"><span data-stu-id="54cee-129">Add the following code to the form's class, modifying the connection string as necessary for your environment.</span></span>  
  
```vb  
' Add these to the top of the class  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Threading  
  
' Add this code to the page's class:  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
  
        ' If you have not included "Asynchronous Processing=true"
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks;" & _  
          "Asynchronous Processing=true"  
    End Function
    Sub Button1_Click( _  
     ByVal sender As Object, ByVal e As System.EventArgs)  
  
        ' In a real-world application, you might be connecting to
        '  three different servers or databases. For the example,  
        '  we connect to only one.  
        Dim connection1 As New SqlConnection(GetConnectionString())  
        Dim connection2 As New SqlConnection(GetConnectionString())  
        Dim connection3 As New SqlConnection(GetConnectionString())  
  
        ' To keep the example simple, all three asynchronous
        ' processes select a row from the same table. WAITFOR  
        ' commands are used to emulate long-running processes  
        ' that complete after different periods of time.  
        Dim commandText1 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:01';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim commandText2 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:05';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim commandText3 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:10';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim waitHandles(2) As WaitHandle  
  
        Try  
            ' For each process, open a connection and begin execution.  
            ' Use the IAsyncResult object returned by
            ' BeginExecuteReader to add a WaitHandle for the process  
            ' to the array.  
            connection1.Open()  
            Dim command1 As New SqlCommand(commandText1, connection1)  
            Dim result1 As IAsyncResult = _  
             command1.BeginExecuteNonQuery()  
            waitHandles(0) = result1.AsyncWaitHandle  
  
            connection2.Open()  
            Dim command2 As New SqlCommand(commandText2, connection2)  
            Dim result2 As IAsyncResult = _  
             command2.BeginExecuteNonQuery()  
            waitHandles(1) = result2.AsyncWaitHandle  
  
            connection3.Open()  
            Dim command3 As New SqlCommand(commandText3, connection3)  
            Dim result3 As IAsyncResult = _  
             command3.BeginExecuteNonQuery()  
            waitHandles(2) = result3.AsyncWaitHandle  
  
            ' WaitAll waits for all of the processes to complete.  
            ' The return value is True if all processes completed,
            ' False if any process timed out.  
            Dim result As Boolean = _  
             WaitHandle.WaitAll(waitHandles, 60000, False)  
            If result Then  
                Dim rowCount1 As Long = _  
                 command1.EndExecuteNonQuery(result1)  
                TextBox1.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
  
                Dim rowCount2 As Long = _  
                 command2.EndExecuteNonQuery(result2)  
                TextBox2.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
  
                Dim rowCount3 As Long = _  
                 command3.EndExecuteNonQuery(result3)  
                TextBox3.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
            Else  
                Throw New Exception("Timeout")  
            End If  
        Catch ex As Exception  
            TextBox4.Text = ex.ToString  
        End Try  
        connection1.Close()  
        connection2.Close()  
        connection3.Close()  
  
    End Sub  
```  
  
```csharp  
// Add the following using statements, if they are not already there.  
using System;  
using System.Data;  
using System.Configuration;  
using System.Web;  
using System.Web.Security;  
using System.Web.UI;  
using System.Web.UI.WebControls;  
using System.Web.UI.WebControls.WebParts;  
using System.Web.UI.HtmlControls;  
using System.Threading;  
using System.Data.SqlClient;  
  
// Add this code to the page's class  
string GetConnectionString()  
    //  To avoid storing the connection string in your code,
    //  you can retrieve it from a configuration file.
    //  If you have not included "Asynchronous Processing=true"
    //  in the connection string, the command will not be able  
    //  to execute asynchronously.  
{  
    return "Data Source=(local);Integrated Security=SSPI;" +  
        "Initial Catalog=AdventureWorks;" +  
        "Asynchronous Processing=true";  
}  
void Button1_Click(object sender, System.EventArgs e)  
{  
    //  In a real-world application, you might be connecting to
    //   three different servers or databases. For the example,  
    //   we connect to only one.  
  
    SqlConnection connection1 =
        new SqlConnection(GetConnectionString());  
    SqlConnection connection2 =
        new SqlConnection(GetConnectionString());  
    SqlConnection connection3 =
        new SqlConnection(GetConnectionString());  
    //  To keep the example simple, all three asynchronous
    //  processes execute UPDATE queries that result in  
      //  no change to the data. WAITFOR  
    //  commands are used to emulate long-running processes  
    //  that complete after different periods of time.  
  
    string commandText1 =
        "UPDATE Production.Product " +  
        "SET ReorderPoint = ReorderPoint + 1 " +  
        "WHERE ReorderPoint Is Not Null;" +  
        "WAITFOR DELAY '0:0:01';" +  
        "UPDATE Production.Product " +  
        "SET ReorderPoint = ReorderPoint - 1 " +  
        "WHERE ReorderPoint Is Not Null";  
  
    string commandText2 =
      "UPDATE Production.Product " +  
      "SET ReorderPoint = ReorderPoint + 1 " +  
      "WHERE ReorderPoint Is Not Null;" +  
      "WAITFOR DELAY '0:0:05';" +  
      "UPDATE Production.Product " +  
      "SET ReorderPoint = ReorderPoint - 1 " +  
      "WHERE ReorderPoint Is Not Null";  
  
    string commandText3 =  
       "UPDATE Production.Product " +  
       "SET ReorderPoint = ReorderPoint + 1 " +  
       "WHERE ReorderPoint Is Not Null;" +  
       "WAITFOR DELAY '0:0:10';" +  
       "UPDATE Production.Product " +  
       "SET ReorderPoint = ReorderPoint - 1 " +  
       "WHERE ReorderPoint Is Not Null";  
    try  
        //  For each process, open a connection and begin
        //  execution. Use the IAsyncResult object returned by
        //  BeginExecuteReader to add a WaitHandle for the
        //  process to the array.  
    {  
        connection1.Open();  
        SqlCommand command1 =  
            new SqlCommand(commandText1, connection1);  
        IAsyncResult result1 = command1.BeginExecuteNonQuery();  
        WaitHandle waitHandle1 = result1.AsyncWaitHandle;  
        connection2.Open();  
  
        SqlCommand command2 =  
            new SqlCommand(commandText2, connection2);  
        IAsyncResult result2 = command2.BeginExecuteNonQuery();  
        WaitHandle waitHandle2 = result2.AsyncWaitHandle;  
        connection3.Open();  
  
        SqlCommand command3 =  
            new SqlCommand(commandText3, connection3);  
        IAsyncResult result3 = command3.BeginExecuteNonQuery();  
        WaitHandle waitHandle3 = result3.AsyncWaitHandle;  
  
        WaitHandle[] waitHandles = {  
            waitHandle1, waitHandle2, waitHandle3  
        };  
  
        bool result;  
        //  WaitAll waits for all of the processes to
        //  complete. The return value is True if the processes  
        //  all completed successfully, False if any process  
        //  timed out.  
  
        result = WaitHandle.WaitAll(waitHandles, 60000, false);  
        if(result)  
        {  
            long rowCount1 =
                command1.EndExecuteNonQuery(result1);  
            TextBox1.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
            long rowCount2 =
                command2.EndExecuteNonQuery(result2);  
            TextBox2.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
  
            long rowCount3 =
                command3.EndExecuteNonQuery(result3);  
            TextBox3.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
        }  
        else  
        {  
            throw new Exception("Timeout");  
        }  
    }  
  
    catch (Exception ex)  
    {  
        TextBox4.Text = ex.ToString();  
    }  
    connection1.Close();  
    connection2.Close();  
    connection3.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="54cee-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54cee-130">See also</span></span>

- [<span data-ttu-id="54cee-131">Operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="54cee-131">Asynchronous Operations</span></span>](asynchronous-operations.md)
- [<span data-ttu-id="54cee-132">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="54cee-132">ADO.NET Overview</span></span>](../ado-net-overview.md)
