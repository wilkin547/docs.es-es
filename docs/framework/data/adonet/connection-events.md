---
title: Eventos de Connection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: a7ad0d4d950da71db0aebca872949fa82669c5c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151707"
---
# <a name="connection-events"></a><span data-ttu-id="267a0-102">Eventos de Connection</span><span class="sxs-lookup"><span data-stu-id="267a0-102">Connection Events</span></span>
<span data-ttu-id="267a0-103">Todos los proveedores de datos de .NET Framework tienen objetos **Connection** con dos eventos que puede usar para recuperar mensajes informativos de un origen de datos o para determinar si ha cambiado el estado de una **conexión.**</span><span class="sxs-lookup"><span data-stu-id="267a0-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="267a0-104">En la tabla siguiente se describen los eventos del objeto **Connection.**</span><span class="sxs-lookup"><span data-stu-id="267a0-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="267a0-105">Evento</span><span class="sxs-lookup"><span data-stu-id="267a0-105">Event</span></span>|<span data-ttu-id="267a0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="267a0-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="267a0-107">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="267a0-107">**InfoMessage**</span></span>|<span data-ttu-id="267a0-108">Se produce cuando se devuelve un mensaje informativo desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="267a0-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="267a0-109">Los mensajes informativos son aquellos procedentes de orígenes de datos que no inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="267a0-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="267a0-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="267a0-110">**StateChange**</span></span>|<span data-ttu-id="267a0-111">Se produce cuando cambia el estado de la **conexión.**</span><span class="sxs-lookup"><span data-stu-id="267a0-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="267a0-112">Trabajar con el evento InfoMessage</span><span class="sxs-lookup"><span data-stu-id="267a0-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="267a0-113">Con el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> del objeto <xref:System.Data.SqlClient.SqlConnection> puede recuperar advertencias o mensajes informativos de un origen de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="267a0-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="267a0-114">Si se devuelven errores desde el origen de datos con un nivel de seguridad entre 11 y 16, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="267a0-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="267a0-115">Sin embargo, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> se puede utilizar para obtener mensajes del origen de datos que no estén asociados a un error.</span><span class="sxs-lookup"><span data-stu-id="267a0-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="267a0-116">En el caso de Microsoft SQL Server, cualquier error que tenga la gravedad 10, como máximo, se considera de tipo informativo y se captura mediante el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="267a0-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="267a0-117">Para obtener más información, consulte el artículo Gravedad de errores del motor de [base de datos.](/sql/relational-databases/errors-events/database-engine-error-severities)</span><span class="sxs-lookup"><span data-stu-id="267a0-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="267a0-118">El <xref:System.Data.SqlClient.SqlConnection.InfoMessage> evento recibe <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> un objeto que contiene, en su **propiedad Errors,** una colección de los mensajes del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="267a0-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="267a0-119">Puede consultar los objetos **Error** de esta colección para el número de error y el texto del mensaje, así como el origen del error.</span><span class="sxs-lookup"><span data-stu-id="267a0-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="267a0-120">El proveedor de datos .NET Framework para SQL Server incluye asimismo datos acerca de la base de datos, el procedimiento almacenado y el número de línea donde se originó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="267a0-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="267a0-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="267a0-121">Example</span></span>  
 <span data-ttu-id="267a0-122">En el ejemplo de código siguiente se muestra cómo se puede agregar un controlador de eventos para el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="267a0-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="267a0-123">Controlar errores como InfoMessages</span><span class="sxs-lookup"><span data-stu-id="267a0-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="267a0-124">Normalmente, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> solo se activa para mensajes informativos y de advertencia enviados desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="267a0-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="267a0-125">Sin embargo, cuando se produce un error real, se detiene la ejecución del método **ExecuteNonQuery** o **ExecuteReader** que inició la operación de servidor y se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="267a0-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="267a0-126">Si desea seguir procesando el resto de las instrucciones de un comando, independientemente de los errores producidos en el servidor, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> de <xref:System.Data.SqlClient.SqlConnection> como `true`.</span><span class="sxs-lookup"><span data-stu-id="267a0-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="267a0-127">De esta forma, la conexión activa el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> para errores, en lugar de iniciar una excepción e interrumpir el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="267a0-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="267a0-128">La aplicación cliente puede controlar el evento y reaccionar ante las situaciones de error.</span><span class="sxs-lookup"><span data-stu-id="267a0-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="267a0-129">Los errores con un nivel de gravedad de 17, como mínimo, que hacen que el servidor interrumpa el procesamiento de comandos, deben controlarse como excepciones.</span><span class="sxs-lookup"><span data-stu-id="267a0-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="267a0-130">En este caso, se inicia una excepción, independientemente del modo en que se controle el error en el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="267a0-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="267a0-131">Trabajar con el evento StateChange</span><span class="sxs-lookup"><span data-stu-id="267a0-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="267a0-132">El evento **StateChange** se produce cuando cambia el estado de una **conexión.**</span><span class="sxs-lookup"><span data-stu-id="267a0-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="267a0-133">El **evento StateChange** recibe <xref:System.Data.StateChangeEventArgs> que le permiten determinar el cambio en el estado de **Connection** mediante el uso de la **OriginalState** y **CurrentState** propiedades.</span><span class="sxs-lookup"><span data-stu-id="267a0-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="267a0-134">El **OriginalState** propiedad <xref:System.Data.ConnectionState> es una enumeración que indica el estado de la **conexión** antes de que cambiara.</span><span class="sxs-lookup"><span data-stu-id="267a0-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="267a0-135">**CurrentState** es <xref:System.Data.ConnectionState> una enumeración que indica el estado de la **conexión** después de cambiar.</span><span class="sxs-lookup"><span data-stu-id="267a0-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="267a0-136">En el ejemplo de código siguiente se utiliza el **StateChange** eventos para escribir un mensaje en la consola cuando cambia el estado de la **conexión.**</span><span class="sxs-lookup"><span data-stu-id="267a0-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="267a0-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="267a0-137">See also</span></span>

- [<span data-ttu-id="267a0-138">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="267a0-138">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="267a0-139">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="267a0-139">ADO.NET Overview</span></span>](ado-net-overview.md)
