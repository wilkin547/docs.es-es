---
description: 'Más información acerca de: eventos de conexión'
title: Eventos de Connection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: fcf131e41ce90db11e84fd241744e348f4ca739e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663812"
---
# <a name="connection-events"></a><span data-ttu-id="acfa8-103">Eventos de Connection</span><span class="sxs-lookup"><span data-stu-id="acfa8-103">Connection Events</span></span>

<span data-ttu-id="acfa8-104">Todos los proveedores de datos .NET Framework tienen objetos de **conexión** con dos eventos que se pueden usar para recuperar mensajes informativos de un origen de datos o para determinar si el estado de una **conexión** ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="acfa8-104">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="acfa8-105">En la tabla siguiente se enumeran los eventos del objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="acfa8-105">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="acfa8-106">Evento</span><span class="sxs-lookup"><span data-stu-id="acfa8-106">Event</span></span>|<span data-ttu-id="acfa8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="acfa8-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acfa8-108">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="acfa8-108">**InfoMessage**</span></span>|<span data-ttu-id="acfa8-109">Se produce cuando se devuelve un mensaje informativo desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acfa8-109">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="acfa8-110">Los mensajes informativos son aquellos procedentes de orígenes de datos que no inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="acfa8-110">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="acfa8-111">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="acfa8-111">**StateChange**</span></span>|<span data-ttu-id="acfa8-112">Se produce cuando cambia el estado del objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="acfa8-112">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="acfa8-113">Trabajar con el evento InfoMessage</span><span class="sxs-lookup"><span data-stu-id="acfa8-113">Working with the InfoMessage Event</span></span>  

 <span data-ttu-id="acfa8-114">Con el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> del objeto <xref:System.Data.SqlClient.SqlConnection> puede recuperar advertencias o mensajes informativos de un origen de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="acfa8-114">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="acfa8-115">Si se devuelven errores desde el origen de datos con un nivel de seguridad entre 11 y 16, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="acfa8-115">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="acfa8-116">Sin embargo, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> se puede utilizar para obtener mensajes del origen de datos que no estén asociados a un error.</span><span class="sxs-lookup"><span data-stu-id="acfa8-116">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="acfa8-117">En el caso de Microsoft SQL Server, cualquier error que tenga la gravedad 10, como máximo, se considera de tipo informativo y se captura mediante el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="acfa8-117">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="acfa8-118">Para obtener más información, consulte el artículo [Niveles de gravedad de error del motor de base de datos](/sql/relational-databases/errors-events/database-engine-error-severities).</span><span class="sxs-lookup"><span data-stu-id="acfa8-118">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="acfa8-119">El evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> recibe un objeto <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> que contiene en su propiedad **Errors** una colección de los mensajes del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acfa8-119">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="acfa8-120">Puede consultar los objetos **Error** de esa colección para conocer el número de error y el texto del mensaje, así como el origen del error.</span><span class="sxs-lookup"><span data-stu-id="acfa8-120">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="acfa8-121">El proveedor de datos .NET Framework para SQL Server incluye asimismo datos acerca de la base de datos, el procedimiento almacenado y el número de línea donde se originó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="acfa8-121">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="acfa8-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acfa8-122">Example</span></span>  

 <span data-ttu-id="acfa8-123">En el ejemplo de código siguiente se muestra cómo se puede agregar un controlador de eventos para el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="acfa8-123">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="acfa8-124">Controlar errores como InfoMessages</span><span class="sxs-lookup"><span data-stu-id="acfa8-124">Handling Errors as InfoMessages</span></span>  

 <span data-ttu-id="acfa8-125">Normalmente, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> solo se activa para mensajes informativos y de advertencia enviados desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="acfa8-125">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="acfa8-126">Sin embargo, cuando se produce un error real, se detiene la ejecución de los métodos **ExecuteNonQuery** o **ExecuteReader** que iniciaron la operación del servidor y se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="acfa8-126">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="acfa8-127">Si desea seguir procesando el resto de las instrucciones de un comando, independientemente de los errores producidos en el servidor, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> de <xref:System.Data.SqlClient.SqlConnection> como `true`.</span><span class="sxs-lookup"><span data-stu-id="acfa8-127">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="acfa8-128">De esta forma, la conexión activa el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> para errores, en lugar de iniciar una excepción e interrumpir el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="acfa8-128">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="acfa8-129">La aplicación cliente puede controlar el evento y reaccionar ante las situaciones de error.</span><span class="sxs-lookup"><span data-stu-id="acfa8-129">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acfa8-130">Los errores con un nivel de gravedad de 17, como mínimo, que hacen que el servidor interrumpa el procesamiento de comandos, deben controlarse como excepciones.</span><span class="sxs-lookup"><span data-stu-id="acfa8-130">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="acfa8-131">En este caso, se inicia una excepción, independientemente del modo en que se controle el error en el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="acfa8-131">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="acfa8-132">Trabajar con el evento StateChange</span><span class="sxs-lookup"><span data-stu-id="acfa8-132">Working with the StateChange Event</span></span>  

 <span data-ttu-id="acfa8-133">El evento **StateChange** se produce cuando cambia el estado de un objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="acfa8-133">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="acfa8-134">El evento **StateChange** recibe la clase <xref:System.Data.StateChangeEventArgs>, que permite determinar el cambio de estado de **Connection** por medio de las propiedades **OriginalState** y **CurrentState**.</span><span class="sxs-lookup"><span data-stu-id="acfa8-134">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="acfa8-135">La propiedad **OriginalState** es una enumeración <xref:System.Data.ConnectionState> que indica el estado del objeto **Connection** antes del cambio.</span><span class="sxs-lookup"><span data-stu-id="acfa8-135">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="acfa8-136">**CurrentState** es una enumeración <xref:System.Data.ConnectionState> que indica el estado del objeto **Connection** después del cambio.</span><span class="sxs-lookup"><span data-stu-id="acfa8-136">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="acfa8-137">En el ejemplo de código siguiente se utiliza el evento **StateChange** para escribir un mensaje en la consola cuando cambia el estado del objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="acfa8-137">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="acfa8-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="acfa8-138">See also</span></span>

- [<span data-ttu-id="acfa8-139">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="acfa8-139">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="acfa8-140">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="acfa8-140">ADO.NET Overview</span></span>](ado-net-overview.md)
