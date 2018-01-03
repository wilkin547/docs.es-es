---
title: "Usar un socket de servidor asincrónico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 128628815f99ecb0e3d89530211c8607d17d3fb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-an-asynchronous-server-socket"></a><span data-ttu-id="9c4d4-102">Usar un socket de servidor asincrónico</span><span class="sxs-lookup"><span data-stu-id="9c4d4-102">Using an Asynchronous Server Socket</span></span>
<span data-ttu-id="9c4d4-103">Los sockets de servidor asincrónico usan el modelo de programación asincrónico de .NET Framework para procesar las solicitudes de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-103">Asynchronous server sockets use the .NET Framework asynchronous programming model to process network service requests.</span></span> <span data-ttu-id="9c4d4-104">La clase <xref:System.Net.Sockets.Socket> sigue el patrón estándar de nomenclatura asincrónico de .NET Framework; por ejemplo, el método sincrónico <xref:System.Net.Sockets.Socket.Accept%2A> se corresponde con los métodos asincrónicos <xref:System.Net.Sockets.Socket.BeginAccept%2A> y <xref:System.Net.Sockets.Socket.EndAccept%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-104">The <xref:System.Net.Sockets.Socket> class follows the standard .NET Framework asynchronous naming pattern; for example, the synchronous <xref:System.Net.Sockets.Socket.Accept%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginAccept%2A> and <xref:System.Net.Sockets.Socket.EndAccept%2A> methods.</span></span>  
  
 <span data-ttu-id="9c4d4-105">Un socket de servidor asincrónico requiere un método para comenzar a aceptar solicitudes de conexión de la red, un método de devolución de llamada para controlar las solicitudes de conexión y comenzar a recibir datos de la red, así como un método de devolución de llamada para dejar de recibir los datos.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-105">An asynchronous server socket requires a method to begin accepting connection requests from the network, a callback method to handle the connection requests and begin receiving data from the network, and a callback method to end receiving the data.</span></span> <span data-ttu-id="9c4d4-106">Todos estos métodos se describen más adelante en la presente sección.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-106">All these methods are discussed further in this section.</span></span>  
  
 <span data-ttu-id="9c4d4-107">En el ejemplo siguiente, para comenzar a aceptar solicitudes de conexión de la red, el método `StartListening` inicializa la clase **Socket** y luego usa el método **BeginAccept** para empezar a aceptar conexiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-107">In the following example, to begin accepting connection requests from the network, the method `StartListening` initializes the **Socket** and then uses the **BeginAccept** method to start accepting new connections.</span></span> <span data-ttu-id="9c4d4-108">Cuando se recibe una nueva solicitud de conexión en el socket, se llama al método de devolución de llamada de aceptación.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-108">The accept callback method is called when a new connection request is received on the socket.</span></span> <span data-ttu-id="9c4d4-109">Este método es responsable de obtener la instancia **Socket** que controlará la conexión y de rechazar esa clase **Socket** en el subproceso que procesará la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-109">It is responsible for getting the **Socket** instance that will handle the connection and handing that **Socket** off to the thread that will process the request.</span></span> <span data-ttu-id="9c4d4-110">El método de devolución de llamada de aceptación implementa el delegado <xref:System.AsyncCallback>; no se devuelve ningún valor y toma un único parámetro de tipo <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-110">The accept callback method implements the <xref:System.AsyncCallback> delegate; it returns a void and takes a single parameter of type <xref:System.IAsyncResult>.</span></span> <span data-ttu-id="9c4d4-111">El ejemplo siguiente es el shell de un método de devolución de llamada de aceptación.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-111">The following example is the shell of an accept callback method.</span></span>  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 <span data-ttu-id="9c4d4-112">El método **BeginAccept** toma dos parámetros, un delegado **AsyncCallback** que señala al método de devolución de llamada de aceptación y un objeto que se usa para pasar información de estado al método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-112">The **BeginAccept** method takes two parameters, an **AsyncCallback** delegate that points to the accept callback method and an object that is used to pass state information to the callback method.</span></span> <span data-ttu-id="9c4d4-113">En el ejemplo siguiente se pasa la clase **Socket** que escucha al método de devolución de llamada a través del parámetro *state*.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-113">In the following example, the listening **Socket** is passed to the callback method through the *state* parameter.</span></span> <span data-ttu-id="9c4d4-114">En este ejemplo se crea un delegado **AsyncCallback** y se empiezan a aceptar conexiones de la red.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-114">This example creates an **AsyncCallback** delegate and starts accepting connections from the network.</span></span>  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 <span data-ttu-id="9c4d4-115">Los sockets asincrónicos usan subprocesos del grupo de subprocesos del sistema para procesar las conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-115">Asynchronous sockets use threads from the system thread pool to process incoming connections.</span></span> <span data-ttu-id="9c4d4-116">Un subproceso es responsable de aceptar conexiones, otro subproceso se usa para controlar cada conexión entrante y otro subproceso es responsable de recibir los datos de la conexión.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-116">One thread is responsible for accepting connections, another thread is used to handle each incoming connection, and another thread is responsible for receiving data from the connection.</span></span> <span data-ttu-id="9c4d4-117">Podría tratarse del mismo subproceso dependiendo del subproceso que esté asignado por el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-117">These could be the same thread, depending on which thread is assigned by the thread pool.</span></span> <span data-ttu-id="9c4d4-118">En el ejemplo siguiente, la clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> suspende la ejecución del subproceso principal e indica cuándo puede continuar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-118">In the following example, the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class suspends execution of the main thread and signals when execution can continue.</span></span>  
  
 <span data-ttu-id="9c4d4-119">En el ejemplo siguiente se muestra un método asincrónico que crea un socket de TCP/IP asincrónico en el equipo local y comienza a aceptar conexiones.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-119">The following example shows an asynchronous method that creates an asynchronous TCP/IP socket on the local computer and begins accepting connections.</span></span> <span data-ttu-id="9c4d4-120">Presupone que hay un **ManualResetEvent** global denominado `allDone`, que el método es miembro de una clase denominada `SocketListener` y que hay definido un método de devolución de llamada denominado `acceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-120">It assumes that there is a global **ManualResetEvent** named `allDone`, that the method is a member of a class named `SocketListener`, and that a callback method named `acceptCallback` is defined.</span></span>  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 <span data-ttu-id="9c4d4-121">El método de devolución de llamada de aceptación (`acceptCallback` en el ejemplo anterior) es responsable de indicar el subproceso de aplicación principal para continuar el procesamiento, de establecer la conexión con el cliente y de iniciar la lectura asincrónica de datos desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-121">The accept callback method (`acceptCallback` in the preceding example) is responsible for signaling the main application thread to continue processing, establishing the connection with the client, and starting the asynchronous read of data from the client.</span></span> <span data-ttu-id="9c4d4-122">El siguiente ejemplo es la primera parte de una implementación del método `acceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-122">The following example is the first part of an implementation of the `acceptCallback` method.</span></span> <span data-ttu-id="9c4d4-123">Esta sección del método indica al subproceso de aplicación principal que continúe el procesamiento y establezca la conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-123">This section of the method signals the main application thread to continue processing and establishes the connection to the client.</span></span> <span data-ttu-id="9c4d4-124">Presupone que hay un **ManualResetEvent** global denominado `allDone`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-124">It assumes a global **ManualResetEvent** named `allDone`.</span></span>  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 <span data-ttu-id="9c4d4-125">La lectura de los datos de un socket de cliente requiere un objeto de estado que pase valores entre llamadas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="9c4d4-126">En el ejemplo siguiente se implementa un objeto de estado para recibir una cadena del cliente remoto.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-126">The following example implements a state object for receiving a string from the remote client.</span></span> <span data-ttu-id="9c4d4-127">Contiene campos para el socket de cliente, un búfer de datos para recibir los datos y un <xref:System.Text.StringBuilder> para crear la cadena de datos enviada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-127">It contains fields for the client socket, a data buffer for receiving data, and a <xref:System.Text.StringBuilder> for creating the data string sent by the client.</span></span> <span data-ttu-id="9c4d4-128">La colocación de estos campos en el objeto de estado permite conservar sus valores en varias llamadas para leer datos desde el socket de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="9c4d4-129">La sección del método `acceptCallback` que comienza a recibir los datos del socket de cliente primero inicializa una instancia de la clase `StateObject` y luego llama al método <xref:System.Net.Sockets.Socket.BeginReceive%2A> para empezar a leer los datos del socket de cliente de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-129">The section of the `acceptCallback` method that starts receiving the data from the client socket first initializes an instance of the `StateObject` class and then calls the <xref:System.Net.Sockets.Socket.BeginReceive%2A> method to start reading the data from the client socket asynchronously.</span></span>  
  
 <span data-ttu-id="9c4d4-130">En el siguiente ejemplo se muestra el método `acceptCallback` completo.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-130">The following example shows the complete `acceptCallback` method.</span></span> <span data-ttu-id="9c4d4-131">Se presupone que hay un **ManualResetEvent** global denominado `allDone,`, que se ha definido la clase `StateObject` y que se ha definido el método `readCallback` en una clase denominada `SocketListener`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-131">It assumes that there is a global **ManualResetEvent** named `allDone,` that the `StateObject` class is defined, and that the `readCallback` method is defined in a class named `SocketListener`.</span></span>  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 <span data-ttu-id="9c4d4-132">El método final que debe implementarse para el servidor de socket asincrónico es el método de devolución de llamada de lectura que devuelve los datos enviados por el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-132">The final method that needs to be implemented for the asynchronous socket server is the read callback method that returns the data sent by the client.</span></span> <span data-ttu-id="9c4d4-133">Al igual que el método de devolución de llamada de aceptación, el método de devolución de llamada de lectura es un delegado **AsyncCallback**.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-133">Like the accept callback method, the read callback method is an **AsyncCallback** delegate.</span></span> <span data-ttu-id="9c4d4-134">Este método lee uno o más bytes del socket de cliente en el búfer de datos y luego vuelve a llamar al método **BeginReceive** hasta que los datos enviados por el cliente están completos.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-134">This method reads one or more bytes from the client socket into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="9c4d4-135">Una vez que se ha leído todo el mensaje desde el cliente, la cadena se muestra en la consola y se cierra el socket de servidor que controla la conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-135">Once the entire message has been read from the client, the string is displayed on the console and the server socket handling the connection to the client is closed.</span></span>  
  
 <span data-ttu-id="9c4d4-136">El ejemplo siguiente implementa el método `readCallback`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-136">The following sample implements the `readCallback` method.</span></span> <span data-ttu-id="9c4d4-137">Se presupone que se ha definido la clase `StateObject`.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-137">It assumes that the `StateObject` class is defined.</span></span>  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c4d4-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c4d4-138">See Also</span></span>  
 [<span data-ttu-id="9c4d4-139">Uso de un socket de servidor sincrónico</span><span class="sxs-lookup"><span data-stu-id="9c4d4-139">Using a Synchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [<span data-ttu-id="9c4d4-140">Ejemplo de sockets de servidor asincrónicos</span><span class="sxs-lookup"><span data-stu-id="9c4d4-140">Asynchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)  
 [<span data-ttu-id="9c4d4-141">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="9c4d4-141">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="9c4d4-142">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="9c4d4-142">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
